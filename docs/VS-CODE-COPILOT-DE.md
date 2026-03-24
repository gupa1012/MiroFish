# MiroFish-Prinzip in VS Code mit GitHub Copilot nutzen

Wenn du MiroFish in deiner Firmenumgebung **nicht komplett installieren darfst**, kannst du das **Prinzip** trotzdem in einer deutlich leichteren Form in **VS Code + GitHub Copilot** nachbauen. Du brauchst dafür **keine Hunderte Subagents** – für viele Anwendungsfälle reichen **4 bis 6 klar definierte Rollen**.

Diese Variante ersetzt nicht die vollständige MiroFish-Laufzeit, ist aber oft der pragmatischste Weg für:

- restriktive Unternehmensumgebungen
- Security-Vorgaben ohne lokale Zusatzdienste
- Teams, die nur VS Code Extensions installieren dürfen
- schnelle Experimente mit wenigen Agentenrollen

## Kurzantwort

Ja – der beste Startpunkt ist meistens **nicht** eine eigene VS Code Extension, sondern:

1. **GitHub Copilot in VS Code**
2. **ein kleines Set wiederverwendbarer Agenten-Anweisungen**
3. **klare Dateien für Kontext, Rollen und Zwischenergebnisse**

Eine **eigene VS Code Extension** lohnt sich erst dann, wenn du den Ablauf später vereinheitlichen oder mit Buttons/Formularen automatisieren willst.

## Empfohlener Minimal-Setup

Lege dir im Workspace zum Beispiel diese Struktur an:

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

- `seed.md`: Ausgangslage, Quellen, Annahmen
- `world.md`: Akteure, Beziehungen, Regeln, Ziele
- `tasks.md`: konkrete Simulationsfragen
- `report.md`: Ergebnisdokument
- `agents/*.md`: wiederverwendbare Anweisungen je Rolle

## Welche “Subagents” du wirklich brauchst

Für eine kleine, brauchbare Simulation reichen meistens diese Rollen:

### 1. Planner

Zerlegt das Problem in Schritte.

**Aufgabe:**
- Ziel klären
- beteiligte Akteure identifizieren
- Unsicherheiten benennen
- Simulationsplan erstellen

### 2. World Builder

Baut die Mini-Welt aus dem Seed-Material.

**Aufgabe:**
- Rollen und Beziehungen extrahieren
- Interessen und Konflikte formulieren
- Randbedingungen definieren

### 3. Simulator

Spielt mehrere Runden oder Szenarien durch.

**Aufgabe:**
- Reaktionen der Akteure simulieren
- Folgeeffekte beschreiben
- alternative Verläufe vergleichen

### 4. Critic

Prüft die Simulation auf schwache Stellen.

**Aufgabe:**
- unrealistische Annahmen finden
- blinde Flecken markieren
- Gegenhypothesen formulieren

### 5. Reporter

Verdichtet alles zu einem nutzbaren Ergebnis.

**Aufgabe:**
- wichtigste Szenarien zusammenfassen
- Risiken und Signale priorisieren
- klare Handlungsempfehlungen formulieren

## So setzt du das mit GitHub Copilot um

### Variante A: Ohne eigene Extension

Das ist für die meisten Teams der richtige Start.

Arbeite mit:

- **GitHub Copilot Chat**
- **Custom Instructions / wiederverwendbaren Prompt-Dateien**
- **Markdown-Dateien als gemeinsamer Speicher**

### Beispielablauf

1. Schreibe dein Ausgangsmaterial in `seed.md`.
2. Öffne `agents/planner.md` und gib Copilot den Auftrag, daraus einen Ablaufplan zu machen.
3. Überführe das Ergebnis in `world.md`.
4. Lasse den Simulator 3 bis 5 plausible Szenarien erzeugen.
5. Lasse den Critic jedes Szenario angreifen.
6. Lasse den Reporter die belastbarsten Ergebnisse in `report.md` schreiben.

Das ist im Kern bereits eine kleine Multi-Agent-Pipeline – nur eben **über klar getrennte Rollen und Dateien** statt über eine große Runtime.

### Variante B: Mit eigener VS Code Extension

Wenn ihr Extensions installieren dürft, ist eine kleine interne Extension sinnvoll, **aber erst als zweiter Schritt**.

Eine eigene Extension ist nützlich, wenn du:

- Standard-Ordner und Dateien automatisch anlegen willst
- Vorlagen für Agentenrollen per Klick erzeugen willst
- wiederkehrende Prompts über Commands starten willst
- Ergebnisse strukturiert in Dateien schreiben willst

Eine sinnvolle erste Extension muss gar nicht viel können. Schon diese Funktionen reichen:

- `Create Simulation Workspace`
- `Insert Planner Prompt`
- `Insert Simulator Prompt`
- `Generate Final Report`

Wichtig: Die Extension sollte möglichst **nur orchestrieren**, nicht selbst komplexe Agentenlogik enthalten.

## Beispiel für Agenten-Anweisungen

Du kannst die Rollen sehr einfach als Markdown-Vorlagen definieren.

### `agents/planner.md`

```md
Du bist der Planner.
Ziel: Zerlege das Problem in 4-6 konkrete Simulationsschritte.
Arbeite nur mit dem Inhalt aus seed.md.
Liefere:
1. Zielbild
2. relevante Akteure
3. offene Unsicherheiten
4. Simulationsplan
```

### `agents/simulator.md`

```md
Du bist der Simulator.
Nutze seed.md, world.md und tasks.md.
Erzeuge 3 alternative Zukunftsverläufe:
- konservativ
- wahrscheinlich
- stress / worst case

Für jeden Verlauf:
1. Auslöser
2. Reaktion der Akteure
3. Ketteneffekte
4. beobachtbare Signale
```

### `agents/critic.md`

```md
Du bist der Critic.
Prüfe die Simulation auf:
- unbelegte Annahmen
- fehlende Akteure
- zu lineare Kausalität
- ignorierte Gegenreaktionen

Liefere nur konkrete Einwände und Verbesserungsvorschläge.
```

## Mapping zum MiroFish-Prinzip

Auch mit kleinem Setup kannst du die Grundidee von MiroFish gut nachbilden:

| MiroFish-Prinzip | Leichte VS-Code-Variante |
|---|---|
| Seed-Informationen extrahieren | `seed.md` mit Quellen und Kontext |
| Welt / Beziehungen aufbauen | `world.md` mit Rollen, Zielen, Regeln |
| Agenten simulieren | Copilot mit getrennten Rollen-Prompts |
| Ergebnisse verdichten | `report.md` mit Szenarien, Risiken, Empfehlungen |

Der wichtigste Punkt ist dabei **Rollenklarheit**. Schon wenige Rollen funktionieren gut, wenn jede Rolle:

- einen klaren Auftrag hat
- definierte Eingaben nutzt
- ein festes Ausgabeformat produziert

## Empfehlung für Enterprise- und Security-Umgebungen

Wenn Sicherheit bei euch der limitierende Faktor ist, starte so einfach wie möglich:

1. **Keine externe Zusatzruntime erzwingen**
2. **Kontext lokal in Dateien halten**
3. **Nur freigegebene Modelle / Endpunkte verwenden**
4. **Keine automatische Code- oder Shell-Ausführung einbauen**
5. **Prompts versionierbar im Repository ablegen**

So bleibt der Ablauf nachvollziehbar, reviewbar und meistens deutlich leichter freigabefähig.

## Wann du doch eine Extension bauen solltest

Eine eigene Extension lohnt sich, wenn mindestens eines davon zutrifft:

- mehrere Nutzer sollen denselben Ablauf verwenden
- ihr braucht standardisierte Agentenvorlagen
- ihr wollt reproduzierbare Reports
- ihr wollt Eingabemasken statt manueller Prompt-Arbeit

Wenn du aber erst einmal nur prüfen willst, ob das Prinzip in deiner Umgebung funktioniert, dann ist **Copilot + 5 Rollendateien + 4 Markdown-Arbeitsdateien** fast immer der beste erste Schritt.

## Praktische Empfehlung

Wenn du heute starten willst, nimm genau diese fünf Rollen:

1. Planner
2. World Builder
3. Simulator
4. Critic
5. Reporter

Damit bekommst du eine schlanke, verständliche und in vielen Firmenumgebungen realistische Annäherung an das MiroFish-Prinzip – direkt in VS Code mit GitHub Copilot.
