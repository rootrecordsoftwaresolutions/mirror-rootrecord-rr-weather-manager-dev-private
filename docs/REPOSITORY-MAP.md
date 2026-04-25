# Repository map

| Path | Purpose |
|------|--------|
| `src/main.js` | Main process, SQLite, almost all IPC, guest/auth, backups. |
| `src/preload.js` | Minimal `contextBridge` for license-style helpers. |
| `src/licenseService.js` | Root Record account / entitlement / session (HTTP API to Worker). |
| `src/cloudBackup.js` | Local and optional online DB backup. |
| `src/weatherSyncEngine.js` | Weather and hazard sync into SQLite. |
| `src/autoUpdate.js` | **electron-updater** (GitHub Releases on public download repo). |
| `scripts/*.cjs` | Asset prep (icons, NSIS, sounds), `electron-builder` driver, `latest-yml`, signing post-step. |
| `build/` | `app-update.yml` (updater), `installer.nsh`, NSIS art outputs, **Azure** signing scripts (no live secrets in Git). |
| `assets/` | Brand sources, `notification-sounds-source/`, `favicon.ico`, NSIS sources; **marketing** stills for design reference. |
| `package.json` | `version`, `build` (electron-builder), `scripts`. |
| `frontend/` | **React** (Create React App) + **Tailwind** web UI that talks to `backend/` — run `npm install` / `npm start` inside `frontend/` (separate from root Electron `npm`). |
| `backend/` | **FastAPI** + **MongoDB** (Motor) API: license proxy, locations, public weather/hazard feeds. See [FRONTEND-AND-BACKEND.md](./FRONTEND-AND-BACKEND.md). |
| `design_guidelines.json` | Product **design tokens** / theme reference for the web client. |
| `test_reports/` | CI / Emergent test artifacts. |
| `.emergent/` | Emergent tooling config (if used). |
| `docs/` | Developer documentation (this tree). |
| `dist/`, `release/`, `node_modules/` | **Not** in Git (local / CI only). |

Public **customer** downloads live on **GitHub Releases** in **`RootRecord/rootrecord-weather-manager-download`**, not in this private source tree.
