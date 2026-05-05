# 📄 P01 – Memòria tècnica de la proposta  
**Client:** FoodLogístic S.A.  

---

## 1. Introducció

Aquest document presenta de manera detallada la proposta tècnica per al desenvolupament i implantació d’una solució digital integral per a **FoodLogístic S.A.**, una empresa que actualment es troba en un procés de transformació digital amb l’objectiu de millorar la seva presencia digital i eficiència operativa.

La proposta inclou els següents components principals:

- Desenvolupament d’una pàgina web corporativa moderna i funcional
- Implementació d’una infraestructura al núvol robusta i escalable
- Configuració d’un sistema de correu empresarial professional
- Definició i desplegament de serveis de manteniment, seguretat i suport tècnic

L’objectiu principal d’aquest projecte és modernitzar completament la infraestructura digital de l’empresa, proporcionant eines actuals que permetin optimitzar processos interns i millorar la imatge externa.

En concret, es busca assolir els següents beneficis:

- Millora significativa de la comunicació interna entre departaments i externa amb clients i proveïdors
- Increment del nivell de seguretat en la gestió i emmagatzematge de dades
- Possibilitat d’escalabilitat segons el creixement del negoci
- Consolidació d’una presència digital corporativa sòlida i professional

---

## 2. Anàlisi de necessitats

### 2.1 Problemes detectats

Després d’una anàlisi inicial de la situació actual de l’empresa, s’han identificat diverses problemàtiques que afecten el rendiment i la seguretat dels sistemes:

| Àrea | Problema |
|------|----------|
| Comunicació | Sistema de correu poc centralitzat, amb possibles problemes de sincronització i manca d’eines col·laboratives |
| Infraestructura | Dependència de sistemes locals amb limitacions d’accés remot i risc elevat davant fallades de maquinari |
| Seguretat | Protecció insuficient davant amenaces externes, absència de polítiques clares de seguretat |
| Presència web | Web poc moderna, desactualitzada o fins i tot inexistent, amb baixa capacitat de captació de clients |

Aquestes limitacions dificulten la competitivitat de l’empresa en un entorn cada vegada més digitalitzat.

---

### 2.2 Necessitats del client

A partir dels problemes detectats, es defineixen les següents necessitats clau que han de ser cobertes per la solució proposada:

- Implementació d’un sistema de correu corporatiu segur, fiable i accessible des de qualsevol dispositiu
- Desenvolupament d’una web corporativa moderna, responsive i preparada per al creixement futur
- Contractació d’un servei de hosting fiable, amb alta disponibilitat i bon rendiment
- Integració d’un sistema automatitzat de còpies de seguretat per evitar pèrdues de dades
- Compliment estricte de la normativa vigent en matèria de protecció de dades (LOPD / RGPD)
- Facilitat de gestió i manteniment dels sistemes per part de l’equip tècnic

---

## 3. Proposta de solució

### 3.1 Infraestructura i alta disponibilitat

Es proposa la implementació d’una arquitectura basada en tecnologies al núvol que garanteixin flexibilitat, disponibilitat i rendiment.

Els components principals de la infraestructura són:

- Servidor VPS al núvol per allotjar la web i serveis associats
- Utilització de WordPress com a sistema de gestió de continguts (CMS)
- Sistema de còpies de seguretat automatitzades amb freqüència configurable
- Possibilitat d’escalabilitat vertical (ampliació de recursos del servidor segons necessitats)

Aquesta arquitectura ofereix diversos avantatges:

- Alta disponibilitat dels serveis, minimitzant temps d’inactivitat
- Reducció de costos en comparació amb infraestructures físiques
- Escalabilitat senzilla i ràpida segons el creixement de l’empresa
- Accés remot segur des de qualsevol ubicació

---

### Arquitectura del sistema

![](img/mermaid-diagram2.png)

---

### 3.2 Serveis al núvol

Per a la gestió del correu electrònic i les eines de col·laboració, s’ha seleccionat la plataforma Zoho Workplace, que ofereix una solució completa i integrada.

Els serveis inclosos dins d’aquesta plataforma són:

- Correu electrònic corporatiu amb domini propi
- Calendari compartit per a la gestió d’esdeveniments i reunions
- Emmagatzematge al núvol per a documents i arxius
- Eines ofimàtiques online (processador de textos, fulls de càlcul, presentacions)
- Sistema de col·laboració en temps real entre usuaris

Aquesta solució permet millorar la productivitat i facilita el treball en equip, especialment en entorns distribuïts.

---

### 3.3 Seguretat i LOPD

La seguretat és un element fonamental dins de la proposta. Es defineixen diverses mesures per garantir la protecció de les dades i el compliment normatiu:

| Mesura | Descripció |
|--------|------------|
| MFA | Implementació d’autenticació multifactor per augmentar la seguretat d’accés |
| Xifrat | Xifrat de dades tant en trànsit (SSL/TLS) com en repòs |
| Backups | Realització de còpies de seguretat automàtiques i periòdiques |
| Control accés | Definició de permisos basats en rols per limitar l’accés a la informació |

A més, es contemplen bones pràctiques com:

- Actualitzacions regulars del sistema
- Monitorització de possibles vulnerabilitats
- Compliment del RGPD en el tractament de dades personals

---

### 3.4 Presència web

La nova web corporativa es desenvoluparà utilitzant tecnologies actuals i orientades a l’experiència d’usuari.

Tecnologies i recursos utilitzats:

- WordPress com a CMS principal
- Tema professional adquirit a ThemeForest amb disseny responsive
- Plugins especialitzats en seguretat, SEO i rendiment

Objectius principals de la web:

- Millorar la imatge corporativa de l’empresa
- Facilitar la captació de nous clients
- Proporcionar informació clara i estructurada sobre serveis i productes
- Garantir una navegació intuïtiva i accessible des de dispositius mòbils

També es tindran en compte aspectes com:

- Optimització SEO per millorar el posicionament en cercadors
- Temps de càrrega reduïts
- Integració amb xarxes socials

---

## 4. Arquitectura i disseny tècnic

### 4.1 Diagrama general

![](img/mermaid-diagram.png)

---

### 4.2 Tecnologies utilitzades

A continuació es detallen les tecnologies seleccionades per a cada àrea del projecte:

| Àrea | Tecnologia |
|------|-----------|
| Web | WordPress |
| Hosting | VPS Linux |
| Correu | Zoho Workplace |
| Seguretat | Wordfence |
| Backups | UpdraftPlus |

Aquestes tecnologies han estat escollides per la seva fiabilitat, comunitat de suport i facilitat d’integració.

---

## 5. Pressupost

El pressupost estimat del projecte es divideix en dos blocs principals:

| Concepte | Cost |
|----------|------|
| Implantació inicial | 2.060 € |
| Cost mensual | 187 €/mes |

El cost d’implantació inclou:

- Configuració de la infraestructura
- Desenvolupament de la web
- Configuració de serveis al núvol
- Implementació de mesures de seguretat

El cost mensual cobreix:

- Hosting VPS
- Subscripcions de serveis (Zoho, plugins premium)
- Manteniment tècnic i suport
- Monitorització i còpies de seguretat

---

## 6. Planificació

### 6.1 Fases del projecte

El projecte es divideix en diferents fases per garantir una execució ordenada i eficient:

| Fase | Durada | Tasques |
|------|--------|--------|
| Anàlisi | 1 setmana | Recollida de requisits i estudi inicial |
| Disseny | 1 setmana | Definició de UX/UI i arquitectura |
| Desenvolupament | 2 setmanes | Creació de la web i configuració del VPS |
| Implementació | 1 setmana | Integració de serveis i desplegament |
| Testing | 3 dies | Proves funcionals i de seguretat |
| Lliurament | 2 dies | Documentació i formació al client |

---

### 6.2 Cronograma

![alt text](img/image.png)

---

## 7. Conclusions

La proposta desenvolupada per a FoodLogístic S.A. representa una solució completa i adaptada a les necessitats actuals i futures de l’empresa.

Principals beneficis:

- Infraestructura moderna, escalable i basada en el núvol
- Millora significativa de la seguretat de la informació
- Optimització de la comunicació interna i externa
- Reducció de costos operatius a llarg termini
- Major capacitat de creixement i adaptació tecnològica

Resultats esperats:

- Web corporativa professional i orientada a clients
- Sistema de correu al núvol eficient i segur
- Infraestructura tecnològica robusta i preparada per al futur

En conclusió, aquesta proposta permet a FoodLogístic S.A. avançar cap a una transformació digital sòlida, millorant tant la seva operativa interna com la seva presència en el mercat.