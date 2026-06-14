# StreetFeast

**StreetFeast — Product Summary**

**Overview**
StreetFeast is a mobile-first street food discovery and recommendation platform built for urban India. Its core purpose is to bridge the gap between food-loving GenZ/Millennial users and authentic street food vendors through hyperlocal video discovery, crowd-sourced trust scores, and a seamless in-app ordering experience. It targets a $41 Bn unorganised market growing at 39% CAGR, with an addressable user base of 200M in Tier-1 cities.

**The Problem**
Street food in India is deeply unorganised. Vendors frequently change locations, making them hard to find. Users struggle to identify vendors with authentic taste, consistent hygiene, and local credibility. Existing platforms like Zomato and Swiggy are built for restaurant delivery and do not distinguish or showcase street food identity. No platform currently exists that solves discovery, trust, and location for the street food ecosystem specifically.

**Target Users**
The primary segment is students and mid-working professionals up to age 25, living in Tier-1 cities. This group has high tech savviness, high order frequency, strong street food consumption habits, and willingness to travel up to 5 km for a good meal. Two personas anchor the product — Shreya (23, student, Delhi) who wants to find authentic street food without trial and error, and Vidyuth (29, street food seller, Delhi) who wants to grow foot traffic despite having good food and affordable prices.

**Vendor Focus**
The product targets food stalls and food trucks specifically. Push cart vendors were excluded because they have low digital literacy, high mobility that makes location tracking impractical, and limited ability to engage with an app-based platform. Food stall and food truck sellers are predominantly literate (per NASVI, 70% of Indian street food vendors are literate, concentrated in these segments), digitally aware, and increasingly modernising their operations.

**Core Solution**
The MVP is built around Video Based Recommendations (VBR), which scored the highest in RICE prioritisation with a score of 15. The app has two primary tabs:

The **Vlogs tab** is a TikTok-style scrollable short video feed featuring food content from top city vloggers and local creators. Each video card displays the vendor's distance from the user, their local recommendation score, and best-seller items. Tapping any label takes the user directly to that vendor's menu page. Videos are monetised, making this a revenue stream as well as a discovery tool.

The **Bytz tab** offers three discovery modes — Top Picks (personalised), Local Recommends (highest-rated vendors nearby), and Near You (all vendors within 5 km). Each vendor card shows open/closed status, distance, and recommendation score. Tapping a vendor opens their full menu page with item photos, prices, operating hours, frequent buys, and a try-these section.

**Recommendation Score Engine**
The local recommendation score is the core trust signal of the platform. After every completed purchase, users are shown a 3-question post-purchase survey. The first two questions (hygiene during preparation, and taste rating on a 0–100 scale) feed into the vendor's overall recommendation score, calculated as the sum of ratings divided by the total number of users who transacted. The third question identifies the vendor's best-seller, which surfaces in the Frequent Buys section of the menu page. Completing the survey unlocks a discount coupon for the next order, incentivising participation.

**Ordering and Payment**
Users can browse a vendor's menu, add items to cart, apply coupons (available only if a prior survey was completed), and pay via PhonePe, GPay, other UPIs, or cash. GST and a platform fee are applied at checkout. Cart management includes add, remove, and quantity update functionality.

**Authentication and Onboarding**
Sign-in and sign-up are OTP-based via mobile number. Immediately after login, the app requests GPS location access, which powers all proximity-based features. New users are routed to account creation while returning users land directly on the Vlogs tab.

**System Design**
The backend uses a load balancer routing traffic across two application servers, with cache servers handling read-heavy operations like video feeds and recommendation scores. Core database tables cover user profiles, vlog data, food truck listings, and recommendation scores with best-seller data. Key API operations include account creation (POST), video feed retrieval (GET), order placement (POST), payment processing (POST), and survey submission (POST) which triggers a score recalculation and database update.

**Risks and Mitigations**
Four key risks are identified. Fake recommendation scores are mitigated by requiring a minimum order value above ₹200 before a survey response is counted. Payment processing failures are addressed by integrating Razorpay with in-app support and defined resolution SLAs. Variable video quality from local creators is managed through content guidelines, user flagging, and algorithmic deprioritisation of underperforming creators. Low perceived value is mitigated through continuous qualitative research and rapid iteration on the score display and survey incentive mechanics.

**Go-To-Market Strategy**
The GTM plan targets literate street food vendors with basic smartphone knowledge on the supply side, and GenZ/Millennials in Tier-1 cities on the demand side. Marketing in the first 6 months focuses on partnering with top food vloggers to highlight the recommendation score USP, training vendors to mention app discounts at point of sale, and providing live customer support from Day 1 to build early trust. Feedback loops are built in from the start for rapid iteration.

**Business Model**
The model is transaction-based across a 3-year roadmap. In the first 6 months, revenue equals users multiplied by transactions, with discounts offered to survey-completing users to bootstrap the recommendation engine and acquire the initial user base. From 6 to 12 months, an in-app wallet is introduced with a streak mechanic requiring at least 3 transactions per month to unlock discounts, building habitual usage. From year 1 to 3, discounts are gated behind an AOV above ₹250, food delivery may be introduced based on demand signals, and the platform expands to Tier-2 and Tier-3 cities based on organic vlogger-led growth and feedback loops. The long-term target is 10% of the 200M addressable segment, equating to 20M users.

**Metrics Framework**
The North Star Metric is Retention Rate (retained users divided by retained plus churned users), reflecting the product's introduction stage focus on proving market fit before scaling. Supporting metrics span the full funnel — Exposure (CTR via ads and vlogs), Adoption (app downloads), Activation (first transaction completion rate), Engagement (video views, shares, session duration), Retention (D3, D7, D15, D30 cohort tracking), Drop-Off Rate (funnel page analysis), Revenue (total revenue minus ad spend and monetisation cost), Referral (NPS and CSAT), and NFRs (load time, server scalability, crash rates, payment load time). Long-term product success is defined as LTV significantly exceeding CAC with improving D30 retention cohorts over successive months.

**Future Scope**
Post year 1, the roadmap includes food delivery expansion, Tier-2/3 city rollout, a vendor analytics dashboard, a personalised taste profile built from order history and survey data, and a formalised StreetFeast Creator Programme with incentive structures for food vloggers.

## App Link --> https://grub-guide-vibes.lovable.app/
