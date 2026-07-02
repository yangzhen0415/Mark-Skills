---
name: amazon-ad-strategy-playbook
description: Amazon advertising strategy playbook for selecting and combining ad tactics by product stage, advertising goal, budget level, category competition, keyword maturity, and profit target. Use when the user asks for 亚马逊广告打法, 广告策略选择, 打曝光, 打收录, 打排名, 打转化, 打首页首位, 控ACOS, 进攻防御, 打爆品, 打霸屏, 海王打法, 海量词收录, ASIN定向, 类目广告, 品牌词, 捡漏, 小语种/小众, 词根/特征词/属性词打法, 时间差打法, 全域流量打法, 前置否定, 搜索词拓词, 出单词分析, or wants an Amazon ad strategy map.
---

# Amazon Ad Strategy Playbook

## Purpose

Use this skill to choose an Amazon advertising strategy mix and turn it into an execution path. Focus on strategic selection and combination of打法, not report-based stop-loss or bulk operations. Use `amazon-ppc-stoploss` when the task is mainly about uploaded ad reports, wasted spend, negative keywords, bid cuts, or Bulk Sheet output.

Read `references/source-strategy-playbook.md` when the user asks for the full 27打法体系, decision tree, scoring systems, or detailed matrices. Read `references/source-ad-notes.md` for the short心得 version and condensed logic.

## Required Context

Collect or infer:

- Product stage: new launch, growth, mature, promotion, clearance, or relaunch.
- Primary goal: exposure, indexing, ranking, conversion, homepage/top-of-search, ACOS/profit, attack, defense, traffic expansion, or brand building.
- Budget level and acceptable ACOS/TACOS.
- Category competition intensity and brand/price/review moat.
- Available keyword state: core terms, search term history, competitor ASINs, Brand Analytics/ABA, or no keyword data.
- Listing readiness: title, image, price, coupon, reviews, CDQ/PQS/SCS/S3 risks when available.

If key inputs are missing, state assumptions and produce a first-pass strategy with evidence gaps.

## Workflow

1. Diagnose the ad objective.
   - Separate business goal from ad metric goal.
   - Identify whether the user needs traffic, indexing, rank, conversion, profit, attack, defense, or lifecycle scaling.

2. Match strategy families.
   - Basic objective tactics: exposure, indexing, ranking, conversion, top-of-search, ACOS control, attack, defense.
   - Traffic expansion tactics: hero product, screen domination, low-cost broad net, massive keyword indexing, related traffic penetration, ASIN targeting, category targeting, brand terms, low-bid漏斗, niche/small-language expansion.
   - Keyword refinement tactics: root/high-frequency words, feature terms, audience-scenario-attribute terms, time-gap traffic, variant/马甲, full-domain traffic, pre-negative traffic漏洞, search term expansion, converting-term feature analysis.
   - Tianji/boutique tactic: 3-6 core terms, slot monitoring, eCPM fit, CDQ/PQS/SCS/S3 support.

3. Build the strategy mix.
   - Choose one main tactic, two supporting tactics, and one protection tactic.
   - Define why each tactic is selected, what data supports it, and what would invalidate it.
   - Avoid stacking too many打法 at once; separate launch, validation, scaling, and profit stages.

4. Convert to execution.
   - Specify campaign type: SP auto/manual, SB, SBV, SD, ASIN targeting, category targeting, Store page, or off-Amazon support.
   - Specify keyword/target source, match type, campaign structure, budget priority, and observation window.
   - Define migration logic: broad/auto discovery -> phrase validation -> exact 1v1 scaling -> defense/profit control.

5. Set monitoring and exit criteria.
   - Use CTR/CVR/ACOS/TACOS/orders/rank/keyword indexed count/slot position as available.
   - Define when to increase bid, lower bid, isolate term, negative exact/phrase, pause, or move to the next stage.

## Output Format

Return:

- Strategy diagnosis: stage, goal, constraints, readiness risks.
- Recommended打法组合: primary tactic, support tactics, protection tactic.
- Campaign architecture: campaign/ad group/targeting/match type/budget priority.
- 7/14/30-day execution rhythm.
- KPI watchlist and decision rules.
- Missing data and assumptions.

For complex requests, include a compact table:

| Goal | Recommended打法 | Campaign Structure | Budget Priority | Observation Window | Success Signal | Stop/Adjust Signal |

## Guardrails

- Do not claim Amazon internal scoring facts unless the source data or reference explicitly supports them.
- Do not execute Seller Central changes; provide plans and reviewable actions only.
- Keep strategy separate from stop-loss execution; route report-heavy waste analysis to `amazon-ppc-stoploss`.
- Flag compliance-sensitive claims, trademark/brand targeting risks, and promotion plans that require margin confirmation.
