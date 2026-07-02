---
name: tianji-hourly-slot-monitor
description: Tianji Amazon ad slot monitoring SOP for hourly tracking of SP regular, SP recommended, SB/SBV, natural rank, competitor changes, slot occupation, bid response, ranking drops, ACOS spikes, competitor product-page ads, and core keyword traffic interruptions. Use when the user asks for 天机打法, 每小时监控, 坑位监控, 坑位快照, SP坑位, SBV坑位, 自然位监控, 核心词排名监控, eCPM调竞价, 排名突然掉位, ACOS突然飙升, 竞品铺广告, or Amazon ad slot monitoring templates.
---

# Tianji Hourly Slot Monitor

## Purpose

Use this skill to design and operate a Tianji-style hourly slot monitoring routine for Amazon core keywords. The focus is observing ranking/slot movement, competitor behavior, and immediate bid or Listing response rules. For probability scoring and detailed eCPM math, pair with `tianji-order-probability-analyzer`.

Read `references/source-hourly-monitor.md` when the user needs full monitoring templates, exact phase timing, abnormal-case SOPs, or dashboard fields.

## Required Context

Collect or infer:

- Marketplace and time zone; default monitoring logic should note the marketplace time zone.
- Product ASIN, 3-6 core keywords, target competitors, and campaign names if available.
- Current rank/slot baseline, ad type coverage, bid/budget status, ACOS/TACOS, price, coupon, review state.
- Monitoring capacity: hourly, every 2 hours, daily snapshots, or temporary promotion watch.

If the user lacks core keywords, start with a core keyword selection pre-step.

## Slot Definitions

Track at least:

- SP regular search ad slot.
- SP recommended/special placement if visible.
- SB/SBV top or video slot when eligible.
- Natural organic rank.
- Nearby competitors: price, coupon, rating, review count, badge, image appeal, promo, delivery, and ad density.

## Workflow

1. Phase 0: preflight.
   - Confirm Listing readiness, core terms, campaign structure, budget, and monitoring tool/source.
   - Establish baseline snapshots before major bid changes.

2. Phase 1: set monitoring schedule.
   - Use hourly monitoring for launch, ranking attack, promotion, or volatile terms.
   - Use lighter daily snapshots for stable mature terms.
   - Record local time and marketplace time so time-window effects are visible.

3. Phase 2: capture each snapshot.
   - Search keyword in a consistent environment.
   - Record SP/SB/SBV/natural positions, own visibility, competitor changes, price/promo badges, and obvious ranking shocks.
   - Note whether ads are missing because of budget exhaustion, low bid, relevance, campaign status, or search volatility.

4. Phase 3: map slot data to action.
   - If target slot is lost but conversion quality is healthy, consider bid or budget support.
   - If slot is held but ACOS rises, inspect conversion, price, coupon, competitors, and term relevance before increasing bid.
   - If natural rank rises after paid slot stability, preserve the structure and reduce only carefully.
   - If ad slot disappears repeatedly, check budget exhaustion, campaign status, relevance, or competitor bid pressure.

5. Phase 4: handle exceptions.
   - Ranking drop: compare ads visibility, natural rank, competitor changes, stock, price, review, coupon, and category shifts.
   - ACOS spike: separate CPC inflation, CTR drop, CVR drop, irrelevant traffic, and competitor promotion.
   - Competitor product-page ads: decide defense, ASIN targeting, coupon/price response, or Listing strengthening.
   - Core term traffic interruption: check campaign status, budget, bid, eligibility, relevance, and search result page changes.

## Output Format

Return:

- Monitoring plan: keywords, slots, frequency, time windows, owner, tools.
- Snapshot table fields.
- Decision matrix for bid/budget/Listing/competitor responses.
- Daily summary template and weekly trend view.
- Exceptions and escalation rules.

Use this snapshot table when useful:

| Time | Keyword | Own SP Slot | Own SB/SBV Slot | Natural Rank | Top Competitors | Price/Coupon Changes | Action | Evidence |

## Guardrails

- Do not treat one snapshot as proof; require repeated signals or explain that evidence is weak.
- Do not raise bids blindly when Listing conversion, margin, or stock is weak.
- Keep observation separate from execution; provide reviewable bid and budget suggestions only.
- Flag data collection bias from personalization, location, browser state, and time zone.
