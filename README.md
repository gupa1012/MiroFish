# MiroFish – sofort starten

Dieses Repository enthält eine **fertige Simulationsvorlage** mit 5 Agentenrollen und einem Beispielszenario. Du kannst direkt loslegen.

## Schnellnavigation

| Was | Wo |
|---|---|
| **Simulation starten** | [simulation/](./simulation/) |
| Ausführliche Anleitung (DE) | [docs/VS-CODE-COPILOT-DE.md](./docs/VS-CODE-COPILOT-DE.md) |
| English overview | [README-EN.md](./README-EN.md) |
| Archiv (alter Full-Stack-Code & Doku) | [docs/archive/](./docs/archive/) |

## 3-Minuten-Start

1. **VS Code öffnen**, GitHub Copilot aktivieren.
2. Ordner `simulation/` öffnen – dort liegt alles bereit.
3. `seed.md` durchlesen oder mit eigenen Daten füllen.
4. Copilot Chat öffnen und Schritt für Schritt mit den Rollen arbeiten:

| Schritt | Rolle | Prompt-Vorlage |
|---------|-------|----------------|
| 1 | **Planner** | Öffne `agents/planner.md`, gib Copilot den Inhalt als Anweisung |
| 2 | **World Builder** | `agents/world-builder.md` → Ergebnis in `world.md` eintragen |
| 3 | **Simulator** | `agents/simulator.md` → 3 Szenarien erzeugen |
| 4 | **Critic** | `agents/critic.md` → Szenarien prüfen |
| 5 | **Reporter** | `agents/reporter.md` → Ergebnis in `report.md` schreiben |

## Was ist in `simulation/` enthalten?

```text
simulation/
  seed.md              ← Ausgangslage (Beispiel: ERP-Einführung)
  world.md             ← Akteure, Beziehungen, Regeln
  tasks.md             ← Simulationsfragen
  report.md            ← Ergebnisvorlage
  agents/
    planner.md         ← Rolle, Aufgabe, Ausgabeformat
    world-builder.md
    simulator.md
    critic.md
    reporter.md
```

Alle Agent-Dateien enthalten **vollständige Rollenbeschreibungen** mit Aufgabe, Eingaben, Ausgabeformat und Regeln. Das Beispielszenario (ERP-Einführung) ist sofort simulierbar.

## Die 5 Basisrollen

| # | Rolle | Aufgabe |
|---|-------|---------|
| 1 | **Planner** | Zerlegt das Problem in Schritte, benennt Unsicherheiten |
| 2 | **World Builder** | Baut Akteure, Beziehungen und Regeln auf |
| 3 | **Simulator** | Spielt 3 Szenarien durch (konservativ, wahrscheinlich, worst case) |
| 4 | **Critic** | Sucht unrealistische Annahmen, bringt Gegenhypothesen ein |
| 5 | **Reporter** | Fasst Risiken, Signale und Empfehlungen zusammen |

## Eigene Agents ergänzen

Die 5 Basisrollen sind der Startpunkt. Wenn deine Simulation zusätzliche Perspektiven braucht, lege einfach weitere Dateien unter `simulation/agents/` an:

```text
agents/einkauf.md
agents/fachbereich.md
agents/freigabe.md
agents/logistik.md
```

Jeder Agent folgt dem gleichen Muster: **klare Rolle → klare Eingaben → klares Ausgabeformat**.

## Was wurde archiviert?

Der gesamte ursprüngliche Full-Stack-Code und die alten READMEs liegen jetzt unter `docs/archive/`:

- Alter Backend- und Frontend-Code → `docs/archive/fullstack/`
- Ursprüngliche README-Dateien → `docs/archive/`

Details: [docs/archive/README.md](./docs/archive/README.md)

## Ausführliche Anleitung

Die vollständige deutsche Anleitung mit Hintergrund, Mapping zum MiroFish-Prinzip und Tipps für Enterprise-Umgebungen:

→ [docs/VS-CODE-COPILOT-DE.md](./docs/VS-CODE-COPILOT-DE.md)
