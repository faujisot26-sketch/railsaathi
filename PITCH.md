# RailSaathi — project pitch

## One sentence

RailSaathi turns the confusing parts of a train ticket into a clear, private trip card that passengers can keep on their phone, even when the network disappears.

## The problem

A passenger's journey information is scattered across a booking confirmation, station boards, messages, and memory. At a crowded station, a passenger may need to quickly confirm the boarding station, destination, coach, berth, and departure time. A generic train-status screen does not solve that last-mile information problem, especially with weak connectivity.

## Who it is for

A passenger preparing for a reserved train journey, particularly someone who wants a readable journey summary and offline access without handing a PNR to an unverified app.

## What is built

The current MVP lets a passenger add only the trip details they choose, understand a common berth layout, keep the trip on the same device, and export or share a trip card intentionally. It displays an explicit data-status boundary for live feeds and PNR lookup.

## Why this approach

Trust is part of the product. A missing railway feed must look missing; it must never be replaced with made-up train movement, delay, or platform data. The MVP works without account creation, sends no journey data to a server, and is useful as a real offline trip organizer.

## What is next

1. Validate the flow with one real passenger and improve it from their feedback.
2. Obtain written data-provider terms for schedules, live status, and PNR enquiry.
3. Add a backend proxy, authentication, retention controls, and privacy/account deletion flows only after the provider and security design are approved.
4. Ship a signed Android build after Play Console and testing requirements are met.
