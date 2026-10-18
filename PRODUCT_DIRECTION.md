# Product direction: RailSaathi Arrival Handoff

## The idea

RailSaathi helps a passenger and their pickup person coordinate the last few steps after a train journey. It focuses on the handoff at the destination station instead of trying to replace live train tracking.

**Pitch:** “Where is my Train tells you where the train is; RailSaathi helps the passenger and pickup person be ready to meet after the train arrives.”

This is a product hypothesis to validate with passengers, not a claim that no other product offers similar features.

## The problem

At an unfamiliar or crowded station, a passenger may need to remember their coach and berth, contact the person meeting them, and find the agreed meeting place. These details can be scattered across messages and ticket screens. Weak connectivity can make them harder to retrieve.

## Proposed MVP flow

1. The passenger enters their own trip details, pickup contact, and a meeting-place note.
2. RailSaathi saves a clear arrival card on that device: destination, coach/berth, contact, and the passenger-entered meeting note.
3. The passenger shares the card intentionally with their chosen contact.
4. A simple checklist guides the handoff: keep ticket available, contact pickup person, go to the agreed meeting point, confirm arrival.
5. The card remains readable offline after the app has loaded once.

## What makes this direction distinct

Where is my Train already offers train status, offline schedules, destination alarms, coach layout/platform information, and PNR-related links. RailSaathi should not compete by copying those features. Its proposed focus is the passenger-to-pickup handoff and personal arrival plan.

All contact and meeting-place details are user-entered. The prototype should not imply that it knows live arrival time, station exits, train location, or that a contact has received a message. Sharing happens only when the passenger chooses it.

## Demo story

Use fictional data. A passenger arriving at “Demo City” has coach S4, berth 48, and a pickup contact. They enter “meet at the main gate” as their own note, save the plan, show the large arrival card, switch to the offline state, and share the card intentionally. State clearly that the meeting point is user-provided, not a verified station map.

## Validate before claiming impact

Ask at least five passengers, including someone who has met a traveler at a busy station, to try the plan creation and handoff flow. Observe whether they can find the contact and meeting note quickly. Record consented feedback and use it to simplify the flow. Do not claim time savings or safety outcomes until measured.

## Later possibilities

- Optional read-aloud and larger text for accessibility.
- A real notification or live arrival signal only after a licensed, reliable data provider is selected.
- Contact check-in only with clear consent and privacy controls.

These are roadmap items, not features already present in the prototype.
