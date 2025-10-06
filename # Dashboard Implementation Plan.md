# Dashboard Implementation Plan

## Data & State Design

- Define TypeScript interfaces in `src/types/index.ts` for tasks, deadlines, study sessions, habits, universities, and system status payloads.
- Establish JSON storage schemas in `server/data/*.json` with seed placeholders.

## Backend Services

- Scaffold Express server in `server/index.ts` with routes grouped under `/api/tasks`, `/api/study-sessions`, `/api/habits`, `/api/universities`, `/api/search`, `/api/system-status` using JSON file persistence helpers in `server/utils/dataStore.ts`.
- Implement cron/job runner in `server/utils/statusMonitor.ts` to poll Node.js/DB health for the status endpoint.

## Frontend Architecture

- Set up global state via React Query + Zustand store in `src/store/index.ts` for syncing API data.
- Configure routing/layout shell in `src/App.tsx` with sidebar navigation and widgets grid in `src/pages/Dashboard.tsx`.

## Feature Widgets

- Build `UpcomingDeadlinesWidget` in `src/components/widgets/UpcomingDeadlinesWidget.tsx` with prioritization and combined course/application data.
- Implement `StudySessionTracker` in `src/components/widgets/StudySessionTracker.tsx` with timer controls, session history modal, and API hooks.
- Create `RecurringHabits` checklist in `src/components/widgets/RecurringHabits.tsx` supporting daily/weekly/monthly recurrence logic.
- Develop university tracker: `src/pages/Universities.tsx` with cards/list view plus nested `RequirementsChecklist` component in `src/components/universities/RequirementsChecklist.tsx`.

## Utilities & System Features

- Add `GlobalSearchBar` component in `src/components/global/GlobalSearchBar.tsx` querying unified `/api/search` endpoint.
- Provide customizable `QuickLinksPanel` in `src/components/global/QuickLinksPanel.tsx` persisted via JSON config.
- Display `SystemStatusIndicator` in `src/components/global/SystemStatusIndicator.tsx` polling the backend status route.

## Styling & UX

- Extend Tailwind theme in `tailwind.config.js` for dashboard palette and spacing; create reusable widget card styles in `src/styles/widgets.css` (imported in `src/main.tsx`).
- Incorporate motion cues with Framer Motion in widget components adhering to slower animation guidance.

## Testing & Tooling

- Write unit tests with Vitest for Zustand stores and utility functions in `src/tests/*`.
- Add API integration tests via Supertest in `server/tests/*` and ensure `npm run test` covers both.
- Document usage and runbooks in `README.md` including instructions to restart Vite after Tailwind changes.