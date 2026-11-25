# ScraperAPI pricing: what does each plan cost, which tier does your volume need, and how many credits does a page really burn? (all 7 plans in one table)

ScraperAPI costs **$49 to $1,975 a month** across six self-serve tiers, plus an Enterprise tier quoted per contract. Annual billing takes exactly 10% off each of them, so the cheapest plan lands at $44.10/month and the largest at $1,777.50/month. Most readers end up choosing **Startup at $149/month**; once they need country targeting outside the US and EU, they move to **Business at $299/month**.

Your monthly bill depends less on the subscription line than on the credit multipliers attached to each request. A JavaScript-rendered page consumes ten times what a plain HTML page does, and a Google search consumes twenty-five times. Below you'll find the full plan table, what a credit actually buys, the real cost per 1,000 pages once multipliers are applied, and the workloads where this product is the wrong purchase.

> **Short version:** scraping mostly plain HTML up to about 1,000,000 pages a month → **Startup, $149/month** (1M credits, 50 threads). You need country-level targeting outside the US and EU, or 3M credits → **Business, $299/month**. Neither tier sells overage, so oversize deliberately.
> 👉 [See all seven ScraperAPI plans and current prices](https://www.scraperapi.com/pricing/?fp_ref=coupons)

## All ScraperAPI plans and prices

| Plan | Monthly / annual (per month) | Credits per month | Concurrent threads | Geotargeting | Link |
| --- | --- | --- | --- | --- | --- |
| Hobby | $49 / $44.10 | 100,000 | 20 | US & EU only | [ View plan](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Startup | $149 / $134.10 | 1,000,000 | 50 | US & EU only | [ View plan](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Business | $299 / $269.10 | 3,000,000 | 100 | Global, country-level | [ View plan](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Scaling (Most Popular) | $475 / $427.50 | 5,000,000 | 200 | Global, country-level | [ View plan](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Professional | $975 / $877.50 | 10,500,000 | 300 | Global, country-level | [ View plan](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Advanced | $1,975 / $1,777.50 | 21,500,000 | 500 | Global, country-level | [ View plan](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Enterprise | Custom | 22,000,000+ | 500+ | Global, country-level | [ View plan](https://www.scraperapi.com/pricing/?fp_ref=coupons) |

Every tier ships the same feature set: JS rendering, premium residential and mobile IPs, anti-bot bypass, JSON autoparse, rotating proxy pools, CAPTCHA handling, custom headers, automatic retries, unlimited bandwidth (you pay per request, not per gigabyte) and a 99.9% uptime guarantee. What changes is volume, thread count, geotargeting and analytics history (30 days on Hobby and Startup, unlimited from Business up). Pay-as-you-go is a Scaling-and-above feature; on the three cheapest tiers, running out of credits simply stops your scraping.

## One credit is not one page

A standard page request costs 1 credit. ScraperAPI's own documentation prices harder targets above that base rate: Amazon at 5 credits, Google and Bing including subdomains at 25, LinkedIn at 30. When ScraperAPI has to defeat Cloudflare, DataDome or PerimeterX protection, it adds 10 credits on top of whatever the base cost was.

Two independent pricing trackers also list parameter-level multipliers that the domain table doesn't show: `render=true` (JavaScript rendering) at 10 credits, `premium=true` (residential or mobile IPs) at 10 credits, and both together at 25. Pass `country_code`, `session_number`, `device_type`, `output_format` or `autoparse` and nothing extra is charged.

Run the arithmetic and the allowance on the box shrinks fast:

- **Hobby, 100,000 credits.** Amazon products at 5 credits each → 20,000 pages a month. The same allowance on a Cloudflare-protected page (1 + 10 = 11 credits) → roughly 9,000 pages.
- **Startup, 1,000,000 credits.** 1M plain pages, or 100,000 JavaScript-rendered pages, or 40,000 Google searches.
- **Scaling, 5,000,000 credits.** 1,000,000 Amazon product pages a month, per ScraperAPI's own worked example.

Switching plans doesn't change any of this. The multiplier is a property of the target site and the parameters you send, so a Professional subscription still pays 25 credits for a Google result.

Two controls keep the bill predictable. The Domain Cost Estimator in the dashboard returns the exact credit cost for any URL before you commit a crawl, and the `max_cost` parameter caps spend on a single request. Use both on unfamiliar domains; a site that looks like plain HTML can turn out to sit behind bot protection once you hit it at volume.

## What 1,000 pages actually cost on each plan

These figures assume the plan is used to its full credit allowance and billed monthly. They are derived from the credit multipliers above, and a third-party pricing study published them in exactly this form.

| Plan | Monthly | Plain HTML | JS rendering | Premium proxy | JS + premium |
| --- | --- | --- | --- | --- | --- |
| Hobby | $49 | $0.49 | $4.90 | $4.90 | $12.25 |
| Startup | $149 | $0.15 | $1.49 | $1.49 | $3.73 |
| Business | $299 | $0.10 | $1.00 | $1.00 | $2.49 |
| Scaling | $475 | $0.10 | $0.95 | $0.95 | $2.38 |
| Professional | $975 | $0.09 | $0.93 | $0.93 | $2.32 |
| Advanced | $1,975 | $0.09 | $0.92 | $0.92 | $2.30 |

Plain HTML settles around $0.09 to $0.15 per 1,000 pages from Startup upward, which is competitive. Rendered and protected pages cost 10 to 30 times that, and this gap explains most complaints about ScraperAPI being expensive. If your targets need rendering on every request, price the job on the JS column, not the plain one.

One structural trap is worth planning around. Say your crawl needs 1.1M credits a month. Startup gives you 1M credits for $149, and you need roughly 10% more than that. Hobby, Startup and Business have no overage, so the only move is Business at $299, close to double the bill for a small volume increase. Either trim the crawl (turn rendering off for pages that don't need it, set `max_cost` on the expensive domains) or budget for Business from the start.

## Free trial, free plan, refunds, and running out of credits

New accounts get **5,000 credits for 7 days with no credit card required**, which is enough to test success rates against your actual targets rather than a demo site. After that there's a permanent free plan: 1,000 credits a month and up to 5 concurrent connections. In practice that's 1,000 plain pages or 100 rendered ones, so it works for a script you run occasionally and not much else.

Paid plans carry a **7-day no-questions-asked refund**; email support within the window and the charge is reversed. You can cancel from the dashboard at any time and cancellation itself is free. If you cancel mid-cycle, remember that credits reset at each renewal and unused ones don't carry over, so there's no point banking allowance for a big crawl next month. Annual subscribers can renew early to refresh the credit balance.

Running out behaves differently depending on tier. On Hobby, Startup and Business, requests beyond the allowance come back as a 429 and scraping pauses until renewal. Nothing is auto-charged. Auto-upgrade is opt-in on Hobby through Professional and moves you to the next tier when credits hit zero. Pay-as-you-go, billed at a fixed per-credit rate with a monthly cap you set, exists only on Scaling, Professional, Advanced and Enterprise. Exceeding your concurrency limit also returns a 429, and those requests are rejected rather than queued, with no extra charge.

👉 [Start the 7-day, 5,000-credit trial without a card](https://dashboard.scraperapi.com/signup?fp_ref=coupons)

## Which plan fits your workload

1. **Evaluating, or running a small side script.** Stay on the free plan. 1,000 credits covers 100 rendered pages, which is enough to see whether your targets get through.
2. **Plain HTML or light parsing, under 1M pages a month.** Startup at $149. It's the first tier where the per-page cost drops to $0.15 per 1,000, and 50 threads handle most mid-sized crawls.
3. **About 100,000 JavaScript-rendered pages a month.** Startup again, exactly. 1M credits ÷ 10 = 100,000 rendered pages. Cross that line and the next tier is Business at $299, so keep rendering scoped to the pages that need it.
4. **You need to appear as a user in Germany, Japan or Brazil.** Business at $299 is the floor. Hobby and Startup limit geotargeting to the US and EU, and nothing below Business changes that.
5. **You expect to exceed the allowance most months.** Scaling at $475, because it's the cheapest tier with pay-as-you-go. Buying a lower tier and upgrading reactively costs more than starting where overage is available.

Hobby at $49 exists for people who want a paid plan without committing to $149, and it's the most expensive per page of the six. For 100,000 plain pages it works out to $0.49 per 1,000 against Startup's $0.15.

👉 [Check what Startup and Business include before you pick](https://www.scraperapi.com/pricing/?fp_ref=coupons)

## When ScraperAPI is the wrong purchase

If most of your requests hit JavaScript-heavy or bot-protected pages, the multipliers do the talking. At 100,000 rendered pages a month, ScraperAPI's $149 works out to $1.49 per 1,000, which is 50% above the $0.995 median across the ten APIs a third-party study priced for that load. Seven of the other nine came in cheaper, with Oxylabs Web Scraper API at $140/month and Bright Data Web Unlocker at $150/month nearest on either side; the cheapest option in that comparison was $99/month. Across 16 workloads (four volumes × four page types), that same study found ScraperAPI cheapest in none, with a best placing of fourth of ten for 1M plain HTML pages a month.

Sustained Google or LinkedIn scraping pushes costs higher still, at 25 and 30 credits per request. And there is no published ScraperAPI plan sized for 1,000,000 protected pages a month, so that workload requires a custom quote.

Two other gaps show up in third-party reviews. ScraperAPI picks countries, sessions and IP tiers but not specific IPs, ASNs or cities; buyers who need city-level targeting are better served by a raw proxy provider. And if you want finished scrapers plus somewhere to run them, Apify's platform model starts at $19 (Starter, including $19 of usage) against ScraperAPI's $49 entry, with 83,000+ ready-made Actors in its store. ScraperAPI makes sense when you already have working code and want a fetch-and-unblock layer underneath it.

## FAQ

**How many credits does the free plan include?**
1,000 credits a month with a maximum of 5 concurrent connections. That's 1,000 plain pages or 100 JavaScript-rendered pages. Separately, new accounts get a 7-day trial with 5,000 credits and no card.

**Do unused credits roll over?**
No. The balance resets at every renewal date. If your usage is uneven across the year, that favors monthly billing over annual, or an early annual renewal when a big crawl is coming.

**Will I be charged automatically if I go over?**
Not on Hobby, Startup or Business. Those tiers return a 429 and pause scraping, with no overage charge. Pay-as-you-go, which bills beyond the allowance at a fixed per-credit rate under a cap you set, starts at Scaling ($475). Auto-upgrade to the next tier is opt-in on Hobby through Professional.

**How much does annual billing save?**
Exactly 10% on every standard plan. Hobby drops to $44.10/month, Startup to $134.10, Business to $269.10, Scaling to $427.50, Professional to $877.50 and Advanced to $1,777.50. No code is involved; the discount applies at the plan level.

**Can I target countries outside the US and EU on a cheap plan?**
No. Hobby and Startup are restricted to US and EU geotargeting. Country-level targeting anywhere in the world starts at Business, $299/month.

**Can I cancel anytime?**
Yes, from the dashboard. Cancellation carries no fee, and paid plans are covered by a 7-day refund policy.

## Before you enter a card number

Match the tier to the page type, not to the credit number on the box. Plain HTML under a million pages → Startup $149. About 100,000 rendered pages → also Startup. Country targeting beyond the US and EU, or 3M credits → Business $299. Repeated overage → Scaling $475, the cheapest tier with pay-as-you-go.

Then confirm two things before checkout. First, run your actual target URLs through the Domain Cost Estimator inside the dashboard during the free trial; the estimator's per-URL number beats any table, including this one, because it accounts for the specific domain and parameters you'll send. Second, decide which geotargeting tier you genuinely need, since that single requirement is what pushes most buyers from $149 to $299.

👉 [Open the pricing page and pick the tier your page count lands in](https://www.scraperapi.com/pricing/?fp_ref=coupons)
