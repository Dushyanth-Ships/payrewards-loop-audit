# pay.com.au Rewards Loop Audit

An outside-in product audit of PayRewards, pay.com.au's B2B rewards programme. It covers how the earn, burn, yearn loop works today, where it may leak, which engagement levers I would test first, and what I would measure before building anything.

**[Read the full audit (PDF, 3 pages)](./pay-com-au-rewards-loop-audit.pdf)**

Built with Claude from public sources, October 2026. No account was opened and no customer data was used.

---

## The problem

pay.com.au describes its business as an earn, burn and yearn cycle: the more customers earn and redeem points, the more they want to keep using the platform. The company has said publicly that speeding up that cycle depends on onboarding and engagement.

The question this audit asks: **which mechanics would actually change how often a business pays through the platform, and which would just be decoration?**

## Key insight

Earning PayRewards is a paid choice made on every payment (no points, 1 point per $1 for a 1.0% fee, or 2 points per $1 for 1.8%). Enrolment is automatic; the decision to earn is not. So the loop depends on that per-payment decision as much as on redemption.

## Where the loop may leak

1. **The earn decision is a cost decision.** Skip the points package on enough bills and the balance barely moves.
2. **Payment rhythm is lumpy.** BAS, payroll, super and rent run monthly or quarterly, so reasons to engage are far apart.
3. **The first redemption can be far away.** Newer and smaller customers may not complete the loop for months.

## Levers, ranked

| Lever | Call |
| --- | --- |
| Goals, with progress shown at the moment of the earn decision | Test first |
| Challenges to move a new bill type onto the platform | Test first |
| Lifecycle journeys keyed to the tax calendar and points expiry | Test first |
| Personalised transfer offers | Test next |
| Referral prompt at the moment of redemption | Test next |
| Tiers (risk of a second ladder alongside existing plans) | Reframe |
| Streaks (don't fit monthly and quarterly bills) | Likely noise |

## What I would measure first

- Points attach rate per payment, goal-setters against everyone else
- Bill categories paid per business, 90 days after a challenge
- 12-month retention, by whether a business redeemed in its first 90 days
- Accounts with no earn or redeem activity for 6+ months
- Median days between payments, by plan and business size

## Two markets

pay.com.au launched in the US as PayRewards in August 2026. The audit covers what has to change between markets (fee model, tax calendar, partner catalogue) and proposes one engine per mechanic with market-specific settings.

## How I worked

- Read pay.com.au's site, help centre and pricing, its Salesforce customer story, and the August 2026 US launch release.
- Used Claude for research, synthesis and drafting, then checked every factual claim against its source.
- Named the unknowns (attach rates, time to first redemption) as questions to answer with internal data, rather than guessing numbers.

## Sources

- [PayRewards FAQs: earn rates, fees, expiry](https://help.pay.com.au/hc/en-au/articles/15109240686351-PayRewards-FAQs)
- [pay.com.au pricing plans](https://www.pay.com.au/?p=1720)
- [pay.com.au guide: maximising PayRewards](https://pay.com.au/guides/the-power-of-points-top-tips-for-maximising-your-payrewards-points/)
- [Salesforce customer story: pay.com.au](https://www.salesforce.com/au/customer-stories/pay-com-au/)
- [PR Newswire, 24 Aug 2026: US launch as PayRewards](https://www.prnewswire.com/news-releases/paycomau-australias-largest-business-rewards-platform-raises-us28m-to-launch-in-the-us-as-payrewards-302857628.html)

---

Dushyanth K G · [dushyanthkg@gmail.com](mailto:dushyanthkg@gmail.com) · [LinkedIn](https://www.linkedin.com/in/dushyanth-k-g-410504103)
