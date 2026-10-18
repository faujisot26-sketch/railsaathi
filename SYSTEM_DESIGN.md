# RailSaathi system design

## Current prototype

~~~mermaid
flowchart LR
  P[Passenger] --> UI[Responsive web app]
  UI --> LS[Browser local storage]
  UI --> SW[Service worker app shell]
  SW --> Cache[Cached static files]
  UI -. explicit export/share .-> P
  UI -. no connection .-x R[Railway data provider]
~~~

The current implementation is static HTML, CSS, and JavaScript. Trip cards stay in local browser storage; the service worker caches only the app shell. No PNR, account, or train data is sent to a server. Export and sharing are user-initiated boundaries.

## Production target

~~~mermaid
flowchart LR
  A[Android app] --> B[RailSaathi API]
  B --> I[Identity and consent]
  B --> C[Cache and rate limits]
  C --> D[Authorized schedule provider]
  C --> E[Authorized live-running provider]
  C --> F[Authorized PNR provider]
  B --> G[Minimal audit events]
  A --> L[Encrypted local trip cache]
~~~

- Keep vendor credentials on the server; never package secrets in a mobile app.
- Confirm written commercial display rights, upstream data source, permitted caching, PNR logging/retention, deletion, quotas, and uptime before integration.
- Mark each response with its provider and last-updated time. On provider failure, surface unavailable/stale state.
- Use minimal access logs; never log full PNR payloads or passenger names by default.
- Make consent, retention, account deletion, and support paths visible before collecting account or ticket data.
- Phone OTP authenticates the RailSaathi account; it does not automatically grant access to IRCTC bookings.

See PRODUCTION_REQUIREMENTS.md for release dependencies.
