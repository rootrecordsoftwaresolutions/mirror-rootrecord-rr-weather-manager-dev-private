# Web frontend and mobile API (React + FastAPI)

This tree adds a **separate** stack from the **Electron** desktop app: a **React** client in `frontend/` and a **Python/FastAPI** service in `backend/`. The desktop `src/main.js` app is unchanged; the web stack is for browsers (and as a reference for future native clients) using the same **license** host and public data sources where applicable.

## Backend (`backend/`)

- **Run** (from `backend/` with a virtualenv and deps from `requirements.txt`):

  ```text
  pip install -r requirements.txt
  uvicorn server:app --reload --host 0.0.0.0 --port 8000
  ```

- **Environment** (see `server.py` for full list; **required** includes `MONGO_URL` and `DB_NAME`). Optional: `LICENSE_API_BASE_URL`, `CORS_ORIGINS` (comma-separated, or `*` in dev).
- **Tests:** `backend/tests/backend_test.py` (pytest); see `test_reports/` for prior run output.

## Frontend (`frontend/`)

- **Run** (separate `node_modules` from the Electron root):

  ```text
  cd frontend
  npm install
  npm start
  ```

- **Build:** `npm run build` inside `frontend/` (output in `frontend/build/`, gitignored at repo root).
- The package name in `frontend/package.json` is `rrweather-mobile` — it is a **web** app (react-scripts), not a Flutter project.

## Design reference

- **`design_guidelines.json`** — theme and UX constraints for the web UI; keep in sync with product when changing styles.

## Emergent

- **`.emergent/`** — configuration used by the Emergent agent flow; safe to read, do not put secrets there.

For architecture of the **Electron** app, see [ARCHITECTURE.md](./ARCHITECTURE.md).
