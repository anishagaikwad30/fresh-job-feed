# Fresh – live job feed

A frontend job feed where new listings appear minutes after they're posted. Built as a portfolio project for a frontend developer role.

**Live demo:** _add your Netlify link here_

## Features

- **Live updates:** a mock WebSocket pushes new jobs and reconnects automatically when the network returns.
- **No layout jumps:** new jobs wait behind a "Show N new jobs" button, so the list doesn't shift while you read.
- **Optimistic saves:** the star updates instantly and rolls back with an error message if the request fails.
- **Offline support:** the feed, saved jobs and queued saves are cached in IndexedDB. Saves made offline sync when you reconnect.
- **Filters:** search, city, work mode, saved-only, and a pause/resume control for the live feed.
- **Job details and apply:** an accessible dialog (focus trapped and restored) with optimistic apply, an Applied filter and sort by newest or pay.
- **Accessibility:** semantic HTML, skip link, visible focus, `aria-pressed` controls, a polite live region for new jobs, reduced-motion support, dark mode.

## Tech

Vanilla JavaScript, HTML and CSS in a single `index.html`. No build step and no dependencies.

## Engineering decisions

- **Buffering new jobs** instead of inserting them: avoids layout shift and keeps keyboard and screen-reader focus stable.
- **Optimistic UI with rollback:** the interface feels instant, and a failed request restores the previous state.
- **IndexedDB over localStorage:** it is asynchronous and suited to larger, structured data such as the feed cache.
- **Mock API and socket:** simulated so the project runs anywhere with no backend. They sit behind small functions that can be replaced with real endpoints.

## Run locally

Open `index.html` in a browser.

## Next steps

- Port to React and TypeScript
- Add a Service Worker for full offline loading
- Add Playwright end-to-end tests
