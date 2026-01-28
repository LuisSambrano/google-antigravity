# 🎬 Antigravity Architect - Live Demo

> **Case Study**: MicroLearn AI Curator - From Vague Idea to Production Blueprint

This is a real example of the **Antigravity Architect v2.1.0** skill in action, demonstrating the 2-phase Socratic discovery workflow.

---

## 📋 Table of Contents

1. [User Input](#user-input) - The vague idea
2. [Phase 1: Discovery Report](#phase-1-discovery-report) - Research + Questions + Objections
3. [User Answers](#user-answers) - Responses to critical questions
4. [Phase 2: Blueprint](#phase-2-blueprint) - Complete technical architecture

---

## 👤 User Input

**User's Initial Request**:

> "Quiero hacer una app para curar micro-aprendizaje. El problema es la parálisis por análisis en plataformas como YouTube o Platzi. Los usuarios guardan 200 videos de 'IA' o 'Diseño UX' y no ven ninguno porque no saben por dónde empezar según su tiempo disponible.
>
> La solución: Un agente que actúe como un Arquitecto de Currículum Dinámico. El usuario le dice: 'Tengo 20 minutos y quiero entender cómo funciona la tokenización de activos RWA'. El agente escanea los videos guardados del usuario (o listas de reproducción), extrae los fragmentos clave (timestamps) y genera una micro-lección compacta."

**Analysis**: This is a typical "vague product idea" - the user knows the problem but hasn't thought through:

- Business model
- Technical feasibility
- Competitive landscape
- MVP scope

This is where the Architect's Discovery phase adds value.

---

## 🔍 Phase 1: Discovery Report

[View Full Discovery Report →](./phase1-discovery.md)

**Key Sections**:

### 1. Industry Research

The Architect researched 3 similar products:

- **Mindstone** (knowledge curator)
- **Snipd** (podcast highlights with AI)
- **Wisecut AI** (video highlight extraction)

**Market Insight**: Proven demand for AI content curation (Snipd has 500K+ users). The gap is **personalization by time** and **multi-platform integration**.

### 2. Critical Questions (Educational Format)

Instead of asking "What database do you want?", the Architect provides:

**Example Question**:

```markdown
### 1. Business Model & Monetization

Why this matters: Recipe apps have low willingness-to-pay.
Most successful ones use ads or affiliate revenue.

Choose one:
A) Freemium (Free + $4.99/month premium)
Pros: Predictable revenue
Cons: Only 2-5% convert
Example: Paprika ($4.99/month, 50K users)

B) Ad-supported
Pros: No payment friction
Cons: Need 500K+ users for $1K/month

C) I don't know - Recommend for me
→ I recommend Freemium (easier to validate)
```

### 3. Educated Objections

The Architect challenges assumptions:

**Objection 1**: "Escanear videos guardados del usuario"

- **Concern**: Platzi has no public API (would require web scraping, violates ToS)
- **Alternative**: Start with "paste link" MVP, add OAuth later
- **Question**: Are you willing to start lean?

---

## ✍️ User Answers

[View Full Answers →](./user-answers.md)

**Key Decisions**:

1. **Business Model**: Freemium (paste link for free, unlimited for $4.99/month)
2. **Output Format**: Text summary with timestamps (not video compilation)
3. **Scale**: Start with YouTube-only, add Platzi later
4. **Platform**: Progressive Web App (PWA)
5. **AI Model**: Gemini 1.5 Flash (cost-optimized)

---

## 🏛️ Phase 2: Blueprint

[View Full Blueprint →](./phase2-blueprint.md)

**Generated Architecture**:

### Tech Stack

- **Frontend**: Next.js 14 + React 19 + Tailwind CSS
- **Backend**: Vercel Edge Functions
- **AI**: Google Gemini 1.5 Flash
- **Data**: Supabase (PostgreSQL + Auth)
- **Video Processing**: YouTube Transcript API (free)

### System Architecture (Mermaid)

```mermaid
graph TB
    subgraph "Client Layer"
        A[User Dashboard]
        B[Paste Video Link Form]
        C[Micro-Lesson Viewer]
    end

    subgraph "API Layer - Vercel Edge"
        D[/api/process-video]
        E[/api/generate-lesson]
    end

    subgraph "External Services"
        F[YouTube Transcript API]
        G[Google Gemini 1.5 Flash]
    end

    subgraph "Data Layer - Supabase"
        H[(PostgreSQL)]
        I[Auth Service]
    end

    B -->|POST video URL| D
    D -->|Fetch transcript| F
    F -->|Return transcript + timestamps| D
    D -->|Store raw transcript| H
    D -->|Trigger| E
    E -->|Send transcript + user time| G
    G -->|Return structured lesson| E
    E -->|Save lesson| H
    C -->|Fetch lessons| H
    A -->|Auth| I
```

### Database Schema

```sql
CREATE TABLE videos (
    id UUID PRIMARY KEY,
    video_url TEXT UNIQUE NOT NULL,
    platform TEXT NOT NULL,
    transcript JSONB,
    processed_at TIMESTAMPTZ DEFAULT NOW()
);

CREATE TABLE micro_lessons (
    id UUID PRIMARY KEY,
    user_id UUID REFERENCES auth.users NOT NULL,
    video_id UUID REFERENCES videos NOT NULL,
    query TEXT NOT NULL,
    time_budget_minutes INTEGER NOT NULL,
    lesson_content JSONB NOT NULL,
    created_at TIMESTAMPTZ DEFAULT NOW()
);
```

### Risk Assessment

**Potential Weaknesses**:

1. **YouTube API Rate Limits** (10K requests/day on free tier)
   - Mitigation: Cache transcripts, limit to 5 videos/day for free users

2. **Gemini Flash Hallucinations** on niche topics
   - Mitigation: Add confidence scores, allow user feedback

**Alternative Approaches Considered**:

- **OpenAI Whisper** for transcription - Rejected (costs $0.006/min vs. YouTube API free)
- **Browser Extension** instead of web app - Rejected (harder to monetize, less scalable)

### Cost Breakdown (Per 1,000 Users/Month)

| Item                   | Cost           |
| ---------------------- | -------------- |
| Vercel Pro             | $20/month      |
| Supabase Pro           | $25/month      |
| Gemini API             | $50/month      |
| **Total**              | **$95/month**  |
| **Revenue** (20% paid) | $1,000/month   |
| **Profit**             | **$905/month** |

### Implementation Plan

**Phase 1: MVP Core (Week 1-2)**

- Next.js scaffold + Supabase setup
- `/api/process-video` endpoint
- `/api/generate-lesson` endpoint
- Simple UI: Paste link → Show lesson

**Phase 2: UX Polish (Week 3)**

- Timeline visualization
- Click timestamp → Open YouTube at that moment
- Mobile-responsive design

**Phase 3: Monetization (Week 4-5)**

- Freemium limits (5 lessons/month)
- Stripe integration
- Analytics dashboard

---

## 📊 Outcome: From Idea to Execution in 30 Minutes

**What the user got**:

- ✅ Validated business model (Freemium)
- ✅ Definitive tech stack (no ambiguity)
- ✅ Complete database schema
- ✅ Risk mitigation strategies
- ✅ Cost projections
- ✅ 8-week implementation roadmap

**What the user avoided**:

- ❌ Building a video compilation feature (expensive, copyright issues)
- ❌ Using Platzi API (doesn't exist, would require illegal scraping)
- ❌ Over-engineering with real-time features (not needed for MVP)

---

## 🎯 Key Takeaways

1. **Discovery Before Design**: The Architect didn't jump to code. It researched competitors, asked critical questions, and challenged assumptions first.

2. **Educational Questions**: Instead of "What database?", it explained PostgreSQL vs. MongoDB with pros/cons and recommended a default.

3. **Red Team Thinking**: The Blueprint includes a "Risk Assessment" section identifying weaknesses and alternatives.

4. **Cost Transparency**: The user knows exactly what it will cost to run this at scale ($95/month for 1K users).

---

## 🚀 Try It Yourself

Want to use the Antigravity Architect skill for your own project?

1. **Clone the repo**: `git clone https://github.com/LuisSambrano/antigravity-skills.git`
2. **Copy the skill**: `cp -r .agent/skills/custom/antigravity-architect ./your-project/.agent/skills/`
3. **Invoke it**: Provide a vague product idea and let the Architect guide you through Discovery → Blueprint

---

## 📞 Questions?

- **Telegram**: [@luissambrano_ux](https://t.me/luissambrano_ux)
- **GitHub Issues**: [Report a bug](https://github.com/LuisSambrano/antigravity-skills/issues)

---

**Built with ❤️ by [Luis Sambrano](https://github.com/LuisSambrano) | Powered by Google Gemini 1.5 Pro**
