# 03. Pricing model

All figures are illustrative assumptions for a student case study.

## Two modes

**Revenue-neutral (default).** The front seat costs `base + P`. The same total `P` is taken off the saver seats, split by weight (the worse the seat, the bigger the discount). A full car earns the driver exactly what flat pricing would.

**Uplift (pilot-gated).** The front seat costs `base + P`. All other seats stay at `base`. A full car earns the driver `P` more.

In both modes the seat price goes to the driver in full. The platform earns only the booking fee `F` per seat, which exists because the booking is paid in the app.

## Worked example 1: Maruti Ertiga (7-seater), Indore → Bhopal, base ₹390, P = ₹100

| Seat | Flat today | Revenue-neutral | Uplift |
|---|---:|---:|---:|
| Front | ₹390 | ₹490 | ₹490 |
| Middle row, left window | ₹390 | ₹390 | ₹390 |
| Middle row, centre (saver, weight 1) | ₹390 | ₹370 | ₹390 |
| Middle row, right window | ₹390 | ₹390 | ₹390 |
| Back row, left (saver, weight 2) | ₹390 | ₹350 | ₹390 |
| Back row, right (saver, weight 2) | ₹390 | ₹350 | ₹390 |
| **Full car, driver total** | **₹2,340** | **₹2,340** | **₹2,440 (+4.3%)** |

## Worked example 2: Maruti Dzire (sedan), base ₹420, P = ₹60

| Seat | Flat today | Revenue-neutral | Uplift |
|---|---:|---:|---:|
| Front | ₹420 | ₹480 | ₹480 |
| Back left window | ₹420 | ₹420 | ₹420 |
| Back centre (saver) | ₹420 | ₹360 | ₹420 |
| Back right window | ₹420 | ₹420 | ₹420 |
| **Full car, driver total** | **₹1,680** | **₹1,680** | **₹1,740 (+3.6%)** |

## Why revenue-neutral can still raise driver earnings

The car is rarely full. Revenue-neutral pricing earns drivers more on most real rides because:

1. **The front seat sells first and sells at a premium.** On a ride with only 1–2 passengers, the front seat is almost always taken, so the driver collects `+P` without giving any saver discount.
2. **Cheaper saver seats fill seats that would otherwise go empty.** Budget riders who skipped a ₹390 back seat may book it at ₹350.

The downside appears when saver seats sell but the front seat doesn't. That is unlikely given the demand, but it is tracked as a guardrail.

## Platform economics (illustrative)

Platform revenue = paid in-app seat bookings × F.

| Assumption | Value |
|---|---|
| Seat bookings per month on pilot corridors | 100,000 |
| Share of bookings paid in app because of seat selection | 30% |
| Booking fee F | ₹15 |
| **Monthly platform revenue from pilot** | **₹4.5 lakh** |

Scale by replacing the first row with the platform's real volumes. The model is linear in both the in-app share and F, which are the two levers the experiment in doc 04 measures.

## Setting the premium band

- **Floor ₹0:** a driver can opt in only to get seat assignment, with no price difference.
- **Ceiling ₹150 (pilot):** keeps the front seat within about 40% of a typical base fare, close to the Uber Comfort premium range.
- Run a Van Westendorp survey (doc 01) before launch to set the ceiling per corridor.
