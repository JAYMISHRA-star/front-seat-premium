# Front Seat Premium: seat selection for intercity carpooling in India

A product management case study. It proposes letting carpool passengers in India **choose their seat and pay a little more for the front seat**. Seats that riders avoid, such as the back-row centre seat, get cheaper.

> **Author:** Jay Mishra, MBA candidate, IIM Sirmaur
> **Type:** Independent student case study. Not affiliated with or endorsed by BlaBlaCar. All prices, volumes and rides are illustrative assumptions.

**Live prototype:** [open the interactive booking flow](prototype/index.html) (also published at https://claude.ai/artifact/VZGavNYVcZcYh23jWACjuf)

---

## The one-paragraph pitch

India has become BlaBlaCar's largest market, but the platform still earns no booking fee there ([TechCrunch, Oct 2025](https://techcrunch.com/2025/10/25/india-the-market-blablacar-once-walked-away-from-is-now-its-biggest)). Passengers already treat seats unequally. The front seat has legroom, a view and less motion sickness. The back-row centre seat has none of these. Yet every seat on a ride costs the same. **Seat selection** prices that difference openly and gives riders a reason to pay in the app. Each paid booking can then carry a small platform fee. By default the front-seat premium pays for the back-seat discounts, so a full car earns the driver the same as today and the ride stays a cost-sharing carpool.

## Where the idea came from

I drive on BlaBlaCar. Several passengers asked me, unprompted, whether they could sit in front, and some said they would pay more for it. That pattern is the starting hypothesis this case study tests.

## Project status

| Version | What it contains | Status |
|---|---|---|
| **v1: Hypotheses and design** | Problem framing, PRD, pricing model, metrics, risks, clickable prototype | ✅ Done |
| **v2: Customer validation** | Rider survey (target 100+ responses), 8–10 rider and 5 driver interviews, Van Westendorp pricing analysis | 🔄 In progress. See [research kit](research/) |
| **v3: Revised recommendation** | PRD and pricing band updated with real data; what changed and why | ⏳ Planned |

Numbers in v1 are assumptions. They will be replaced with survey results in v2, and the change log will show which hypotheses held up.

## What's in this repo

| Document | What it answers |
|---|---|
| [01. Problem and research](docs/01-problem-and-research.md) | Who wants the front seat, why, and what competitors do today |
| [02. Product requirements (PRD)](docs/02-prd.md) | Scope, user stories, flows, edge cases, what's out of scope |
| [03. Pricing model](docs/03-pricing-model.md) | Revenue-neutral vs. uplift pricing, worked examples, platform economics |
| [04. Metrics and experiment](docs/04-metrics-and-experiment.md) | North-star metric, guardrails, A/B test design, decision rules |
| [05. Risks and go-to-market](docs/05-risks-and-gtm.md) | Regulatory, safety and trust risks; phased rollout plan |
| [Prototype](prototype/index.html) | Clickable rider booking flow plus a driver pricing simulator |
| [Research kit](research/) | Google Form survey questions and interview guide for v2 |

## Key decisions at a glance

1. **Revenue-neutral by default.** The front premium is offset by saver-seat discounts. A full car pays the driver the same total. This keeps the ride a cost-sharing carpool rather than for-profit transport, which matters for regulation in India (see doc 05).
2. **Drivers opt in and set the premium** within a platform-set band (₹0 to ₹150 for the prototype).
3. **Seat choice requires paying in the app.** That is what unlocks a booking fee. The prototype assumes ₹15 per seat.
4. **Safety comes before revenue.** Any rider can switch to a back seat for free at pickup if they feel uncomfortable. The safety-switch rate is a guardrail metric.

## Market check: is anyone already doing this?

I found no major carpool or ride-hailing app that charges for the front seat specifically. That makes this an untested idea rather than a copy. The closest precedents are:

- **Airlines** charge for seat selection (front rows, extra legroom, aisle). That is the mental model the prototype borrows.
- **Uber Comfort** charges about 20–40% more for guaranteed legroom and a quieter ride ([Fortune, 2019](https://fortune.com/2019/07/09/uber-comfort-rides-legroom-quiet-driver/)).
- **BlaBlaCar's "Max. 2 in the back"** option (2016) let drivers promise a less crowded back seat, at no extra charge ([BlaBlaCar blog](https://blog.blablacar.com/newsroom/news-list/ridesharing-comfy)).
- **BlaBlaCar in Europe** charges a service fee of roughly 16–20% of the passenger price ([BlaBlaCar legal](https://legal.blablacar.com/en-gb/service-fee/)).

## How to view the prototype locally

Download the repo and open `prototype/index.html` in any browser. It has no build step and no dependencies.

## License

Text and code are released under the MIT License (see [LICENSE](LICENSE)). "BlaBlaCar" is a trademark of its owner and is used here only to describe the context of the case study.
