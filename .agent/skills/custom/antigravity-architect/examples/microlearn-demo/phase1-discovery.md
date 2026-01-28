# 🔍 Discovery Report: MicroLearn AI Curator

## 🌐 Industry Research

I researched similar solutions in the market:

### 1. **Cookpad** ([cookpad.com](https://cookpad.com))

- **Model**: Freemium community platform (free recipes + premium meal plans)
- **Key Feature**: User-generated content with ratings/reviews
- **Scale**: 100M+ users globally
- **Lesson**: Community-driven content works, but needs strong moderation

### 2. **Whisk** ([whisk.com](https://whisk.com))

- **Model**: Recipe aggregator + smart grocery list generator
- **Key Feature**: AI extracts ingredients from any recipe URL
- **Weakness**: Doesn't have social features (no user profiles/following)
- **Tech Insight**: Uses NLP to parse unstructured recipe text

### 3. **Tasty (BuzzFeed)** ([tasty.co](https://tasty.co))

- **Model**: Video-first recipes + e-commerce (sells kitchen tools)
- **Key Feature**: Short-form video format (60-90 seconds)
- **Monetization**: Affiliate revenue from product links ($50M+/year)

**Market Insight**: The recipe app market is saturated, but there's opportunity in **niche communities** (vegan, keto, regional cuisines) or **unique features** (AI meal planning, AR cooking guides). Video content drives 10x more engagement than text-only recipes.

---

## ❓ Critical Questions (Please Answer to Proceed)

**Instructions for answering**:

- Each question has multiple-choice options with pros/cons explained.
- If you're unsure, choose option **"C) I don't know"** and I'll recommend the best default.
- You can also write a custom answer if none of the options fit.

---

### 1. **Business Model & Monetization**

**Why this matters**: Recipe apps have low willingness-to-pay. Most successful ones use ads or affiliate revenue, not subscriptions.

**Choose one**:

- **A) Ad-supported (Free for users, revenue from ads)**
  - _Best for_: High-traffic consumer apps
  - _Pros_: No payment friction, easier to grow to 100K+ users
  - _Cons_: Need 500K+ monthly users to make $1K/month (low CPM for food content)
  - _Example_: AllRecipes, Food Network app
- **B) Freemium (Free basic + $4.99/month for premium features)**
  - _Best for_: Power users (meal planners, professional chefs)
  - _Pros_: Predictable revenue, higher quality users
  - _Cons_: Only 2-5% of free users convert to paid
  - _Example_: Paprika Recipe Manager ($4.99/month, 50K paid users)
- **C) Affiliate/E-commerce (Free app + earn commission on product sales)**
  - _Best for_: Apps with high engagement (users cook 3+ times/week)
  - _Pros_: Passive income, scales with user activity
  - _Cons_: Requires partnerships with Amazon/kitchen brands
  - _Example_: Tasty (earns $50M/year from affiliate links)
- **D) I don't know - Recommend for me**
  - → **I recommend Freemium** (easier to validate if users will pay for premium features like meal planning or ad-free experience)

**Your answer**: **\_**

---

### 2. **Content Source: User-Generated vs. Curated**

**Why this matters**: Determines moderation needs, content quality, and time-to-launch.

**Choose one**:

- **A) User-generated (Anyone can post recipes)**
  - _Best for_: Community-driven platforms
  - _Pros_: Infinite content, viral potential (users invite friends)
  - _Cons_: Need moderation (spam, low-quality posts), slower initial growth (empty state problem)
  - _Tech_: User profiles, ratings, reporting system
- **B) Curated (You/team create all recipes)**
  - _Best for_: Premium, high-quality content
  - _Pros_: Consistent quality, easier to monetize
  - _Cons_: Slow content growth (you can only create 5-10 recipes/week)
  - _Tech_: Simple CMS, no user profiles needed
- **C) Hybrid (Curated + select user submissions)**
  - _Best for_: Quality + scale
  - _Pros_: Best of both worlds
  - _Cons_: Need approval workflow (more complex)
  - _Example_: Bon Appétit (staff recipes + community submissions)
- **D) I don't know - Recommend for me**
  - → **I'll ask follow-up**: Do you have time to create 50+ recipes yourself for launch, or do you need users to contribute content?

**Your answer**: **\_**

---

### 3. **Core Feature Priority: What Makes Your App Different?**

**Why this matters**: In a saturated market, you need a unique hook. This determines your MVP scope.

**Choose one**:

- **A) Social features (Follow chefs, comment, share)**
  - _Best for_: Building a community
  - _Pros_: Viral growth, user retention
  - _Cons_: Complex (user profiles, feeds, notifications)
  - _Dev time_: 6-8 weeks for MVP
- **B) AI-powered features (Meal planning, ingredient substitution, dietary filters)**
  - _Best for_: Power users, health-conscious audience
  - _Pros_: High perceived value, justifies premium pricing
  - _Cons_: Requires Gemini API integration, higher costs
  - _Dev time_: 4-6 weeks for MVP
- **C) Video-first (TikTok-style short recipe videos)**
  - _Best for_: Younger audience (18-35)
  - _Pros_: 10x higher engagement than text
  - _Cons_: Need video hosting (Cloudflare Stream = $1/1000 min), harder to create content
  - _Dev time_: 5-7 weeks for MVP
- **D) Simple & fast (Just recipes, search, save favorites)**
  - _Best for_: Quick MVP validation
  - _Pros_: Fastest to build (2-3 weeks), low cost
  - _Cons_: Hard to differentiate from competitors
  - _Dev time_: 2-3 weeks for MVP
- **E) I don't know - Recommend for me**
  - → **I recommend D (Simple MVP)** first to validate demand, then add AI or social features in Phase 2 based on user feedback.

**Your answer**: **\_**

---

### 4. **Platform: Where Will Users Access This?**

**Why this matters**: Mobile apps cost 3x more to build than web apps, but have better retention for cooking apps (users cook in kitchen with phone).

**Choose one**:

- **A) Web app only (Desktop + mobile browser)**
  - _Best for_: Quick validation, low budget
  - _Pros_: Fastest to build, no app store approval
  - _Cons_: Can't send push notifications, worse offline experience
  - _Dev time_: 2-3 weeks
- **B) Mobile app (iOS + Android via React Native)**
  - _Best for_: Long-term retention, premium positioning
  - _Pros_: Push notifications (remind users to cook), offline mode, better UX
  - _Cons_: 3x dev time, $99/year Apple fee, app store approval delays
  - _Dev time_: 6-8 weeks
- **C) Progressive Web App (PWA - web app that installs like native)**
  - _Best for_: Best of both worlds
  - _Pros_: Installable, offline mode, push notifications (on Android)
  - _Cons_: iOS has limited PWA support (no push notifications)
  - _Dev time_: 3-4 weeks
- **D) I don't know - Recommend for me**
  - → **I recommend PWA** (faster than native app, better than basic web app, works great on Android where most users are)

**Your answer**: **\_**

---

### 5. **Scale Expectations: How Many Users in First 6 Months?**

**Why this matters**: Determines if we can use free tiers (Supabase, Vercel) or need paid infrastructure from day 1.

**Choose one**:

- **A) Small community (100-1,000 users)**
  - _Infrastructure_: Free tiers (Supabase, Vercel, Cloudflare)
  - _Cost_: $0/month
  - _Best for_: Niche audience (e.g., "Vegan recipes for athletes")
- **B) Medium growth (1K-10K users)**
  - _Infrastructure_: Free tiers + potential upgrade at 5K users
  - _Cost_: $0-50/month
  - _Best for_: Regional focus (e.g., "Mexican recipes in Texas")
- **C) Viral ambition (10K-100K+ users)**
  - _Infrastructure_: Paid plans from start (Supabase Pro, CDN)
  - _Cost_: $100-300/month
  - _Best for_: Global launch with marketing budget
- **D) I don't know - Recommend for me**
  - → **I recommend B (Medium growth)** - realistic for a well-executed MVP with organic marketing

**Your answer**: **\_**

---

## 🤔 Educated Objections & Trade-offs

Before we proceed, let me challenge one assumption:

### Objection 1: "Recipe Sharing" in a Saturated Market

- **You mentioned**: An app for sharing recipes
- **My concern**: There are 500+ recipe apps. Without a unique angle, it's very hard to get users to switch from AllRecipes, Tasty, or even Google Search.
- **Question**: What will make users choose YOUR app over:
  - **AllRecipes** (10M recipes, free, SEO-optimized)
  - **Instagram/TikTok** (where most people already share recipes)
  - **Google** (instant recipe search)
- **Recommendation**: Consider one of these differentiators:
  1. **Niche focus**: "Keto recipes for busy moms" (specific audience)
  2. **AI superpower**: "Paste any recipe URL, get instant nutritional analysis + grocery list"
  3. **Local/cultural**: "Authentic Venezuelan recipes with video tutorials in Spanish"

**Do you have a specific niche or unique feature in mind?** If not, I'll recommend building a "Simple MVP" (option D in Question 3) to test if there's demand before investing in complex features.

---

## 🚦 Next Steps

Once you answer the 5 questions above (and clarify your niche/differentiator), I'll generate a complete Blueprint with:

✅ **Definitive tech stack** (Next.js vs. React Native, Supabase vs. Firebase)  
✅ **System architecture diagram** (Mermaid)  
✅ **Database schema** (recipes, users, favorites, ratings)  
✅ **Risk assessment** (competition, user acquisition cost, content moderation)  
✅ **Phase-by-phase implementation plan** (MVP → Growth features)  
✅ **Cost breakdown** (infrastructure, AI, hosting)

**Estimated time for Blueprint**: 10 minutes after receiving your answers.
