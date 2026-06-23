# <i> Social Media User Engagement Analysis Dashboard </i>
![1000166608](https://github.com/user-attachments/assets/a1e2a50c-1c07-4708-a469-5cfda534c612)

This Power BI report analyzes **5,000 viral social-media posts** across 4 platforms, 8 regions, 6 content formats and 10 hashtags to help brands understand reach, engagement composition and audience behaviour. The 2025 revision **re-engineers the model's aggregations, corrects a metric-labelling error in the original report, and rebuilds the canvas as a 3-page executive dashboard** with verified, decision-grade insights.

---

<br>

<div align="center">

![License](https://img.shields.io/badge/License-MIT-blue.svg) 
![Power BI](https://img.shields.io/badge/Power%20BI-Analytics-blue?style=flat&logo=powerbi)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow?style=flat&logo=powerbi&logoColor=black)


</div>

<div align="center">

### Designed and Analyzed by a Power BI Data Analyst

<br>

<img src="https://github.com/user-attachments/assets/8b171aa9-2d34-4fb5-9f1e-c813e999228b" width="250"/>

<br>
<br>

[![Credly Badge](https://img.shields.io/badge/View-Certificates-orange?)](https://www.credly.com/users/haroon-k-m)



**Skills**  

Microsoft Power BI · Data Modeling · Dashboards · Data Analysis · Data Storytelling · Business Intelligence (BI) · Statistical Data Analysis

</div>

<br>

---

<video src="https://github.com/user-attachments/assets/4e9cbe04-1b9c-46b3-9f52-886cea898ea9" controls width="350"></video>

<br>

## What's new in this revision

> **The headline fix — counts were being charted as totals.**
> The original report aggregated every metric with **`Count` (CountNonNull)** instead of **`Sum`**. So "Shares by Platform = 1,324" was never 1,324 shares — it was the *number of YouTube posts*. All four metric charts displayed the same four numbers (1,324 / 1,260 / 1,212 / 1,204), i.e. the post count per platform, not engagement. Re-aggregated to true sums, the story changes completely.

| Metric | Original report (mislabelled) | Corrected total |
| --- | --- | --- |
| Total Views | "1,324" (post count) | **12.47 B** |
| Total Likes | "1,324" (post count) | **1.26 B** |
| Total Shares | "1,324" (post count) | **252.6 M** |
| Total Comments | "1,324" (post count) | **124.4 M** |
| Engagement Rate | — | **13.1 %** |

Other upgrades:
* **Correct aggregations** — `Sum` for totals, `Average` for per-post performance, `Count` only where a count is actually meant.
* **A 3-page executive design** — Overview → Platform & Content deep-dive → Audience, Hashtags & Findings — on a clean, MNC-grade "Executive Light" theme with KPI cards, a consistent accent palette and cross-filtering.
* **Honest, verified storytelling** — every figure below was computed twice with independent engines (Python and PowerShell) and reconciled to the unit.

---

## Dashboard at a glance

**Page 1 · Executive Overview** — 6 headline KPIs, Total Views by Platform, Engagement Mix (Likes/Shares/Comments) by Platform, Engagement-Level split, Total Views by Region and Avg Views per Content Format.

**Page 2 · Platform & Content** — per-post normalisation: Avg Views & Avg Likes per post by platform, post-volume mix, the Platform × Content-Format matrix, and avg engagement by format.

**Page 3 · Audience, Hashtags & Findings** — real view share by region, top hashtags by reach, the engagement-label paradox, and an analyst's note.

---

# Corrected Analytics

## 1. Engagement totals (the corrected KPIs)
* The platform earns **12.47 billion views, 1.26 billion likes, 252.6 million shares and 124.4 million comments** across 5,000 posts.
* Combined engagement (likes + shares + comments) is **1.63 billion**, an **overall engagement rate of 13.1 %** of views.

## 2. Reach by Platform — volume, not virality
* On **totals**, YouTube leads (3.37 B views) ahead of TikTok (3.17 B), Twitter (3.02 B) and Instagram (2.91 B) — **but only because YouTube carries the most posts (1,324 vs ~1,210).**
* On a **per-post** basis the platforms are nearly identical: **2.40 M – 2.55 M views per post** (a spread of just ±3 %). Channel choice barely moves per-post reach.
* **Instagram is the efficiency leader:** the highest engagement rate (**13.8 %**) and the highest average likes per post (257 K), despite near-fewest posts.

## 3. Engagement Mix by Platform
* Likes dominate the engagement profile on every platform (~77 % of engagement), followed by shares (~16 %) and comments (~7 %).
* The mix is remarkably stable across platforms — there is no channel where users disproportionately *comment* or *share* rather than like.

## 4. Content Format Performance
* All six formats land within **2.47 M – 2.53 M average views** — **Reel** is marginally strongest (2.53 M) and **Post** weakest (2.47 M), a ~2 % gap.
* Practical read: format selection is not a meaningful reach lever in this dataset; cadence and targeting matter more.

## 5. Views by Region — the corrected leaderboard
* The original pie charted **post counts**, not view sums — and its narrative mislabelled the regions: it credited "Germany" with the top 13.54 %, but **13.54 % is actually the USA's share of *posts*** (Germany in fact has the *fewest* posts, 566).
* Ranked correctly by **total views**, the leader is the **USA (14.1 % of all views, 1.76 B)**, then Brazil (13.2 %), the UK (13.0 %) and Canada (12.9 %); Japan is last (11.5 %).
* Regional **engagement rates are statistically flat** (12.4–13.8 %, a 1.3-point spread that is indistinguishable from chance, permutation *p* ≈ 0.21) — there is no "high-engagement market" to target in this data.

## 6. Hashtags
* By **total reach**, **#Fitness** (1.39 B views) leads — but mostly because it carries the most posts (536). Per-post reach differs by only ~7 % across all ten hashtags.
* Apparent "like magnets" such as **#Education** and **#Tech** (~260 K avg likes) sit **within sampling noise** (*p* ≈ 0.92): no hashtag reliably out-performs another on a per-post basis.

## 7. The Engagement-Level paradox
* Posts manually tagged **"High"** engagement actually average **fewer views (2.45 M)** than **"Medium" (2.53 M)** or **"Low" (2.51 M)** posts.
* The categorical `Engagement_Level` flag is therefore **decoupled from real reach** and should not be used to prioritise content.

---

# Analyst's Note — methodology & data quality
* **Independent verification.** Every aggregate was computed with two independent engines (Python `csv` and PowerShell `Measure-Object`) and reconciled to the unit.
* **The metrics are statistically independent.** Pairwise correlations between Views, Likes, Shares and Comments are all within **|r| < 0.02** — knowing one metric tells you nothing about another.
* **Signature of synthetic data.** Views are near-uniform: mean (2.494 M) ≈ median (2.497 M), and the standard deviation (1.459 M) ≈ range ÷ √12. Combined with the zero correlations and the flat per-segment averages, this dataset behaves like **independently-sampled random values**, so "what makes a post go viral" is effectively a coin-flip here.

## Recommendation
Treat reach in this dataset as **volume-led**: scale posting cadence rather than chasing a "best" format, hashtag or market — per-post performance is statistically flat. The one real efficiency edge is **Instagram (13.8 % engagement rate; the platform-rate spread is significant at *p* ≈ 0.02, unlike the regional one)**, and **ignore the `Engagement Level` label** for prioritisation — it does not track actual performance.

---

> **Files** — `source/Users_Analysis.pbix` (redesigned report) · `source/Users_Analysis_v1_original.pbix` (original, preserved) · `source/Viral_Social_Media_Trends.csv` (dataset).
