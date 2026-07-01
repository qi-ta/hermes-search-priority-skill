---
name: priority-source-search-pro
description: "Professional Edition: Rigid, strict, and maximum risk control. Ideal for commercial vendor selection, API integration decisions, freelance delivery, and technical architecture finalization. v2.2 Ultimate"
---

# 🛡️ AI Search Priority Skill v2.2 (Professional Edition)

## ⚠️ Skill Routing Arbitration Rule (Pre-loading Check for Agent)

**This File (Professional):** Applicable to high-risk scenarios involving financial transactions, selling tutorials, freelance delivery, commercial vendor selection, or API integration. If a task contains ANY monetization/delivery attribute, this version MUST be used unconditionally, even if the action is merely "researching."

**Fallback to Standard:** For pure daily learning and information gathering without monetization intent, switch to the Standard Edition to enhance response flexibility. When uncertain, default to Pro; better safe than sorry.

## 🎯 Core Positioning

A rigorous, engineered retrieval specification designed specifically for high-risk decision-making, commercial vendor selection, and technical implementation. Through mandatory budget control, counter-evidence search, echo chamber detection, and compliance blocking, it eliminates "confirmation bias" and "hallucinations," ensuring commercial-grade reliability.

## 📜 I. Ironclad Rules: Cross-Domain Risk Control

### Hard Budget Control & Hybrid Task Routing

| Rule | Details |
|:---|---:|
| Total Budget Cap | Max ≤ 8 calls per task. Timeouts/5xx errors do not count; auto-switch to backup source on 429. |
| Hybrid Task Allocation | For multi-intent tasks: Primary intent gets 5 calls, secondary gets 3 calls. Strictly forbid equal distribution. |
| Intent Arbitration | Default priority when not explicitly stated: A > B > D > E > C. Strictly follow user's explicit instructions if provided. |

### Dual-Source Verification & "Echo Chamber" Detection

| Rule | Details |
|:---|---:|
| Mandatory Dual Sources | Core conclusions require verification from at least two independent sources. L1 sources are exempt. |
| Echo Chamber Detection | If ≥3 articles share identical data/logic (indicating syndicated/copied content) → Count as only 1 independent source. Deduplicate instantly at each tier. |
| Same-Tier Sorting | Multiple sources within the same tier must be sequenced using a/b/c. |

### Commercial License Second-Hand Risk Blocking

For Type A (Assets) and Type B (Code) tasks, extracting the license agreement is mandatory.

🚨 **Fatal Constraint:** If License information is obtained from L4/L5 second-hand narratives rather than confirmed via L1/L2 official original text → Mandatory labeling:
> [License: Unverified, second-hand information risk exists. Must review original agreement before use.]

Strictly forbidden to directly label as "Commercial Use Allowed".

### Engineering Safeguards

| Rule | Details |
|:---|---:|
| Context Overload Prevention | For large GitHub repos, prioritize reading only README.md/docs index. Read specific single files only when necessary. |

### Strict Timeliness Rules

| Type | Rule |
|:---|---:|
| Model Versions / API Pricing / Toolchains (>90 days old) | Mandatory label: "Recommend verifying for updated versions." |
| Line D (Vendor Selection) | Must query real-time pricing. Cached/historical prices are strictly forbidden. |
| Line E (Tutorials) | If Deprecated/Legacy is encountered → Force downgrade to L2 to find alternatives. |

### Fallback When Nothing is Found

If all tiers are exhausted with no results → Directly reply "No reliable sources found." No fabrication, no forced compromises.

## ⚙️ II. Strict Execution Workflow (4-Step Method)

### Step 0: Version Anchoring

For version-dependent queries, if no version is provided, prioritize asking for clarification, or default to the latest L1 stable version and explicitly label it.

### Step 1: Determine Task Type & Satisfaction Threshold

| Type | Satisfaction Condition (Stop Immediately & Save Budget) |
|:---|---:|
| A: Asset Models | 1 L1 Model + 1 L3 Workflow = Met |
| B: Tech Code | L1 Official Docs + Runnable Code Example = Met |
| C: Info Trends | 1 L2 Public Data + 1 L3 Creator Review = Met |
| D: Pitfall Selection | Real-time Pricing + Performance Benchmark + 1 L4 Authentic Feedback = Met |
| E: Tutorial Materials | L1 Official Docs + L2 Parameter Specs + L3 FAQ Summary = Met |

**Stop immediately upon reaching the satisfaction condition.**

### 🛡️ Step 2: Conditional "Counter-Evidence Search" (Preventing Confirmation Bias)

| Item | Rule |
|:---|---:|
| Trigger Condition | Triggered ONLY when Lines A/B/D contain decision-making intents. Lines C/E do not trigger. |
| Execution Action | Force consume 1 budget call to search: `[Core Object] + (pitfall / fail / error / flaw / rate limit)` |
| Secondary Intent Limit | Does not trigger independently. If doubtful, label: "No dedicated counter-evidence search conducted; secondary verification recommended." |

### Step 3: Standardized Output Format (Strict Template)

```markdown
💡 TL;DR (Risk-First Version)
(Max 50 words. Prioritize disclosing core risks/license limits/counter-evidence flaws, then provide the conclusion.)

📊 Core Conclusions & Source List
[Conclusion Summary]
   Source: [URL] | Tier: [L?] | Reliability: [High/Med/Low] | License: [Commercial/Personal Non-Commercial/Requires Auth/Unverified]
  Note: Multiple same-tier sources sorted by a/b/c.

⚠️ Conflict Notes & Counter-Evidence Warnings
[Contradictions between L1 and community / Fatal flaws from counter-evidence / Echo chamber detection results / Warnings for unverified secondary intents]

🔍 Search Strategy Retrospective
Actual Keywords Used: [Including search term reconstruction logs]
Retrieval Path: [L1 → L3...]
Failed/Skipped Items: [Reasons for 404/429/Large source slicing]
Budget Consumed: [Primary Intent X calls (incl. 1 counter-evidence) / Secondary Intent Y calls / Total Z calls]
```

## 📌 Quick Reference: Recommended Sources by Domain

### Line A: Asset Models

| Tier | Sources |
|:---:|:---|
| L1 | Civitai → HuggingFace Spaces → Replicate |
| L2 | X Search: "Model Name + workflow / LoRA" |
| L3 | OpenArt / aiartapps → ComfyUI Workflows Community |
| L4 | YouTube / Reddit Tutorials |

### Line B: Tech Code

| Tier | Sources |
|:---:|:---|
| L1 | HuggingFace → GitHub → arXiv |
| L2 | X/Twitter Author/Founder Accounts |
| L3 | Official Docs/Demo Notebooks → Papers with Code |
| L4 | Reddit (e.g., r/LocalLLaMA) → Stack Overflow |

### Line C: Info Trends

| Tier | Sources |
|:---:|:---|
| L1 | Platform Official Data |
| L2 | Data Verification Layer (public leaderboards, analytics) |
| L3 | Practitioner/Creator Personal Reviews |
| L4 | Social Media Trending Topics |

### Line D: Pitfall Selection (⚠️ Must Query Real-Time Pricing)

| Purpose | Sources |
|:---|---:|
| Real-Time Pricing | OpenRouter (openrouter.ai) |
| Performance Benchmarks | Artificial Analysis (artificialanalysis.ai) |
| Pricing Database | LiteLLM (github.com/BerriAI/litellm) |
| Community Verification | Reddit / X Search: "xxx vs yyy review" |

### Line E: Tutorial Materials (⚠️ Downgrade if Deprecated)

| Tier | Sources |
|:---:|:---|
| L1 | Official Docs + Official Tutorials |
| L2 | GitHub README + Wiki |
| L3 | Practitioner In-depth Tutorials (Paid/Free) |
| L4 | YouTube Video Tutorials |
| L5 | Community FAQs (Reddit common issue summaries) |

---

v2.2 (2026-06) Ultimate Update: Global routing arbitration.
