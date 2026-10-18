# RailSaathi — hackathon pitch

## 30-second pitch

RailSaathi is a private, offline-first trip companion for train passengers. It keeps the details already on a passenger's ticket—boarding station, destination, coach, berth, and departure—in one readable card that stays on their phone. The demo also explains a common berth layout. It is useful without handing a PNR to an unverified service, and it never pretends to know a train's live position when no authorized feed is connected.

## 60-second pitch in Hinglish

“Station par jaldi mein passenger ko apni boarding station, destination, coach aur berth dobara dhoondhni padti hai—aur network bhi weak ho sakta hai. RailSaathi in details ko ek simple trip card mein rakhta hai, jo isi phone par save rehta hai aur pehli baar load hone ke baad offline bhi khul sakta hai. Passenger apna trip add, edit, share ya delete kar sakta hai, aur common berth layout check kar sakta hai. Is prototype mein data kisi server par upload nahi hota. Hum live train location ya PNR access ka jhootha claim nahi karte—woh authorized railway data integration ke baad hi aayega. Humne ek chhoti, testable problem ko privacy aur offline use ke saath solve kiya hai.”

## The problem

A passenger's journey information is scattered across a booking confirmation, station boards, messages, and memory. At a crowded station, they may need to confirm the boarding station, destination, coach, berth, and departure quickly. A weak connection makes reopening a booking or status page harder.

## What works in this build

- Add, edit, share, export, and delete a trip card.
- Keep saved trip cards in this browser on this device.
- Reopen the app shell offline after the first online visit on a supported browser.
- Check berth guidance for common Sleeper and AC 3 Tier numbering.
- Show a clear boundary: there is no live feed, PNR lookup, IRCTC account connection, or phone sign-in.

## Differentiator

Trust is a product decision. The app does not fill missing railway data with invented train movement, delay, platform, or ticket details. A passenger can use it as a private trip organizer now; live services require written authorization and a secure provider integration.

## Likely judge questions

**Why not show live train tracking?**  
A live indicator without an authorized, current data feed would be misleading. This MVP demonstrates the offline trip workflow; the design separates schedule, live-running, and PNR providers so each can be added with clear source and freshness labels.

**Why is this better than a notes app?**  
It groups train, route, class, coach, berth, departure, and a common berth guide into a single responsive flow, with explicit offline and privacy behavior. This is an early product hypothesis; it still needs passenger feedback to prove the workflow is clearer.

**Can users retrieve their IRCTC ticket with phone login?**  
No. Phone OTP would create a RailSaathi account; it does not grant access to IRCTC bookings. Ticket lookup requires a separately authorized provider and explicit consent.

**What is the next measurable step?**  
Ask five passengers to complete the add-and-find-my-berth flow, observe where they hesitate, and target a measurable improvement in completion time before adding licensed live data.

## Roadmap

1. Validate the flow with passengers and publish what changed from their feedback.
2. Obtain written rights for schedules, live running status, and authorized PNR enquiry.
3. Add a backend proxy, freshness labels, consent, retention controls, and account deletion only after provider terms and a security review.
4. Build and test the Android application before a Play Store release.
