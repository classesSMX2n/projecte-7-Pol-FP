# T03: Servidor de fitxers 📁

## Breu descripció

A mesura que el volum de negoci creix, també ho fa la quantitat de dades generades, i això pot provocar problemes d’organització i accés a la informació. A **FoodLogistic**, cada departament guardava la seva documentació de manera local, fet que dificultava tenir una **visió global i controlada** de les dades.

Per solucionar aquesta situació, es planteja la implementació d’un **servidor de fitxers centralitzat**, segur i organitzat, que permeti gestionar l’accés a la informació segons els diferents departaments.

L’objectiu d’aquesta tasca és desplegar una infraestructura basada en:

- **Permisos NTFS i SMB**
- **Quotes d’emmagatzematge**
- **Filtrat de fitxers amb FSRM**

Tot això demostrant el domini de diferents eines d’administració com:

- Explorador de fitxers  
- Server Manager  
- PowerShell  

---

## Descripció de l'activitat

### 1️⃣ Preparació i seguretat de grups (Active Directory) 👥

**Objectiu:** Organitzar els usuaris segons els seus rols dins l’empresa.

**Accions a realitzar:**

- Crear una estructura d’**Unitats Organitzatives (OU)** coherent dins del domini `foodlogistic.test`.
- Crear els següents **grups de seguretat**:
  - **Administracio** → gestió de factures i albarans  
  - **Transport** → xofers i caps de flota  
  - **Direccio** → gerència  

---

### 2️⃣ Implementació de recursos compartits 📂

**Objectiu:** Crear diferents carpetes compartides amb mètodes i configuracions específiques.

#### A. Carpeta Public (Explorador de fitxers)

- Compartida per a tots els usuaris  
- Permisos:
  - **SMB:** Lectura  
  - **NTFS:** Modificació  
- Verificar els permisos efectius  

---

#### B. Carpeta Operacions (Server Manager)

- Crear el recurs compartit mitjançant **File and Storage Services**  
- Activar **Access-Based Enumeration**  
- Restricció: només accessible pel grup **Transport**

---

#### C/D. Carpeta Confidencial (PowerShell) 🔒

**Opció C (bàsica):**

- Crear carpeta **Direccio$** (oculta)  
- Accés només per al grup **Direccio**  
- Compartir amb `New-SmbShare`  
- Assignar unitat **Z:** mitjançant GPO  

**Opció D (avançada):**

- Crear carpeta **Direccio**  
- Accés restringit al grup **Direccio**  
- Compartir amb `New-SmbShare`  
- Activar **Access-Based Enumeration via PowerShell**  
- Assignar unitat **Z:** amb GPO  

---

### 3️⃣ Control d’emmagatzematge (Quotes i FSRM) 💾

**Objectiu:** Evitar l’ús indegut de l’espai de disc.

#### Quotes NTFS (per volum)

- Activar quotes al volum de dades  
- Límit per defecte: **500 MB per usuari**

---

#### FSRM (per carpeta)

- Instal·lar **File Server Resource Manager**

**Quota a Public:**
- Límit: **200 MB (Hard Quota)**  
- Avís al 90% amb missatge personalitzat  

**Filtrat a Operacions:**
- Bloquejar fitxers:
  - Executables (.exe, .msi)  
  - Multimèdia (àudio i vídeo)

---

### 4️⃣ Verificació i auditoria 🔍

**Objectiu:** Comprovar que totes les configuracions funcionen correctament.

**Proves a realitzar des d’un client Windows 10/11:**

- Verificar accés segons el grup d’usuari  
- Comprovar visibilitat de carpetes  
- Intentar copiar un fitxer **.exe** a Operacions  
- Provar si canviant l’extensió (ex: .txt) es pot evitar el filtre  

---

## Què cal lliurar 📄

Informe tècnic en format Markdown amb:

### 1️⃣ Resum de configuració
- Taula amb:
  - Nom de la carpeta  
  - Camí UNC  
  - Grups amb accés  
  - Mètode utilitzat  

### 2️⃣ Evidències
- Captures de pantalla de:
  - Configuració de permisos  
  - Compartició de carpetes  
  - Quotes i FSRM  

### 3️⃣ Proves de funcionament
- Verificacions des dels clients:
  - Accés correcte segons permisos  
  - Funcionament de quotes  
  - Restriccions de fitxers  

---

## Material de suport 📚

- **0224 SOX — Material UD8: AA2**  
Disponible al Moodle de l’assignatura