---
name: tianji-order-probability-analyzer
description: Tianji order probability and eCPM analysis method for Amazon ad slots, competitor comparison, 26-dimension listing/search-page analysis, time weighting, slot weighting, conversion likelihood, bid response, and optimization priority. Use when the user asks for 出单概率分析, 天机出单概率, eCPM拟合, 每次曝光价值, 坑位权重, 时间权重, 竞品实况分析, 营销力/信任力/产品力评分, 关键词出单概率, or how to decide bids from probability and competitor conditions.
---

# Tianji Order Probability Analyzer

## Purpose

Use this skill to estimate whether a keyword/slot/competitor situation is likely to produce orders and what action should follow. It translates search-page evidence, competitor strength, time window, slot weight, and eCPM logic into bid, Listing, pricing, and monitoring recommendations.

Read `references/source-order-probability.md` when the user needs the full 26-dimension scoring system, formulas, quick cards, or monitoring table designs.

## Required Context

Collect or infer:

- Keyword, marketplace, time window, and target slot.
- Our ASIN data: price, coupon, rating, review count, image quality, delivery, badges, rank, campaign metrics, conversion, CPC, ACOS/TACOS if available.
- Competitor set around the target slot.
- Current goal: win slot, hold rank, improve conversion, reduce waste, or choose whether to bid.

If metrics are missing, produce a qualitative probability grade and list the missing fields needed for numeric scoring.

## Scoring Structure

Score in four layers:

- Marketing power: search-page attractiveness such as image, title hook, price, coupon, badge, rating, review count, delivery, promo, brand signal, and visible differentiation.
- Trust power: review quality, rating stability, Q&A/review confidence, brand credibility, return risk, and detail-page support when available.
- Product power: functional fit, feature match, scenario match, attribute match, and competitor weakness.
- Competition proxy: visible competitor strength, slot density, sales/rank proxies, and promotion pressure.

Then adjust by:

- Time weight: current traffic/conversion window matters more than stale observations.
- Slot weight: top-of-search, video, product page, and organic positions have different expected value.
- eCPM fit: estimated exposure value should reflect CTR x CVR x selling price x a constant/proxy, adjusted by CPC and margin limits.

## Workflow

1. Define the target decision.
   - Decide whether the task is bid increase, bid decrease, slot attack, defense, Listing optimization, competitor response, or keyword rejection.

2. Capture evidence.
   - Compare our ASIN with nearby competitors on marketing power, trust power, product power, and competition proxy.
   - Note whether evidence comes from search page, detail page, ad metrics, keyword report, or manual observation.

3. Estimate order probability.
   - Use numeric scoring when enough data exists.
   - Use High/Medium/Low/Unknown when data is incomplete.
   - Explain the top positive and negative drivers, not just the final score.

4. Fit eCPM or exposure value.
   - Use known CTR, CVR, selling price, CPC, and conversion history when present.
   - If absent, state proxy assumptions and keep recommendations conservative.
   - Compare expected value with bid, CPC, margin, and target ACOS.

5. Map to action.
   - High probability + profitable economics: protect or raise bid, isolate exact term, hold slot.
   - High probability + weak visibility: test bid/placement support and monitor hourly.
   - Low probability + high cost: reduce bid, narrow match, improve Listing, or negative only if relevance is poor.
   - Strong competitor advantage: fix price/coupon/image/review gap before escalating spend.

## Output Format

Return:

- Decision summary: bid/hold/reduce/optimize/avoid.
- Probability grade and evidence drivers.
- Competitor comparison table.
- eCPM/exposure value notes.
- Optimization priority list.
- Monitoring follow-up and invalidation signals.

Use this table when useful:

| Dimension | Our ASIN | Competitor Signal | Score/Grade | Evidence | Action |

## Guardrails

- Do not fabricate CTR, CVR, CPC, rank, sales, or conversion data.
- Do not recommend bid increases when probability is weak or margin is unknown without stating risk.
- Treat competitor brand terms and trademark-sensitive targeting cautiously.
- Use `tianji-hourly-slot-monitor` when the user needs recurring snapshot cadence or monitoring tables rather than probability analysis.
