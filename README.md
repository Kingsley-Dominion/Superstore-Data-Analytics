# Superstore Sales & Profit Analytics Dashboards

**Tool:** Power BI
**Dataset:** Global Superstore (retail transactions across Consumer, Corporate, and Home Office segments, spanning Technology, Furniture, and Office Supplies categories, across seven global markets)

## Overview

This project breaks down retail performance across two connected dashboards — a **Sales Dashboard** tracking revenue and order volume, and a **Profit Dashboard** tracking profitability and priority-level performance. Together they move from "how much are we selling and to whom" to "where is that revenue actually turning into profit," which is the natural next question a stakeholder asks after seeing top-line sales numbers.

Both dashboards are filterable — the Sales Dashboard by customer segment (Consumer / Corporate / Home Office) and the Profit Dashboard by shipping mode (First Class / Same Day / Second Class / Standard Class) — so a viewer can isolate performance for a specific slice of the business without leaving the report.

---

## 1. Sales Dashboard -  Consumer Filtered

![Sales Dashboard](Image/superstore-sales-dashboard.png)

### Headline metrics
- **Sum of Sales:** 7M
- **Number of Orders:** 27K
- **Sold Quantity:** 92K

These three cards anchor the report — average order value works out to roughly $259.3K (7M / 27K orders), a useful benchmark to track over time or compare across segments.

### Chart breakdown

**Sales by Sub-Category** — a descending bar chart led by Phones (905K), Chairs (778K), Bookcases (765K), and Copiers (757K), tapering down to Fasteners (42K) and Labels (39K) at the bottom.
*Insight:* Revenue is concentrated in a handful of high-ticket sub-categories. The top four sub-categories alone account for a large share of total sales, which makes them the natural priority for inventory planning and promotional focus — while the long tail of low-volume items (Labels, Fasteners, Envelopes) contributes comparatively little and may not be worth heavy marketing spend.

**Sales by Categories** (donut) — Technology 37%, Furniture 33%, Office Supplies 30%.
*Insight:* The three categories are more evenly split than the sub-category chart suggests, meaning Technology's lead comes from a few standout sub-categories (Phones, Copiers) rather than category-wide dominance. This is a good example of why drilling from category into sub-category matters before making stocking decisions.

**Sales by Ship Mode** — Standard Class (3.9M) Second Class (1.3M), First Class (1.0M), and Same Day (0.30M).
*Insight:* Customers overwhelmingly default to the slowest, cheapest shipping option. This has two implications worth investigating further: either customers aren't price-sensitive enough to upgrade, or faster shipping isn't being marketed effectively at checkout — both are testable hypotheses for a follow-up analysis.

**Asian Region Yearly Sales** (2011–2014 line chart, split by Central / North / Southeast Asia) — all three sub-regions dip around 2013 (to roughly 49K-70k) before climbing steadily through 2014, with North Asia (95K) and Southeast Asia (80K) pulling ahead of Central Asia (65K) by the end of the period.
*Insight:* The shared 2012 dip across all three sub-regions points to a market-wide factor that year rather than a region-specific issue. The subsequent recovery is strongest in North Asia, which by 2014 is growing faster than its neighbors — worth flagging as the region to watch for continued investment.

**Sales by Market** — APAC leads at 1.8M, followed by EU (1.5M), US (1.2M), LATAM (1.1M), EMEA (0.4M), Africa (0.40M), and Canada (0.02M).
*Insight:* APAC and EU together account for close to half of total sales, while Canada is nearly negligible. This is the chart to check before any conversation about regional expansion or resource reallocation.

**Segment cards** (Consumer / Corporate / Home Office) — act as slicers, letting any of the charts above be filtered down to a single customer segment for comparison.

---

## 2. Profit Dashboard

![Profit Dashboard](Image/superstore-profit-dashboard.png)

### Headline metric - Standard Class Filtered

*Insight:* For Standard Class On its own, "50% of target" is a neutral number — its usefulness comes from pairing it with the sub-category and market breakdowns below to see which parts of the business are pulling that number up or down.

### Chart breakdown

**Profit by Order Priority** (donut) — profit splits across High, Medium, and Critical priority orders in shares of roughly 25%, 32%, and 43%.
*Insight:* Profit isn't evenly distributed across priority tiers — the largest single tier contributes more than half of total profit. Since order priority is often tied to customer type or fulfillment urgency, this is worth cross-referencing with segment data to see whether high-value customers cluster in a particular priority tier.

**Profit by Market** — APAC again leads (281K), followed by EU (230KK), US (164K), LATAM (132K), Africa (447K), EMEA (29K), and Canada at 8K.
*Insight:* This is the chart that reframes the sales story. EU sold nearly as much as APAC (0.92M vs 1.08M in sales) but generates noticeably less profit (230K vs 281K) — a sign of thinner margins in that market. Canada is the starkest case: it contributes real sales volume (0.02M) but essentially zero profit, which flags it as a market worth a margin investigation rather than a sales-volume push.

**Profit by Sub-Category** — led by Copiers (148.1K), Phones (139.K), and Bookcases (102.62K), but **Tables comes in at -36.08K** — the only sub-category losing money.
*Insight:* This is the single most actionable chart in the dashboard. Tables sell well enough to show up in the sales breakdown but actively lose money once costs are accounted for — a strong signal to review pricing, discounting, or supplier costs specifically for that sub-category rather than treating it as a normal underperformer.

**Asian Region Yearly Profits** (2011–2014) — North Asia peaks at 34.09K in 2014 before, while Central Asia mantains slight growth trend in 2013 (24.09K) and 2014 (26.91K), and Southeast Asia stays modest but positive throughout.
*Insight:* This directly complicates the sales-side takeaway. North Asia was the sales growth leader, but its profit is volatile and actually climaxed in 2014 even as revenue kept climbing — a classic sign that growth may be coming at the expense of margin (heavier discounting, higher fulfillment costs, or a shifting product mix). Central Asia's move into negative profit despite modest sales is worth a root-cause look.

**Top 3 Region by Profit** (donut) — Central Asia leads at 47%, with North Asia and South Asia each contributing 29% and 24% respectively.
*Insight:* Reinforces Central Asia's role as the top profit driver within the region, but the closeness of the other two shares shows profit is more evenly spread across North and South Asia than the raw sales numbers alone would suggest.

**Ship Mode filter** (First Class / Same Day / Second Class / Standard Class) — lets every chart above be recalculated for a single shipping mode, useful for testing whether the Standard Class's dominant sales volume is helping or hurting overall profit.

---

## Key Takeaways (Cross-Dashboard)

1. **Sales volume and profitability tell different stories.** APAC leads on both, but EU and EMEA sell well without translating that into proportional profit — margin, not volume, is the gap to close there.
2. **Tables is the one sub-category actively losing money** despite reasonable sales volume — the clearest, most specific action item in the entire analysis.
3. **North Asia's growth looks less stable once profit is considered** — strong and rising sales, but profit that peaked in 2013 and pulled back in 2014.
4. **Standard Class shipping dominates order volume**, which is worth testing against profit-by-ship-mode to see whether that preference is cost-neutral or eating into margin.

---

## How to reproduce

1. Load the Global Superstore dataset into Power BI Desktop.
2. Build the Sales Dashboard: KPI cards (Sum of Sales, No of Orders, Sold Quantity), bar charts for Sub-Category and Ship Mode, donut for Category split, line chart for Asian region trends, bar chart for Market, and segment slicer cards.
3. Build the Profit Dashboard: gauge for Profit Target, donut charts for Order Priority and Top 3 Region, bar charts for Market and Sub-Category, line chart for Asian region profit trends, and a Ship Mode slicer.
4. Apply consistent conditional formatting (gold/black theme for Profit, blue/grey theme for Sales) to visually distinguish the two reports at a glance.
