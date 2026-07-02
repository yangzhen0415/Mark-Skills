---
name: amazon-boutique-ad-execution
description: Amazon boutique advertising execution SOP for building staged campaign architecture around core keywords, auto discovery, manual 1v1 exact campaigns, ASIN targeting, category ads, video ads, Store subpage ads, search term transfer, and daily/weekly optimization. Use when the user asks for 精品广告打法, 凌空子广告SOP, 新品广告搭建, 核心词1v1, 自动广告探词, 手动精准广告, ASIN定投, 类目广告, 视频广告SBV, 品牌旗舰店广告, 搜索词筛选, STR转移, or staged Amazon ad execution.
---

# Amazon Boutique Ad Execution

## Purpose

Use this skill to turn a selected Amazon ad strategy into a staged campaign structure and operating SOP. This skill is execution-oriented: campaign architecture, core keyword selection, bid/budget setup, search term migration, and daily/weekly review rhythms.

Read `references/source-boutique-execution.md` for the complete精品广告 execution method and monitoring templates. Read `references/source-ad-sop.md` for the shorter standard SOP, KPI baselines, FAQ, and promotion-period routines.

## Required Context

Collect or infer:

- Product stage: D1-D30 launch, D31-D90 growth, D90+ mature, promotion, relaunch.
- Marketplace, price, margin/target ACOS, review count/rating, coupon/deal status.
- 5-10 core keywords or data sources for finding them: Brand Analytics/ABA, opportunity explorer, competitor reverse lookup, search term report.
- Current campaign structure, if any.
- Whether brand assets are available: Brand Registry, SB/SBV, Store page, video creative.

If core keywords are missing, first produce a core keyword selection SOP rather than a full campaign build.

## Workflow

1. Preflight Listing and keyword readiness.
   - Check title, images, price, coupon, reviews, stock, and core term relevance.
   - Select 5-10 core terms using demand, relevance, conversion likelihood, and competitor traffic overlap.
   - Group term roots and synonyms before campaign creation.

2. Build the four-layer structure.
   - Layer 1 auto ads: close match, loose match, substitutes, complements for discovery and ASIN harvesting.
   - Layer 2 manual core terms: 1 campaign x 1 ad group x 1 keyword x 1 match when precision matters; use exact for proven core terms and phrase/broad for expansion.
   - Layer 3 ASIN and category targeting: use converting ASINs, related competitors, category refinements, and defensive placements.
   - Layer 4 brand amplification: SBV and Store subpage ads when Brand Registry, creative, reviews, and budget are ready.

3. Set bids and budgets.
   - Allocate budget by stage: discovery and data collection early, exact/core ranking during growth, profit and defense during maturity.
   - Choose bidding strategy based on goal: fixed/down-only for control, up-and-down for ranking or high-confidence conversion pushes.
   - Keep budget hierarchy explicit so support campaigns do not starve core campaigns.

4. Operate search term migration.
   - Review search term reports weekly, or faster during launch/promo.
   - Classify terms into high-value, potential, waste, competitor, accessory/low-volume, and irrelevant.
   - Move high-value terms into 1v1 manual campaigns; negative irrelevant/waste terms with exact or phrase according to risk.

5. Manage stage rhythm.
   - Launch: build data foundation, indexing, and first conversion signals.
   - Growth: isolate winners, push rank, expand ASIN/category traffic.
   - Mature: control ACOS/TACOS, protect branded/core traffic, scale profitable terms.
   - Promotion: widen budget and monitoring, then clean structure and bids after the event.

## Output Format

Return:

- Campaign architecture table.
- Core keyword list and role assignment.
- Initial bid/budget plan and rationale.
- Daily 20-minute checklist and weekly 60-90 minute checklist.
- Search term migration and negative keyword rules.
- Stage-specific KPIs and adjustment triggers.

Use this campaign table when useful:

| Layer | Campaign Type | Target Source | Match/Targeting | Purpose | Budget Priority | Bid Logic | Review Cadence |

## Boundaries

- Do not directly change ads in Seller Central.
- Do not recommend aggressive bid scaling without margin, stock, and conversion readiness notes.
- Route pure wasted-spend report analysis and bulk negative generation to `amazon-ppc-stoploss`.
- If the user asks for hourly slot occupation and eCPM decisions, use or reference `tianji-hourly-slot-monitor` and `tianji-order-probability-analyzer`.
