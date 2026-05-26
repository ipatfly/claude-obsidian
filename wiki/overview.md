---
type: overview
title: "Wiki-Übersicht & Alltags-Navigator"
created: 2026-04-07
updated: 2026-05-26
tags:
  - meta
  - overview
status: evergreen
related:
  - "[[index]]"
  - "[[hot]]"
  - "[[log]]"
  - "[[dashboard]]"
  - "[[LLM Wiki Pattern]]"
sources:
---

# Wiki-Übersicht & Alltags-Navigator

Willkommen in deiner persistenten Wissensbasis! Dieses Wiki basiert auf Andrej Karpathys **LLM Wiki Pattern** und wächst mit jeder Interaktion organisch mit. Der Chat ist nur das Interface – das Wiki ist das bleibende Produkt.

Schnellnavigation: [[index|Master-Katalog]] | [[hot|Hot Cache (Kontext)]] | [[log|Operations-Logbuch]] | [[dashboard|Dataview Dashboard]]

---

## 🚀 Die Kern-Workflows im Alltag

Das System übernimmt die gesamte Schreibarbeit, das Verknüpfen und die Pflege. Du steuerst die Zufuhr von Quellen und stellst die Fragen.

### 1. Ingest (Quellen einlesen)
* **Ablauf:** Du legst eine neue Quelle (z. B. einen Web-Clip, Artikel oder ein PDF) im Ordner `_raw/` ab und sagst dem Agenten: `"ingest [Dateiname]"` (oder nutzt `/wiki-ingest`).
* **Was passiert im Hintergrund?** 
  Der Agent liest die Quelle, extrahiert Entitäten, Konzepte und Themen und erstellt oder aktualisiert ca. 8–15 Wiki-Seiten. Er verknüpft sie untereinander, aktualisiert den Master-Index (`index.md`), den Hot Cache (`hot.md`) und fügt ganz oben im Operations-Logbuch (`log.md`) einen kurzen Eintrag hinzu.
  *Hinweis: Die Rohdatei in `_raw/` bleibt immer unberührt und schreibgeschützt.*

### 2. Query (Wissen abfragen)
* **Ablauf:** Du fragst einfach im Chat: `"Was weißt du über [Thema]?"` (oder nutzt `/wiki-query`).
* **Was passiert im Hintergrund?** 
  Der Agent liest zuerst den Hot Cache (`hot.md`), um den jüngsten Kontext zu laden. Falls nötig, schaut er in den Index (`index.md`) und liest gezielt 3–5 relevante Wiki-Seiten. Er generiert eine fundierte Antwort mit präzisen Wikilinks. Gute Antworten können auf Wunsch dauerhaft als Note in `wiki/questions/` abgelegt werden.

### 3. Lint (Wartung & Health-Check)
* **Ablauf:** Alle 10–15 eingelesenen Quellen sagst du einfach: `"lint the wiki"` (oder nutzt `/wiki-lint`).
* **Was passiert im Hintergrund?** 
  Der Linter analysiert alle Wiki-Seiten und spürt verwaiste Seiten (Orphans), tote Wikilinks, Lücken im Frontmatter oder fehlende Querverweise auf. Er erstellt einen detaillierten Report in `wiki/meta/lint-report-YYYY-MM-DD.md`, den du in Obsidian einsehen kannst, und bietet an, gefundene Fehler automatisch zu beheben.

### 4. Fold (Logbuch-Kompaktierung)
* **Ablauf:** Wenn das Logbuch sehr lang wird, sagst du: `"fold the log"` (oder nutzt `/wiki-fold`).
* **Was passiert im Hintergrund?** 
  Der Fold-Skill liest die ältesten Einträge aus `wiki/log.md` und rollt sie in strukturierte Übersichtsseiten im Ordner `wiki/folds/` zusammen. Dadurch bleibt dein Haupt-Logbuch klein, übersichtlich und spart wertvolle Kontext-Token.

---

## 🛠️ Aktive Skills & Trigger-Phrasen

Hier ist die Übersicht deiner alltagstauglichen Sprachbefehle:

| Skill | Trigger / Aufruf | Zweck im Alltag |
| :--- | :--- | :--- |
| **`wiki`** | `/wiki` oder `set up wiki` | Setup-Status prüfen oder neues Wiki scaffolden |
| **`wiki-ingest`** | `ingest [Dateiname]` oder `ingest [URL]` | Einzelne oder mehrere Quellen in das Wiki einpflegen |
| **`wiki-query`** | `Was weißt du über X?` oder `query quick: X` | Wiki durchsuchen und präzise Antworten generieren |
| **`wiki-lint`** | `lint the wiki` oder `health check` | Wiki-Struktur prüfen und Fehler (tote Links etc.) aufdecken |
| **`wiki-fold`** | `fold the log` oder `log rollup` | Altes Logbuch komprimieren und Folds anlegen |
| **`save`** | `/save` oder `save this conversation` | Aktuellen Chatverlauf als Note im Wiki archivieren |
| **`autoresearch`**| `research [Thema]` oder `/autoresearch` | Autonomes Suchen, Ingesten und Zusammenfassen eines Themas |
| **`canvas`** | `/canvas` oder `add to canvas` | Visuelle Canvas-Karten in Obsidian verwalten und anlegen |

---

## 📁 Die Logik hinter den Ordnern

Um die Ordnung aufrechtzuerhalten, folgt das Wiki einer klaren Zuständigkeit:

```
vault/
├── _raw/               # Deine unveränderlichen Original-Quellen (schreibgeschützt!)
├── _templates/         # Obsidian-Vorlagen für neue Seiten (Templater)
├── _attachments/       # Bilder, PDFs und Anhänge, die in Wiki-Seiten eingebettet sind
└── wiki/               # Das lebendige, wachsende Wiki (gehört dem Agenten)
    ├── index.md        # Der Master-Katalog aller Seiten
    ├── hot.md          # Hot Cache: Die wichtigsten jüngsten Erkenntnisse (~500 Wörter)
    ├── log.md          # Schlankes, chronologisches Logbuch (neue Einträge immer OBEN!)
    ├── meta/           # Große, detaillierte Berichte (wie Lint-Reports und Session-Protokolle)
    ├── concepts/       # Ideen, Frameworks und Pattern (z. B. [[LLM Wiki Pattern]])
    ├── entities/       # Personen, Repositories, Organisationen (z. B. [[Andrej Karpathy]])
    ├── sources/        # Zusammenfassungen der eingelesenen Quellen aus _raw/
    └── questions/      # Dauerhaft gesicherte Antworten auf deine Fragen
```

> [!TIP]
> **Das Prinzip des compounding Knowledge:** 
> Wenn du eine neue Quelle einliest, erstelle ich fast nie ein komplett neues, isoliertes Dokument. Stattdessen aktualisiere und ergänze ich bestehende Konzept- und Entitäten-Seiten. So verwebt sich dein Wissen immer dichter und widerspruchsfreie Erkenntnisse bauen direkt aufeinander auf!
