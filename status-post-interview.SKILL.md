---
name: status-post-interview
description: "Guides a consulting team member through a short structured interview (written or voice-to-text) to generate their weekly async status post for the \"A Status\" channel. Use this skill whenever someone wants to write, draft, or prepare their weekly status update, Statuspost, Wochenstatus, or weekly check-in — even if they just say \"ich muss noch meinen Status schreiben\" or \"help me with my update\". The skill runs a focused 5-field interview and outputs a ready-to-paste Teams/Slack post. Always use this skill for weekly status post creation — do not attempt to generate the post without running the interview first."
---

# Status Post Interview Skill

## Zweck

Dieses Skill führt ein Teammitglied in unter 5 Minuten durch ein strukturiertes Interview und generiert daraus einen fertig formatierten Wochenstatus-Post für den A-Status-Channel (Teams oder Slack).

Das Ausgabeformat ist verbindlich. Es darf nicht vereinfacht, umstrukturiert oder kreativ abgewandelt werden.

---

## Feste Channel-Links (permanent)

Die folgenden drei Channels haben permanente Hyperlinks und müssen **immer** als Markdown-Hyperlinks in den Post eingebettet werden – nicht als Platzhalter:

| Projekt-Zuordnung | Channel-Name | Hyperlink |
|---|---|---|
| nBM | K Atruvia | `[K Atruvia](https://teams.microsoft.com/l/channel/19%3A16ba7566e71b4f5496cec1b432575735%40thread.skype/K%20Atruvia?groupId=0f50ce28-55f7-46c1-97a6-d7e8875fd20a&tenantId=cc1fd84a-b1d7-4508-bbae-07a059baa0c3)` |
| FoW Marketing | A Marketing | `[A Marketing](https://teams.microsoft.com/l/channel/19%3A5557f424cabe4b348b806ec1b7cd0f9a%40thread.skype/A%20Marketing?groupId=0f50ce28-55f7-46c1-97a6-d7e8875fd20a&tenantId=cc1fd84a-b1d7-4508-bbae-07a059baa0c3)` |
| AI Scaling / L&D | A AI Learning und Development | `[A AI Learning und Development](https://teams.microsoft.com/l/channel/19%3A292b785673354fd786d87de957dad0ef%40thread.skype/A%20AI%20Learning%20und%20Development?groupId=0f50ce28-55f7-46c1-97a6-d7e8875fd20a&tenantId=cc1fd84a-b1d7-4508-bbae-07a059baa0c3)` |

Neue Projekte ohne bestätigten Channel: `#[channel]` als Platzhalter setzen. Einmal pro Gespräch fragen, ob ein Channel existiert – nicht bei jedem Post erneut.

---

## Das verbindliche Ausgabeformat

```
**📅 KW [XX] | [Name]**

**1 · Erledigt letzte Woche**
1.1 [Output/Meilenstein]
1.2 [weiterer Output – wenn vorhanden]

**2 · Fokus diese Woche**
2.1 [Priorität mit Output-Signal]
2.2 [weitere Priorität – wenn vorhanden]

**3 · Aktive Projekte**
3.1 [Projektname] → [Status] → [Channel-Link oder #[channel]]
3.2 [weiteres Projekt – wenn vorhanden]

**4 · Input / Unterstützung gesucht**
4.1 [Konkret: wer, was, bis wann – oder „–"]

**5 · Infos & Erreichbarkeit**
5.1 [Überschneidung, Ressourcenkonflikt, relevante Info – oder „–"]
5.2 [Eingeschränkte Erreichbarkeit: Zeitblock / Abwesenheit – oder „–"]
```

**Formatregeln:**
- Nummerierung ist immer zweistellig (1.1, 1.2 etc.) – auch bei einzelnen Einträgen
- Leere Felder werden mit `–` befüllt, nicht weggelassen
- Projektstatus aus: `on track` / `at risk` / `blocked` / `slow progress`
- Bei `at risk`, `blocked` oder `slow progress`: kurzer Grund in Klammern, z.B. `→ at risk (Ressourcen-Engpass)`
- Channel-Links als Markdown-Hyperlinks für bekannte Channels, `#[channel]` als Platzhalter für unbekannte
- Kein Fließtext, keine vollständigen Sätze – stichpunktartig, output-orientiert
- Tätigkeiten beschreiben ("habe gearbeitet an X") sind verboten – nur Ergebnisse
- Namensschreibweisen und Klammern exakt übernehmen wie geliefert (z.B. `Vorname (Nachname)`)

**Ausgabe-Format (Teams-kompatibel):**
- Output immer als Plain Text (NICHT im Codeblock) – direkt per Copy-Paste in Teams einfügbar
- `**bold**` Markdown wird von Teams nativ gerendert
- Kein Hinweis auf manuelle Verlinkung nötig – Links sind direkt eingebettet
- Keine `---`-Trennlinien oder sonstige Dekoration um den Post herum

---

## Interview-Ablauf

### Einstieg

Begrüße kurz und setze den Rahmen:

> „Kurz durch 5 Fragen – danach ist der Post fertig. Los geht's."

KW und Name aus Kontext ableiten (Datum, Memory). Nur rückfragen wenn unklar.

---

### Batch-Input erkennen

**Kritisch:** Wenn die Person in einer Antwort Informationen für mehrere Felder liefert (z.B. „Letzte Woche: X. Diese Woche: Y. Erreichbarkeit: Z"), dann:

1. Alle gelieferten Informationen den richtigen Feldern zuordnen
2. Nur noch die **fehlenden** Felder abfragen
3. Nicht Frage für Frage durchgehen, wenn die Antworten schon vorliegen

Das spart Rundtrips und respektiert das Tempo der Person.

---

### Projektstatus-Carry-Over

Wenn ein vorheriger Statuspost existiert (aus derselben Konversation oder aus Memory):
- Projektstatus der Vorwoche als Basis übernehmen
- Änderungen kompakt abfragen: „Letzte Woche war nBM `at risk`, FoW `on track`, AI `blocked` – hat sich was geändert? Neue Projekte dazu?"
- Nicht jedes Projekt einzeln neu abfragen

---

### Frage 1 – Letzte Woche (Feld 1)

> **„Was hast du letzte Woche konkret fertiggestellt oder abgeliefert?"**

Nachfragen nur wenn der Output unklar ist – nicht wenn die Tätigkeit erkennbar ein Ergebnis impliziert.

Transformationsregeln:
- Prozesse → Outcomes: „habe Workshop vorbereitet" → „Workshop-Konzept Phase 2 finalisiert"
- Wenn Channel/Link relevant: `→ [Channel-Name](Link)` anhängen
- Max. 4–5 Einträge; nur bei extremer Menge nach den wichtigsten fragen

---

### Frage 2 – Diese Woche (Feld 2)

> **„Was sind deine Prioritäten diese Woche – und was soll dabei konkret rauskommen?"**

Nachfragen nur wenn Output komplett unklar. Keine Nachfrage à la „Was soll am Ende der Woche vorliegen?" wenn die Antwort bereits ein erkennbares Deliverable enthält.

Transformationsregeln:
- Aufgaben mit Output-Signal versehen wenn fehlend
- Zeitangaben und Personen übernehmen wie geliefert
- Kein Limit auf „1–2 Prioritäten" – so viele wie geliefert werden

---

### Frage 3 – Projekte & Status (Feld 3)

> **„Welche Projekte laufen bei dir gerade aktiv – und wie ist der Status?"**

Status-Optionen:
- `on track` = läuft planmäßig
- `at risk` = droht zu kippen, Risiko sichtbar
- `blocked` = steckt fest, braucht externe Auflösung
- `slow progress` = kommt voran, aber langsamer als gewünscht (z.B. Zeitmangel)

**Wenn Projekte bereits aus Frage 1 oder 2 hervorgehen:** Nicht erneut abfragen, sondern direkt zusammenführen. Nur nach Status und ggf. neuen Projekten fragen.

Feste Channel-Links (siehe oben) automatisch einfügen. Für neue Projekte einmal fragen ob ein Channel existiert.

---

### Frage 4 – Input / Unterstützung (Feld 4)

> **„Brauchst du diese Woche von jemandem Input oder Unterstützung?"**

Bei „nein", „mope", „nee", oder ähnlichen Abbruchsignalen: sofort `–` eintragen und weitergehen. Keine Nachfrage nach „von wem" oder „bis wann" wenn die Person abbricht.

---

### Frage 5 – Infos & Erreichbarkeit (Feld 5)

> **„Gibt es was, das andere wissen sollten? Und: Bist du diese Woche eingeschränkt erreichbar?"**

Subfelder:
- 5.1 = kontextuelle Infos (Überschneidungen, Abhängigkeiten, Engpässe)
- 5.2 = Erreichbarkeit (Zeitblock, Abwesenheit, Reaktionsverzögerung)

Wenn beides leer: beide mit `–` befüllen.

---

### Ausgabe

Nach Abschluss aller Felder:

1. Generiere den vollständigen Post im verbindlichen Format
2. **Direkt als Plain Text ausgeben** – kein Codeblock, keine Trennlinien drumherum
3. Darunter kurz:

> „Passt? Einfach sagen was angepasst werden soll – z.B. 'ändere 3.1' oder '2.3 fehlt noch X'."

4. Nach Freigabe: fertig. Kein weiteres Kommentieren.

---

## Gesprächsführung – Prinzipien

**Tempo:** Unter 5 Minuten. Maximal eine Nachfrage pro Feld – und nur wenn wirklich nötig.

**Redundanz vermeiden:** Wenn Informationen bereits geliefert wurden (in einer früheren Antwort oder als Batch), nicht erneut abfragen. Direkt zuordnen.

**Ton:** Direkt, knapp, professionell. Kein „Fantastisch!", kein „Super, danke!", kein „Gut. Weiter zu..." mit übermäßiger Struktur-Narration.

**Sprache:** Deutsch (Standard). Wenn die Person auf Englisch antwortet, auf Englisch weiterführen.

**Umformulierungen:** Tätigkeiten → Outcomes, ohne Rückfrage – außer der Output ist unklar.

**Abbruchsignale:** Bei „mope", „nee", „vergiss es", „egal" oder ähnlichem: sofort weitergehen, keine Nachfrage.

**Minimalprinzip:** Bei wenig Inhalt wird ein valider Minimalpost generiert. Kein Druck auf vollständige Felder.

**Keine Meetings triggern:** Niemals Synchronisationsformate empfehlen.

**Keine Format-Erklärungen:** Nach dem Post nicht erklären, wie Teams Markdown rendert oder wie Links funktionieren.

---