# AGENTS.md

## Cursor Cloud specific instructions

This repository is **documentation-only**. It is a Spanish-language "ZERO TO HERO"
study-tutor content project for the **ELECTRO1** course. There is no application,
no source code, no services, and no runtime.

- **No dependencies / no build / no tests / no services.** There is no package
  manager, dependency manifest, lockfile, build system, test framework, Docker,
  or CI config. Nothing needs to be installed, compiled, started, or served.
- **The update script is a no-op** (`true`). Do not add install/build/run steps —
  there is nothing for them to act on.
- **The "product" is a Cursor always-on rule**: `.cursor/rules/tutor-zero-to-hero.mdc`
  (`alwaysApply: true`). It "runs" only inside Cursor — the editor loads the rule
  and the AI assistant behaves as the tutor. There is nothing to launch or record.
- **Repo layout**: `README.md` (overview), `tutor/PROTOCOLO.md` (protocol),
  `tutor/ENTRADA.md` (intake template), `tutor/PLANTILLA_GUIA.md` and
  `tutor/PLANTILLA_RESOLUCION.md` (templates), `tutor/inbox/` (raw study material),
  `tutor/sesiones/` (saved resolutions).
- **Content golden rule** (from the tutor protocol): never invent problem
  statements or data. If material is missing, ask for the minimum needed. Do not
  fabricate ELECTRO1 exercises to "demonstrate" the tutor.
- **How to sanity-check the repo**: confirm the `.mdc` frontmatter contains
  `alwaysApply: true` so Cursor loads the rule, and confirm the `README.md`
  internal links resolve to existing files/dirs. Both are plain file checks — no
  tooling required.
