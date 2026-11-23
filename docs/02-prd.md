# 02. Product requirements: Seat Selection with Front Seat Premium

| | |
|---|---|
| **Status** | Draft for discussion |
| **Owner** | Jay Mishra (case study) |
| **Market** | India, intercity carpool |
| **Target release** | Pilot on 3 corridors, then phased (see doc 05) |

## 1. Goal

Let passengers pick a specific seat when they book, priced by seat position. Use paid seat selection to move bookings into in-app payment.

## 2. Non-goals (v1)

- Dynamic or surge pricing by demand. Prices are set by the driver within a band.
- Seat selection for bus or train products.
- Paid luggage or other add-ons.
- Changing seat after pickup, except the free safety switch (R7).

## 3. Users and user stories

**Rider**
- As a tall rider, I want to reserve the front seat before I travel, so I don't have to negotiate for it at pickup.
- As a budget rider, I want a cheaper seat option, so I can travel for less if I accept the back row.
- As a rider travelling with a friend, I want to book two seats next to each other.
- As a solo woman rider, I want to know who the driver is before I choose the front seat, and I want to be able to move to the back for free if I feel uncomfortable.

**Driver**
- As a driver, I want to choose whether my ride uses seat pricing, so I keep control of my car.
- As a driver, I want to see what each seat will earn me before I publish, so I can be sure I won't lose money.
- As a driver, I want the app to tell passengers their seat, so I don't have to settle disputes at pickup.

## 4. Requirements

| ID | Requirement | Priority |
|---|---|---|
| R1 | Drivers can opt in to seat pricing when they publish a ride. Default is off during the pilot. | Must |
| R2 | When opted in, the driver sets a front-seat premium between ₹0 and ₹150 (band set by the platform per corridor). | Must |
| R3 | **Revenue-neutral mode (default):** the app spreads matching discounts across saver seats, so a full car totals the same as flat pricing. **Uplift mode** (optional, pilot-gated): saver seats stay at the base price. | Must |
| R4 | Riders see a top-down seat map with a price on each seat, colour-coded as Front / Standard / Saver / Booked. | Must |
| R5 | Choosing a seat requires paying in the app (UPI, card, net banking). A per-seat booking fee applies (assumed ₹15). | Must |
| R6 | The booking confirmation and the driver's passenger list show each person's seat. | Must |
| R7 | **Safety switch:** a rider in the front seat can move to any free back seat at pickup, with no questions and a full refund of the difference. | Must |
| R8 | The search results card shows "Front seat available" and the lowest seat price ("from ₹X"). | Should |
| R9 | Riders can book adjacent seats as a group. | Should |
| R10 | If the driver cancels or changes the car, seat-based charges are refunded in full. | Must |
| R11 | Riders with a declared medical need (for example motion sickness) can request the front seat at standard price, subject to availability. | Could |

## 5. Key flows

**Rider:** Search → ride card ("from ₹370 · Front seat available") → seat map → pick seat(s) → review price and booking fee → pay in app → ticket shows seat.

**Driver:** Publish ride → "Turn on seat pricing?" → set front premium with slider → preview of per-seat prices and full-car total → publish.

Both flows are clickable in the [prototype](../prototype/index.html).

## 6. Edge cases

| Case | Handling |
|---|---|
| Driver brings a different car than listed | Seat map is reset. Riders keep their price tier, or rebook, or cancel with a full refund. |
| Two riders claim the same seat at pickup | The ticket is the source of truth. The driver sees seat names in the app. |
| Front seat is unsold at departure | It stays empty or the driver offers it at base price. No automatic discount in v1. |
| Rider pays in cash outside the app | No seat guarantee. Only in-app bookings reserve a seat. |
| A saver seat in revenue-neutral mode is never sold | The driver earns less than the flat-price total on that ride. Tracked as a driver-earnings guardrail (doc 04). |

## 7. Dependencies

- In-app payments and payouts to drivers in India.
- A car-model database with seat layouts (5-seater sedan or hatchback, 7-seater MUV).
- Support playbook for seat disputes and the safety switch.

## 8. Open questions

1. Should the platform fee be a flat ₹15 per seat or a percentage?
2. Is uplift mode safe to offer at all under India's rules on private vehicles (see doc 05)?
3. Should drivers who opt in get better ranking in search? That would speed adoption but could feel unfair.
