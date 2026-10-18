# RailSaathi

**Your journey, understood.** The current build is an offline-first trip companion. Its proposed next direction is Arrival Handoff: helping a passenger and their pickup person coordinate the meeting after the journey.

## Proposed next direction

Arrival Handoff is a product concept, not a feature in the current app. It would let a passenger save and intentionally share a user-entered pickup contact and meeting note with their trip details. See [PRODUCT_DIRECTION.md](PRODUCT_DIRECTION.md) for the idea, demo story, and validation plan.

## What works now

- Add, edit, delete, export, and share your own journey cards.
- Save journeys in this browser on this device; cards remain available offline after the first visit.
- Check a berth number against a general Sleeper or AC 3 Tier layout.
- Install the web app on supported browsers.
- View the data status clearly: live location, delay, platform, PNR lookup, and IRCTC login are not connected.

The sample trip is explicitly illustrative. It is not a current train schedule, ticket, or live status. Never enter a real PNR or sensitive passenger information.

## Try it

Open index.html in a browser, or host this folder as a static site. Service workers require HTTPS (or localhost) for offline caching and installation.

### Deploy

- **Netlify:** for a manual deploy, drag this folder into the deploy area. If the GitHub repository contains these files at its root, connect the repository and set the publish directory to `.` (or leave it blank if Netlify treats the repository root as the default).
- **GitHub Pages:** this repository includes a workflow that publishes the root folder on pushes to `main`. Open **Settings → Pages**, choose **GitHub Actions** as the build and deployment source, and save. The first successful workflow run publishes the app at `https://faujisot26-sketch.github.io/railsaathi/`.
- No build step, API key, or account is needed for this prototype.

## Privacy boundary

Trip cards are stored in local browser storage. They are not encrypted, uploaded, or synced. Anyone with access to this browser profile may be able to see them. Export creates a file on your device; only share it with someone you trust. Clearing site data removes saved trips. Use the delete button to remove them deliberately.

## Data required before production

A production release needs written authorization for train schedules, running status, and PNR results; a secure backend to protect provider credentials; defined retention/deletion rules; a privacy policy; and Google Play testing/release work. See PRODUCTION_REQUIREMENTS.md.

## Project map

- index.html — complete responsive app and local trip workflows
- manifest.webmanifest, sw.js, icon.svg — install and offline app shell
- PITCH.md — project story and judge Q&A
- PRODUCT_DIRECTION.md — proposed Arrival Handoff concept and validation plan
- SYSTEM_DESIGN.md — data boundaries and production architecture
- DEMO_SCRIPT.md — a three-minute walkthrough
- HACKATHON_CHECKLIST.md — final presentation checklist
