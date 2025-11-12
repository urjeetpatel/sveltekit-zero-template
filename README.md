# sveltekit-zero-template

A minimal starter template for building SvelteKit 5 apps with PostgreSQL (Drizzle) and Zero Sync for live data synchronization.

Why this template
- Minimal, unstyled scaffold focused on developer productivity.
- Demonstrates a mix of SvelteKit remote functions + Zero Sync for realtime data.
- Docker Compose included for quick local development with Postgres and Zero.

Quick links
- License: GNU GPLv3 — see LICENSE in the repo.
- Issues: open an issue for bugs or feature requests.

Features
- SvelteKit 5 frontend
- Drizzle ORM for PostgreSQL access
- zero-svelte integration for realtime sync (alpha)
- Example remote functions for secure server-side logic
- Optional Traefik reverse proxy in compose setup

Prerequisites
- Node.js (LTS recommended)
- pnpm / npm / yarn
- Docker & docker-compose (for local stacks)
- Optional: a Zero Sync instance (local or hosted)

Quick start
1. Clone
   git clone <repo-url>
   cd sveltekit-zero-template

2. Install
   pnpm install
   # or npm install / yarn

3. Configure
   - Copy .env.example to .env and set values (DATABASE_URL, ZERO_SYNC_URL, ZERO_API_KEY, PORT).

4. Run development
   pnpm dev
   # Open http://localhost:5173 (or configured PORT)

Docker (local)
- If docker-compose.yml is present, run:
  docker compose up --build
- Services typically: app, postgres, zero-sync, traefik (optional).
- Ensure env variables used by compose are set (or in a compose env file).

Environment variables (example)
- DATABASE_URL=postgresql://user:pass@localhost:5432/dbname
- ZERO_SYNC_URL=http://localhost:PORT
- ZERO_API_KEY=your_key_if_required
- PORT=5173

Project structure (high level)
- app/src/ — SvelteKit app source
- app/src/lib — shared UI and utilities
- app/src/routes or server/ — remote functions and endpoints
- app/db/ or drizzle/ — database schemas and migrations (if present)
- docker-compose.yml — optional local compose orchestration

Using Zero vs remote functions
- Use SvelteKit remote functions for sensitive server-only operations.
- Use Zero Sync for collections that must remain live and consistent across clients.

Contributing
- Fork → branch → PR. Provide a clear description and reproduction steps for bugs.
- Add tests/examples for larger changes.
- See CONTRIBUTING.md if present.

Formatting
- This repo uses a formatter configured in the `app` package. Before committing, run the formatter from the `app` directory:

```bash
cd app
pnpm run format
```

- The repository includes a GitHub Actions check that runs on pushes and pull requests targeting the `Development` branch. The check will fail if formatting makes changes — please commit formatted files before opening or updating a PR so merges are not blocked.

License
This repository is licensed under GNU General Public License v3.0 (GPLv3). See the LICENSE file for full terms.

Contact
- Open an issue for questions, bugs, or feature requests.


