# 📊 Planificació del projecte SMiX2

## 🧭 Introducció
Aquest document descriu la planificació del projecte SMiX2, amb l’objectiu d’organitzar les tasques, optimitzar el temps i coordinar el treball entre els membres de l’equip (Pol i Biel).

El projecte es desenvolupa al llarg de **4 setmanes (del 7 al 29 d’abril de 2026)**.

---

## 🔗 Ordre de tasques i dependències
Les tasques s’han organitzat seguint una lògica seqüencial amb alguns processos en paral·lel:

- **Pol**:
  - T01 → T03 → T05 → T07
- **Biel**:
  - T02 → T04 → T06 → T08

Això permet:
- començar amb anàlisi inicial,
- continuar amb implementació tècnica,
- finalitzar amb validació i decisions finals.

---

## ⏱️ Justificació temporal
Les durades s’han estimat segons la dificultat de cada tasca:

- Tasques llargues (8 dies): desenvolupament (web, servidor)
- Tasques mitjanes (5 dies): anàlisi i implementació
- Tasques curtes (4 dies): ajustos i decisions finals

S’ha buscat un equilibri en la càrrega de treball entre els dos membres.

---

## 📅 Planificació per setmanes

### Setmana 1 (7–11 abril)
- T01 (Pol)
- Inici T02 (Biel)

### Setmana 2 (14–18 abril)
- T03 (Pol)
- Continuació T02 i inici T04 (Biel)

### Setmana 3 (21–25 abril)
- T05 (Pol)
- T06 (Biel)

### Setmana 4 (28–29 abril)
- T07 (Pol)
- T08 (Biel)
- Tancament del projecte

---

## ⚙️ Decisions importants
- Divisió clara de rols (Pol tècnic / Biel web)
- Execució de tasques en paral·lel per optimitzar temps
- Priorització de tasques crítiques al principi

---

## ⚠️ Colls d’ampolla
Possibles punts crítics del projecte:

- Dependència entre tasques (retards en cadena)
- Sobrecàrrega en setmanes intermèdies
- Poc marge de temps al final

---

## 🧠 Reflexió final
La planificació permet tenir una visió clara del projecte, repartir responsabilitats i anticipar problemes. Tot i així, serà necessari adaptar-se a possibles imprevistos.

---

## 📊 Diagrama de Gantt (PlantUML)

```plantuml
@startgantt
title Projecte SMiX2 (7–29 Abril 2026)

Project starts 2026-04-07
saturday are closed
sunday are closed
printscale weekly

[T01 - Estudi competència] lasts 5 days
[T03 - Servidor de fitxers] lasts 8 days
[T05 - Vídeo LOPD] lasts 4 days
[T07 - Correu cloud] lasts 5 days

[T02 - Web corporativa] lasts 8 days
[T04 - Servidor impressió] lasts 4 days
[T06 - Adaptació web normativa] lasts 8 days
[T08 - Tria web definitiva] lasts 4 days

[T03] starts at [T01]'s end
[T05] starts at [T03]'s end
[T07] starts at [T05]'s end

[T04] starts at [T02]'s start
[T06] starts at [T04]'s end
[T08] starts at [T06]'s end

@endgantt
```

---

## 👥 Matriu RACI

La següent matriu defineix els rols i responsabilitats de cada membre de l’equip en les diferents tasques del projecte:

| Tasca | Responsable (R) | Accountable (A) | Consultat (C) | Informat (I) |
|------|----------------|----------------|--------------|-------------|
| T01 - Estudi competència | Pol | Pol | Biel | Biel |
| T02 - Web corporativa | Biel | Biel | Pol | Pol |
| T03 - Servidor de fitxers | Pol | Pol | Biel | Biel |
| T04 - Servidor impressió | Biel | Biel | Pol | Pol |
| T05 - Vídeo LOPD | Pol | Pol | Biel | Biel |
| T06 - Adaptació web normativa | Biel | Biel | Pol | Pol |
| T07 - Correu cloud | Pol | Pol | Biel | Biel |
| T08 - Tria web definitiva | Biel | Biel | Pol | Pol |

### 📝 Explicació
- **Responsable (R)**: Qui executa la tasca  
- **Accountable (A)**: Qui valida el resultat final  
- **Consultat (C)**: Qui aporta informació o opinió  
- **Informat (I)**: Qui ha d’estar al corrent del progrés  

Aquesta distribució assegura una assignació clara de responsabilitats i una bona coordinació dins l’equip.

---

## ⚠️ Taula de riscos i contingències

Risc | Afecta | Impacte | Mesura de contingència
--- | --- | --- | ---
Retard en tasques tècniques | T03, T06 | Alt | Replanificar i prioritzar tasques crítiques
Problemes tècnics | Servidors/web | Alt | Realitzar proves prèvies i backups
Mala coordinació | Tot el projecte | Mitjà | Fer reunions setmanals de seguiment
Falta de temps final | T07, T08 | Alt | Reduir tasques no crítiques
Errors en requisits | Web/LOPD | Mitjà | Revisió contínua amb validació

---

![Gantt](/Tasques/T09/img/gantt.png)
[README](/Tasques/T09/README.md)
