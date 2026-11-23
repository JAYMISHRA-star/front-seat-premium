# 04. Metrics and experiment

## North-star metric

**Seats booked and paid in the app per week.** It captures rider value (they got the seat they wanted), driver value (paid, guaranteed seats) and platform value (fee-bearing bookings).

## Metric tree

| Layer | Metric | Target direction |
|---|---|---|
| Adoption | % of published rides with seat pricing on (driver opt-in rate) | ↑ |
| Adoption | % of riders who open the seat map | ↑ |
| Rider value | Front-seat attach rate (front sold / front available) | ↑ |
| Rider value | Search-to-booking conversion | ↑ or flat |
| Driver value | Driver earnings per published ride | ↑ |
| Driver value | Average seats filled per ride | ↑ |
| Platform value | Share of bookings paid in the app | ↑ |
| Platform value | Booking-fee revenue per week | ↑ |

## Guardrails (pause the rollout if any of these break)

| Guardrail | Threshold |
|---|---|
| Rider cancellation rate | No more than 1 point above control |
| Seat-dispute support tickets | Fewer than 1 per 500 seat-priced bookings |
| Safety-switch rate (front → back at pickup) | Watched weekly, segmented by rider gender. A spike triggers a review. |
| Safety and harassment reports | No increase versus control |
| Driver earnings on rides where saver seats sold but front didn't | Tracked; must stay rare (< 5% of rides) |
| Rider app rating / NPS | No drop |

## Experiment design

**Unit of randomisation: the driver**, not the rider. Pricing is set per ride, and riders on the same ride see the same map. Randomising riders would show different prices for the same seat.

- **Population:** drivers on 3 pilot corridors who publish at least 2 rides per month.
- **Arms:**
  - Control: flat pricing (today)
  - Treatment A: seat selection, revenue-neutral
  - Treatment B: seat selection, uplift (only if cleared by legal, see doc 05)
- **Duration:** 6 weeks. That covers at least 4 full weekend cycles and avoids festival weeks, or controls for them.
- **Primary metric:** driver earnings per published ride.
- **Secondary:** seats filled per ride, in-app payment share, search-to-booking conversion.
- **Interference:** treatment and control rides appear in the same search results. Riders who want the front seat may move toward treatment rides. That is the effect we want to measure, but it can inflate the treatment result. A follow-up **corridor-level switchback** (alternate weeks per corridor) gives a cleaner estimate of the market-wide effect.

## Rough sample size

To detect a 5% lift in driver earnings per ride, with a coefficient of variation of about 0.6, α = 0.05 and 80% power, you need about 2,300 rides per arm. Pilot corridors at a few hundred rides per day reach that within the 6-week window. Check this against real variance before launch.

## Decision rules

| Result | Decision |
|---|---|
| Primary up, guardrails hold | Expand to 10 more corridors (doc 05, phase 3) |
| Primary flat, in-app share up | Ship revenue-neutral as a payments driver; rethink the premium band |
| Any safety guardrail breaks | Stop, investigate, redesign the safety switch before retesting |
| Conversion drops more than 2 points | Make seat pricing visible only after the rider picks a ride, then retest |
