---
name: planner-card-interview
description: Führt einen strukturierten Interview-Dialog, um eine vollständig ausgefüllte Microsoft Teams Planner-Karte zu erstellen. Verwende diesen Skill immer wenn jemand eine neue Aufgabe, Task oder Karte im Planner anlegen möchte – auch wenn sie nur sagen "ich will eine Karte erstellen", "neue Aufgabe im Board", "trag das mal ein" oder eine Aufgabe kurz beschreiben (z.B. "Landingpage erstellen", "KI-Agenten bauen"). Der Skill führt einen iterativen Dialog bis alle Pflichtfelder vollständig sind und gibt am Ende das fertige Copy-Paste-Template aus.
---

# Planner Card Interview Skill

## Zweck

Führe einen strukturierten, effizienten Dialog mit dem User, um alle Felder des Teams-Planner-Karten-Templates zu befüllen. Ziel ist ein sofort verwendbares, vollständiges Template als Copy-Paste-Output.

---

## Template-Struktur (Referenz)

```
(*Pflichtfeld)

🎯 ZIEL*
1.1 [Ein Satz. Was soll am Ende existieren oder eingetreten sein?]

📥 INPUT / VORAUSSETZUNGEN*
[Was muss vorliegen, bevor diese Aufgabe starten kann?]
2.1 
2.2 
2.3 

🔲 OUT OF SCOPE*
[Explizite Abgrenzung – was gehört nicht dazu?]
3.1 
3.2 
3.3 

✅ DEFINITION OF DONE*
[Wann ist diese Karte fertig? Konkret, prüfbar.]
4.1 
4.2 
4.3 

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[OPTIONAL:]

🤝 STAKEHOLDER / ABSTIMMUNG
[Wer muss reviewen, approven oder informiert werden?]
5.1 
5.2 

⚠️ RISIKEN / ABHÄNGIGKEITEN
[Was könnte blockieren? Welche Tasks hängen davon ab?]
6.1 
6.2 

⚙️ RESSOURCEN / TOOLS
[Welche Tools, Zugänge, Budgets sind nötig?]
7.1 
7.2 

⏱️ ERWARTUNGSHORIZONT AUFWAND
Stunden, Tage

🔗 RELEVANTE LINKS
[z.B. Loop-Seiten, SharePoint-Ablagen etc.]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📜 REGELN:
– Keine Karte ohne Pflichtfelder
– Zugewiesene Person = Verantwortlich für regelmäßige Pflege
– Arbeit an Karte wird nicht begonnen ohne Aufwandsabschätzung
– Kommunikation erfolgt im Channel: Planner ist für Status, Channel für Prozess
– Bei Statusupdate oder Änderung der Beschreibung: kurzer Channel-Post
   mit @Mention bei nächstem Handlungsschritt
```

---

## Interview-Ablauf

### Phase 0 – Einstieg

Der User beschreibt die Aufgabe (kurz oder ausführlich). Extrahiere daraus sofort alles, was du ableiten kannst:
- Formuliere einen **Ziel-Vorschlag** (1.1)
- Leite offensichtliche **Inputs** und **Out-of-Scope**-Punkte ab
- Mache einen ersten **DoD-Entwurf**

Starte NICHT mit einer leeren Frage. Präsentiere deinen Entwurf direkt und frage gezielt nach, was fehlt oder falsch ist.

---

### Phase 1 – Pflichtfelder klären (iterativ)

Gehe die vier Pflichtblöcke durch. Maximal **zwei offene Fragen pro Runde**.

#### 1. ZIEL (1.1)
- Muss in einem Satz formulierbar sein
- Enthält: Was entsteht? Für wen? Mit welchem Nutzen?
- Wenn unklar: "Was soll nach Abschluss dieser Aufgabe existieren oder möglich sein, was vorher nicht möglich war?"

#### 2. INPUT / VORAUSSETZUNGEN (2.x)
- Frage: "Was muss vorliegen, bevor jemand mit dieser Aufgabe starten kann?"
- Typische Kategorien: Daten/Dokumente, Zugänge, Entscheidungen/Freigaben, Abhängigkeiten zu anderen Tasks
- Mindestens 2 Punkte anstreben

#### 3. OUT OF SCOPE (3.x)
- Frage: "Was gehört explizit NICHT zu dieser Aufgabe?"
- Wichtig für: Scope Creep verhindern, Erwartungsmanagement
- Ableiten aus dem Ziel: Was liegt nahe, ist aber bewusst ausgeschlossen?
- Mindestens 2 Punkte anstreben

#### 4. DEFINITION OF DONE (4.x)
- Jeder Punkt muss prüfbar sein ("ist erstellt", "liegt vor", "wurde getestet")
- Keine vagen Formulierungen ("ist gut", "funktioniert irgendwie")
- Ableiten aus Ziel + vorhandenem Input des Users
- Mindestens 3 Punkte anstreben

---

### Phase 2 – Optionale Felder anbieten

Sobald alle Pflichtfelder vollständig sind, frage **einmal gebündelt**:

> "Die Pflichtfelder sind vollständig. Möchtest du noch optionale Felder befüllen?
> – 🤝 Stakeholder / Abstimmung
> – ⚠️ Risiken / Abhängigkeiten
> – ⚙️ Ressourcen / Tools
> – ⏱️ Erwartungshorizont Aufwand
> – 🔗 Relevante Links
> Sag einfach welche – oder 'nein' für direkten Output."

Befülle nur die, die der User explizit anspricht oder die du aus dem bisherigen Kontext ableiten kannst.

---

### Phase 3 – Output

Sobald alle Pflichtfelder vollständig sind (und optionale geklärt), gib das vollständige Template aus:

- Als **Code-Block** (direkt kopierbar)
- Mit allen nummerierten Punkten
- Optionale Blöcke: nur ausgeben wenn befüllt, sonst weglassen
- Der **REGELN-Block** wird IMMER am Ende ausgegeben (unverändert)
- Danach kurze Hinweiszeile: welche optionalen Felder noch leer sind

---

## Qualitätskriterien

Vor dem finalen Output prüfe intern:

| Kriterium | Check |
|---|---|
| Ziel in einem Satz? | ✓ / ✗ |
| Mindestens 2 Inputs? | ✓ / ✗ |
| Mindestens 2 Out-of-Scope? | ✓ / ✗ |
| Mindestens 3 DoD-Punkte, alle prüfbar? | ✓ / ✗ |
| Keine Wiederholungen zwischen Ziel und DoD? | ✓ / ✗ |
| Nummerierung vollständig und konsistent? | ✓ / ✗ |

Wenn ein Kriterium nicht erfüllt ist: nochmals nachfragen, bevor Output generiert wird.

---

## Verhaltensprinzipien

- **Keine leeren Fragen** – immer mit einem Entwurf oder Vorschlag einsteigen
- **Maximal 2 Fragen pro Runde** – kein Fragebogen-Feeling
- **Aus dem Kontext ableiten** – was logisch aus dem Ziel folgt, nicht nochmals fragen
- **Präzise Sprache** – DoD-Punkte müssen testbar sein, keine Weichformulierungen
- **Kein Overengineering** – einfache Tasks brauchen kein 10-Punkte-DoD
- **Schnell zum Output** – Ziel ist das fertige Template, nicht ein perfektes Interview
