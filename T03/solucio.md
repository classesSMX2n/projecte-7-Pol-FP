# Servidor de fitxers

## 1. Preparació i seguretat de Grups (AD)

Farem 2 OUs una per usuaris un altre per equips i crearem 3 grups administració, transport, direcció
![alt text](img/image.png)

## 2. Implementació de recursos compartits

### A. Carpeta Public

Crearem la carpeta public mitjançant el explorador d'arxius
Asignarem permisos smb nomes laectura tothom
![alt text](img/image-1.png)
![alt text](img/image-2.png)

### B. Carpeta Operacions

Crearem la carpeta operacions amb Server Manager FSSM
![alt text](img/image-3.png)

Seleccionarem la seguent opcio
![alt text](img/image-4.png)

Ens preguntara la ruta en la qual volem compartir anirem a Type a custom path 
![alt text](img/image-5.png)

Crearem la carpeta i la anomenarem Operacions
![alt text](img/image-6.png)

Continuarem
![alt text](img/image-7.png)

Per fer que nomes es mostri pels usuaris que tenen acces activarem l'opcio Acces-Based Enumeration
![alt text](img/image-8.png)

Li donarem a customize permission
![alt text](img/image-9.png)´

Posarem Full control per el grup transport i treurem permissos a tota la resta
![alt text](img/image-10.png)
![alt text](img/image-11.png)

Tindrem un resum de els usuaris que tindran permissos a la carpeta
![alt text](img/image-12.png)
![alt text](img/image-13.png)

Tindrem aquesta finestra de Conclusió
![alt text](img/image-14.png)

### D. Carpeta Confidencial

Crearem la carpeta Direccio amb el Powershell
```powershell
New-Item -Path "C:\Direccio" -ItemType Directory`
```
![alt text](img/image-15.png)

A continuació amb les seguents comandes configurarem els permisos
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

Crearem una GPO on mapejarem la unitat a nomes els usuaris de Direcció
![alt text](img/image-16.png)
![alt text](img/image-17.png)

## 3. Control d'Emmagatzematge (FSRM i Quotes NTFS)

### Quotes NTFS (Control per Volum)

Començarem instalant el File Server Resource Manager(FSRM)
![alt text](img/image-18.png)

Posarem al disc E una quota de 500MB amb un avis de 400MB
![alt text](img/image-19.png)

### FSRM (Control per Carpeta)

Obrirem FSRM i crearem una plantilla de quota 
![alt text](img/image-20.png)

A notification Thresholds farem click a Add
![alt text](img/image-21.png)

Ara crearem una nova quota la posarem a la carpeta public i seleccionarem la pllantilla que em creat abanç
![alt text](img/image-22.png)

Ara filtrarem per arxius fent que a la carpeta Operacions no es pugin guardar arxius executables ni fitxers d'audio o video
Crearem una plantilla per no permetre els arxius anteriorment mencionats
![alt text](img/image-23.png)

Crearem la prohibicio a File Screens i seleccionarem la plantilla
![alt text](img/image-24.png)

## 4. Verificació i Auditoria

### COMPROVACIÓ GRUP TRANSPORT
comprovarem que tenim la carpeta operacions amb el usuari b.batalla del grup transport no podrem veure les altres carpetes
![alt text](img/image-25.png)


Ara veurem com podem entrar a dins de la carpeta i no podrem posar a dins un arxiu .exe pero si podem posar un txt
![alt text](img/image-26.png)

Ara si cambiem el .exe per txt veurem com podem posarlo dins de la carpeta 
![alt text](img/image-27.png)

### COMPROVACIÓ GRUP DIRECCIÓ
comprovarem que tenim la carpeta direccio amb el usuari m.melendo del grup direcció no podrem vuere les altres.
![alt text](img/image-28.png)

com podem veure la gpo esta correctament montada com la unitat Z:
![alt text](img/image-29.png)

### COMPROVACIÓ GRUP ADMINSITRACIÓ
El grup Administració pot veure nomes la carpeta public
![alt text](img/image-30.png)