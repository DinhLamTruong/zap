# Copilot Instructions for zap-zalo

## Project Overview
- **zap-zalo** is a React single-page application, bootstrapped with Create React App but migrated to use Vite for development and builds.
- The main UI is an iframe embedding `https://m-dev.zap.vn/` (see `src/App.js`).
- App configuration is managed via `app-config.json`.

## Key Files & Structure
- `src/App.js`: Main entry, renders the embedded Zalo app via iframe.
- `src/index.js`: React root, sets up rendering and web vitals reporting.
- `public/index.html`: HTML template, includes Zalo platform verification meta tag.
- `app-config.json`: UI and app settings (title, colors, header, etc).
- `.env`: Contains `APP_ID` and `ZMP_TOKEN` for environment-specific config.
- `vite.config.js`: Vite setup, uses `@vitejs/plugin-react` and `zmp-vite-plugin`.

## Developer Workflows
- **Start dev server:** `npm run dev` (served by Vite, not CRA)
- **Testing:** Uses Jest and React Testing Library. Run tests with `npm test`.
- **Build for production:** `npm run build` (handled by Vite)
- **No custom scripts** for linting or formatting; relies on CRA/Vite defaults.

## Patterns & Conventions
- **Component Structure:** Minimal, single top-level `App` component. Extend by adding new components in `src/` and importing into `App.js`.
- **Styling:** CSS files in `src/` (e.g., `App.css`, `index.css`).
- **Testing:** Place test files alongside components, e.g., `App.test.js`.
- **Environment Variables:** Use `.env` for secrets/config, referenced via Vite's import.meta.env (if needed).
- **App Config:** UI and behavior settings are centralized in `app-config.json`.

## Integration & External Dependencies
- **Zalo Platform:** Embedded via iframe; Zalo site verification meta in `public/index.html`.
- **Dependencies:**
  - React 19, ReactDOM 19
  - Vite for build/dev
  - `@vitejs/plugin-react`, `zmp-vite-plugin` for Zalo Mini App support
  - Testing: `@testing-library/*`, `jest-dom`, `web-vitals`

## Special Notes
- **Do not eject**: Project is not ejected; config is managed via Vite and plugins.
- **Public assets:** Place static files in `public/`.
- **No backend/server code** in this repo.

## Example: Adding a New Feature
1. Create a new component in `src/` (e.g., `MyFeature.js`).
2. Import and use it in `App.js`.
3. Add tests in `MyFeature.test.js`.
4. Update `app-config.json` if UI config is needed.

---

For more, see `README.md` and Vite/React documentation links within.
