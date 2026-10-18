# RailSaathi: what is required for a real public app

This is a production checklist, not sample train data. Do not show invented train positions, platform numbers, PNR details, or timings as live information.

## Current hackathon MVP

The current repository is a static, offline-first web app. A user can manually add, edit, share, and delete a trip card; see a common berth layout; and export locally saved data. Trip cards stay in browser local storage on the same device. There is no sign-in, cloud sync, real-time status, booking lookup, or PNR integration. The PNR approach selected for the future product is an authorized PNR lookup, but no provider or contract has been selected.

## Data access

### Scheduled train and station information

The Open Government Data Platform lists an Indian Railways train timetable dataset, but its catalogue says it was last updated on 24 January 2018. It is not a trustworthy source for a current all-trains launch without a fresh authoritative update.

IRCTC's current Train Information Enquiry Scheme (TIES) policy lists train schedules, trains between stations, fare/availability, and PNR enquiry. Registration is for an eligible firm/organisation and requires an application and integration. The policy does not list live running location as one of its current enquiry features, so the app also needs a separately authorized live running-data source.

The IRCTC policy currently linked from its website (edition 2025, v2.1, effective 20 Sep 2025) lists mobile-app fees as:

- General firm: ₹10 lakh + tax one-time integration; ₹5 lakh + tax minimum annual commitment.
- Eligible startup/MSME: ₹5 lakh + tax one-time integration; ₹2.5 lakh + tax minimum annual commitment.
- In addition, ₹5 lakh refundable security deposit and ₹0.25 + tax per enquiry; the annual commitment or enquiry charges, whichever is higher, applies.

Startup/MSME pricing has registration and certification conditions. Confirm the current policy and eligibility with IRCTC before relying on these amounts.

## User accounts and tickets

- Phone OTP login authenticates a RailSaathi account; it does not grant access to a passenger's IRCTC bookings.
- PNR lookup or ticket retrieval must use an authorized railway data integration. Protect PNRs and passenger details in transit and at rest, restrict staff access, and set a deletion/retention policy.
- A user may save a trip manually as an interim product feature, but that is not the same as retrieving the user's tickets from IRCTC.
- Google Play requires a privacy policy and accurate Data safety disclosures. If users can create accounts, provide account deletion both inside the app and through an external web page.

## App and release

- Android application: Kotlin + Jetpack Compose; repository layer separates UI, local saved trips, identity, and licensed train-data providers.
- Identity: Firebase Phone Authentication can provide OTP login after a Firebase project is configured, app signatures are registered, SMS regions are enabled, and users consent to phone-number processing.
- Backend: keep data-provider credentials on a server, never inside the Android app. Add caching, request limits, timestamps, and clear stale-data states.
- Google Play: developer account, verified identity, signed Android App Bundle, store listing, privacy policy URL, Data safety form, and Play review are required. Newly created personal accounts may also need the required closed test before production access.

## Decisions needed before live integration

1. Which authorized provider or contract supplies current schedules, live train movement, and PNR enquiry? IRCTC TIES alone does not list live movement in its current feature set.
2. Does the owner have the eligible registered entity and budget for the official route, or should we compare licensed commercial providers first?
3. What retention/deletion limits and user consent language are required by the selected provider for PNR responses?
4. Does the owner already have a Google Play Console and Firebase project?

Keep all train responses labeled with the data provider and last-updated time. If a provider is unavailable, say so; never silently fall back to fabricated live status.

## Provider screening notes (18 Oct 2026)

These are discovery leads, not approved integrations. A public endpoint or free tier is not proof that its provider has the rights, privacy controls, or service level needed for a public ticket app.

| Candidate | Publicly stated features | What still needs written verification |
|---|---|---|
| IRCTC TIES | Official schedule, trains-between-stations, fare/availability and PNR enquiry | Commercial agreement/eligibility and cost; live running-location feed is not listed in the current feature list |
| Qrail | Vendor advertises schedules, PNR, running status; lists a free tier (100 requests/day) and a Pro tier (₹1,999/year, 10,000 requests/day) | Written commercial redistribution rights, upstream data authorization, PNR retention/deletion practices, uptime/quotas and current pricing |
| API Mitra | Vendor advertises schedule, live status and PNR endpoints with failover; docs state a 30 requests/min train-endpoint limit | Written commercial redistribution rights, PNR data handling/retention, upstream source and production SLA |
| RailRadar | Advertises live status driven by voluntary passenger GPS and separate API plans | Its terms say it does not provide official PNR processing and describes status as crowd-powered secondary guidance; therefore it does not satisfy the requested PNR integration as reviewed |

Before selecting a third-party provider, obtain a written answer that its license permits a public Google Play app to display both train data and passenger-wise PNR responses, and confirm whether PNR payloads are logged or retained. Do not send real PNRs to a trial API while evaluating it.
