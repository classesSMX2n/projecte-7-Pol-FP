# 📅 T09: Estimació temporal de projecte
## 📊 Diagrama de Gantt professional

---

## 🧾 Breu descripció

Un dels errors més habituals en equips tècnics novells és confondre **“fer feina”** amb **“gestionar un projecte”**.  
Començar a configurar servidors, desenvolupar una web o desplegar serveis sense una planificació rigorosa acostuma a provocar:

- ⏰ Retards
- 🚧 Colls d’ampolla
- 🔧 Solucions improvisades

En aquest punt del projecte, la direcció de **FoodLogístics S.A.** no vol només una proposta tècnica: **vol garanties**.

### La direcció vol saber:
- ✅ Quan estaran les solucions operatives  
- 🔄 Quin ordre se seguirà  
- ⚠️ Què passarà si alguna tasca es retarda  
- 👥 Si l’equip és capaç de treballar de manera professional  

👉 L’objectiu **no és només “fer un Gantt”**, sinó demostrar capacitat real de **planificació tècnica i organitzativa**.

---

## 🎯 Objectius específics de la tasca

Treballar com a **equip de projecte** per construir una planificació **completa i realista** del desplegament de la solució per a FoodLogístics S.A., utilitzant un **diagrama de Gantt amb PlantUML (UMLTree)**.

---

## 🧩 Fases del projecte

### 🔍 Fase 1: Anàlisi real del projecte (pensament estructural)

#### 1.1 Identificació de tasques i dependències
A partir de les tasques **T01–T08**, cal identificar:
- 🔢 Ordre lògic d’execució  
- 🔀 Tasques paral·leles  
- ⛔ Tasques bloquejants  

##### Preguntes clau:
**- Quines tasques no poden començar sense acabar-ne una altra?**

La T02, ja que sense aquesta que és la web i el push no es poden fer moltes de les altres.

**- On poden aparèixer colls d’ampolla?**

Amb la T06 o la T08 que és l'elecció de la web.

**- Quines tasques són més crítiques?**

La T03, ja que és el muntatge de tot el Windows Server amb el servidor de fitxers.

#### 1.2 Identificació del camí crític
Cal determinar:
- ⏱️ Tasques que, si es retarden, afecten tot el projecte  
- 🕒 Tasques amb marge (slack)  

👉 No només identificar-lo, sinó **entendre’l**.

---

### 🤖 Fase 2: Estimació d’esforç amb criteri (ús d’IA guiat)

Per cada tasca cal estimar la durada en hores tenint en compte:
- 📖 Temps de comprensió
- 🔎 Temps de recerca
- 🛠️ Implementació tècnica
- 🧪 Proves i errors
- 📝 Documentació
- 👥 Coordinació amb l’equip
- ⏸️ Interrupcions possibles
- 🛡️ Temps de marge per imprevistos

✅ Ús d’IA **obligatori**, però **crític i justificat**.

---

### 👥 Fase 3: Assignació de recursos

Distribució clara de tasques:
- Qui fa què
- Tasques compartides
- Dependències entre membres

🚫 Evitar:
- Sobrecàrrega d’una persona
- Temps morts d’altres

---

### 📈 Fase 4: Construcció del diagrama de Gantt (UMLTree)

El diagrama ha de mostrar:
- 🧩 Tasques T01–T08
- ⏳ Durada de cada tasca
- 🔗 Dependències
- 🔀 Execució en paral·lel
- 🗓️ Visió temporal de 3–4 setmanes

👉 Ha de reflectir **decisions reals**, no només ser un dibuix.

---

### 🚨 Fase 5: Pla de contingència

Identificar com a mínim:
- ⚠️ 2 riscos crítics reals
- 📉 Impacte en el projecte
- 🛠️ Estratègia de mitigació

Exemples:
- Retard en servidor → buffer o paral·lelització  
- Problemes amb cloud → alternativa definida  

---

Ha d’incloure:
- Introducció i context
- Ordre de tasques i dependències
- Justificació d’estimacions
- Planificació setmana a setmana
- Decisions clau
- Anàlisi de colls d’ampolla

---

### 2️⃣ Codi PlantUML i imatge del Gantt
Incloure:
- Arxiu `.puml`
- Imatge exportada del diagrama

El diagrama ha de mostrar:
- 📅 4 setmanes
- 🔀 Solapaments
- 🔗 Relació entre activitats

---

### 3️⃣ Matriu RACI
Taula amb:
- 👤 Responsable (R)
- ✅ Responsable final / Accountable (A)
- 💬 Consultat (C)
- 📢 Informat (I)

---

### 4️⃣ Taula de riscos i contingències
Per a cada risc:
- Problema possible
- Part del projecte afectada
- Impacte
- Mesura de resposta

---

## ❗ Important
Tots els elements han d’estar **connectats i coherents**:
- README explica la lògica
- Gantt la representa
- RACI mostra l’organització
- Riscos anticipen desviacions

---

## 🧠 Preguntes clau obligatòries

**- Quina és la tasca més crítica del projecte i per què?**

La tasca més crítica ha estat la T03 de servidor de fitxers. Apart de la seva allargada, és una tasca que requereix molt de temps i concentració en tots el pasos.

**- On heu detectat el principal coll d’ampolla?**

Amb la T02. Hi ha moltes tasques que requeríen que aquesta tasca estigués feta, i sense aquesta no podíes fer-ne d'altres.

**- Quina decisió de planificació ha estat més difícil?**

L'organització i repartiment de les tasques entre els dos membres del grup.

**- Heu modificat alguna estimació inicial? Per què?**

Sí. Teníem en compte que la T03 no anava a tardar massa temps en fer-se, però aquesta al final ens ha acabat durant massa i hem hagut de redistribuir les tasques, i anar amb més pressa amb les altres.

**- Quin risc podria fer fracassar el projecte?**

La mala organització entre els dos, tot i que no és el cas.

**- Si tinguéssiu una setmana més, què canviaríeu?**

Visualment, faríem més atractiva la web final, i les tasques les faríem millor i més documentades.

---

[Solució](/Tasques/T09/solucio.md)

![Gantt](/Tasques/T09/img/gantt.png)
