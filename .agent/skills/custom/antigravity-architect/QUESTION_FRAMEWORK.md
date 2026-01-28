# Discovery Question Framework - Examples

This document shows how to format questions in the Discovery phase to be educational and accessible for novice users.

## ❌ Bad Example (Old Format)

```markdown
## ❓ Critical Questions

1. What's your business model?
2. What database do you want?
3. Do you need real-time features?
4. What's your target scale?
```

**Problems**:

- No context on why these questions matter
- Assumes user knows technical implications
- No guidance for users who don't know the answer

---

## ✅ Good Example (New Format with Question Helper Framework)

```markdown
## ❓ Critical Questions (Please Answer to Proceed)

**Instructions for answering**:

- Each question has multiple-choice options with pros/cons explained.
- If you're unsure, choose option "C) I don't know" and I'll recommend the best default.
- You can also write a custom answer if none of the options fit.

---

### 1. **Business Model & Monetization**

**Why this matters**: Determines if we need payment processing, rate limiting, and how we structure user tiers.

**Choose one**:

- **A) Freemium** (Free tier with limits + Paid upgrade)
  - _Best for_: Rapid user growth, viral potential
  - _Pros_: Low barrier to entry, easier to get first 1,000 users
  - _Cons_: Need to build rate limiting, risk of abuse
  - _Example_: Notion, Canva
- **B) Subscription-only** ($X/month, no free tier)
  - _Best for_: Premium positioning, predictable revenue
  - _Pros_: Higher quality users, simpler infrastructure
  - _Cons_: Slower growth, harder to validate product-market fit
  - _Example_: Netflix, Spotify Premium
- **C) I don't know - Recommend for me**
  - → **I recommend Freemium** for MVPs (easier to validate demand)

**Your answer**: **\_**

---

### 2. **Technical Performance Requirements**

**Why this matters**: Real-time features cost 5-10x more in infrastructure than batch processing.

**Choose one**:

- **A) Real-time** (Updates appear instantly, <1 second delay)
  - _Best for_: Chat apps, live dashboards, collaborative tools
  - _Tech_: WebSockets, Supabase Realtime, Firebase
  - _Cost_: $50-200/month at 1K users
- **B) Near real-time** (Updates within 5-30 seconds)
  - _Best for_: Social feeds, notifications, analytics
  - _Tech_: Polling, Server-Sent Events
  - _Cost_: $10-30/month at 1K users
- **C) Batch/Async** (Updates within minutes/hours)
  - _Best for_: Email digests, reports, background processing
  - _Tech_: Cron jobs, queues
  - _Cost_: $5-10/month at 1K users
- **D) I don't know - Recommend for me**
  - → **I'll ask follow-up**: Which features need to be instant vs. can wait?

**Your answer**: **\_**
```

---

## Key Principles

1. **Always explain "Why this matters"**: Connect the question to business/technical impact.

2. **Provide 2-3 concrete options**: Each with:
   - **Best for**: Use case description
   - **Pros**: Benefits
   - **Cons**: Trade-offs
   - **Example/Tech**: Real-world reference or tech stack

3. **Always include "I don't know" option**: With a recommended default or follow-up question.

4. **Use cost/time estimates when relevant**: "$50/month at 1K users" is more concrete than "expensive".

5. **Reference familiar products**: "Like Notion" or "Like Netflix" helps users understand.

---

## When to Use Follow-up Questions

If user chooses "I don't know", the Architect should ask a simpler, more specific question:

**Example**:

User chose "D) I don't know" for "Technical Performance Requirements"

**Architect's follow-up**:

```
Let me ask a simpler question:

When a user performs an action (e.g., sends a message, updates a profile),
how quickly do OTHER users need to see that change?

A) Instantly (like WhatsApp chat) → Real-time
B) Within a few seconds (like Twitter feed) → Near real-time
C) Doesn't matter, can take minutes (like email) → Batch/Async

Your answer: _____
```

---

## Template for Creating New Questions

```markdown
### [Number]. **[Question Category]**

**Why this matters**: [1-sentence business/technical impact]

**Choose one**:

- **A) [Option Name]** ([Short description])
  - _Best for_: [Use case]
  - _Pros_: [Benefit 1], [Benefit 2]
  - _Cons_: [Trade-off]
  - _Example/Tech_: [Reference]
- **B) [Option Name]** ([Short description])
  - _Best for_: [Use case]
  - _Pros_: [Benefit]
  - _Cons_: [Trade-off]
- **C) I don't know - Recommend for me**
  - → **I recommend [Option]** because [reason]

**Your answer**: **\_**
```
