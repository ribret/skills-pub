# status-post-interview · Claude Skill

> **Intern · prosma GmbH & Co. KG**

---

## Was ist das?

Ein Claude-Skill, der Teammitglieder in unter 5 Minuten durch ein strukturiertes Interview führt und daraus einen fertig formatierten Wochenstatus-Post für den **A-Status-Channel** (Microsoft Teams) generiert.

Der Skill übernimmt:
- Gezielte Abfrage der 5 Pflichtfelder
- Transformation von Tätigkeitsbeschreibungen in Outcomes
- Automatische Verlinkung bekannter Projekt-Channels
- Ausgabe als direkt kopierbarer Plain-Text-Post

---

## Installation

1. Datei `status-post-interview.skill` herunterladen
2. In Claude.ai: **Einstellungen → Skills → Skill installieren**
3. Datei auswählen → bestätigen

Der Skill ist danach aktiv und wird automatisch ausgelöst.

---

## Verwendung

Einfach in Claude schreiben:

- „Ich muss noch meinen Status schreiben"
- „Statuspost KW [XX]"
- „Help me with my weekly update"

Claude führt dann das Interview durch und gibt den fertigen Post aus.

---

## Ausgabeformat

```
📅 KW [XX] | [Name]

1 · Erledigt letzte Woche
2 · Fokus diese Woche
3 · Aktive Projekte
4 · Input / Unterstützung gesucht
5 · Infos & Erreichbarkeit
```

Projektstatus-Werte: `on track` · `at risk` · `blocked` · `slow progress`

---

## Enthaltene Channel-Links

| Projekt | Channel |
|---|---|
| nBM | K Atruvia |
| FoW Marketing | A Marketing |
| AI Scaling / L&D | A AI Learning und Development |

Neue Projekte ohne Channel: Platzhalter `#[channel]` wird gesetzt.

---

## Dateistruktur

```
status-post-interview/
└── SKILL.md        # Skill-Definition (Interview-Logik, Format, Regeln)
```

Die `.skill`-Datei ist ein ZIP-Archiv. Inhalt einsehbar via:
```bash
unzip -p status-post-interview.skill status-post-interview/SKILL.md
```

---

## Wartung & Weiterentwicklung

Änderungen an Interview-Logik, Format oder Channel-Links: `SKILL.md` bearbeiten, neu paketieren, hier ablegen.

Ansprechpartner: **Richard Bretzger**
