# History

## LUCIT-Systems-and-Development origin

> Superseded — repo now lives under `oliver-zehentleitner`, MIT-licensed.

**Id:** 1fb27149-5ceb-4cb0-813c-0c8072e82a79
**Type:** decision
**Status:** superseded
**Evidence:** confirmed
**Source:** commit `e5aecb1` "Remove LUCIT licensing and rebrand to MIT open source"; earliest commit `32bdf57` "INIT", 2024-09-04, already within the LUCIT era
**Superseded by:** https://github.com/oliver-zehentleitner/unicorn-binance-suite — 2749fc08-cdca-456b-a8bd-fd4b646ff64c — as of 2026-09-28

Same lineage as the rest of the suite — this module was not born newer/independent of the LUCIT history despite being one of the more recently active repos. Package directories were renamed `lucit-ubdcc-* → ubdcc-*` as part of the rebrand.

**Reason:** LUCIT is no longer part of how this project is licensed, distributed, or supported.

## OVH → ghcr.io registry migration

> Superseded — migration complete.

**Id:** c090532e-b1b7-4884-bac3-ed1d17cf1ceb
**Type:** decision
**Status:** superseded
**Evidence:** confirmed
**Source:** commits `0421504` "K8s YAMLs: migrate to ghcr.io with version tag instead of SHA digest", `587c750` "Helm: update image registry URLs from OVH to ghcr.io"
**Superseded by:** none — the migration was completed (commits `0421504`, `587c750`); no later decision replaced it

Docker images now live on `ghcr.io/oliver-zehentleitner/ubdcc-*`. `admin/k8s/*.yaml` and `dev/helm/ubdcc/` no longer reference the old OVH container registry or its SHA256 digests.

**Note found while writing this:** `TASKS.md` still had this listed as an open backlog item ("Update Helm chart and K8s YAMLs to ghcr.io") and `AGENTS.md` repeated the same stale claim — both predate the actual migration commits above. Fixed the `AGENTS.md` claim as part of this pass; the `TASKS.md` checkbox is left for Oliver to close since it's his backlog, not `context/`'s to groom.

## No conda-forge distribution — by design, not an oversight

**Id:** 8ee1d2a2-dccc-4cda-bc0f-8fef0e601e00
**Type:** decision
**Status:** active
**Evidence:** confirmed
**Source:** commit `ea5fd2c`: "UBDCC is intentionally not distributed via conda-forge (PyPI + ghcr.io Docker only). The badge pointed at a build_conda.yml workflow that doesn't exist and never will."

Unlike its sibling suite modules, UBDCC has no conda-forge feedstock and never did — distribution is PyPI (wheels per sub-package) plus Docker images on `ghcr.io`.

**Reason:** stated directly in the commit removing a leftover Anaconda badge — this was a deliberate scope decision for this module, not a migration-in-progress or an oversight like the LUCIT-era conda cleanups in the rest of the suite.
