# RailSaathi — hackathon pitch

## 30-second pitch

RailSaathi is a private, offline-first arrival handoff companion for train passengers and the people meeting them. It puts the passenger-entered destination, coach and berth, pickup contact, and meeting note into one readable card that stays on their phone and can be shared intentionally. Where is my Train helps locate the train; RailSaathi’s proposed focus is helping the passenger and pickup person coordinate the station handoff. It does not claim live arrival data or verified station directions.

## 60-second pitch in Hinglish

“Station par pahunchne ke baad passenger aur pickup karne wale ko milne ki jagah aur contact dobara dhoondhna pad sakta hai—network bhi weak ho sakta hai. RailSaathi ek arrival handoff card banata hai jisme passenger apna coach, berth, pickup contact aur meeting note save karke apni marzi se share karta hai. Card isi phone par rehta hai aur app pehle load ho jaane ke baad offline khul sakta hai. Where is my Train train ko locate karne mein madad karta hai; RailSaathi ka proposed focus passenger aur pickup person ko milne ke liye ready karna hai. Hum live arrival ya verified station directions ka claim nahi karte. Yeh idea ab passengers ke saath validate karna hai.”

## The problem

A passenger's journey information is scattered across a booking confirmation, station boards, messages, and memory. At an unfamiliar or crowded station, a passenger and their pickup person may need to find the contact, coach/berth, and agreed meeting place quickly. A weak connection can make scattered messages harder to retrieve.

## What works in this build

- Add, edit, share, export, and delete a trip card.
- Keep saved trip cards in this browser on this device.
- Reopen the app shell offline after the first online visit on a supported browser.
- Check berth guidance for common Sleeper and AC 3 Tier numbering.
- Show a clear boundary: there is no live feed, PNR lookup, IRCTC account connection, or phone sign-in.

## Proposed differentiator

Arrival Handoff is a proposed next direction, not functionality already implemented in the app. Trust is a product decision. The app does not fill missing railway data with invented train movement, delay, platform, or ticket details. The current build works as a private trip organizer. The handoff flow still needs to be built and validated; live services require written authorization and a secure provider integration.

## Likely judge questions

**Why not show live train tracking?**  
A live indicator without an authorized, current data feed would be misleading. This MVP demonstrates the offline trip workflow; the design separates schedule, live-running, and PNR providers so each can be added with clear source and freshness labels.

**Why is this better than a notes app?**  
Its proposed focus is the passenger-to-pickup handoff: a private, user-entered arrival plan that can be read offline and intentionally shared. This is an early product hypothesis; it still needs passenger feedback to prove the workflow is useful.

**Can users retrieve their IRCTC ticket with phone login?**  
No. Phone OTP would create a RailSaathi account; it does not grant access to IRCTC bookings. Ticket lookup requires a separately authorized provider and explicit consent.

**What is the next measurable step?**  
Ask five passengers and pickup contacts to create and use an arrival handoff plan, observe where they hesitate, and measure whether they can find the meeting details quickly.

## Roadmap

1. Validate the flow with passengers and publish what changed from their feedback.
2. Obtain written rights for schedules, live running status, and authorized PNR enquiry.
3. Add a backend proxy, freshness labels, consent, retention controls, and account deletion only after provider terms and a security review.
4. Build and test the Android application before a Play Store release.
