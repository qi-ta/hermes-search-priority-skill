---
name: priority-source-search
description: "Standard Edition: Flexible and high fault-tolerance. Ideal for daily learning, information gathering, and general tutorial creation. v2.2 Ultimate"
---

# 🧠 AI Search Priority Skill v2.2 (Standard Edition)

## ⚠️ Skill Routing Arbitration Rule (Pre-loading Check for Agent)

**This File (Standard):** Applicable to scenarios with no direct commercial monetization intent, such as daily learning, information gathering, and general tutorial creation.

**Mandatory Switch to Professional:** Applies to scenarios involving financial transactions, selling tutorials, freelance delivery, commercial vendor selection, or API integration. If a task contains ANY monetization/delivery attribute, the Professional version MUST be used unconditionally, even if the action is merely "researching." When uncertain, default to Pro; better safe than sorry.

## 🎯 Core Positioning

This Skill provides a flexible, high-fault-tolerance information retrieval specification. Through a 5-tier Evidence Level system (L1-L5) and intent routing, it resolves common search issues like "low-quality sources" and "outdated information," ensuring responses are both practical and user-friendly.

## 📜 I. Cross-Domain General Rules

### Evidence Priority & Source Verification

| Level | Description | Examples |
|:---:|:---|---:|
| L1 🥇 | Primary Sources | Official GitHub, HuggingFace, arXiv, Official Documentation |
| L2 🥇 | First-hand from Creators | Creators' official social accounts, official blogs, Release Notes |
| L3 🥈 | Reproducible Content | Verifications with code/demos/benchmarks, Colab Notebooks |
| L4 🥉 | Community Validation | Reddit real-world tests, Hacker News genuine experiences |
| L5 🏁 | Media Relays | Tech news, marketing accounts (for leads only) |

**Verification Principle:** Prioritize L1-L3 sources. Dual-source cross-validation is encouraged, but a single authoritative L1/L2 source is sufficient to output a conclusion directly. L1 is exempt from the dual-source requirement.

### Dynamic Timeliness Exemption

| Type | Rule |
|:---|---:|
| ✅ Needs Tagging (Prompt if >90 days) | "Volatile info" like API pricing, model versions, platform rules |
| ❌ Exempt | "Constant knowledge" like underlying algorithm principles, classic papers |

### Flexible Fallback & Lead Delivery (Preventing Blunt Refusals)

**Lead-Level Delivery:** If perfect L1-L3 sources are not found after exhaustive search → Strictly forbid replying "Not found". Switch to "Lead Delivery" mode, provide L4/L5 info, and prepend with:
> ⚠️ Currently, only community discussions/media leads were retrieved, lacking official empirical cross-validation. Information is for reference only.

**Funnel Retrieval:** If search results = 0 → Auto-"broaden" (strip marginal modifiers, search core entity); if results are too messy → "narrow down" (add qualifiers).

### Engineering & Experience Optimization

| Rule | Details |
|:---|---:|
| Large Source Anti-Bloat | For large GitHub repos, prioritize reading only README.md/docs index. Strictly forbid full-volume reading. |
| Cookie Failure Fallback | Degrade to publicly crawlable pages when cookies fail. |

## ⚙️ II. Standard Execution Workflow

### Step 1: Intent Recognition & Routing

| Type | Typical Question | Mainline |
|:---:|:---|---:|
| A | "What model/LoRA to use for XX effect?" | Asset Models |
| B | "How to implement this tech solution?" | Tech Code |
| C | "What are the current trends in AI video?" | Info Trends |
| D | "Which is more worth it: Sora vs Runway?" | Pitfall Selection |
| E | "I need to create an XX tutorial, what materials to gather?" | Tutorial Materials |

*Default priority chain when intent is unclear or contains multiple intents: A > B > D > E > C. Strictly follow user's explicit instructions if provided.*

### Step 2: Tiered Retrieval & Dynamic Adjustment

- Retrieve tier by tier starting from L1.
- **Query Reconstruction:** Immediately add qualifiers if results go off-topic.
- **Stop When Sufficient:** Stop immediately upon finding the core source that directly solves the problem.
- **Call Limit:** Suggested ≤ 8 calls. Timeouts/5xx do not count; switch to backup source on 429.

### Step 3: Standardized Output Format

```markdown
💡 Core Conclusion (TL;DR)
(Plain language summary within 50 words: "What to do / Where to find it / What the conclusion is".)

📊 Detailed Info & Source List
[Key Conclusion Point]
   Source: [URL] | Tier: [L?] | Timeliness: [Time since publication]
  Note: Sort multiple sources of the same tier as a/b/c.

⚠️ Caveats & Limitations
[Limitations of the info, timeliness risks, or community disputes]
(If involving Category A/B assets or code, MANDATORY append: "For commercial use, please switch to the Professional edition to execute strict License verification.")

🔍 Search Strategy Brief
Keywords Used: [List core search terms and reconstruction process]
Retrieval Path: [e.g., L1 Official Docs → L3 Community Tests]
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

### Line D: Pitfall Selection

| Purpose | Sources |
|:---|---:|
| Real-Time Pricing | OpenRouter (openrouter.ai) |
| Performance Benchmarks | Artificial Analysis (artificialanalysis.ai) |
| Pricing Database | LiteLLM (github.com/BerriAI/litellm) |
| Community Verification | Reddit / X Search: "xxx vs yyy review" |

### Line E: Tutorial Materials

| Tier | Sources |
|:---:|:---|
| L1 | Official Docs + Official Tutorials |
| L2 | GitHub README + Wiki |
| L3 | Practitioner In-depth Tutorials (Paid/Free) |
| L4 | YouTube Video Tutorials |
| L5 | Community FAQs (Reddit common issue summaries) |

---

v2.2 (2026-06) Ultimate Update: Global routing arbitration, default priority chain, A/B line commercial prompts.
