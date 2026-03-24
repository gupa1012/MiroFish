# MiroFish – leichtgewichtiger Einstieg

Dieses Repository ist jetzt auf einen **leichtgewichtigen Einstieg mit VS Code + GitHub Copilot** ausgerichtet.

Wenn du das ursprüngliche MiroFish-Projekt in deiner Firmenumgebung **nicht installieren darfst**, kannst du trotzdem das **Prinzip** nutzen: ein kleines Set an Rollen, klare Markdown-Dateien und GitHub Copilot als Orchestrierung.

## Schnellnavigation

- **Leichtgewichtige Anleitung:** [docs/VS-CODE-COPILOT-DE.md](./docs/VS-CODE-COPILOT-DE.md)
- **Archiv des ursprünglichen Projekts:** [docs/archive/README.md](./docs/archive/README.md)
- **Archivierte Original-README (中文):** [docs/archive/README-original-zh.md](./docs/archive/README-original-zh.md)
- **Archived original README (English):** [docs/archive/README-original-en.md](./docs/archive/README-original-en.md)
- **English overview:** [README-EN.md](./README-EN.md)

## Was ist hier jetzt der empfohlene Weg?

**Nicht** mehr zuerst das komplette alte Full-Stack-Projekt lokal hochziehen.

**Sondern zuerst:**

1. VS Code öffnen
2. GitHub Copilot nutzen
3. mit **5 klaren Rollen** arbeiten
4. alles in ein paar Markdown-Dateien dokumentieren

So bekommst du eine deutlich schlankere Variante des MiroFish-Prinzips, ohne die ursprüngliche Infrastruktur vollständig nachbauen zu müssen.

## 5-Minuten-Start

Lege in einem Arbeitsordner diese Struktur an:

```text
copilot-sim/
  seed.md
  world.md
  tasks.md
  report.md
  agents/
    planner.md
    world-builder.md
    simulator.md
    critic.md
    reporter.md
```

### Bedeutung der Dateien

- `seed.md` – Ausgangslage, Quellen, Kontext
- `world.md` – Akteure, Beziehungen, Regeln
- `tasks.md` – deine eigentlichen Simulationsfragen
- `report.md` – Ergebnis und Empfehlungen
- `agents/*.md` – wiederverwendbare Rollen-Anweisungen

## Die 5 Rollen, die meist reichen

### 1. Planner
- zerlegt die Aufgabe in konkrete Schritte
- benennt Unsicherheiten

### 2. World Builder
- baut die Mini-Welt aus dem Seed-Material
- beschreibt Rollen, Interessen und Konflikte

### 3. Simulator
- spielt 3 bis 5 Szenarien durch
- beschreibt Reaktionen und Ketteneffekte

### 4. Critic
- sucht unrealistische Annahmen
- bringt Gegenhypothesen ein

### 5. Reporter
- fasst die Ergebnisse zusammen
- priorisiert Risiken, Signale und Empfehlungen

## Flexible Agentenrollen je nach Usecase

Die 5 Basisrollen sind der Startpunkt, aber **nicht** die Obergrenze.

Wenn deine Simulation zusätzliche Perspektiven braucht, kannst du je nach Usecase weitere Agents ergänzen. Bei einer **Prozesssimulation** kann zum Beispiel **jeder Prozessbeteiligte einen eigenen Agent** bekommen, damit sichtbar wird, wie Teilprozesse ineinandergreifen, wo Übergaben scheitern und welche Interessen kollidieren.

Beispiel:

- `agents/einkauf.md`
- `agents/fachbereich.md`
- `agents/freigabe.md`
- `agents/logistik.md`

Das Prinzip bleibt gleich: **klare Rolle, klare Eingaben, klares Ausgabeformat**.

## Konkreter Ablauf in VS Code

1. Schreibe dein Material in `seed.md`.
2. Bitte Copilot als **Planner**, daraus einen Ablaufplan zu erstellen.
3. Übernimm das Ergebnis in `world.md`.
4. Bitte Copilot als **Simulator**, mehrere Zukunftsverläufe durchzuspielen.
5. Bitte Copilot als **Critic**, die Szenarien anzugreifen.
6. Bitte Copilot als **Reporter**, ein kompaktes Ergebnis in `report.md` zu schreiben.

Damit hast du bereits eine kleine Multi-Agent-Pipeline – nur ohne schwere lokale Runtime.

## Wann du eine eigene VS Code Extension brauchst

Eine eigene Extension lohnt sich erst, wenn du:

- denselben Ablauf häufig wiederholst
- Dateien und Vorlagen per Klick erzeugen willst
- den Prozess teamweit standardisieren willst

Für den Einstieg ist **Copilot + Markdown + 5 Rollen** fast immer die einfachste Lösung.

## Was wurde archiviert?

Die bisherige, umfangreichere Projektpräsentation des ursprünglichen MiroFish-Projekts wurde aus der Startseite herausgenommen und ins Archiv verschoben:

- große Projektvorstellung
- Demo-/Showcase-lastige README-Inhalte
- ursprüngliche Full-Stack-Einstiegstexte

Damit bleibt die Haupt-README bewusst kurz, praktisch und auf deinen leichtgewichtigen Anwendungsfall fokussiert.

## Falls du doch den ursprünglichen Stack brauchst

Der ursprüngliche Code bleibt im Repository erhalten:

- `backend/`
- `frontend/`
- `docker-compose.yml`
- `.env.example`

Wenn du später doch auf den ursprünglichen Stack zurückgehen willst, findest du den alten Einstieg hier:

- [docs/archive/README.md](./docs/archive/README.md)

## Empfehlung

Wenn du **heute** starten willst, beginne mit:

- GitHub Copilot in VS Code
- `seed.md`
- `world.md`
- `tasks.md`
- `report.md`
- 5 Basisrollen-Dateien unter `agents/`
- bei Bedarf zusätzliche Usecase-Agents pro Beteiligtem oder Teilprozess

Die ausführlichere deutsche Anleitung mit Beispiel-Prompts findest du hier:

- [docs/VS-CODE-COPILOT-DE.md](./docs/VS-CODE-COPILOT-DE.md)
