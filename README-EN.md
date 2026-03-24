# MiroFish – lightweight entry point

This repository is now oriented toward a **lightweight VS Code + GitHub Copilot workflow** instead of pushing new users straight into the original full-stack setup.

If you cannot install the original project in a restricted enterprise environment, start with a small set of agent roles, a few markdown files, and Copilot as the coordinator.

## Quick links

- **German lightweight guide:** [docs/VS-CODE-COPILOT-DE.md](./docs/VS-CODE-COPILOT-DE.md)
- **Archive of the original project docs:** [docs/archive/README.md](./docs/archive/README.md)
- **Archived original README (中文):** [docs/archive/README-original-zh.md](./docs/archive/README-original-zh.md)
- **Archived original README (English):** [docs/archive/README-original-en.md](./docs/archive/README-original-en.md)
- **German README:** [README.md](./README.md)

## Recommended lightweight workflow

Create a workspace like this:

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

Use these five roles:

1. Planner
2. World Builder
3. Simulator
4. Critic
5. Reporter

Then run the workflow in Copilot Chat:

1. Put your source material into `seed.md`
2. Ask the Planner to create the simulation plan
3. Turn that into `world.md`
4. Ask the Simulator for multiple scenario paths
5. Ask the Critic to challenge the assumptions
6. Ask the Reporter to summarize the outcome in `report.md`

## Extending the base agents for each simulation type

You are not limited to the five base roles.

If a simulation needs additional viewpoints, add use-case-specific agents. For a **process simulation**, each participant can get its own agent so you can see how subprocesses interact, where handoffs fail, and where incentives or constraints conflict.

Example:

- `agents/procurement.md`
- `agents/business-owner.md`
- `agents/approval.md`
- `agents/logistics.md`

The same rule still applies: **clear role, clear inputs, clear output format**.

## What was archived?

The previous, heavier landing-page style documentation from the original MiroFish project has been archived so that the root README stays short and practical.

The original codebase is still present in:

- `backend/`
- `frontend/`
- `docker-compose.yml`
- `.env.example`

If you need the original project presentation and setup flow, use the archive:

- [docs/archive/README.md](./docs/archive/README.md)
