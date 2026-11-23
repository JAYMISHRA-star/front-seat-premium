# 05. Risks and go-to-market

## Risk register

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| **Regulatory.** In India, carrying passengers for profit in a private (white-plate) car can count as commercial use. Charging more than cost could weaken the "cost-sharing" position. | Medium | High | Revenue-neutral is the default. Uplift mode only after legal review. Keep a per-ride cap linked to estimated fuel and toll costs. |
| **Rider safety.** Seat pricing could nudge solo women riders into the front seat next to an unknown driver. | Medium | High | Free safety switch at pickup (PRD R7), driver profile and rating shown on the seat map, safety-switch rate tracked by gender. |
| **Fairness perception.** "Paying more for the same ride" may feel unfair. | Medium | Medium | Frame it as choice: the back seat gets cheaper. Show the saver price first ("from ₹350"). |
| **Seat disputes at pickup** | Medium | Low | Seat named on the ticket and on the driver's list; support playbook. |
| **Driver opt-out** | Medium | Medium | Earnings preview before publish; revenue-neutral guarantees no loss on a full car. |
| **Car swap.** Driver arrives in a different car than listed. | Low | Medium | Reset the seat map, keep tiers, full refund option (PRD edge cases). |
| **Cannibalisation of cash bookings creates friction** | Medium | Medium | Seat choice is optional. Riders can still book without picking a seat. |

## Go-to-market plan

| Phase | Scope | Goal | Exit criteria |
|---|---|---|---|
| 0. Discover (4 weeks) | Survey, interviews, data pull (doc 01) | Validate willingness to pay and safety concerns | Front-seat WTP ≥ ₹50 for at least 30% of riders |
| 1. Concierge pilot (4 weeks) | 50 hand-picked drivers on 1 corridor; seat assigned by support team | Test operations and disputes with no build cost | Dispute rate and driver satisfaction acceptable |
| 2. A/B test (6 weeks) | 3 corridors, driver-level randomisation (doc 04) | Measure earnings, conversion, in-app share | Decision rules in doc 04 |
| 3. Scale | 10+ corridors, then all intercity routes | Make seat pricing the default for new drivers | Guardrails hold at scale |

## Messaging

- **To riders:** "Pick your seat. Front seat for more legroom, back seat for less."
- **To drivers:** "Turn on seat pricing. A full car earns the same, and the front seat sells first."
- **Internally:** "Seat selection is how we move India to in-app payment."

## What I would do differently with real data

- Price the premium per corridor and per car type instead of using one band.
- Test showing seat maps only on rides with 3 or more open seats, where seat position matters most.
- Explore a "Comfort" bundle (front seat plus max 2 in the back) as a later product line.
