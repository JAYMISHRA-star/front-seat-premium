# 01. Problem and research

## Problem statement

On an intercity carpool in India, every passenger seat costs the same, but the seats are not equal. Passengers compete informally for the front seat, usually on a first-come basis at pickup. That creates three problems:

- **Riders** who value the front seat cannot secure it, even when they would pay more for it.
- **Riders** in the worst seats (back-row centre, the third row of a 7-seater) pay full price for the least comfort. Some avoid booking crowded cars entirely.
- **The platform** has no booking fee in India and no strong reason for riders to pay in the app instead of in cash to the driver.

## Who wants the front seat, and why

These hypotheses come from my own rides as a BlaBlaCar driver. They have not been validated yet. The research plan below is how I would test them.

| Segment | Why the front seat matters | Willingness to pay (hypothesis) |
|---|---|---|
| Tall riders and older riders | Legroom; easier to get in and out | High |
| Riders prone to motion sickness | Front seat with a forward view reduces nausea on ghat roads | High |
| Working professionals | Space for a laptop, phone charging, fewer interruptions | Medium |
| Solo women riders | Mixed. Some prefer the front seat, others prefer not to sit next to an unknown male driver | Varies; needs research |
| Budget riders and students | Prefer the cheapest seat and will accept the back row for a discount | Negative (they gain from saver seats) |

The last two rows matter. The feature has to work for riders who want to pay *less*, and it must never pressure anyone into a seat they find unsafe.

## Competitive landscape

| Product | What it offers | Paid? |
|---|---|---|
| Airlines (IndiGo, Air India, international carriers) | Paid seat selection by row and legroom | Yes |
| Uber Comfort | Newer cars, more legroom, quiet-ride preference | Yes, about 20–40% over UberX |
| UberX Share / Lyft Shared | Riders may sit in front if they need to | No |
| BlaBlaCar "Max. 2 in the back" | Driver promises at most two passengers in the back | No |
| BlaBlaCar (Europe) | Service fee of about 16–20% of passenger price | Yes, but not seat-based |
| BlaBlaCar (India) | No passenger fee as of Oct 2025 | No |

**Insight:** No carpool platform prices seats by position. Airlines have already taught Indian travellers to accept paid seat selection, so the idea is new for carpools but familiar to riders.

Sources: [Fortune on Uber Comfort](https://fortune.com/2019/07/09/uber-comfort-rides-legroom-quiet-driver/), [BlaBlaCar comfort option](https://blog.blablacar.com/newsroom/news-list/ridesharing-comfy), [BlaBlaCar service fee](https://legal.blablacar.com/en-gb/service-fee/), [TechCrunch on BlaBlaCar India](https://techcrunch.com/2025/10/25/india-the-market-blablacar-once-walked-away-from-is-now-its-biggest).

## Research plan (to validate before building)

1. **Rider survey (n ≈ 300)** on 3–4 busy corridors (for example Indore–Bhopal, Delhi–Jaipur, Bengaluru–Mysuru). Questions: seat preference, reasons, and a Van Westendorp price-sensitivity block for the front-seat premium.
2. **15–20 rider interviews**, deliberately including solo women riders, to understand how safety shapes seat preference.
3. **10 driver interviews.** Would drivers opt in? Would they accept a revenue-neutral model, or only an uplift model? How do they settle seat disputes today?
4. **Data pull (if inside the company):** share of rides with 3 or more passengers, cancellation rate by number of booked seats, and support tickets that mention seats.

## Success looks like

Riders who care about the seat get it, riders who don't pay less, drivers earn at least as much as before, and the platform gains a reason for riders to pay in the app.
