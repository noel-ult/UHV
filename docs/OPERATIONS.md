# UHV: verification and operations

Reviewed against [default-branch commit 112c5ae038f7](https://github.com/noel-ult/UHV/commit/112c5ae038f7262179d286ee76917eccf71fbd8c) on 2026-10-28. Start with the [developer guide](PROJECT_GUIDE.md) for installation and architecture, and the [source reference](REFERENCE.md) for exact scripts, configuration readers, routes, and source locations.

## Issues, notices, and roles

Use disposable regular/admin accounts to exercise login, issue creation/comments, notice publishing, and denied admin actions. Check a database-backed route as well as /api/health.

These are acceptance scenarios for a maintainer to run in the documented environment. Their inclusion is not a claim that live integrations or production credentials were tested during this documentation update.

## Deployment and failure diagnosis

PostgreSQL initialization can fail while HTTP still starts. Inspect startup logs and schema permissions. Build-time VITE_API_URL and server FRONTEND_URL must match the deployed topology.

## Maintaining the contract

When behavior changes, update the guide and examples in the same PR. Check the entry point and working directory before copying commands. Use the linked source readers to distinguish build-time configuration from process environment. For failures, capture the first application error, runtime version, selected mode, and redacted configuration names before later proxy or port errors.

Keep changes tied to evidence: a declared command is not proof it passes, a process health response is not a successful end-to-end workflow, and a historical report describes its own revision. Record actual check results and any unavailable external services in the PR.
