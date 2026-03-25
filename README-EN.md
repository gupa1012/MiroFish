# MiroFish – start immediately

This repository contains a **ready-to-use simulation template** with 5 agent roles and an example scenario. You can start right away.

## Quick links

| What | Where |
|------|-------|
| **Start simulation** | [simulation/](./simulation/) |
| Detailed guide (German) | [docs/VS-CODE-COPILOT-DE.md](./docs/VS-CODE-COPILOT-DE.md) |
| German README | [README.md](./README.md) |
| Archive (old full-stack code & docs) | [docs/archive/](./docs/archive/) |

## 3-minute start

1. **Open VS Code**, enable GitHub Copilot.
2. Open the `simulation/` folder – everything is ready.
3. Read `seed.md` or fill in your own data.
4. Open Copilot Chat and work through the roles step by step:

| Step | Role | Prompt template |
|------|------|-----------------|
| 1 | **Planner** | Open `agents/planner.md`, give Copilot the content as instruction |
| 2 | **World Builder** | `agents/world-builder.md` → put result into `world.md` |
| 3 | **Simulator** | `agents/simulator.md` → generate 3 scenarios |
| 4 | **Critic** | `agents/critic.md` → challenge the scenarios |
| 5 | **Reporter** | `agents/reporter.md` → write result into `report.md` |

## What's in `simulation/`?

```text
simulation/
  seed.md              ← Starting situation (example: ERP rollout)
  world.md             ← Actors, relationships, rules
  tasks.md             ← Simulation questions
  report.md            ← Result template
  agents/
    planner.md         ← Role, task, output format
    world-builder.md
    simulator.md
    critic.md
    reporter.md
```

All agent files contain **complete role descriptions** with task, inputs, output format, and rules. The example scenario (ERP rollout) is ready to simulate.

## The 5 base roles

| # | Role | Task |
|---|------|------|
| 1 | **Planner** | Breaks down the problem into steps, identifies uncertainties |
| 2 | **World Builder** | Builds actors, relationships, and rules |
| 3 | **Simulator** | Plays through 3 scenarios (conservative, probable, worst case) |
| 4 | **Critic** | Finds unrealistic assumptions, brings counter-hypotheses |
| 5 | **Reporter** | Summarizes risks, signals, and recommendations |

## Adding custom agents

The 5 base roles are the starting point. If your simulation needs additional perspectives, add more files under `simulation/agents/`:

```text
agents/procurement.md
agents/business-owner.md
agents/approval.md
agents/logistics.md
```

Every agent follows the same pattern: **clear role → clear inputs → clear output format**.

## What was archived?

All original full-stack code and legacy READMEs now live under `docs/archive/`:

- Old backend & frontend code → `docs/archive/fullstack/`
- Original README files → `docs/archive/`

Details: [docs/archive/README.md](./docs/archive/README.md)
