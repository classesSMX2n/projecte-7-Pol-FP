# Servidor de fitxers

## 1. Preparació i seguretat de Grups (AD)

## Justificació de l’estructura AD

S’han creat tres OUs: **Usuaris**, **Equips** i **Grups** per separar els diferents objectes i facilitar-ne la gestió i l’aplicació de polítiques.

Dins de l’OU **Grups** s’han creat els grups **Administracio**, **Transport** i **Direccio**, que permeten assignar permisos de forma eficient per departaments.

Aquesta estructura és clara, escalable i facilita la gestió centralitzada dels permisos.

![alt text](img/image.png)

---

## 2. Implementació de recursos compartits

### A. Carpeta Public

Crearem la carpeta **Public** mitjançant l’explorador d’arxius.

Assignarem permisos SMB de només lectura per a tothom.

![alt text](img/image-1.png)  
![alt text](img/image-2.png)

---

### B. Carpeta Operacions

**IMPORTANT:** Cal crear una carpeta arrel i, dins d’aquesta, totes les subcarpetes. Si no, l’**Access-Based Enumeration** no funcionarà correctament.

Crearem la carpeta **Operacions** amb el Server Manager (FSSM).

![alt text](img/image-3.png)

Seleccionarem la següent opció:

![alt text](img/image-4.png)

Ens demanarà la ruta; seleccionarem **Type a custom path**.

![alt text](img/image-5.png)

Crearem la carpeta i l’anomenarem **Operacions**.

![alt text](img/image-6.png)

Continuarem:

![alt text](img/image-7.png)

Per fer que només es mostri als usuaris que tenen accés, activarem l’opció **Access-Based Enumeration**.

![alt text](img/image-8.png)

Farem clic a **Customize permissions**.

![alt text](img/image-9.png)

Assignarem **Full Control** al grup **Transport** i eliminarem permisos a la resta.

![alt text](img/image-10.png)  
![alt text](img/image-11.png)

Obtindrem un resum dels permisos:

![alt text](img/image-12.png)  
![alt text](img/image-13.png)

Pantalla de conclusió:

![alt text](img/image-14.png)

---

### D. Carpeta Confidencial

Crearem la carpeta Direccio amb el Powershell
```powershell
New-Item -Path "C:\Direccio" -ItemType Directory`
```
![alt text](img/image-15.png)

A continuació amb les següents comandes configurarem els permisos
```powershell
# Eliminar herència
icacls "E:\Direccio" /inheritance:r

# Donar permisos al grup Direccio
icacls "E:\Direccio" /grant "foodlogistic.test\Direccio:(OI)(CI)F"

# Opcional: assegurar accés administrador
icacls "E:\Direccio" /grant "Administrators:(OI)(CI)F"
```

Compartirem la carpeta amb New-SmbShare
```powershell
New-SmbShare `
```

Activarem Access-Based Enumeration
```powershell
Set-SmbShare -Name "Direccio" -FolderEnumerationMode AccessBased
```

Crearem una GPO on mapejarem la unitat a només els usuaris de Direcció
![alt text](img/image-16.png)
![alt text](img/image-17.png)

## 3. Control d'Emmagatzematge (FSRM i Quotes NTFS)

### Quotes NTFS (Control per Volum)

Començarem instal·lant el File Server Resource Manager (FSRM)
![alt text](img/image-18.png)

Posarem al disc E una quota de 500MB amb un avís de 400MB
![alt text](img/image-19.png)

### FSRM (Control per Carpeta)

Obrirem FSRM i crearem una plantilla de quota
![alt text](img/image-20.png)

A notification Thresholds farem click a Add
![alt text](img/image-21.png)

Ara crearem una nova quota i la posarem a la carpeta Public i seleccionarem la plantilla que hem creat abans
![alt text](img/image-22.png)

Ara filtrarem per arxius fent que a la carpeta Operacions no es puguin guardar arxius executables ni fitxers d'àudio o vídeo
Crearem una plantilla per bloquejar aquests arxius
![alt text](img/image-23.png)

Crearem la prohibició a File Screens i seleccionarem la plantilla
![alt text](img/image-24.png)

## 4. Verificació i Auditoria

### COMPROVACIÓ GRUP TRANSPORT
Comprovarem que tenim la carpeta Operacions amb l’usuari b.batalla del grup Transport. No podrem veure les altres carpetes.
![alt text](img/image-25.png)


Ara veurem com podem entrar dins la carpeta i no podrem posar un fitxer .exe però sí un .txt
![alt text](img/image-26.png)

Si canviem l’extensió de .exe a .txt es pot copiar dins la carpeta
![alt text](img/image-27.png)

### COMPROVACIÓ GRUP DIRECCIÓ
Comprovarem que tenim la carpeta Direccio amb l’usuari m.melendo del grup Direcció. No podrem veure les altres carpetes.
![alt text](img/image-28.png)

La GPO està correctament aplicada amb la unitat Z:
![alt text](img/image-29.png)

### COMPROVACIÓ GRUP ADMINSITRACIÓ
El grup Administració només pot veure la carpeta Public
![alt text](img/image-30.png)

### COMPROVACIÓ QUOTA DISC E

Com podem veure volem possar mes de 500MB al nostre disc E per la restricció de quota no ens deixara
![alt text](img/image-31.png)

La quota de 200MB a la carpeta Public també funciona correctament
![alt text](img/image-32.png)