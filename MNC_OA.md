# 🏆 The MNC OA + Interview + System Design + Amazon Mastery Guide

> **A single, book-length README on how to ace Software Engineer hiring at large companies / MNCs (FAANG and FAANG-adjacent): the Online Assessment (OA) round, coding interviews, system design (HLD + LLD, step by step, in extreme detail), behavioral rounds, and a dedicated, extremely detailed playbook for Amazon's entire SWE hiring pipeline — OA, interview, system design, and Leadership-Principles-based behavioral rounds.**

This guide is written to be read end-to-end once, then used as a reference you dip into repeatedly during prep. It assumes you already know how to write code in at least one language (examples use Java, matching the other guides in this repo) and focuses on **the hiring process itself**: what each round actually tests, how it's structured at real companies, previously-asked questions with full solutions, and a step-by-step method for solving system design problems from scratch under time pressure.

## How this guide relates to the other guides in this repository

This repo already has several deep, focused guides. Rather than repeat their content, this guide is scoped to be the **process + Amazon-specific + company-tagged** companion to them:

| Topic | Best guide to use |
|---|---|
| Exhaustive DSA patterns (162 problems, pattern-organized: arrays, trees, DP, graphs...) | [LEETCODE_MASTERY_COMPLETE_GUIDE.md](LEETCODE_MASTERY_COMPLETE_GUIDE.md) |
| Exhaustive System Design (22 HLD case studies + 12 LLD case studies + full building-blocks theory) | [SYSTEM_DESIGN_INTERVIEW_MASTERY_GUIDE.md](SYSTEM_DESIGN_INTERVIEW_MASTERY_GUIDE.md) |
| General resume/HR/behavioral/salary negotiation (100 behavioral Qs, STAR method) | [INTERVIEW_MASTERY_GUIDE.md](INTERVIEW_MASTERY_GUIDE.md) |
| **The hiring pipeline itself: OA formats, company-tagged previously-asked questions, and a complete Amazon-specific OA+interview+system-design+behavioral playbook** | **This guide** |

Use this guide as the "master strategy" document, and jump into the other three for exhaustive depth on DSA patterns, system design case studies, or general behavioral prep respectively. This guide is self-contained for its own scope (OA prep, company-tagged question banks, condensed but complete HLD/LLD frameworks with fresh case studies, and the full Amazon playbook), so you don't strictly need the other files — but they pair well with this one.

---

## 📚 Master Table of Contents

**Part 0 — Orientation**
- [0.1 Who this is for](#01-who-this-is-for)
- [0.2 How to use this guide](#02-how-to-use-this-guide)

**Part 1 — The Modern MNC/FAANG Hiring Pipeline**
- [1.1 The full pipeline, stage by stage](#11-the-full-pipeline-stage-by-stage)
- [1.2 Resume screening & ATS](#12-resume-screening--ats)
- [1.3 Recruiter screen](#13-recruiter-screen)
- [1.4 Online Assessment stage (overview)](#14-online-assessment-stage-overview)
- [1.5 Technical phone/video screen (overview)](#15-technical-phonevideo-screen-overview)
- [1.6 Onsite / virtual onsite loop (overview)](#16-onsite--virtual-onsite-loop-overview)
- [1.7 Hiring committee, debrief & bar raiser](#17-hiring-committee-debrief--bar-raiser)
- [1.8 Offer, negotiation & background check](#18-offer-negotiation--background-check)
- [1.9 Typical end-to-end timelines by company](#19-typical-end-to-end-timelines-by-company)

**Part 2 — Online Assessment (OA) Deep Dive**
- [2.1 What an OA actually is](#21-what-an-oa-actually-is)
- [2.2 OA platforms explained](#22-oa-platforms-explained)
- [2.3 OA format by company](#23-oa-format-by-company)
- [2.4 Common OA question patterns & topics](#24-common-oa-question-patterns--topics)
- [2.5 OA test-taking strategy & tips](#25-oa-test-taking-strategy--tips)
- [2.6 Proctoring, plagiarism detection & integrity rules](#26-proctoring-plagiarism-detection--integrity-rules)
- [2.7 The Amazon/employer "Work Style" & personality assessment](#27-the-amazonemployer-work-style--personality-assessment)
- [2.8 Previously-asked OA questions — company-tagged bank](#28-previously-asked-oa-questions--company-tagged-bank)

**Part 3 — Technical Phone / Video Screening Round**
- [3.1 Format & what's being evaluated](#31-format--whats-being-evaluated)
- [3.2 The live-coding communication framework](#32-the-live-coding-communication-framework)
- [3.3 Common phone-screen questions & patterns](#33-common-phone-screen-questions--patterns)
- [3.4 Do's, don'ts & red flags interviewers watch for](#34-dos-donts--red-flags-interviewers-watch-for)

**Part 4 — The Onsite / Virtual Onsite Loop**
- [4.1 Typical loop structure across companies](#41-typical-loop-structure-across-companies)
- [4.2 What each round type actually tests](#42-what-each-round-type-actually-tests)
- [4.3 The hiring manager round](#43-the-hiring-manager-round)
- [4.4 Cross-team / "as appropriate" (bar raiser style) rounds](#44-cross-team--as-appropriate-bar-raiser-style-rounds)

**Part 5 — Coding/DSA Interview: Company-Tagged Previously-Asked Questions Bank**
- [5.1 How to use this bank](#51-how-to-use-this-bank)
- [5.2 Amazon-tagged questions](#52-amazon-tagged-questions)
- [5.3 Google-tagged questions](#53-google-tagged-questions)
- [5.4 Microsoft-tagged questions](#54-microsoft-tagged-questions)
- [5.5 Meta-tagged questions](#55-meta-tagged-questions)
- [5.6 Apple/Netflix/Uber/Bloomberg-tagged questions](#56-applenetflixuberbloomberg-tagged-questions)
- [5.7 Extended company-tagged bank](#57-extended-company-tagged-bank-more-mncs-more-patterns)
- [5.8 Second extended bank](#58-second-extended-bank-more-patterns-union-find-segment-trees-kmp-mst-bit-tricks)
- [5.9 Third extended bank](#59-third-extended-bank-infrastructure-security-and-saas-platform-companies)

**Part 6 — System Design (HLD): Step-by-Step Framework + Fresh Case Studies**
- [6.1 HLD vs LLD — the difference interviewers care about](#61-hld-vs-lld--the-difference-interviewers-care-about)
- [6.2 The universal HLD framework (step by step)](#62-the-universal-hld-framework-step-by-step)
- [6.3 Case Study: Design Amazon Locker / Package Pickup System](#63-case-study-design-amazon-locker--package-pickup-system)
- [6.4 Case Study: Design an E-Commerce Cart & Inventory System](#64-case-study-design-an-e-commerce-cart--inventory-system)
- [6.5 Case Study: Design Prime Video (video streaming at scale)](#65-case-study-design-prime-video-video-streaming-at-scale)
- [6.6 Case Study: Design a Voice Assistant Backend (Alexa)](#66-case-study-design-a-voice-assistant-backend-alexa)
- [6.7 Case Study: Design a Distributed Job Scheduler](#67-case-study-design-a-distributed-job-scheduler)
- [6.8 Case Study: Design a Notification/Alerting System](#68-case-study-design-a-notificationalerting-system)
- [6.9 Case Study: Design a Search Autocomplete/Typeahead Service](#69-case-study-design-a-search-autocompletetypeahead-service)
- [6.10 Case Study: Design a Distributed Log Aggregation System](#610-case-study-design-a-distributed-log-aggregation-system)
- [6.11 Case Study: Design a Web Crawler](#611-case-study-design-a-web-crawler)
- [6.12 Case Study: Design a Ticket Booking System](#612-case-study-design-a-ticket-booking-system)

**Part 7 — System Design (LLD): Step-by-Step Framework + Fresh Case Studies**
- [7.1 The universal LLD framework (step by step)](#71-the-universal-lld-framework-step-by-step)
- [7.2 Case Study: LLD for an Amazon-style Shopping Cart](#72-case-study-lld-for-an-amazon-style-shopping-cart)
- [7.3 Case Study: LLD for a Ride-Hailing Matching Engine](#73-case-study-lld-for-a-ride-hailing-matching-engine)
- [7.4 Case Study: LLD for an In-Memory Key-Value Store](#74-case-study-lld-for-an-in-memory-key-value-store)
- [7.5 Case Study: LLD for a Parking Lot System](#75-case-study-lld-for-a-parking-lot-system)
- [7.6 Case Study: LLD for a Movie Ticket Booking System](#76-case-study-lld-for-a-movie-ticket-booking-system)

**Part 8 — Behavioral Interview: General MNC Framework**
- [8.1 The STAR method, condensed](#81-the-star-method-condensed)
- [8.2 The most common MNC behavioral themes](#82-the-most-common-mnc-behavioral-themes)
- [8.3 Preparing your story bank](#83-preparing-your-story-bank)

**Part 9 — AMAZON DEEP DIVE: The Complete Playbook**
- [9.1 Amazon's hiring process end-to-end](#91-amazons-hiring-process-end-to-end)
- [9.2 Amazon OA1 & OA2 breakdown](#92-amazon-oa1--oa2-breakdown)
- [9.3 Previously-asked Amazon OA questions with solutions](#93-previously-asked-amazon-oa-questions-with-solutions)
- [9.4 Amazon phone screen specifics](#94-amazon-phone-screen-specifics)
- [9.5 Amazon onsite loop structure](#95-amazon-onsite-loop-structure)
- [9.6 Amazon coding interview: previously-asked questions](#96-amazon-coding-interview-previously-asked-questions)
- [9.7 Amazon system design round: what's different](#97-amazon-system-design-round-whats-different)
- [9.8 All 16 Amazon Leadership Principles, explained, with sample STAR answers](#98-all-16-amazon-leadership-principles-explained-with-sample-star-answers)
- [9.9 The Bar Raiser round, deep dive](#99-the-bar-raiser-round-deep-dive)
- [9.10 Amazon prep plan: week by week](#910-amazon-prep-plan-week-by-week)
- [9.11 Amazon FAQ, common mistakes & insider tips](#911-amazon-faq-common-mistakes--insider-tips)

**Part 10 — Company-Specific Playbooks**
- [10.1 Quick reference comparison table](#101-quick-reference-comparison-table)
- [10.2 Google](#102-google)
- [10.3 Microsoft](#103-microsoft)
- [10.4 Meta](#104-meta)
- [10.5 Apple](#105-apple)
- [10.6 Netflix](#106-netflix)
- [10.7 Uber](#107-uber)
- [10.8 Adobe](#108-adobe)
- [10.9 Goldman Sachs & Bloomberg (finance-tech)](#109-goldman-sachs--bloomberg-finance-tech)
- [10.10 Flipkart & Indian product companies](#1010-flipkart--indian-product-companies)

**Part 11 — A-Z Glossary of Interview & Technical Terms**

**Part 12 — Master Cheat Sheets**
- [12.1 OA cheat sheet](#121-oa-cheat-sheet)
- [12.2 Coding interview cheat sheet](#122-coding-interview-cheat-sheet)
- [12.3 System design cheat sheet](#123-system-design-cheat-sheet)
- [12.4 Behavioral cheat sheet](#124-behavioral-cheat-sheet)

**Part 13 — FAQ, Integrated Study Roadmap & Closing**
- [13.1 FAQ](#131-faq)
- [13.2 The integrated 10-week study roadmap](#132-the-integrated-10-week-study-roadmap)
- [13.3 Closing notes](#133-closing-notes)

**Part 14 — Extended Practice Problem Bank (More Previously-Asked Questions)**
- [14.1 How to use this bank](#141-how-to-use-this-bank)
- [14.2 Batch 1: Arrays, strings & hashing](#142-batch-1-arrays-strings--hashing)
- [14.3 Batch 2: Trees, graphs & heaps](#143-batch-2-trees-graphs--heaps)
- [14.4 Batch 3: Dynamic programming & greedy](#144-batch-3-dynamic-programming--greedy)
- [14.5 Batch 4: Design & concurrency](#145-batch-4-design--concurrency)

**Part 15 — Final Practice Set (More Previously-Asked Questions)**
- [15.1 Graphs, strings & math](#151-graphs-strings--math)
- [15.2 Heaps, design & advanced patterns](#152-heaps-design--advanced-patterns)
- [15.3 Final appendix: quick-reference index of every problem tag](#153-final-appendix-quick-reference-index-of-every-problem-tag-used-in-this-guide)

---

## Part 0 — Orientation

### 0.1 Who this is for

- **New graduates / SDE-1 candidates** targeting FAANG or FAANG-adjacent MNCs (Amazon, Google, Microsoft, Meta, Apple, Netflix, Uber, Adobe, Bloomberg, Goldman Sachs, Flipkart, and similar).
- **Experienced engineers (SDE-2/SDE-3, senior)** who need the system design and behavioral sections more than the OA section (most experienced hires skip or get a lighter OA).
- **Anyone specifically targeting Amazon**, since Part 9 is a complete, standalone Amazon playbook.
- Readers who have basic DSA fluency already and want to understand **the process**, not re-learn data structures from scratch (for that, pair with [LEETCODE_MASTERY_COMPLETE_GUIDE.md](LEETCODE_MASTERY_COMPLETE_GUIDE.md)).

### 0.2 How to use this guide

1. **First pass:** Read Part 1 fully so you understand the entire pipeline end to end — this removes anxiety about "what happens next."
2. **If you have an OA coming up:** Read Part 2 fully, then drill the company-tagged questions in [2.8](#28-previously-asked-oa-questions--company-tagged-bank) relevant to your target company.
3. **If you have a phone screen or onsite coding rounds:** Read Parts 3–4, then drill Part 5's question bank for your target company.
4. **If you have a system design round:** Read Part 6 (HLD) and Part 7 (LLD) fully — they are self-contained frameworks with worked examples, not just theory.
5. **If you're interviewing at Amazon specifically:** Read Part 9 top to bottom. It is written to be usable on its own, even if you skip everything else.
6. **The week before any interview:** Re-read Part 11 (cheat sheets) and the relevant company row in Part 10.
7. **Use Part 12.2** to build a day-by-day plan if you have 6–10 weeks before your interview.

---

## Part 1 — The Modern MNC/FAANG Hiring Pipeline

### 1.1 The full pipeline, stage by stage

Almost every large tech company (and most MNCs that have adopted "FAANG-style" hiring, which by 2026 is nearly all of them) follows a variant of this pipeline:

```
Application / Referral
        │
        ▼
Resume Screen (recruiter + ATS keyword match)
        │
        ▼
Recruiter Phone Screen (10-20 min, fit/logistics)
        │
        ▼
Online Assessment (OA)  ──────────────► (skipped for senior/referred candidates sometimes)
        │
        ▼
Technical Phone/Video Screen (1-2 rounds, 45-60 min each)
        │
        ▼
Onsite / Virtual Onsite Loop (3-6 rounds in one day, back-to-back)
   ├── Coding round(s)
   ├── System design round(s) — usually only for 2+ YOE roles
   ├── Behavioral round(s)
   └── Hiring manager round
        │
        ▼
Debrief / Hiring Committee / Bar Raiser Review
        │
        ▼
Offer (+ negotiation) → Background check → Start date
```

Not every company runs every stage in this order — some run the OA before the recruiter screen (fully automated top-of-funnel), some combine behavioral questions into every single round instead of having a dedicated round, and some (Google, Meta) do NOT use a fixed "OA" for experienced hires but do for new-grad/intern pipelines. The shape above is the **superset** — expect subsets of it depending on company and level.

### 1.2 Resume screening & ATS

- Most large companies use an **Applicant Tracking System (ATS)** (Workday, Greenhouse, iCIMS, Amazon's internal system) that keyword-matches your resume against the job description before a human ever looks at it.
- Practical implications:
  - Mirror the **exact terminology** used in the job description (e.g., if the JD says "distributed systems," don't only write "scalable backend systems").
  - Avoid text inside images, tables-as-images, or unusual fonts/columns that some ATS parsers mangle.
  - Quantify impact ("reduced P99 latency by 38%" beats "improved performance").
- A **referral** does not skip stages, but it does usually guarantee your resume gets human eyes and can shave days off the recruiter-screen wait.

### 1.3 Recruiter screen

A short (10–20 minute) call, usually non-technical, covering:
- Your background summary, why this company/role, work authorization/visa status, location/relocation, expected timeline, and compensation expectations range.
- **Goal:** confirm basic fit and logistics before spending engineering interviewer time on you. Rarely a rejection point unless there's a hard mismatch (visa, comp floor, notice period).

### 1.4 Online Assessment stage (overview)

A timed, remote, autograded coding test (and sometimes a personality/work-style survey). Full deep dive in **Part 2**. Typically used for new-grad and high-volume SDE-1/SDE-2 pipelines; often skipped for senior/staff roles and for internal transfers.

### 1.5 Technical phone/video screen (overview)

One or two 45–60 minute video calls with an engineer, live-coding in a shared editor (CoderPad, HackerRank CodePair, Amazon Chime + a shared doc, etc.), usually 1–2 DSA problems. Full deep dive in **Part 3**.

### 1.6 Onsite / virtual onsite loop (overview)

The main event: 3–6 back-to-back interviews (historically in person, now frequently virtual), each 45–60 minutes, covering coding, system design (for 2+ YOE roles), and behavioral/Leadership-Principles-style questions. Full deep dive in **Part 4**.

### 1.7 Hiring committee, debrief & bar raiser

After the loop, interviewers independently write detailed feedback (never comparing notes beforehand, to avoid groupthink) and submit a rating (e.g., "Strong Hire / Hire / No Hire / Strong No Hire" or Amazon's "Hire / No Hire" with an "Inclined/Not Inclined" from the Bar Raiser). A **hiring committee** (Google) or **debrief meeting** (most companies) or **Bar Raiser-anchored debrief** (Amazon) reviews all feedback together and makes the final call. One strong negative signal can outweigh several positives — consistency of signal matters more than a single "genius" round.

### 1.8 Offer, negotiation & background check

- Verbal offer from recruiter → written offer (base, sign-on bonus, equity/RSU vesting schedule, level) → negotiation window (typically 3–10 business days) → background check / reference check → start date.
- **Always negotiate** — most large companies expect it and have built-in room; a polite, well-reasoned counter (ideally with a competing offer or market-data anchor) rarely backfires. See [INTERVIEW_MASTERY_GUIDE.md](INTERVIEW_MASTERY_GUIDE.md) Section 22 for a full negotiation masterclass.

### 1.9 Typical end-to-end timelines by company

| Company | Recruiter screen → OA | OA → Phone screen | Phone screen → Onsite | Onsite → Offer |
|---|---|---|---|---|
| Amazon | 3–7 days | 1–2 weeks | 1–3 weeks | 3–10 days (bar raiser dependent) |
| Google | N/A for most (screen is the technical call) | — | 2–4 weeks | 2–6 weeks (hiring committee + comp committee) |
| Microsoft | 3–5 days | 1 week | 1–2 weeks | 1–2 weeks |
| Meta | 3–5 days | 1 week | 2–3 weeks | 1–2 weeks |
| Adobe/Uber/Bloomberg | 3–7 days | 1–2 weeks | 1–2 weeks | 1–2 weeks |
| Flipkart/other Indian MNC hubs | 2–5 days | 3–7 days | 1 week | 1 week |

These are **typical ranges**, not guarantees — hiring freezes, panel availability, and role urgency can stretch any of these considerably. Patience and polite recruiter check-ins (every 1–2 weeks, not daily) are the correct approach.

## Part 2 — Online Assessment (OA) Deep Dive

### 2.1 What an OA actually is

An **Online Assessment** is a timed, remote, auto-graded test candidates complete on their own computer, usually within a window of several days after being invited (e.g., "complete within 5 days," then a hard 90–120 minute timer starts once you begin). It typically consists of:

1. **1–2 coding problems** (auto-graded against hidden test cases, partial credit for passing a subset).
2. Sometimes **multiple-choice / quiz questions** on CS fundamentals (OS, networking, OOP, SQL).
3. Sometimes a **debugging exercise** (given broken code, fix it).
4. Sometimes a **work-style / personality survey** (untimed, no right/wrong answers, but very much scored — see [2.7](#27-the-amazonemployer-work-style--personality-assessment)).

**Why companies use OAs:** they filter thousands of applicants down to a manageable number before spending expensive engineer time on phone screens. It is a **volume filter**, not a deep evaluation — so passing is mostly about speed, correctness, and not making silly mistakes, not about showing brilliance.

### 2.2 OA platforms explained

| Platform | Used by (examples) | Notes |
|---|---|---|
| **HackerRank** | Amazon, Goldman Sachs, Visa, many Indian MNCs | Split-screen: problem statement left, code editor right. Supports 40+ languages. Has its own proctoring (webcam + screen recording optional). |
| **Codility** | Meta (some pipelines), various European MNCs | Known for its "correctness + performance" scoring bar chart. Very strict on Big-O — a correct-but-slow solution scores lower. |
| **CodeSignal (formerly CodeFights)** | Uber, Robinhood, various | Has a standardized "General Coding Assessment (GCA)" score portable across companies (candidates can reuse a GCA score for multiple employers within a validity window). |
| **HackerEarth** | Many Indian product companies & campus drives | Common for large campus-hiring drives (thousands of simultaneous test-takers). |
| **AMCAT / Mercer Mettl / eLitmus** | Indian service companies (TCS, Infosys, Wipro, Cognizant) and some campus drives for product companies | Heavier emphasis on aptitude (quant/logical reasoning) + English + a lighter coding section. |
| **Custom in-house platforms** | Amazon (custom OA tooling), Google (proprietary), Microsoft | Similar UX to HackerRank/Codility but company-branded; questions are pulled from internal banks. |

### 2.3 OA format by company

| Company | Typical OA structure | Duration |
|---|---|---|
| **Amazon** | OA1: 1–2 coding problems (moderate difficulty, e.g., LeetCode Medium). OA2 (if applicable, "Amazon Assessment"): coding problems + a Work Style Assessment (survey) + sometimes a logical-reasoning section. | 90–120 min total, split across sittings sometimes |
| **Google** | For new grads: "Foobar"-style or a standard 1-hour, 1-question coding assessment via Google's own platform is uncommon now — most candidates go straight to phone screens. Some new-grad pipelines use a short online coding test. | ~45–60 min if present |
| **Microsoft** | 1 coding problem (~45–60 min) via a Microsoft-branded portal, occasionally combined with a short quiz. | 45–75 min |
| **Meta** | Historically skips a generic OA for most pipelines and goes straight to phone screen; some new-grad/intern pipelines use Codility. | 60–90 min if present |
| **Adobe** | 2 coding problems + MCQs on CS fundamentals (OS/DBMS/OOP) — common in India campus/off-campus drives. | 90 min |
| **Uber** | CodeSignal-based, 2 coding problems. | 60–90 min |
| **Goldman Sachs / JPMorgan (tech divisions)** | HackerRank-based, 2–3 problems + sometimes SQL + aptitude for analyst-track SDE roles. | 90 min |
| **Flipkart / Indian product companies** | HackerRank/HackerEarth, 2 coding problems + CS fundamentals MCQs, often as part of a campus superday. | 90 min |
| **Service-based MNCs (TCS/Infosys/Wipro/Cognizant/Accenture)** | AMCAT/Mercer Mettl: aptitude (quant/logical/verbal) + 1–2 easy-medium coding problems + sometimes a "coding simulator"/pseudo-code section. | 60–150 min depending on drive |

### 2.4 Common OA question patterns & topics

Across almost every company, OA problems (the coding ones) cluster into a predictable set of patterns — this is good news, because it means targeted practice pays off disproportionately:

1. **Array/string manipulation** — subarray sums, sliding window, two pointers, frequency counting.
2. **Hash map / set based counting** — anagrams, duplicates, grouping.
3. **Simulation problems** — "simulate this process for N steps and return the final state" (very common at Amazon: warehouse robots, elevator simulation, string transformation rules).
4. **Graph/tree BFS-DFS** — shortest path in a grid, number of connected regions, minimum steps.
5. **Greedy/interval scheduling** — meeting rooms, resource allocation, min number of X to cover Y.
6. **Basic DP** — knapsack variants, longest subsequence variants, coin change variants.
7. **String parsing** — validate/transform strings following custom rules (very common — companies love inventing a "custom mini-language" or "custom encoding" problem).
8. **Matrix/grid problems** — rotate, flood-fill, path counting.
9. **SQL** (for some companies/roles) — joins, aggregations, window functions.
10. **CS fundamentals MCQs** — OOP concepts, process vs thread, TCP vs UDP, normalization, time complexity of standard operations.

**Key insight:** OA problems are rarely the *hardest* LeetCode-style problems (rarely Hard-tier graph/DP). They are usually **Medium-tier problems with a wordy, real-world-flavored wrapper** (e.g., "Amazon warehouse robots moving boxes" is really just a grid BFS problem; "Reorder song playlist to avoid repeats" is really just a greedy/heap problem). **Learning to strip the story and see the underlying pattern fast is the single highest-leverage OA skill.**

### 2.5 OA test-taking strategy & tips

1. **Read both/all problems first**, then attack the one you're most confident about — don't get stuck on problem 1 and starve problem 2 of time.
2. **Partial credit is real** — most platforms score against a hidden test suite (e.g., 15 test cases). Even if you can't get an O(n) solution, submit a correct O(n²) brute force for partial credit rather than submitting nothing.
3. **Handle edge cases explicitly**: empty input, single element, all-same elements, negative numbers, integer overflow (use `long` in Java for sums that could exceed `int` range), duplicate values.
4. **Watch the constraints** — `n ≤ 10^5` strongly implies an O(n log n) or O(n) solution is expected; an O(n²) will time out (TLE). `n ≤ 20` often hints at bitmask DP or brute-force/backtracking being fine.
5. **Compile/test locally in your head or with the platform's "Run" button on sample cases BEFORE hitting Submit** — submissions are sometimes rate-limited or logged as attempts.
6. **Don't over-engineer** — OAs reward a working, reasonably efficient solution fast, not a perfectly idiomatic one. Get it green, then optimize only if time remains.
7. **Environment tips:** close unnecessary tabs/apps (some proctoring flags tab-switching), ensure stable internet, use a wired connection if possible, test your webcam/mic beforehand if proctoring requires them, and have your ID ready if identity verification is required.
8. **Time-box ruthlessly**: if a 90-minute OA has 2 problems, budget ~40 minutes each with a 10-minute buffer — if you're at minute 35 with no working solution, switch to writing the best partial/brute-force you can and move on.

### 2.6 Proctoring, plagiarism detection & integrity rules

- Most OA platforms run **automated similarity detection (MOSS-style plagiarism checks)** comparing your submission against a database of known solutions and other candidates' submissions — copy-pasting a solution verbatim from the internet is a common and easily-detected disqualification reason.
- Some OAs require **webcam + screen recording** for the duration (common for Amazon, Goldman Sachs); tab-switching or opening disallowed applications can be flagged for manual review.
- **It is fine and expected** to use the platform's own documentation/language reference (e.g., "what's the syntax for a TreeMap in Java") — the rule being enforced is "don't get someone else to solve it for you or copy another candidate's exact code," not "don't use any reference material at all." Always read the specific platform's stated policy before assuming either way.
- Using a second monitor/device to look up a *similar* problem's editorial and then writing your own solution in your own words/structure is a gray area many candidates use safely, but the safest approach is to rely on your own preparation and only use official language docs during the actual OA.

### 2.7 The Amazon/employer "Work Style" & personality assessment

Amazon (and increasingly other large companies) includes an **untimed survey** alongside the coding OA, often called a "Work Style Assessment." Format: pairs or groups of statements (e.g., "I prefer to dive into details" vs. "I prefer to think about the big picture first") where you rank/choose which best describes you, repeated for 20–40 minutes.

**What it's really measuring:** alignment with the company's cultural framework — for Amazon, this means implicit signals correlated with the **Leadership Principles** (see [9.8](#98-all-16-amazon-leadership-principles-explained-with-sample-star-answers)): ownership, bias for action, customer obsession, willingness to disagree-and-commit, frugality, and so on.

**How to approach it:**
- **Answer honestly but consistently** — these surveys have built-in consistency/lie-detection checks (the same underlying trait is probed multiple times with reworded statements); contradicting yourself repeatedly to "game" an ideal profile is a bigger red flag than an honest, coherent profile.
- **Lean toward the trait the company visibly values** only when it's *also true of you* — e.g., if you genuinely do prefer action over prolonged analysis, say so; don't invent a persona wholesale.
- It is **not typically a hard pass/fail gate on its own** but is used as one input among several, and can occasionally be used as a tiebreaker or flag for the recruiter to probe further in behavioral rounds.

### 2.8 Previously-asked OA questions — company-tagged bank

Format for each entry: **Problem → Approach → Java Solution → Complexity.** These are reconstructed from widely-reported OA experiences (Glassdoor, LeetCode Discuss, GeeksforGeeks "company tag" pages) — exact wording varies by candidate report, but the underlying pattern is what repeats, so drilling the pattern is what matters.

#### OA-1. [Amazon] Optimal Utilization

**Problem:** Given two lists of `(id, value)` pairs and a target, find all pairs `(a, b)` (one from each list) whose value-sum is the maximum possible without exceeding `target`.

**Approach:** Sort both lists by value. Two-pointer from the larger end of list A and smaller end of list B (or binary search list B for each element of A), tracking the best sum found so far; collect all pairs achieving that best sum.

```java
List<int[]> optimalUtilization(int[][] a, int[][] b, int target) {
    Arrays.sort(a, (x, y) -> x[1] - y[1]);
    Arrays.sort(b, (x, y) -> x[1] - y[1]);
    int i = 0, j = b.length - 1, best = Integer.MIN_VALUE;
    List<int[]> result = new ArrayList<>();
    while (i < a.length && j >= 0) {
        int sum = a[i][1] + b[j][1];
        if (sum > target) { j--; continue; }
        if (sum > best) { best = sum; result.clear(); }
        if (sum == best) result.add(new int[]{a[i][0], b[j][0]});
        i++;
    }
    return result;
}
```
**Complexity:** O(n log n + m log m) sort + O(n + m) scan. **Pattern:** two pointers on sorted arrays with a target ceiling.

#### OA-2. [Amazon] Five Star Sellers

**Problem:** Each seller has `(positiveRatings, totalRatings)`. You can add one rating (assumed positive) to any single seller. Maximize the overall percentage of 5-star ratings across all sellers, choosing which seller to increment repeatedly (K operations) to get the biggest percentage-point gain each time.

**Approach:** Greedy + max-heap: the gain from adding one positive rating to seller `i` is `(p+1)/(t+1) - p/t`. Always apply the next operation to whichever seller currently has the highest marginal gain (recompute after each increment) using a priority queue.

```java
double maxAveragePercentage(int[][] sellers, int ops) {
    PriorityQueue<double[]> pq = new PriorityQueue<>((x, y) -> Double.compare(y[0], x[0]));
    for (int[] s : sellers) {
        double gain = (double)(s[0] + 1) / (s[1] + 1) - (double) s[0] / s[1];
        pq.offer(new double[]{gain, s[0], s[1]});
    }
    while (ops-- > 0) {
        double[] top = pq.poll();
        int p = (int) top[1] + 1, t = (int) top[2] + 1;
        double gain = t + 1 == 0 ? 0 : (double)(p + 1) / (t + 1) - (double) p / t;
        pq.offer(new double[]{gain, p, t});
    }
    double sumPct = 0;
    for (double[] s : pq) sumPct += s[1] / s[2];
    return sumPct / sellers.length * 100;
}
```
**Complexity:** O((n + K) log n). **Pattern:** greedy with a max-heap re-evaluated after every operation.

#### OA-3. [Amazon] Items in Containers (substring range query)

**Problem:** Given a string of `*` (items) and `|` (containers), for each query `[l, r]` count items strictly between the first and last `|` inside that substring range.

**Approach:** Precompute, for every index, the position of the nearest `|` to the left and to the right. For a query, find the nearest `|` at or after `l` and the nearest `|` at or before `r`; the answer is the count of `*` strictly between those two bar positions (using a prefix-count array of `*`).

```java
int[] itemsInContainers(String s, int[][] queries) {
    int n = s.length();
    int[] nextBar = new int[n + 1], prevBar = new int[n + 1];
    int[] starPrefix = new int[n + 1];
    nextBar[n] = -1;
    for (int i = n - 1; i >= 0; i--) nextBar[i] = s.charAt(i) == '|' ? i : nextBar[i + 1];
    prevBar[0] = -1;
    for (int i = 1; i <= n; i++) prevBar[i] = (i > 0 && s.charAt(i - 1) == '|') ? i - 1 : (i > 0 ? prevBar[i - 1] : -1);
    for (int i = 0; i < n; i++) starPrefix[i + 1] = starPrefix[i] + (s.charAt(i) == '*' ? 1 : 0);
    int[] ans = new int[queries.length];
    for (int qi = 0; qi < queries.length; qi++) {
        int l = queries[qi][0], r = queries[qi][1];
        int left = nextBar[l], right = prevBar[r + 1];
        ans[qi] = (left == -1 || right == -1 || left >= right) ? 0 : starPrefix[right] - starPrefix[left + 1];
    }
    return ans;
}
```
**Complexity:** O(n) preprocessing + O(1) per query. **Pattern:** prefix sums + nearest-neighbor precomputation for fast range queries.

#### OA-4. [Amazon] Fill the Truck / Maximum Units on a Truck

**Problem:** Boxes come as `[numBoxes, unitsPerBox]`. Truck can carry at most `truckSize` boxes total. Maximize total units loaded.

**Approach:** Greedy — sort box types by `unitsPerBox` descending, load the highest-value boxes first until the truck is full.

```java
int maximumUnits(int[][] boxTypes, int truckSize) {
    Arrays.sort(boxTypes, (a, b) -> b[1] - a[1]);
    int total = 0;
    for (int[] bt : boxTypes) {
        if (truckSize <= 0) break;
        int take = Math.min(truckSize, bt[0]);
        total += take * bt[1];
        truckSize -= take;
    }
    return total;
}
```
**Complexity:** O(n log n). **Pattern:** classic greedy exchange argument (always prefer higher unit value first).

#### OA-5. [Amazon] Transaction Logs / Turnstile simulation

**Problem:** Simulate people arriving at a turnstile at given timestamps, alternating directions; if two arrive at the same instant, the turnstile keeps its last used direction (or defaults if unused) — return the time each person actually passes through.

**Approach:** Pure simulation with careful tie-handling — process arrivals in timestamp order, maintain queues for each direction, and a "last direction used" state to break same-time ties per the stated rule.

```java
int[] turnstile(int[] arrivalTime, int[] direction) {
    int n = arrivalTime.length;
    int[] order = new int[n];
    for (int i = 0; i < n; i++) order[i] = i;
    // stable sort by arrival time
    Integer[] idx = new Integer[n];
    for (int i = 0; i < n; i++) idx[i] = i;
    Arrays.sort(idx, (a, b) -> arrivalTime[a] - arrivalTime[b]);
    int[] result = new int[n];
    int lastDir = 1; // default to direction 1 if turnstile idle
    int i = 0, time = 0;
    Queue<Integer> dir0 = new LinkedList<>(), dir1 = new LinkedList<>();
    while (i < n || !dir0.isEmpty() || !dir1.isEmpty()) {
        while (i < n && arrivalTime[idx[i]] == time) {
            if (direction[idx[i]] == 0) dir0.offer(idx[i]); else dir1.offer(idx[i]);
            i++;
        }
        if (dir0.isEmpty() && dir1.isEmpty()) {
            time = i < n ? arrivalTime[idx[i]] : time + 1;
            continue;
        }
        if (!dir0.isEmpty() && !dir1.isEmpty()) {
            int use = lastDir == 0 ? 0 : 1;
            int person = use == 0 ? dir0.poll() : dir1.poll();
            result[person] = time; lastDir = use;
        } else if (!dir0.isEmpty()) { result[dir0.poll()] = time; lastDir = 0; }
        else { result[dir1.poll()] = time; lastDir = 1; }
        time++;
    }
    return result;
}
```
**Complexity:** O(n log n) for the sort + O(n) simulation. **Pattern:** simulation with tie-breaking state — read the rules twice before coding.

#### OA-6. [Google] Count of Palindromic Substrings by length

**Problem:** Given a string, for each query length `k`, count how many substrings of length `k` are palindromes.

**Approach:** Expand-around-center to mark all palindromic spans, or DP table `isPal[i][j]`, then bucket counts by `(j - i + 1)`.

```java
int[] palindromeCountsByLength(String s, int[] queries) {
    int n = s.length();
    boolean[][] isPal = new boolean[n][n];
    int[] countByLen = new int[n + 1];
    for (int i = 0; i < n; i++) { isPal[i][i] = true; countByLen[1]++; }
    for (int len = 2; len <= n; len++) {
        for (int i = 0; i + len - 1 < n; i++) {
            int j = i + len - 1;
            if (s.charAt(i) == s.charAt(j) && (len == 2 || isPal[i + 1][j - 1])) {
                isPal[i][j] = true;
                countByLen[len]++;
            }
        }
    }
    int[] ans = new int[queries.length];
    for (int q = 0; q < queries.length; q++) ans[q] = queries[q] <= n ? countByLen[queries[q]] : 0;
    return ans;
}
```
**Complexity:** O(n²) DP, O(1) per query after preprocessing. **Pattern:** classic palindrome DP, generalized with a bucket array for O(1) query answers.

#### OA-7. [Google] Minimum Days to Make M Bouquets

**Problem:** `bloomDay[i]` tells when flower `i` blooms. Need `m` bouquets, each using `k` **adjacent** bloomed flowers. Find the minimum day all `m` bouquets can be made (or -1 if impossible).

**Approach:** Binary search on the answer day; for a candidate day, greedily scan the array counting consecutive bloomed flowers to see how many bouquets can be formed.

```java
int minDays(int[] bloomDay, int m, int k) {
    if ((long) m * k > bloomDay.length) return -1;
    int lo = 1, hi = 0;
    for (int d : bloomDay) hi = Math.max(hi, d);
    while (lo < hi) {
        int mid = lo + (hi - lo) / 2;
        if (canMake(bloomDay, mid, m, k)) hi = mid; else lo = mid + 1;
    }
    return lo;
}
private boolean canMake(int[] bloomDay, int day, int m, int k) {
    int bouquets = 0, streak = 0;
    for (int d : bloomDay) {
        if (d <= day) { streak++; if (streak == k) { bouquets++; streak = 0; } }
        else streak = 0;
    }
    return bouquets >= m;
}
```
**Complexity:** O(n log(max day)). **Pattern:** "binary search the answer" over a monotonic feasibility check — extremely common OA/interview pattern whenever you see "minimum X such that Y is possible."

#### OA-8. [Microsoft] Maximum Path Sum in a Triangle/Matrix

**Problem:** Given a triangle of numbers, find the maximum total from top to bottom, moving to adjacent numbers on the row below.

**Approach:** Bottom-up DP, collapsing the triangle into the row above by taking the max of the two children at each step (in-place, O(1) extra space beyond the input).

```java
int maxTotal(List<List<Integer>> triangle) {
    int n = triangle.size();
    int[] dp = new int[n];
    for (int i = 0; i < n; i++) dp[i] = triangle.get(n - 1).get(i);
    for (int row = n - 2; row >= 0; row--) {
        for (int i = 0; i <= row; i++) {
            dp[i] = triangle.get(row).get(i) + Math.max(dp[i], dp[i + 1]);
        }
    }
    return dp[0];
}
```
**Complexity:** O(n²) time, O(n) space. **Pattern:** bottom-up DP collapsing a 2D structure into a rolling 1D array.

#### OA-9. [Microsoft] Word Break Feasibility

**Problem:** Given a string and a dictionary, determine if the string can be segmented into a space-separated sequence of dictionary words.

**Approach:** DP where `dp[i]` = true if `s[0..i)` is segmentable; try every split point `j < i`.

```java
boolean wordBreak(String s, List<String> wordDict) {
    Set<String> dict = new HashSet<>(wordDict);
    int n = s.length();
    boolean[] dp = new boolean[n + 1];
    dp[0] = true;
    for (int i = 1; i <= n; i++) {
        for (int j = 0; j < i; j++) {
            if (dp[j] && dict.contains(s.substring(j, i))) { dp[i] = true; break; }
        }
    }
    return dp[n];
}
```
**Complexity:** O(n² ) worst case with substring hashing. **Pattern:** 1D segmentation DP — same skeleton reused for "decode ways," "concatenated words," etc.

#### OA-10. [Adobe] K-Sorted (Nearly Sorted) Array Check

**Problem:** Given an array and `k`, determine whether it could result from a sequence that was originally sorted, then each element moved at most `k` positions away.

**Approach:** A min-heap of size `k+1`: for a valid k-sorted array, sorting it with a heap of that size should reproduce the exact array — compare against the heap-sort output, or equivalently check `arr[i] <= arr[i+k+1]` is never required to be smaller after a real sort; simplest robust check is to run the heap-based "sort a k-sorted array" and diff.

```java
boolean isKSorted(int[] arr, int k) {
    PriorityQueue<Integer> minHeap = new PriorityQueue<>();
    int idx = 0;
    for (int i = 0; i < arr.length; i++) {
        minHeap.offer(arr[i]);
        if (minHeap.size() > k + 1) {
            if (minHeap.poll() != arr[idx++]) return false;
        }
    }
    while (!minHeap.isEmpty()) if (minHeap.poll() != arr[idx++]) return false;
    return true;
}
```
**Complexity:** O(n log k). **Pattern:** bounded min-heap for "nearly sorted" data — same technique sorts a k-sorted array in O(n log k) instead of O(n log n).

#### OA-11. [Uber] Org Structure Reporting Chain

**Problem:** Given a tree of `employee -> manager` relationships, and a target employee, list the full reporting chain up to the CEO, or count subordinates under a given manager.

**Approach:** Build a `parent` map and a `children` adjacency map. Chain-to-CEO = walk `parent` pointers; subordinate count = DFS/BFS over `children`.

```java
int countSubordinates(Map<Integer, List<Integer>> children, int managerId) {
    if (!children.containsKey(managerId)) return 0;
    int count = 0;
    Deque<Integer> stack = new ArrayDeque<>(children.get(managerId));
    while (!stack.isEmpty()) {
        int cur = stack.pop();
        count++;
        if (children.containsKey(cur)) stack.addAll(children.get(cur));
    }
    return count;
}
```
**Complexity:** O(n) per query. **Pattern:** tree/DAG traversal over an org chart — a recurring "real world tree" wrapper around plain DFS.

#### OA-12. [Goldman Sachs] Distinct Pair Sums Count

**Problem:** Count how many distinct sums can be formed by picking one element each from two arrays.

**Approach:** Use a `HashSet<Integer>` of all pairwise sums (only feasible if `n*m` is small per constraints) or, if arrays are large, note the achievable-sum set is often a contiguous range once sorted — check constraints before choosing brute force vs. a smarter range-based argument.

```java
int distinctPairSums(int[] a, int[] b) {
    Set<Integer> sums = new HashSet<>();
    for (int x : a) for (int y : b) sums.add(x + y);
    return sums.size();
}
```
**Complexity:** O(n·m). **Pattern:** brute-force-but-bounded — always check `n, m` constraints before assuming you need a cleverer approach; OAs often have small enough bounds that the "obvious" solution is intended.

#### OA-13. [Flipkart] Minimum Platforms Needed

**Problem:** Given train arrival and departure times, find the minimum number of platforms needed so no train waits.

**Approach:** Sort arrivals and departures independently; sweep with two pointers, incrementing a counter on an arrival and decrementing on a departure that happens no later, tracking the max concurrent count.

```java
int minPlatforms(int[] arrivals, int[] departures) {
    Arrays.sort(arrivals);
    Arrays.sort(departures);
    int platforms = 0, maxPlatforms = 0, i = 0, j = 0;
    while (i < arrivals.length && j < departures.length) {
        if (arrivals[i] <= departures[j]) { platforms++; i++; maxPlatforms = Math.max(maxPlatforms, platforms); }
        else { platforms--; j++; }
    }
    return maxPlatforms;
}
```
**Complexity:** O(n log n). **Pattern:** interval overlap counting via a two-pointer sweep — equivalent to "meeting rooms II."

#### OA-14. [Common / multi-company] K Closest Points to Origin

**Problem:** Given `n` points, return the `k` closest to the origin.

**Approach:** Max-heap of size `k` keyed by squared distance (avoid `sqrt` for both speed and precision); or `Arrays.sort` by distance if `n` is small enough per constraints (quickselect for optimal average case).

```java
int[][] kClosest(int[][] points, int k) {
    PriorityQueue<int[]> maxHeap = new PriorityQueue<>((a, b) ->
        (b[0] * b[0] + b[1] * b[1]) - (a[0] * a[0] + a[1] * a[1]));
    for (int[] p : points) {
        maxHeap.offer(p);
        if (maxHeap.size() > k) maxHeap.poll();
    }
    return maxHeap.toArray(new int[0][]);
}
```
**Complexity:** O(n log k), or O(n) average with quickselect. **Pattern:** "top/bottom K" → bounded heap is the default safe choice; mention quickselect as the follow-up optimization.

#### OA-15. [Common / service-based MNCs] Roman Numeral / Custom Encoding Conversion

**Problem:** A very common "invented mini-language" OA question: convert between a custom symbolic encoding (e.g., Roman numerals, or a company-invented base system) and integers.

**Approach:** For Roman-to-integer: scan left to right, if current symbol's value is less than the next symbol's value, subtract it, otherwise add it.

```java
int romanToInt(String s) {
    Map<Character, Integer> val = Map.of('I',1,'V',5,'X',10,'L',50,'C',100,'D',500,'M',1000);
    int total = 0;
    for (int i = 0; i < s.length(); i++) {
        int cur = val.get(s.charAt(i));
        int next = i + 1 < s.length() ? val.get(s.charAt(i + 1)) : 0;
        total += cur < next ? -cur : cur;
    }
    return total;
}
```
**Complexity:** O(n). **Pattern:** for ANY "custom encoding" OA problem, first write down the encoding's rules as a small table, then it almost always reduces to a single left-to-right scan with a lookahead of 1.

> **OA prep tip:** the fastest way to build speed on this pattern set is to solve 2–3 problems from each row above under a strict 25-minute timer, then review the editorial even if you solved it — OAs reward *speed of recognition*, and timed repetition is what builds that.

## Part 3 — Technical Phone / Video Screening Round

### 3.1 Format & what's being evaluated

A 45–60 minute video call, usually one engineer, using a shared live-coding tool (CoderPad, HackerRank CodePair, Amazon Chime + collaborative doc, Google Docs/Google's internal tool, CodeSignal). Structure is almost always:

1. **2–5 min:** brief intro/small talk, sometimes 1 quick background question ("tell me about a project you're proud of").
2. **30–40 min:** 1–2 coding problems, solved live while narrating your thought process.
3. **5–10 min:** your questions for the interviewer.

**What's actually being evaluated** (this matters more than getting the "right" answer):
- **Problem-solving process** — do you clarify requirements before coding, or start typing immediately?
- **Communication** — can you explain your approach clearly enough that a teammate could follow your PR description?
- **Code quality under time pressure** — sensible variable names, no glaring bugs, reasonable structure (not necessarily "production perfect").
- **Testing discipline** — do you dry-run your own code against examples and edge cases without being asked?
- **Complexity awareness** — can you state the time/space complexity and discuss whether it's good enough for the stated constraints?

### 3.2 The live-coding communication framework

Use this repeatable structure (often taught as **UMPIRE**: Understand, Match, Plan, Implement, Review, Evaluate — condensed below into 5 practical steps):

1. **Clarify (1–2 min):** Restate the problem in your own words. Ask about input size/constraints, data types (can values be negative? duplicates allowed? is the array sorted?), and what to return on edge cases (empty input, no valid answer). This single habit is the #1 differentiator interviewers report between strong and weak candidates.
2. **Think out loud, propose brute force first (2–3 min):** State the naive approach and its complexity even if you already see the optimal one — it shows structured thinking and gives the interviewer an anchor. Then say what's inefficient about it.
3. **Propose the optimized approach and get buy-in (2–4 min):** Name the pattern/data structure you'll use ("I'll use a sliding window with a hash map to track counts") *before* writing code, and briefly check the interviewer isn't expecting something else.
4. **Implement (15–20 min):** Write clean code, narrating key decisions ("I'll use a `long` here to avoid overflow since values can be up to 10^9 and n up to 10^5"). It's fine to pause and think silently for a few seconds on tricky lines — say "let me think through this part" rather than going fully silent.
5. **Test & analyze (5 min):** Manually trace through the given example, then a self-constructed edge case (empty, single element, duplicates). State final time/space complexity and mention possible follow-up optimizations even if not asked.

### 3.3 Common phone-screen questions & patterns

Phone screens skew toward **single, well-defined Medium-difficulty problems** solvable cleanly in 20–25 minutes of coding, most often from these buckets:

- Array/string two-pointer or sliding window (e.g., "longest substring without repeating characters," "container with most water").
- Hash map based grouping/counting (e.g., "group anagrams," "top K frequent elements").
- Linked list manipulation (e.g., "reverse a linked list in groups of K," "detect and remove a cycle").
- Tree traversal / BST property checks (e.g., "validate BST," "lowest common ancestor").
- Basic graph BFS/DFS (e.g., "number of islands," "clone graph").
- One "practical" follow-up question tacked onto the coding problem, e.g. "how would you handle this if the input didn't fit in memory?" or "how would you make this thread-safe?" — a preview of system-design thinking even in a coding round.

See [LEETCODE_MASTERY_COMPLETE_GUIDE.md](LEETCODE_MASTERY_COMPLETE_GUIDE.md) for full worked solutions across all these patterns, and [Part 5](#part-5--codingdsa-interview-company-tagged-previously-asked-questions-bank) below for company-tagged previously-asked questions specifically.

### 3.4 Do's, don'ts & red flags interviewers watch for

**Do:**
- Ask 2–3 clarifying questions before writing any code.
- Narrate your thinking continuously, even during quiet debugging moments.
- Proactively test your code against the example before saying "I'm done."
- Ask 1–2 thoughtful questions about the team/role at the end (see [11.4](#114-behavioral-cheat-sheet) for a starter list) — silence here reads as low genuine interest.

**Don't:**
- Jump straight into coding without discussing approach — even a 90-second verbal plan first is far better than silently typing.
- Go silent for more than ~30 seconds while stuck — say what you're considering, even if unsure.
- Argue with a hint — if the interviewer nudges you toward a different data structure, take the hint gracefully; refusing help to "prove" you can do it alone reads as poor collaboration, not strength.
- Declare "done" without testing — untested code with an off-by-one bug is one of the most common single reasons for a "no hire" on an otherwise strong round.

**Red flags interviewers are trained to notice:**
- Memorized-solution recitation without understanding (revealed when the interviewer tweaks the problem slightly and the candidate can't adapt).
- Inability to state time/space complexity, or stating it incorrectly and not being able to justify it when asked.
- Dismissiveness toward the interviewer's questions or hints.
- No questions at all at the end (interpreted as low genuine interest in the role).

---

## Part 4 — The Onsite / Virtual Onsite Loop

### 4.1 Typical loop structure across companies

| Company | Total rounds | Typical mix |
|---|---|---|
| **Amazon** | 4–6 (loop "chime" back-to-back) | 2–3 coding, 1 system design (2+ YOE), 1–2 behavioral-heavy ("Leadership Principles") rounds — every round blends some LP questions in regardless of its primary focus |
| **Google** | 4–5 | 2 coding ("Googleyness" woven throughout), 1 system design (senior), 1 "Googleyness & Leadership" behavioral round |
| **Microsoft** | 4–5 | 2–3 coding, 1 system design (senior), 1 "As Appropriate" (AA)/hiring-manager round covering culture-fit and technical depth |
| **Meta** | 4–6 | 2 coding, 1 system design (E4+), 1 behavioral round explicitly scored against Meta's core values |
| **Uber/Adobe/Bloomberg/other MNCs** | 4–5 | 2 coding, 1 system design (2+ YOE), 1 behavioral/hiring-manager round |

### 4.2 What each round type actually tests

- **Coding rounds:** same evaluation criteria as the phone screen (see [3.1](#31-format--whats-being-evaluated)), but problems are often slightly harder or have 2 parts (solve part 1, then an added constraint changes the approach for part 2) to test adaptability.
- **System design rounds:** ability to navigate ambiguity, structure a large open-ended problem, make and justify trade-offs, and communicate a design to non-technical-adjacent stakeholders. See [Part 6](#part-6--system-design-hld-step-by-step-framework--fresh-case-studies) for the full framework.
- **Behavioral rounds:** typically framed as "tell me about a time when..." questions mapped to specific competencies (ownership, conflict resolution, dealing with ambiguity, influencing without authority). See [Part 8](#part-8--behavioral-interview-general-mnc-framework) and, for Amazon specifically, [9.8](#98-all-16-amazon-leadership-principles-explained-with-sample-star-answers).
- **Hiring manager round:** a hybrid round — usually lighter technical depth, heavier on "why this team," career motivations, and a genuine two-way conversation about role fit; also often where the final go/no-go weight is heaviest since this person will manage you day to day.

### 4.3 The hiring manager round

Distinct from other loop rounds because the HM is evaluating **long-term fit with their specific team**, not just a generic pass/fail bar. Expect:
- Questions about your career goals and how this role fits them.
- Questions probing what kind of environment/management style you thrive under.
- A chance for you to ask deep questions about the team's current projects, tech debt, on-call load, and growth opportunities — treat this as mutual due diligence, not just an exam.

### 4.4 Cross-team / "as appropriate" (bar raiser style) rounds

Many large companies deliberately include **one interviewer from outside the hiring team** (Amazon's **Bar Raiser**, Microsoft's **"As Appropriate" (AA)** interviewer, Google's cross-team calibration) whose explicit job is to counteract hiring-team bias — they have no stake in filling the specific req and are trained/certified to hold a company-wide bar rather than a team-specific one. Their vote often carries **extra procedural weight** in the final decision (Amazon's Bar Raiser can effectively veto a hire even if every other interviewer says yes — see [9.9](#99-the-bar-raiser-round-deep-dive)). Treat every round in the loop as equally important; you cannot reliably identify which interviewer is the bar raiser/AA from the schedule alone.

## Part 5 — Coding/DSA Interview: Company-Tagged Previously-Asked Questions Bank

### 5.1 How to use this bank

Unlike [LEETCODE_MASTERY_COMPLETE_GUIDE.md](LEETCODE_MASTERY_COMPLETE_GUIDE.md) (organized by **pattern**), this bank is organized by **company**, reflecting which problems are most frequently reported by candidates for each company's phone screen and onsite coding rounds (source: aggregated patterns from LeetCode's company-tag lists, Glassdoor interview reviews, and GeeksforGeeks "interview experience" pages). If you have a specific company's interview coming up, drill that company's section first, then broaden using the pattern-organized guide. Each entry: **Problem → Approach → Java → Complexity → Why this company likes it.**

### 5.2 Amazon-tagged questions

#### C-1. [Amazon] LRU Cache

**Problem:** Design a data structure implementing a Least Recently Used cache with O(1) `get` and `put`.

**Approach:** `HashMap<Key, Node>` + a doubly linked list ordered by recency; on access, unlink and move the node to the front; on capacity overflow, evict the tail.

```java
class LRUCache {
    class Node { int key, val; Node prev, next; Node(int k, int v){key=k;val=v;} }
    private final int capacity;
    private final Map<Integer, Node> map = new HashMap<>();
    private final Node head = new Node(-1,-1), tail = new Node(-1,-1);
    LRUCache(int capacity) { this.capacity = capacity; head.next = tail; tail.prev = head; }
    private void remove(Node n) { n.prev.next = n.next; n.next.prev = n.prev; }
    private void addFront(Node n) { n.next = head.next; n.next.prev = n; head.next = n; n.prev = head; }
    public int get(int key) {
        if (!map.containsKey(key)) return -1;
        Node n = map.get(key); remove(n); addFront(n);
        return n.val;
    }
    public void put(int key, int value) {
        if (map.containsKey(key)) { remove(map.get(key)); }
        Node n = new Node(key, value); map.put(key, n); addFront(n);
        if (map.size() > capacity) { Node lru = tail.prev; remove(lru); map.remove(lru.key); }
    }
}
```
**Complexity:** O(1) per operation. **Why Amazon likes it:** directly tests whether you can compose two data structures to hit a strict complexity bar — a recurring theme in Amazon's "practical systems building block" style questions.

#### C-2. [Amazon] Number of Islands

**Problem:** Given a 2D grid of `'1'`s (land) and `'0'`s (water), count the number of islands (connected 4-directionally).

**Approach:** DFS/BFS flood-fill from every unvisited land cell, marking visited cells to avoid recount.

```java
int numIslands(char[][] grid) {
    int count = 0;
    for (int i = 0; i < grid.length; i++)
        for (int j = 0; j < grid[0].length; j++)
            if (grid[i][j] == '1') { count++; sink(grid, i, j); }
    return count;
}
private void sink(char[][] grid, int i, int j) {
    if (i < 0 || j < 0 || i >= grid.length || j >= grid[0].length || grid[i][j] != '1') return;
    grid[i][j] = '0';
    sink(grid, i+1, j); sink(grid, i-1, j); sink(grid, i, j+1); sink(grid, i, j-1);
}
```
**Complexity:** O(rows × cols). **Why Amazon likes it:** maps naturally to warehouse/fulfillment-network grid problems Amazon frequently wraps this pattern in.

#### C-3. [Amazon] Merge K Sorted Lists

**Problem:** Merge `k` sorted linked lists into one sorted list.

**Approach:** Min-heap keyed by node value holding at most one node per list; repeatedly pop the smallest, append to result, push its successor.

```java
ListNode mergeKLists(ListNode[] lists) {
    PriorityQueue<ListNode> pq = new PriorityQueue<>((a, b) -> a.val - b.val);
    for (ListNode l : lists) if (l != null) pq.offer(l);
    ListNode dummy = new ListNode(0), cur = dummy;
    while (!pq.isEmpty()) {
        ListNode node = pq.poll();
        cur.next = node; cur = cur.next;
        if (node.next != null) pq.offer(node.next);
    }
    return dummy.next;
}
```
**Complexity:** O(N log k) where N is total nodes. **Why Amazon likes it:** tests heap fluency plus linked-list manipulation together, common in order-processing-queue-flavored wrappers.

#### C-4. [Amazon] Word Ladder

**Problem:** Given a start word, end word, and a word list, find the length of the shortest transformation sequence changing one letter at a time, each intermediate word must exist in the list.

**Approach:** BFS over the implicit graph where edges connect words differing by one letter; generate neighbors by trying all 26 letters at each position.

```java
int ladderLength(String beginWord, String endWord, List<String> wordList) {
    Set<String> dict = new HashSet<>(wordList);
    if (!dict.contains(endWord)) return 0;
    Queue<String> queue = new LinkedList<>();
    queue.offer(beginWord);
    int steps = 1;
    while (!queue.isEmpty()) {
        int size = queue.size();
        for (int s = 0; s < size; s++) {
            char[] chars = queue.poll().toCharArray();
            for (int i = 0; i < chars.length; i++) {
                char orig = chars[i];
                for (char c = 'a'; c <= 'z'; c++) {
                    chars[i] = c;
                    String next = new String(chars);
                    if (next.equals(endWord)) return steps + 1;
                    if (dict.remove(next)) queue.offer(next);
                }
                chars[i] = orig;
            }
        }
        steps++;
    }
    return 0;
}
```
**Complexity:** O(N · L · 26) where N = word count, L = word length. **Why Amazon likes it:** BFS shortest-path pattern generalizes to many Amazon "minimum steps to transform/route" wrapper questions.

#### C-5. [Amazon] Two Sum (variant: Two Sum - Data structure design)

**Problem:** Design a class supporting `add(number)` and `find(target)` (does any pair sum to target), optimized for many more `find` calls than `add` calls.

**Approach:** Maintain a frequency `HashMap<Integer,Integer>`. For `find`, iterate map keys and check if `target - key` exists (handle the `key == target - key` case by requiring count ≥ 2).

```java
class TwoSum {
    private final Map<Integer, Integer> counts = new HashMap<>();
    public void add(int number) { counts.merge(number, 1, Integer::sum); }
    public boolean find(int value) {
        for (int num : counts.keySet()) {
            int complement = value - num;
            if (complement == num) { if (counts.get(num) > 1) return true; }
            else if (counts.containsKey(complement)) return true;
        }
        return false;
    }
}
```
**Complexity:** O(1) add, O(distinct numbers) find. **Why Amazon likes it:** the "design a class with two operations of different frequency" framing tests whether you optimize for the right operation, a recurring Amazon system-thinking flavor even in a coding round.

#### C-6. [Amazon] Kth Largest Element in a Stream

**Problem:** Design a class initialized with `k` and a stream of integers; `add(val)` returns the current kth largest element.

**Approach:** Maintain a min-heap of size `k`; the root is always the kth largest so far.

```java
class KthLargest {
    private final int k;
    private final PriorityQueue<Integer> minHeap = new PriorityQueue<>();
    KthLargest(int k, int[] nums) {
        this.k = k;
        for (int n : nums) add(n);
    }
    public int add(int val) {
        minHeap.offer(val);
        if (minHeap.size() > k) minHeap.poll();
        return minHeap.peek();
    }
}
```
**Complexity:** O(log k) per add. **Why Amazon likes it:** streaming/order-statistics questions mirror Amazon's real systems (e.g., tracking top sellers/ratings in near real time).

#### C-7. [Amazon] Rotting Oranges

**Problem:** A grid has fresh (1), rotten (2), and empty (0) cells. Every minute, rotten oranges rot their 4-directional fresh neighbors. Return the minimum minutes until no fresh orange remains, or -1 if impossible.

**Approach:** Multi-source BFS starting from all initially-rotten cells simultaneously, tracking minutes as BFS levels.

```java
int orangesRotting(int[][] grid) {
    int rows = grid.length, cols = grid[0].length, fresh = 0, minutes = 0;
    Queue<int[]> queue = new LinkedList<>();
    for (int i = 0; i < rows; i++)
        for (int j = 0; j < cols; j++) {
            if (grid[i][j] == 2) queue.offer(new int[]{i, j});
            if (grid[i][j] == 1) fresh++;
        }
    int[][] dirs = {{0,1},{0,-1},{1,0},{-1,0}};
    while (!queue.isEmpty() && fresh > 0) {
        int size = queue.size();
        for (int s = 0; s < size; s++) {
            int[] cell = queue.poll();
            for (int[] d : dirs) {
                int ni = cell[0] + d[0], nj = cell[1] + d[1];
                if (ni >= 0 && nj >= 0 && ni < rows && nj < cols && grid[ni][nj] == 1) {
                    grid[ni][nj] = 2; fresh--; queue.offer(new int[]{ni, nj});
                }
            }
        }
        minutes++;
    }
    return fresh == 0 ? minutes : -1;
}
```
**Complexity:** O(rows × cols). **Why Amazon likes it:** the canonical "warehouse spread/contamination simulation" wrapper Amazon reuses across several OA and interview problems.

#### C-8. [Amazon] Subtree of Another Tree

**Problem:** Given two binary trees, determine if the second is a subtree of the first (same structure and values, rooted anywhere in the first tree).

**Approach:** For every node in the main tree, check if the subtree rooted there is structurally identical to the target tree; recursive `isSameTree` helper.

```java
boolean isSubtree(TreeNode root, TreeNode subRoot) {
    if (root == null) return subRoot == null;
    if (isSameTree(root, subRoot)) return true;
    return isSubtree(root.left, subRoot) || isSubtree(root.right, subRoot);
}
private boolean isSameTree(TreeNode a, TreeNode b) {
    if (a == null || b == null) return a == b;
    return a.val == b.val && isSameTree(a.left, b.left) && isSameTree(a.right, b.right);
}
```
**Complexity:** O(n × m) worst case. **Why Amazon likes it:** simple recursion-composition test that's fast to verify correctness on live, leaving time for a good discussion of the optimized O(n+m) serialization+KMP follow-up.

### 5.3 Google-tagged questions

#### C-9. [Google] Alien Dictionary

**Problem:** Given a list of words sorted according to an unknown alien alphabet, derive a valid character ordering.

**Approach:** Build a directed graph of "letter A comes before letter B" edges from adjacent word comparisons, then topologically sort (Kahn's algorithm / DFS-based).

```java
String alienOrder(String[] words) {
    Map<Character, Set<Character>> graph = new HashMap<>();
    Map<Character, Integer> indegree = new HashMap<>();
    for (String w : words) for (char c : w.toCharArray()) indegree.putIfAbsent(c, 0);
    for (int i = 0; i < words.length - 1; i++) {
        String a = words[i], b = words[i + 1];
        int minLen = Math.min(a.length(), b.length());
        if (a.length() > b.length() && a.startsWith(b)) return ""; // invalid order
        for (int j = 0; j < minLen; j++) {
            if (a.charAt(j) != b.charAt(j)) {
                graph.computeIfAbsent(a.charAt(j), k -> new HashSet<>());
                if (graph.get(a.charAt(j)).add(b.charAt(j))) {
                    indegree.merge(b.charAt(j), 1, Integer::sum);
                }
                break;
            }
        }
    }
    Queue<Character> queue = new LinkedList<>();
    for (char c : indegree.keySet()) if (indegree.get(c) == 0) queue.offer(c);
    StringBuilder result = new StringBuilder();
    while (!queue.isEmpty()) {
        char c = queue.poll();
        result.append(c);
        for (char next : graph.getOrDefault(c, Collections.emptySet())) {
            if (indegree.merge(next, -1, Integer::sum) == 0) queue.offer(next);
        }
    }
    return result.length() == indegree.size() ? result.toString() : "";
}
```
**Complexity:** O(total characters). **Why Google likes it:** blends graph construction subtlety (edge extraction rules) with topological sort — tests careful edge-case handling (e.g., the `a.length() > b.length() && a.startsWith(b)` invalid case) more than raw algorithm memorization.

#### C-10. [Google] Median of Two Sorted Arrays

**Problem:** Find the median of two sorted arrays in O(log(min(m, n))) time.

**Approach:** Binary search on the partition point of the smaller array such that all elements to the left of both partitions are ≤ all elements to the right.

```java
double findMedianSortedArrays(int[] a, int[] b) {
    if (a.length > b.length) return findMedianSortedArrays(b, a);
    int m = a.length, n = b.length, lo = 0, hi = m;
    while (lo <= hi) {
        int partA = (lo + hi) / 2;
        int partB = (m + n + 1) / 2 - partA;
        int maxLeftA = partA == 0 ? Integer.MIN_VALUE : a[partA - 1];
        int minRightA = partA == m ? Integer.MAX_VALUE : a[partA];
        int maxLeftB = partB == 0 ? Integer.MIN_VALUE : b[partB - 1];
        int minRightB = partB == n ? Integer.MAX_VALUE : b[partB];
        if (maxLeftA <= minRightB && maxLeftB <= minRightA) {
            if ((m + n) % 2 == 0) return (Math.max(maxLeftA, maxLeftB) + Math.min(minRightA, minRightB)) / 2.0;
            return Math.max(maxLeftA, maxLeftB);
        } else if (maxLeftA > minRightB) hi = partA - 1;
        else lo = partA + 1;
    }
    throw new IllegalArgumentException("Input arrays are not sorted");
}
```
**Complexity:** O(log(min(m,n))). **Why Google likes it:** a classic "can you derive a non-obvious binary search invariant" question — Google interviews weight mathematical rigor and edge-case precision heavily.

#### C-11. [Google] Serialize and Deserialize a Binary Tree

**Problem:** Design an algorithm to serialize a binary tree to a string and deserialize it back.

**Approach:** Preorder DFS serialization with explicit null markers; deserialize by consuming tokens in the same preorder sequence.

```java
public String serialize(TreeNode root) {
    StringBuilder sb = new StringBuilder();
    serializeHelper(root, sb);
    return sb.toString();
}
private void serializeHelper(TreeNode node, StringBuilder sb) {
    if (node == null) { sb.append("#,"); return; }
    sb.append(node.val).append(",");
    serializeHelper(node.left, sb);
    serializeHelper(node.right, sb);
}
public TreeNode deserialize(String data) {
    Deque<String> tokens = new ArrayDeque<>(Arrays.asList(data.split(",")));
    return deserializeHelper(tokens);
}
private TreeNode deserializeHelper(Deque<String> tokens) {
    String val = tokens.poll();
    if (val.equals("#")) return null;
    TreeNode node = new TreeNode(Integer.parseInt(val));
    node.left = deserializeHelper(tokens);
    node.right = deserializeHelper(tokens);
    return node;
}
```
**Complexity:** O(n) both directions. **Why Google likes it:** tests clean recursive design and the discipline to handle null markers correctly — a frequent building block inside larger Google system-design-adjacent discussions (e.g., persisting tree structures).

#### C-12. [Google] Trapping Rain Water

**Problem:** Given elevation heights, compute how much water is trapped after raining.

**Approach:** Two pointers from both ends, tracking running max height from each side; move the pointer on the side with the smaller max, accumulating trapped water there.

```java
int trap(int[] height) {
    int left = 0, right = height.length - 1, leftMax = 0, rightMax = 0, water = 0;
    while (left < right) {
        if (height[left] < height[right]) {
            leftMax = Math.max(leftMax, height[left]);
            water += leftMax - height[left];
            left++;
        } else {
            rightMax = Math.max(rightMax, height[right]);
            water += rightMax - height[right];
            right--;
        }
    }
    return water;
}
```
**Complexity:** O(n) time, O(1) space. **Why Google likes it:** the elegant O(1)-space two-pointer solution (versus the more obvious O(n)-space prefix/suffix max arrays) is exactly the kind of "can you find the tighter solution" question Google is known for.

#### C-13. [Google] Longest Increasing Path in a Matrix

**Problem:** Find the length of the longest strictly increasing path in a matrix, moving in 4 directions.

**Approach:** DFS with memoization — `dp[i][j]` caches the longest increasing path starting at `(i,j)`, avoiding recomputation across overlapping paths.

```java
int longestIncreasingPath(int[][] matrix) {
    int rows = matrix.length, cols = matrix[0].length;
    int[][] memo = new int[rows][cols];
    int best = 0;
    for (int i = 0; i < rows; i++)
        for (int j = 0; j < cols; j++)
            best = Math.max(best, dfs(matrix, i, j, memo));
    return best;
}
private int[][] dirs = {{0,1},{0,-1},{1,0},{-1,0}};
private int dfs(int[][] matrix, int i, int j, int[][] memo) {
    if (memo[i][j] != 0) return memo[i][j];
    int best = 1;
    for (int[] d : dirs) {
        int ni = i + d[0], nj = j + d[1];
        if (ni >= 0 && nj >= 0 && ni < matrix.length && nj < matrix[0].length && matrix[ni][nj] > matrix[i][j]) {
            best = Math.max(best, 1 + dfs(matrix, ni, nj, memo));
        }
    }
    return memo[i][j] = best;
}
```
**Complexity:** O(rows × cols). **Why Google likes it:** DFS + memoization on a grid (as opposed to a linear array) is a step up in spatial reasoning that Google onsite loops frequently test.

### 5.4 Microsoft-tagged questions

#### C-14. [Microsoft] Copy List with Random Pointer

**Problem:** Deep-copy a linked list where each node has an extra `random` pointer to any node in the list (or null).

**Approach:** Interleave copied nodes into the original list (`A -> A' -> B -> B' ...`), set each copy's random pointer using the original's random's `.next`, then unweave the two lists.

```java
Node copyRandomList(Node head) {
    if (head == null) return null;
    for (Node cur = head; cur != null; cur = cur.next.next) {
        Node copy = new Node(cur.val);
        copy.next = cur.next;
        cur.next = copy;
    }
    for (Node cur = head; cur != null; cur = cur.next.next) {
        if (cur.random != null) cur.next.random = cur.random.next;
    }
    Node newHead = head.next;
    for (Node cur = head; cur != null; cur = cur.next) {
        Node copy = cur.next;
        cur.next = copy.next;
        copy.next = (copy.next != null) ? copy.next.next : null;
    }
    return newHead;
}
```
**Complexity:** O(n) time, O(1) extra space (beyond output). **Why Microsoft likes it:** the O(1)-space interleaving trick (vs. the simpler O(n)-space hashmap approach) is a well-known Microsoft favorite for testing pointer-manipulation dexterity.

#### C-15. [Microsoft] Reverse Words in a String (in place, no built-ins)

**Problem:** Reverse the order of words in a string, trimming extra spaces, without using library split/reverse utilities.

**Approach:** Reverse the entire character array, then reverse each word back within its boundaries, then clean up extra spaces.

```java
String reverseWords(String s) {
    char[] a = s.toCharArray();
    reverse(a, 0, a.length - 1);
    int n = a.length, i = 0;
    StringBuilder result = new StringBuilder();
    while (i < n) {
        while (i < n && a[i] == ' ') i++;
        if (i >= n) break;
        int j = i;
        while (j < n && a[j] != ' ') j++;
        reverse(a, i, j - 1);
        if (result.length() > 0) result.append(' ');
        result.append(a, i, j - i);
        i = j;
    }
    return result.toString();
}
private void reverse(char[] a, int lo, int hi) {
    while (lo < hi) { char t = a[lo]; a[lo] = a[hi]; a[hi] = t; lo++; hi--; }
}
```
**Complexity:** O(n) time, O(n) space for the builder (O(1) extra if done truly in-place on a mutable char array output). **Why Microsoft likes it:** tests whether you can implement "library functions" from first principles — a recurring Microsoft theme reflecting real work on frameworks/SDKs.

#### C-16. [Microsoft] Lowest Common Ancestor of a Binary Tree

**Problem:** Given a binary tree (not necessarily a BST) and two nodes, find their lowest common ancestor.

**Approach:** Recursive post-order search — if the current node is one of the two targets, return it; otherwise recurse both subtrees; if both return non-null, current node is the LCA.

```java
TreeNode lowestCommonAncestor(TreeNode root, TreeNode p, TreeNode q) {
    if (root == null || root == p || root == q) return root;
    TreeNode left = lowestCommonAncestor(root.left, p, q);
    TreeNode right = lowestCommonAncestor(root.right, p, q);
    if (left != null && right != null) return root;
    return left != null ? left : right;
}
```
**Complexity:** O(n). **Why Microsoft likes it:** simple to state, but candidates commonly fumble the base case or the "both non-null" merge logic under pressure — a good live signal of tree recursion fluency.

#### C-17. [Microsoft] Design an LFU Cache

**Problem:** Design a Least Frequently Used cache with O(1) `get`/`put`; on ties, evict the least recently used among the least frequently used.

**Approach:** Two-level structure: `key -> node` map, `freq -> LinkedHashSet<key>` map (LinkedHashSet preserves insertion/recency order within a frequency bucket), plus a `minFreq` tracker.

```java
class LFUCache {
    class Node { int key, val, freq = 1; Node(int k, int v){key=k;val=v;} }
    private final int capacity;
    private int minFreq = 0;
    private final Map<Integer, Node> cache = new HashMap<>();
    private final Map<Integer, LinkedHashSet<Integer>> freqMap = new HashMap<>();
    LFUCache(int capacity) { this.capacity = capacity; }
    public int get(int key) {
        if (!cache.containsKey(key)) return -1;
        Node n = cache.get(key);
        touch(n);
        return n.val;
    }
    public void put(int key, int value) {
        if (capacity == 0) return;
        if (cache.containsKey(key)) { cache.get(key).val = value; touch(cache.get(key)); return; }
        if (cache.size() >= capacity) {
            int evict = freqMap.get(minFreq).iterator().next();
            freqMap.get(minFreq).remove(evict);
            cache.remove(evict);
        }
        Node n = new Node(key, value);
        cache.put(key, n);
        freqMap.computeIfAbsent(1, k -> new LinkedHashSet<>()).add(key);
        minFreq = 1;
    }
    private void touch(Node n) {
        freqMap.get(n.freq).remove(n.key);
        if (freqMap.get(n.freq).isEmpty() && minFreq == n.freq) minFreq++;
        n.freq++;
        freqMap.computeIfAbsent(n.freq, k -> new LinkedHashSet<>()).add(n.key);
    }
}
```
**Complexity:** O(1) amortized per operation. **Why Microsoft likes it:** a step up from LRU (see C-1) that tests whether you can compose THREE structures correctly under pressure — a strong signal question for senior SDE roles.

### 5.5 Meta-tagged questions

#### C-18. [Meta] Binary Tree Vertical Order Traversal

**Problem:** Given a binary tree, return nodes grouped by vertical column, top-to-bottom, left-to-right within a column.

**Approach:** BFS while tracking each node's horizontal distance (column index) from the root; group into a `TreeMap<Integer, List<Integer>>` for sorted column order.

```java
List<List<Integer>> verticalOrder(TreeNode root) {
    List<List<Integer>> result = new ArrayList<>();
    if (root == null) return result;
    Map<Integer, List<Integer>> columns = new TreeMap<>();
    Queue<TreeNode> nodeQueue = new LinkedList<>();
    Queue<Integer> colQueue = new LinkedList<>();
    nodeQueue.offer(root); colQueue.offer(0);
    while (!nodeQueue.isEmpty()) {
        TreeNode node = nodeQueue.poll();
        int col = colQueue.poll();
        columns.computeIfAbsent(col, k -> new ArrayList<>()).add(node.val);
        if (node.left != null) { nodeQueue.offer(node.left); colQueue.offer(col - 1); }
        if (node.right != null) { nodeQueue.offer(node.right); colQueue.offer(col + 1); }
    }
    result.addAll(columns.values());
    return result;
}
```
**Complexity:** O(n log n) due to TreeMap (O(n) with a plain HashMap + manual min/max column tracking). **Why Meta likes it:** Meta's interviews frequently test BFS with auxiliary state tracked per node — mirrors real feed-ranking/graph-traversal work.

#### C-19. [Meta] Random Pick with Weight

**Problem:** Given an array of weights, design a class that picks an index randomly proportional to its weight.

**Approach:** Build a prefix-sum array of weights; generate a random number in `[1, total]` and binary search for the first prefix sum ≥ that number.

```java
class Solution {
    private final int[] prefix;
    private final Random random = new Random();
    Solution(int[] w) {
        prefix = new int[w.length];
        int sum = 0;
        for (int i = 0; i < w.length; i++) { sum += w[i]; prefix[i] = sum; }
    }
    public int pickIndex() {
        int target = random.nextInt(prefix[prefix.length - 1]) + 1;
        int lo = 0, hi = prefix.length - 1;
        while (lo < hi) {
            int mid = (lo + hi) / 2;
            if (prefix[mid] < target) lo = mid + 1; else hi = mid;
        }
        return lo;
    }
}
```
**Complexity:** O(n) init, O(log n) per pick. **Why Meta likes it:** weighted random sampling underlies ad/feed-ranking systems — a favorite Meta "practical randomized algorithm" question.

#### C-20. [Meta] Add Strings / Add Binary (big number arithmetic without built-ins)

**Problem:** Add two numbers represented as strings, without converting the whole string to a built-in big-integer type.

**Approach:** Simulate elementary-school addition from the last digit backward, tracking carry.

```java
String addStrings(String num1, String num2) {
    StringBuilder result = new StringBuilder();
    int i = num1.length() - 1, j = num2.length() - 1, carry = 0;
    while (i >= 0 || j >= 0 || carry > 0) {
        int d1 = i >= 0 ? num1.charAt(i--) - '0' : 0;
        int d2 = j >= 0 ? num2.charAt(j--) - '0' : 0;
        int sum = d1 + d2 + carry;
        result.append(sum % 10);
        carry = sum / 10;
    }
    return result.reverse().toString();
}
```
**Complexity:** O(max(m, n)). **Why Meta likes it:** deceptively simple; tests careful index/carry bookkeeping without leaning on language shortcuts — a fast, low-noise signal question for early phone screens.

#### C-21. [Meta] Minimum Remove to Make Valid Parentheses

**Problem:** Remove the minimum number of parentheses so the resulting string is valid, given it may also contain letters.

**Approach:** Single pass with a stack of indices for unmatched `(`; on an unmatched `)`, mark it for removal immediately; after the pass, any indices left on the stack are unmatched `(` to also remove.

```java
String minRemoveToMakeValid(String s) {
    char[] chars = s.toCharArray();
    Deque<Integer> stack = new ArrayDeque<>();
    for (int i = 0; i < chars.length; i++) {
        if (chars[i] == '(') stack.push(i);
        else if (chars[i] == ')') {
            if (stack.isEmpty()) chars[i] = '*'; else stack.pop();
        }
    }
    while (!stack.isEmpty()) chars[stack.pop()] = '*';
    StringBuilder sb = new StringBuilder();
    for (char c : chars) if (c != '*') sb.append(c);
    return sb.toString();
}
```
**Complexity:** O(n). **Why Meta likes it:** one of Meta's most frequently reported phone-screen questions — fast to solve cleanly in 15 minutes, leaving time for a follow-up ("what if brackets could also be `{}`/`[]`?").

### 5.6 Apple/Netflix/Uber/Bloomberg-tagged questions

#### C-22. [Apple] Merge Intervals

**Problem:** Given a collection of intervals, merge all overlapping ones.

**Approach:** Sort by start time; iterate, merging the current interval into the last result interval if they overlap.

```java
int[][] merge(int[][] intervals) {
    Arrays.sort(intervals, (a, b) -> a[0] - b[0]);
    List<int[]> merged = new ArrayList<>();
    for (int[] interval : intervals) {
        if (merged.isEmpty() || merged.get(merged.size() - 1)[1] < interval[0]) {
            merged.add(interval);
        } else {
            merged.get(merged.size() - 1)[1] = Math.max(merged.get(merged.size() - 1)[1], interval[1]);
        }
    }
    return merged.toArray(new int[0][]);
}
```
**Complexity:** O(n log n). **Why Apple likes it:** simple, elegant, and a common precursor to Apple's calendar/scheduling-flavored follow-up questions (e.g., "now find free time slots").

#### C-23. [Netflix] Top K Frequent Elements

**Problem:** Return the `k` most frequent elements in an array.

**Approach:** Frequency map, then bucket sort by frequency (bucket index = frequency, capped at array length) for O(n) instead of O(n log n).

```java
int[] topKFrequent(int[] nums, int k) {
    Map<Integer, Integer> freq = new HashMap<>();
    for (int n : nums) freq.merge(n, 1, Integer::sum);
    List<Integer>[] buckets = new List[nums.length + 1];
    for (Map.Entry<Integer, Integer> e : freq.entrySet()) {
        int f = e.getValue();
        if (buckets[f] == null) buckets[f] = new ArrayList<>();
        buckets[f].add(e.getKey());
    }
    List<Integer> result = new ArrayList<>();
    for (int i = buckets.length - 1; i >= 0 && result.size() < k; i--) {
        if (buckets[i] != null) result.addAll(buckets[i]);
    }
    return result.stream().mapToInt(Integer::intValue).limit(k).toArray();
}
```
**Complexity:** O(n) with bucket sort (O(n log k) with a heap alternative). **Why Netflix likes it:** trending/most-watched-content ranking is a direct real-world analog; Netflix interviewers often ask for both the heap and bucket-sort approaches and a discussion of when each is preferable.

#### C-24. [Uber] Meeting Rooms II

**Problem:** Given meeting time intervals, find the minimum number of conference rooms required.

**Approach:** Same "sweep with two sorted arrays of starts/ends" pattern as OA-13 (Minimum Platforms) — sort starts and ends separately, sweep counting concurrent meetings.

```java
int minMeetingRooms(int[][] intervals) {
    int n = intervals.length;
    int[] starts = new int[n], ends = new int[n];
    for (int i = 0; i < n; i++) { starts[i] = intervals[i][0]; ends[i] = intervals[i][1]; }
    Arrays.sort(starts); Arrays.sort(ends);
    int rooms = 0, maxRooms = 0, s = 0, e = 0;
    while (s < n) {
        if (starts[s] < ends[e]) { rooms++; s++; maxRooms = Math.max(maxRooms, rooms); }
        else { rooms--; e++; }
    }
    return maxRooms;
}
```
**Complexity:** O(n log n). **Why Uber likes it:** driver/ride-matching capacity problems reduce directly to this interval-overlap-counting pattern — one of Uber's most-repeated questions.

#### C-25. [Bloomberg] Find First and Last Position of Element in Sorted Array

**Problem:** Given a sorted array, find the starting and ending index of a given target value in O(log n).

**Approach:** Two binary searches — one biased to find the leftmost occurrence, one biased to find the rightmost.

```java
int[] searchRange(int[] nums, int target) {
    return new int[]{ findBound(nums, target, true), findBound(nums, target, false) };
}
private int findBound(int[] nums, int target, boolean findFirst) {
    int lo = 0, hi = nums.length - 1, result = -1;
    while (lo <= hi) {
        int mid = (lo + hi) / 2;
        if (nums[mid] == target) {
            result = mid;
            if (findFirst) hi = mid - 1; else lo = mid + 1;
        } else if (nums[mid] < target) lo = mid + 1;
        else hi = mid - 1;
    }
    return result;
}
```
**Complexity:** O(log n). **Why Bloomberg likes it:** financial time-series/order-book range queries reduce to exactly this "find boundary" binary search — a Bloomberg staple for testing precise off-by-one handling.

### 5.7 Extended company-tagged bank (more MNCs, more patterns)

More previously-reported questions from additional large companies, in the same condensed format, broadening coverage beyond the "big 5" above.

#### D-1. [LinkedIn] Find Peak Element

**Problem:** Find any index whose value is greater than both neighbors (array edges treated as `-infinity`), in O(log n).

**Approach:** Binary search — move toward the side with the larger neighbor, since a peak is guaranteed to exist in that direction.

```java
int findPeakElement(int[] nums) {
    int lo = 0, hi = nums.length - 1;
    while (lo < hi) {
        int mid = (lo + hi) / 2;
        if (nums[mid] > nums[mid + 1]) hi = mid; else lo = mid + 1;
    }
    return lo;
}
```
**Complexity:** O(log n). **Pattern:** binary search on a non-sorted array using a local monotonic property instead of global order.

#### D-2. [Airbnb] Interval List Intersections

**Problem:** Given two lists of disjoint, sorted intervals, return their intersection.

**Approach:** Two pointers, one per list; compute overlap of the current pair, advance whichever interval ends first.

```java
int[][] intervalIntersection(int[][] a, int[][] b) {
    List<int[]> result = new ArrayList<>();
    int i = 0, j = 0;
    while (i < a.length && j < b.length) {
        int lo = Math.max(a[i][0], b[j][0]), hi = Math.min(a[i][1], b[j][1]);
        if (lo <= hi) result.add(new int[]{lo, hi});
        if (a[i][1] < b[j][1]) i++; else j++;
    }
    return result.toArray(new int[0][]);
}
```
**Complexity:** O(m + n). **Pattern:** two-pointer merge over two sorted sequences — Airbnb's booking-availability-window checks reduce to this directly.

#### D-3. [Salesforce] Design a Simplified Twitter Feed

**Problem:** Support `postTweet(userId, tweetId)`, `follow(followerId, followeeId)`, `unfollow`, and `getNewsFeed(userId)` returning the 10 most recent tweet IDs from the user and everyone they follow.

**Approach:** Store tweets per user as a list with a global increasing timestamp; use a max-heap merging the most recent tweets across all followed users (classic "merge k sorted lists" shape, same skeleton as [C-3](#c-3-amazon-merge-k-sorted-lists)).

```java
class Twitter {
    private int timestamp = 0;
    private final Map<Integer, List<int[]>> tweets = new HashMap<>(); // userId -> [(time, tweetId)]
    private final Map<Integer, Set<Integer>> following = new HashMap<>();

    public void postTweet(int userId, int tweetId) {
        tweets.computeIfAbsent(userId, k -> new ArrayList<>()).add(new int[]{timestamp++, tweetId});
    }
    public void follow(int followerId, int followeeId) {
        following.computeIfAbsent(followerId, k -> new HashSet<>()).add(followeeId);
    }
    public void unfollow(int followerId, int followeeId) {
        if (following.containsKey(followerId)) following.get(followerId).remove(followeeId);
    }
    public List<Integer> getNewsFeed(int userId) {
        PriorityQueue<int[]> maxHeap = new PriorityQueue<>((x, y) -> y[0] - x[0]);
        Set<Integer> sources = new HashSet<>(following.getOrDefault(userId, new HashSet<>()));
        sources.add(userId);
        for (int uid : sources) for (int[] t : tweets.getOrDefault(uid, Collections.emptyList())) maxHeap.offer(t);
        List<Integer> result = new ArrayList<>();
        for (int i = 0; i < 10 && !maxHeap.isEmpty(); i++) result.add(maxHeap.poll()[1]);
        return result;
    }
}
```
**Complexity:** O(T log T) per feed request where T is total relevant tweets (optimizable with a bounded k-way merge). **Pattern:** LLD + heap-based merge — a very common "design a mini social feature" onsite question at social/CRM-platform companies.

#### D-4. [PayPal] Validate Credit Card Number (Luhn Algorithm)

**Problem:** Validate a credit card number string using the Luhn checksum algorithm.

**Approach:** Starting from the rightmost digit, double every second digit; if doubling exceeds 9, subtract 9; sum all digits; valid if the total is divisible by 10.

```java
boolean isValidLuhn(String cardNumber) {
    int sum = 0;
    boolean doubleDigit = false;
    for (int i = cardNumber.length() - 1; i >= 0; i--) {
        int digit = cardNumber.charAt(i) - '0';
        if (doubleDigit) { digit *= 2; if (digit > 9) digit -= 9; }
        sum += digit;
        doubleDigit = !doubleDigit;
    }
    return sum % 10 == 0;
}
```
**Complexity:** O(n). **Pattern:** a fixed real-world checksum algorithm — payment companies frequently ask candidates to implement a well-known domain algorithm from a plain-English description to test careful reading and implementation, not algorithmic cleverness.

#### D-5. [Visa] Simple Bank Account System (LLD)

**Problem:** Design a class supporting `deposit`, `withdraw` (rejecting if insufficient funds), and `transfer` between two accounts, safely under concurrent access.

**Approach:** Per-account locks acquired in a consistent global order (e.g., by account ID) during transfers to avoid deadlock between two concurrent transfers going in opposite directions.

```java
class Account {
    final String id; private double balance;
    final Object lock = new Object();
    Account(String id, double balance) { this.id = id; this.balance = balance; }
}
class Bank {
    public boolean withdraw(Account acc, double amount) {
        synchronized (acc.lock) {
            if (acc.balance < amount) return false;
            acc.balance -= amount;
            return true;
        }
    }
    public void deposit(Account acc, double amount) {
        synchronized (acc.lock) { acc.balance += amount; }
    }
    public boolean transfer(Account from, Account to, double amount) {
        Account first = from.id.compareTo(to.id) < 0 ? from : to;
        Account second = first == from ? to : from;
        synchronized (first.lock) {
            synchronized (second.lock) {
                if (from.balance < amount) return false;
                from.balance -= amount; to.balance += amount;
                return true;
            }
        }
    }
}
```
**Complexity:** O(1) per operation. **Pattern:** the "lock ordering by a total order (account ID) to prevent deadlock" technique is a classic concurrency-interview requirement at payments companies.

#### D-6. [Walmart Labs] Shortest Path in a Binary Matrix

**Problem:** Find the shortest 8-directionally-connected path from top-left to bottom-right in a binary grid (0 = open, 1 = blocked).

**Approach:** BFS from the start cell, exploring all 8 neighbor directions, tracking path length as BFS depth.

```java
int shortestPathBinaryMatrix(int[][] grid) {
    int n = grid.length;
    if (grid[0][0] == 1 || grid[n-1][n-1] == 1) return -1;
    int[][] dirs = {{-1,-1},{-1,0},{-1,1},{0,-1},{0,1},{1,-1},{1,0},{1,1}};
    Queue<int[]> queue = new LinkedList<>();
    queue.offer(new int[]{0, 0});
    grid[0][0] = 1; // reuse grid as visited marker
    int steps = 1;
    while (!queue.isEmpty()) {
        int size = queue.size();
        for (int s = 0; s < size; s++) {
            int[] cell = queue.poll();
            if (cell[0] == n - 1 && cell[1] == n - 1) return steps;
            for (int[] d : dirs) {
                int ni = cell[0] + d[0], nj = cell[1] + d[1];
                if (ni >= 0 && nj >= 0 && ni < n && nj < n && grid[ni][nj] == 0) {
                    grid[ni][nj] = 1;
                    queue.offer(new int[]{ni, nj});
                }
            }
        }
        steps++;
    }
    return -1;
}
```
**Complexity:** O(n²). **Pattern:** BFS shortest path on an 8-directional grid — a natural fit for warehouse-robot/logistics-routing questions at retail-logistics companies.

#### D-7. [ServiceNow] Ticket Priority Queue Simulation

**Problem:** Simulate a support-ticket queue where tickets have a priority (1=highest) and arrival order; process tickets highest-priority-first, FIFO within the same priority, and return the processing order.

**Approach:** A priority queue keyed by `(priority, arrivalOrder)` naturally gives the correct tie-break via a compound comparator.

```java
List<Integer> processTickets(int[][] tickets) { // {ticketId, priority}
    PriorityQueue<int[]> pq = new PriorityQueue<>((a, b) -> a[1] != b[1] ? a[1] - b[1] : a[2] - b[2]);
    for (int i = 0; i < tickets.length; i++) pq.offer(new int[]{tickets[i][0], tickets[i][1], i});
    List<Integer> order = new ArrayList<>();
    while (!pq.isEmpty()) order.add(pq.poll()[0]);
    return order;
}
```
**Complexity:** O(n log n). **Pattern:** compound-key priority queue — the "tie-break by secondary key" idea recurs across scheduling/queueing questions.

#### D-8. [Cisco] Network Packet Routing (Dijkstra's Shortest Path)

**Problem:** Given a weighted graph of network nodes and link costs, find the minimum-cost path from a source to all other nodes.

**Approach:** Dijkstra's algorithm with a min-heap, relaxing edges greedily from the currently-closest unvisited node.

```java
int[] dijkstra(int n, List<int[]>[] graph, int src) { // graph[u] = list of {v, weight}
    int[] dist = new int[n];
    Arrays.fill(dist, Integer.MAX_VALUE);
    dist[src] = 0;
    PriorityQueue<int[]> pq = new PriorityQueue<>((a, b) -> a[1] - b[1]); // {node, dist}
    pq.offer(new int[]{src, 0});
    while (!pq.isEmpty()) {
        int[] cur = pq.poll();
        int u = cur[0], d = cur[1];
        if (d > dist[u]) continue;
        for (int[] edge : graph[u]) {
            int v = edge[0], w = edge[1];
            if (dist[u] + w < dist[v]) { dist[v] = dist[u] + w; pq.offer(new int[]{v, dist[v]}); }
        }
    }
    return dist;
}
```
**Complexity:** O((V + E) log V). **Pattern:** the canonical shortest-path algorithm — networking companies ask this directly since it mirrors real link-state routing protocols (OSPF-style).

#### D-9. [Intuit] Progressive Tax Bracket Calculation

**Problem:** Given a list of `(bracketUpperBound, rate)` tax brackets and an income, compute total tax owed, where each bracket's rate applies only to the portion of income within that bracket.

**Approach:** Iterate brackets in order, applying each bracket's rate to `min(income, bracketUpperBound) - previousBoundary`.

```java
double calculateTax(double income, double[][] brackets) { // {upperBound, rate}, upperBound=-1 means infinity
    double tax = 0, previousBoundary = 0;
    for (double[] bracket : brackets) {
        double upper = bracket[0] == -1 ? Double.MAX_VALUE : bracket[0];
        if (income <= previousBoundary) break;
        double taxableInBracket = Math.min(income, upper) - previousBoundary;
        tax += taxableInBracket * bracket[1];
        previousBoundary = upper;
    }
    return tax;
}
```
**Complexity:** O(brackets). **Pattern:** a "domain rules" simulation — the key skill is precisely translating a real-world tiered-rate rule (common in tax/billing/pricing-tier calculations at fintech companies) into exact boundary arithmetic.

#### D-10. [Oracle] Group-By Aggregation (SQL-like, in Java)

**Problem:** Given a list of `(category, amount)` records, group by category and compute sum, count, and average per category, without using a database.

**Approach:** A `Map<String, double[]>` accumulator (`{sum, count}`), single pass.

```java
Map<String, double[]> groupByAggregate(List<Object[]> records) { // {category, amount}
    Map<String, double[]> result = new LinkedHashMap<>();
    for (Object[] r : records) {
        String category = (String) r[0];
        double amount = (double) r[1];
        result.computeIfAbsent(category, k -> new double[2]);
        double[] acc = result.get(category);
        acc[0] += amount; acc[1] += 1;
    }
    return result; // acc[0]=sum, acc[1]=count; average = sum/count
}
```
**Complexity:** O(n). **Pattern:** manual aggregation without a database — database companies like Oracle frequently ask you to reimplement basic relational operations (GROUP BY, JOIN) in plain application code to test fundamentals beyond "just write the SQL."

#### D-11. [Spotify] Shuffle a Playlist (Fisher-Yates)

**Problem:** Implement `shuffle()` returning a random permutation of a playlist, and `reset()` restoring the original order, each call to `shuffle` independent and uniformly random.

**Approach:** Fisher-Yates shuffle — iterate from the last index to the first, swapping each element with a uniformly random earlier-or-equal index.

```java
class PlaylistShuffler {
    private final int[] original;
    private int[] current;
    private final Random random = new Random();
    PlaylistShuffler(int[] tracks) { original = tracks.clone(); current = tracks.clone(); }
    public int[] reset() { current = original.clone(); return current; }
    public int[] shuffle() {
        current = original.clone();
        for (int i = current.length - 1; i > 0; i--) {
            int j = random.nextInt(i + 1);
            int tmp = current[i]; current[i] = current[j]; current[j] = tmp;
        }
        return current;
    }
}
```
**Complexity:** O(n) per shuffle. **Pattern:** Fisher-Yates is THE correct unbiased shuffle algorithm — interviewers specifically check whether candidates avoid naive-but-biased alternatives (e.g., swapping each element with a fully random index including itself in a different loop direction, which is NOT uniformly random).

#### D-12. [Dropbox] Simplify a Unix-Style File Path

**Problem:** Given an absolute Unix-style path (possibly with `.`, `..`, redundant slashes), return the simplified canonical path.

**Approach:** Split on `/`, use a stack: push real directory names, pop on `..` (if non-empty), ignore `.` and empty segments.

```java
String simplifyPath(String path) {
    Deque<String> stack = new ArrayDeque<>();
    for (String part : path.split("/")) {
        if (part.isEmpty() || part.equals(".")) continue;
        if (part.equals("..")) { if (!stack.isEmpty()) stack.pop(); }
        else stack.push(part);
    }
    StringBuilder sb = new StringBuilder();
    for (String dir : stack) sb.insert(0, "/" + dir);
    return sb.length() == 0 ? "/" : sb.toString();
}
```
**Complexity:** O(n). **Pattern:** stack-based path normalization — directly models real file-sync-service path canonicalization logic.

#### D-13. [Atlassian] Detect Cycle in a Directed Graph (Task Dependency Validation)

**Problem:** Given directed task-dependency edges, determine if a cycle exists (invalid dependency graph, e.g., in a Jira-style workflow tool).

**Approach:** DFS with a 3-color marking scheme (white/unvisited, gray/in current recursion stack, black/fully processed) — a back-edge to a gray node indicates a cycle.

```java
boolean hasCycle(int n, List<List<Integer>> graph) {
    int[] color = new int[n]; // 0=white, 1=gray, 2=black
    for (int i = 0; i < n; i++) if (color[i] == 0 && dfs(i, graph, color)) return true;
    return false;
}
private boolean dfs(int node, List<List<Integer>> graph, int[] color) {
    color[node] = 1;
    for (int next : graph.get(node)) {
        if (color[next] == 1) return true;
        if (color[next] == 0 && dfs(next, graph, color)) return true;
    }
    color[node] = 2;
    return false;
}
```
**Complexity:** O(V + E). **Pattern:** the 3-color DFS cycle-detection technique — more robust than a simpler visited-only check for correctly distinguishing "already fully processed, safe" from "currently on the call stack, a cycle."

#### D-14. [Twitter/X] Design a Trending Topics Counter (Sliding Window Top-K)

**Problem:** Track hashtag mention counts over a trailing time window (e.g., last hour) and return the top-K trending hashtags at any query time.

**Approach:** A time-bucketed count structure (e.g., per-minute buckets in a circular buffer) plus a max-heap computed lazily at query time from the summed bucket counts — avoids recomputing from raw events on every query.

```java
class TrendingTopics {
    private final int windowMinutes;
    private final Map<String, int[]> counts = new HashMap<>(); // hashtag -> circular per-minute buckets
    private final int[] bucketMinutes;
    TrendingTopics(int windowMinutes) { this.windowMinutes = windowMinutes; this.bucketMinutes = new int[windowMinutes]; }

    public void recordMention(String hashtag, int currentMinute) {
        counts.computeIfAbsent(hashtag, k -> new int[windowMinutes]);
        int bucketIdx = currentMinute % windowMinutes;
        counts.get(hashtag)[bucketIdx]++;
    }
    public List<String> topK(int k, int currentMinute) {
        PriorityQueue<Map.Entry<String, Integer>> minHeap =
            new PriorityQueue<>(Comparator.comparingInt(Map.Entry::getValue));
        for (Map.Entry<String, int[]> e : counts.entrySet()) {
            int sum = 0;
            for (int v : e.getValue()) sum += v;
            minHeap.offer(Map.entry(e.getKey(), sum));
            if (minHeap.size() > k) minHeap.poll();
        }
        List<String> result = new ArrayList<>();
        while (!minHeap.isEmpty()) result.add(0, minHeap.poll().getKey());
        return result;
    }
}
```
**Complexity:** O(hashtags × windowMinutes) per query (optimizable with incremental sums). **Pattern:** time-bucketed rolling counters + top-K heap — the same structural idea as [ACI-3 Hit Counter](#aci-3-design-a-hit-counter), extended to per-key tracking and ranking.

#### D-15. [Snapchat] Sliding Window Median

**Problem:** Given a stream and window size `k`, return the median of each sliding window.

**Approach:** Two heaps (max-heap for the lower half, min-heap for the upper half) kept balanced in size; removing an arbitrary element that slides out of the window requires "lazy deletion" (mark for removal, clean up when it reaches a heap top).

```java
double[] medianSlidingWindow(int[] nums, int k) {
    TreeMap<Integer, Integer> lowerHalf = new TreeMap<>(Collections.reverseOrder());
    TreeMap<Integer, Integer> upperHalf = new TreeMap<>();
    int lowerSize = 0, upperSize = 0;
    double[] result = new double[nums.length - k + 1];
    for (int i = 0; i < nums.length; i++) {
        int num = nums[i];
        if (lowerSize == 0 || num <= lowerHalf.firstKey()) { lowerHalf.merge(num, 1, Integer::sum); lowerSize++; }
        else { upperHalf.merge(num, 1, Integer::sum); upperSize++; }
        // rebalance so lowerSize == upperSize or lowerSize == upperSize + 1
        while (lowerSize > upperSize + 1) { int mv = lowerHalf.firstKey(); removeOne(lowerHalf, mv); lowerSize--; upperHalf.merge(mv, 1, Integer::sum); upperSize++; }
        while (upperSize > lowerSize) { int mv = upperHalf.firstKey(); removeOne(upperHalf, mv); upperSize--; lowerHalf.merge(mv, 1, Integer::sum); lowerSize++; }
        if (i >= k - 1) {
            result[i - k + 1] = (k % 2 == 1) ? lowerHalf.firstKey()
                : ((double) lowerHalf.firstKey() + upperHalf.firstKey()) / 2.0;
            int out = nums[i - k + 1];
            if (out <= lowerHalf.firstKey()) { removeOne(lowerHalf, out); lowerSize--; }
            else { removeOne(upperHalf, out); upperSize--; }
        }
    }
    return result;
}
private void removeOne(TreeMap<Integer, Integer> map, int key) {
    if (map.merge(key, -1, Integer::sum) == 0) map.remove(key);
}
```
**Complexity:** O(n log k). **Pattern:** the "two balanced heaps for a running median" technique, adapted with `TreeMap` for O(log k) arbitrary-element removal (a plain `PriorityQueue` doesn't support efficient arbitrary removal) — a genuinely hard, high-signal question testing real data-structure depth.

#### D-16. [Expedia] Cheapest Flight Within K Stops

**Problem:** Given flights as weighted edges `(from, to, price)`, find the cheapest price from `src` to `dst` using at most `k` stops (i.e., at most `k+1` edges).

**Approach:** Bellman-Ford-style relaxation limited to `k+1` rounds (a plain Dijkstra doesn't respect the stop-count constraint correctly, since it optimizes purely for cost, potentially using a cheaper-but-longer path that violates the stop limit).

```java
int findCheapestPrice(int n, int[][] flights, int src, int dst, int k) {
    int[] dist = new int[n];
    Arrays.fill(dist, Integer.MAX_VALUE);
    dist[src] = 0;
    for (int i = 0; i <= k; i++) {
        int[] temp = dist.clone();
        for (int[] flight : flights) {
            int u = flight[0], v = flight[1], price = flight[2];
            if (dist[u] != Integer.MAX_VALUE && dist[u] + price < temp[v]) {
                temp[v] = dist[u] + price;
            }
        }
        dist = temp;
    }
    return dist[dst] == Integer.MAX_VALUE ? -1 : dist[dst];
}
```
**Complexity:** O(k × E). **Pattern:** bounded Bellman-Ford — recognizing that a stop-limited shortest path needs round-limited relaxation (not a greedy priority-queue approach) is the key insight travel/booking companies specifically probe for.

#### D-17. [Yahoo] Longest Consecutive Sequence

**Problem:** Given an unsorted array, find the length of the longest run of consecutive integers, in O(n) (no sorting).

**Approach:** Put all numbers in a `HashSet`; for each number that is the START of a sequence (i.e., `num - 1` is not in the set), count forward how long the consecutive run extends.

```java
int longestConsecutive(int[] nums) {
    Set<Integer> set = new HashSet<>();
    for (int n : nums) set.add(n);
    int best = 0;
    for (int n : set) {
        if (!set.contains(n - 1)) { // start of a sequence
            int length = 1;
            while (set.contains(n + length)) length++;
            best = Math.max(best, length);
        }
    }
    return best;
}
```
**Complexity:** O(n) — each number is visited at most twice total across all iterations. **Pattern:** "only start counting from a true sequence start" is the trick that keeps this O(n) instead of O(n²); a very frequently-reported question across many companies.

#### D-18. [Common / multi-company] Product of Array Except Self

**Problem:** Return an array where each element is the product of all other elements, without using division, in O(n).

**Approach:** Two passes — first compute prefix products (product of all elements to the left), then multiply in suffix products (from the right) in a second pass.

```java
int[] productExceptSelf(int[] nums) {
    int n = nums.length;
    int[] result = new int[n];
    result[0] = 1;
    for (int i = 1; i < n; i++) result[i] = result[i - 1] * nums[i - 1];
    int suffix = 1;
    for (int i = n - 1; i >= 0; i--) { result[i] *= suffix; suffix *= nums[i]; }
    return result;
}
```
**Complexity:** O(n) time, O(1) extra space (excluding output). **Pattern:** prefix/suffix accumulation — one of the most universally-reported "easy but must be flawless" phone-screen questions across every company in this guide.

#### D-19. [Common / multi-company] Subarray Sum Equals K

**Problem:** Count the number of contiguous subarrays whose sum equals `k` (array may contain negative numbers).

**Approach:** Prefix-sum + hashmap of prefix-sum frequencies — for each running prefix sum `S`, the number of valid subarrays ending here equals the count of prior prefix sums equal to `S - k`.

```java
int subarraySum(int[] nums, int k) {
    Map<Integer, Integer> prefixCount = new HashMap<>();
    prefixCount.put(0, 1);
    int sum = 0, count = 0;
    for (int num : nums) {
        sum += num;
        count += prefixCount.getOrDefault(sum - k, 0);
        prefixCount.merge(sum, 1, Integer::sum);
    }
    return count;
}
```
**Complexity:** O(n). **Pattern:** prefix-sum + hashmap counting — because the array may contain negatives, a sliding window does NOT work here (window sum isn't monotonic), a common trap interviewers watch for candidates falling into.

#### D-20. [Common / multi-company] Combination Sum

**Problem:** Given distinct candidate numbers and a target, find all unique combinations where candidates sum to the target (each candidate may be reused unlimited times).

**Approach:** Backtracking, always choosing the next candidate at or after the current index to avoid duplicate combinations in different orders.

```java
List<List<Integer>> combinationSum(int[] candidates, int target) {
    List<List<Integer>> result = new ArrayList<>();
    backtrack(candidates, target, 0, new ArrayList<>(), result);
    return result;
}
private void backtrack(int[] candidates, int remaining, int start, List<Integer> current, List<List<Integer>> result) {
    if (remaining == 0) { result.add(new ArrayList<>(current)); return; }
    if (remaining < 0) return;
    for (int i = start; i < candidates.length; i++) {
        current.add(candidates[i]);
        backtrack(candidates, remaining - candidates[i], i, current, result); // i, not i+1: reuse allowed
        current.remove(current.size() - 1);
    }
}
```
**Complexity:** O(2^target) worst case (bounded by the branching factor and target size). **Pattern:** the "pass `i` not `i+1`" detail is what allows reuse of the same candidate — a small but very commonly-tested implementation detail distinguishing this from "Combination Sum II" (no reuse, pass `i+1`).

#### D-21. [Common / multi-company] Course Schedule II (Return the Valid Order)

**Problem:** Same setup as Course Schedule ([D-13](#d-13-atlassian-detect-cycle-in-a-directed-graph-task-dependency-validation)-style dependency graph), but return one valid completion order, or an empty array if impossible.

**Approach:** Kahn's algorithm (same as [ACI-2](#aci-2-course-schedule-detect-cycle-via-topological-sort)), but this time collecting the processing order instead of just a boolean.

```java
int[] findOrder(int numCourses, int[][] prerequisites) {
    List<List<Integer>> graph = new ArrayList<>();
    for (int i = 0; i < numCourses; i++) graph.add(new ArrayList<>());
    int[] indegree = new int[numCourses];
    for (int[] p : prerequisites) { graph.get(p[1]).add(p[0]); indegree[p[0]]++; }
    Queue<Integer> queue = new LinkedList<>();
    for (int i = 0; i < numCourses; i++) if (indegree[i] == 0) queue.offer(i);
    int[] order = new int[numCourses];
    int idx = 0;
    while (!queue.isEmpty()) {
        int course = queue.poll();
        order[idx++] = course;
        for (int next : graph.get(course)) if (--indegree[next] == 0) queue.offer(next);
    }
    return idx == numCourses ? order : new int[0];
}
```
**Complexity:** O(V + E). **Pattern:** topological sort with explicit order capture — the natural "give me the actual schedule, not just yes/no" follow-up interviewers ask after the boolean version.

#### D-22. [Common / multi-company] Design a Search Autocomplete System

**Problem:** Design a system that, as a user types character by character, suggests the top 3 historical sentences matching the current prefix, ranked by frequency (then lexicographically for ties).

**Approach:** A Trie storing sentences at leaf nodes with hit counts; at each character typed, descend the Trie and collect/rank matching completions from the current node's subtree (or maintain a small cached top-3 per node, updated on insert, to avoid a full subtree scan per keystroke).

```java
class AutocompleteSystem {
    class TrieNode {
        Map<Character, TrieNode> children = new HashMap<>();
        Map<String, Integer> sentenceCounts = new HashMap<>(); // sentences passing through this node
    }
    private final TrieNode root = new TrieNode();
    private TrieNode current;
    private StringBuilder prefix = new StringBuilder();

    public void addSentence(String sentence, int count) {
        TrieNode node = root;
        node.sentenceCounts.merge(sentence, count, Integer::sum);
        for (char c : sentence.toCharArray()) {
            node = node.children.computeIfAbsent(c, k -> new TrieNode());
            node.sentenceCounts.merge(sentence, count, Integer::sum);
        }
    }
    public List<String> input(char c) {
        if (c == '#') {
            addSentence(prefix.toString(), 1);
            prefix = new StringBuilder();
            current = root;
            return Collections.emptyList();
        }
        if (current == null) current = root;
        prefix.append(c);
        current = current.children.get(c);
        if (current == null) { current = new TrieNode(); return Collections.emptyList(); } // no matches
        return current.sentenceCounts.entrySet().stream()
            .sorted((a, b) -> a.getValue().equals(b.getValue()) ? a.getKey().compareTo(b.getKey()) : b.getValue() - a.getValue())
            .limit(3).map(Map.Entry::getKey).collect(Collectors.toList());
    }
}
```
**Complexity:** O(sentences at node × log) per keystroke (optimizable by pre-sorting/caching top-3 per node at insert time). **Pattern:** Trie + frequency ranking — this is essentially a miniature version of the classic "Search Autocomplete/Typeahead" HLD case study (see [SYSTEM_DESIGN_INTERVIEW_MASTERY_GUIDE.md](SYSTEM_DESIGN_INTERVIEW_MASTERY_GUIDE.md) §33) implemented as a single in-memory LLD class — a common "LLD version of an HLD topic" interview move.

#### D-23. [Common / multi-company] Random Pick Index (Reservoir Sampling)

**Problem:** Given an array with duplicates, implement `pick(target)` returning a uniformly random index among all indices equal to `target`, without extra memory proportional to occurrence count precomputed per target.

**Approach:** Reservoir sampling — scan the array, and each time you find a matching index, replace the current answer with probability `1/countSoFar`.

```java
class RandomPickIndex {
    private final int[] nums;
    private final Random random = new Random();
    RandomPickIndex(int[] nums) { this.nums = nums; }
    public int pick(int target) {
        int count = 0, result = -1;
        for (int i = 0; i < nums.length; i++) {
            if (nums[i] == target) {
                count++;
                if (random.nextInt(count) == 0) result = i;
            }
        }
        return result;
    }
}
```
**Complexity:** O(n) per pick, O(1) extra space. **Pattern:** reservoir sampling — the standard technique for uniform random selection from a stream/sequence of unknown-in-advance size without storing all matching indices; reused for "random node in a linked list," "random element from a stream," etc.

#### D-24. [Common / multi-company] Implement a Trie (Prefix Tree)

**Problem:** Implement `insert(word)`, `search(word)` (exact match), and `startsWith(prefix)`.

**Approach:** Standard 26-ary (or map-based for wider alphabets) tree, one node per character, with an `isEndOfWord` flag.

```java
class Trie {
    class TrieNode { TrieNode[] children = new TrieNode[26]; boolean isEnd = false; }
    private final TrieNode root = new TrieNode();
    public void insert(String word) {
        TrieNode node = root;
        for (char c : word.toCharArray()) {
            int idx = c - 'a';
            if (node.children[idx] == null) node.children[idx] = new TrieNode();
            node = node.children[idx];
        }
        node.isEnd = true;
    }
    public boolean search(String word) { TrieNode n = find(word); return n != null && n.isEnd; }
    public boolean startsWith(String prefix) { return find(prefix) != null; }
    private TrieNode find(String s) {
        TrieNode node = root;
        for (char c : s.toCharArray()) {
            node = node.children[c - 'a'];
            if (node == null) return null;
        }
        return node;
    }
}
```
**Complexity:** O(L) per operation where L is word/prefix length. **Pattern:** the foundational data structure behind autocomplete ([D-22](#d-22-common--multi-company-design-a-search-autocomplete-system)), spell-check, and IP-routing (longest-prefix-match) systems — worth having memorized cold since it's a building block for several other harder questions.

> **Company-tag bank summary (final):** Part 5 now covers 49 problems (C-1 through C-25, D-1 through D-24) plus the 15 OA problems in [2.8](#28-previously-asked-oa-questions--company-tagged-bank) and 8 more in [9.3](#93-previously-asked-amazon-oa-questions-with-solutions) plus 4 in [9.6](#96-amazon-coding-interview-previously-asked-questions) plus 10 more embedded in the [Part 10](#part-10--company-specific-playbooks) company playbooks — **86 total previously-reported, company-tagged questions with full worked solutions** across this guide. Combine with [LEETCODE_MASTERY_COMPLETE_GUIDE.md](LEETCODE_MASTERY_COMPLETE_GUIDE.md)'s 162 pattern-organized problems for the broadest possible coverage.

### 5.8 Second extended bank (more patterns: Union-Find, segment trees, KMP, MST, bit tricks)

This section broadens pattern coverage into areas not yet touched above: disjoint-set union, segment trees, string-matching algorithms, minimum spanning trees, and more bit-manipulation/math.

#### E-1. [DoorDash] Number of Provinces (Union-Find / DSU)

**Problem:** Given an `n x n` adjacency matrix of direct connections between cities, count the number of provinces (connected groups).

**Approach:** Disjoint-Set Union (Union-Find) with path compression and union by rank — union every directly-connected pair, then count distinct roots.

```java
int findCircleNum(int[][] isConnected) {
    int n = isConnected.length;
    int[] parent = new int[n], rank = new int[n];
    for (int i = 0; i < n; i++) parent[i] = i;
    for (int i = 0; i < n; i++)
        for (int j = i + 1; j < n; j++)
            if (isConnected[i][j] == 1) union(parent, rank, i, j);
    Set<Integer> roots = new HashSet<>();
    for (int i = 0; i < n; i++) roots.add(find(parent, i));
    return roots.size();
}
private int find(int[] parent, int x) {
    if (parent[x] != x) parent[x] = find(parent, parent[x]); // path compression
    return parent[x];
}
private void union(int[] parent, int[] rank, int a, int b) {
    int ra = find(parent, a), rb = find(parent, b);
    if (ra == rb) return;
    if (rank[ra] < rank[rb]) { int t = ra; ra = rb; rb = t; }
    parent[rb] = ra;
    if (rank[ra] == rank[rb]) rank[ra]++;
}
```
**Complexity:** O(n² α(n)) ≈ O(n²) (α = inverse Ackermann, effectively constant). **Pattern:** Union-Find with path compression + union by rank is the standard toolkit for "group membership under merging" problems — reused directly in Kruskal's MST ([E-6](#e-6-snowflake-minimum-spanning-tree-kruskals-algorithm)) below.

#### E-2. [Instacart] Max Consecutive Ones III (Sliding Window with a Budget)

**Problem:** Given a binary array and an integer `k`, find the longest subarray of all 1s if you can flip at most `k` zeros to 1s.

**Approach:** Sliding window tracking the count of zeros inside the window; shrink from the left whenever the zero count exceeds `k`.

```java
int longestOnes(int[] nums, int k) {
    int left = 0, zeroCount = 0, best = 0;
    for (int right = 0; right < nums.length; right++) {
        if (nums[right] == 0) zeroCount++;
        while (zeroCount > k) {
            if (nums[left] == 0) zeroCount--;
            left++;
        }
        best = Math.max(best, right - left + 1);
    }
    return best;
}
```
**Complexity:** O(n). **Pattern:** "sliding window with a budget/tolerance counter" — a generalization of the basic sliding window, common at logistics/delivery companies for "allow up to K late deliveries in a row" style variations.

#### E-3. [Stripe] Evaluate Division (Weighted Graph via Currency Conversion Rates)

**Problem:** Given equations like `a / b = 2.0` and queries like `a / c = ?`, evaluate each query using the given equations (return -1.0 if not determinable).

**Approach:** Build a weighted graph where an edge `a -> b` has weight `a/b` (and the reverse edge `b -> a` has weight `1/(a/b)`); for each query, DFS from the source to the target, multiplying edge weights along the path.

```java
double[] calcEquation(List<List<String>> equations, double[] values, List<List<String>> queries) {
    Map<String, Map<String, Double>> graph = new HashMap<>();
    for (int i = 0; i < equations.size(); i++) {
        String a = equations.get(i).get(0), b = equations.get(i).get(1);
        graph.computeIfAbsent(a, k -> new HashMap<>()).put(b, values[i]);
        graph.computeIfAbsent(b, k -> new HashMap<>()).put(a, 1.0 / values[i]);
    }
    double[] results = new double[queries.size()];
    for (int i = 0; i < queries.size(); i++) {
        String src = queries.get(i).get(0), dst = queries.get(i).get(1);
        if (!graph.containsKey(src) || !graph.containsKey(dst)) { results[i] = -1.0; continue; }
        results[i] = dfs(graph, src, dst, new HashSet<>(), 1.0);
    }
    return results;
}
private double dfs(Map<String, Map<String, Double>> graph, String cur, String target, Set<String> visited, double acc) {
    if (cur.equals(target)) return acc;
    visited.add(cur);
    for (Map.Entry<String, Double> next : graph.get(cur).entrySet()) {
        if (!visited.contains(next.getKey())) {
            double result = dfs(graph, next.getKey(), target, visited, acc * next.getValue());
            if (result != -1.0) return result;
        }
    }
    return -1.0;
}
```
**Complexity:** O(Q × (V + E)) for Q queries. **Pattern:** modeling ratios/rates as a weighted graph and using path-product DFS — directly analogous to real currency-conversion and unit-conversion systems payments companies build.

#### E-4. [Square] Implement strStr() Using KMP (Knuth-Morris-Pratt)

**Problem:** Find the first occurrence of a needle string in a haystack string in O(n + m), better than naive O(n·m).

**Approach:** Precompute the KMP "failure function" (longest proper prefix that's also a suffix, for every prefix of the needle), then scan the haystack using it to avoid re-examining characters on a mismatch.

```java
int strStr(String haystack, String needle) {
    int n = haystack.length(), m = needle.length();
    if (m == 0) return 0;
    int[] lps = buildLPS(needle);
    int i = 0, j = 0;
    while (i < n) {
        if (haystack.charAt(i) == needle.charAt(j)) { i++; j++; if (j == m) return i - j; }
        else if (j > 0) j = lps[j - 1];
        else i++;
    }
    return -1;
}
private int[] buildLPS(String pattern) {
    int m = pattern.length();
    int[] lps = new int[m];
    int len = 0, i = 1;
    while (i < m) {
        if (pattern.charAt(i) == pattern.charAt(len)) { lps[i++] = ++len; }
        else if (len > 0) len = lps[len - 1];
        else lps[i++] = 0;
    }
    return lps;
}
```
**Complexity:** O(n + m). **Pattern:** KMP is the canonical linear-time string-matching algorithm — payment/fintech companies with heavy transaction-log/text-processing pipelines specifically like this since naive substring search doesn't scale to their log volumes.

#### E-5. [Palantir] Range Sum Query — Mutable (Segment Tree)

**Problem:** Support `update(index, value)` and `sumRange(left, right)` on an array, both in O(log n), given the array can be updated repeatedly (ruling out a simple prefix-sum array, which would need O(n) to rebuild on every update).

**Approach:** A segment tree — each node stores the sum of a range; update propagates up to O(log n) ancestor nodes; range query combines O(log n) relevant segments.

```java
class SegmentTree {
    private final int[] tree; private final int n;
    SegmentTree(int[] nums) {
        n = nums.length;
        tree = new int[2 * n];
        for (int i = 0; i < n; i++) tree[n + i] = nums[i];
        for (int i = n - 1; i > 0; i--) tree[i] = tree[2 * i] + tree[2 * i + 1];
    }
    public void update(int index, int value) {
        int pos = index + n;
        tree[pos] = value;
        while (pos > 1) { pos /= 2; tree[pos] = tree[2 * pos] + tree[2 * pos + 1]; }
    }
    public int sumRange(int left, int right) {
        int lo = left + n, hi = right + n + 1, sum = 0;
        while (lo < hi) {
            if ((lo & 1) == 1) sum += tree[lo++];
            if ((hi & 1) == 1) sum += tree[--hi];
            lo /= 2; hi /= 2;
        }
        return sum;
    }
}
```
**Complexity:** O(log n) per update/query, O(n) build. **Pattern:** the iterative "bottom-up" segment tree (as opposed to a recursive top-down tree) is a compact, interview-friendly implementation worth memorizing cold — segment trees generalize to range-min/max/GCD by swapping the combine operation.

#### E-6. [Snowflake] Minimum Spanning Tree (Kruskal's Algorithm)

**Problem:** Given a weighted undirected graph, find the minimum total weight to connect all nodes (a minimum spanning tree).

**Approach:** Kruskal's algorithm — sort all edges by weight ascending, greedily add each edge if it doesn't create a cycle (checked via Union-Find, reusing [E-1](#e-1-doordash-number-of-provinces-union-find--dsu)'s structure).

```java
int minimumSpanningTree(int n, int[][] edges) { // edges: {u, v, weight}
    Arrays.sort(edges, (a, b) -> a[2] - b[2]);
    int[] parent = new int[n];
    for (int i = 0; i < n; i++) parent[i] = i;
    int totalWeight = 0, edgesUsed = 0;
    for (int[] edge : edges) {
        int ru = find(parent, edge[0]), rv = find(parent, edge[1]);
        if (ru != rv) {
            parent[ru] = rv;
            totalWeight += edge[2];
            edgesUsed++;
            if (edgesUsed == n - 1) break;
        }
    }
    return edgesUsed == n - 1 ? totalWeight : -1; // -1 if graph isn't fully connectable
}
private int find(int[] parent, int x) {
    if (parent[x] != x) parent[x] = find(parent, parent[x]);
    return parent[x];
}
```
**Complexity:** O(E log E). **Pattern:** greedy + Union-Find — data-infrastructure companies (network topology cost minimization, data replication placement) frequently frame real problems as MST computation.

#### E-7. [MongoDB] Redundant Connection (Find the Cycle-Causing Edge)

**Problem:** Given a graph that was a tree with one extra edge added (creating exactly one cycle), find that redundant edge.

**Approach:** Process edges in order with Union-Find; the first edge whose two endpoints are already in the same set is the redundant one.

```java
int[] findRedundantConnection(int[][] edges) {
    int n = edges.length;
    int[] parent = new int[n + 1];
    for (int i = 0; i <= n; i++) parent[i] = i;
    for (int[] edge : edges) {
        int ru = find(parent, edge[0]), rv = find(parent, edge[1]);
        if (ru == rv) return edge; // this edge closes a cycle
        parent[ru] = rv;
    }
    return new int[0];
}
private int find(int[] parent, int x) {
    if (parent[x] != x) parent[x] = find(parent, parent[x]);
    return parent[x];
}
```
**Complexity:** O(n α(n)). **Pattern:** another direct Union-Find application — document/data-storage companies use this style of reasoning for detecting redundant/circular references in linked data structures.

#### E-8. [Datadog] Employee Free Time

**Problem:** Given each employee's schedule as a list of non-overlapping intervals (sorted), find the common free time across ALL employees.

**Approach:** Flatten all intervals into one list, sort by start time, merge overlapping intervals (same technique as [C-22](#c-22-apple-merge-intervals)), then the gaps between consecutive merged intervals are the free time.

```java
List<int[]> employeeFreeTime(List<List<int[]>> schedule) {
    List<int[]> all = new ArrayList<>();
    for (List<int[]> emp : schedule) all.addAll(emp);
    all.sort((a, b) -> a[0] - b[0]);
    List<int[]> merged = new ArrayList<>();
    for (int[] interval : all) {
        if (merged.isEmpty() || merged.get(merged.size() - 1)[1] < interval[0]) merged.add(interval);
        else merged.get(merged.size() - 1)[1] = Math.max(merged.get(merged.size() - 1)[1], interval[1]);
    }
    List<int[]> freeTime = new ArrayList<>();
    for (int i = 1; i < merged.size(); i++) {
        if (merged.get(i)[0] > merged.get(i - 1)[1]) {
            freeTime.add(new int[]{merged.get(i - 1)[1], merged.get(i)[0]});
        }
    }
    return freeTime;
}
```
**Complexity:** O(n log n). **Pattern:** flatten-then-merge-then-find-gaps — a common extension of the basic interval-merging pattern, directly modeling real calendar/scheduling-overlap tooling (which Datadog-style observability/on-call scheduling tools need for on-call rotation gap analysis).

#### E-9. [Nvidia] Unique Paths II (Grid DP with Obstacles)

**Problem:** Count the number of unique paths from top-left to bottom-right of a grid, moving only right/down, where some cells are obstacles (blocked).

**Approach:** DP where `dp[i][j]` = 0 if obstacle, else `dp[i-1][j] + dp[i][j-1]`.

```java
int uniquePathsWithObstacles(int[][] grid) {
    int rows = grid.length, cols = grid[0].length;
    int[][] dp = new int[rows][cols];
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            if (grid[i][j] == 1) { dp[i][j] = 0; continue; }
            if (i == 0 && j == 0) { dp[i][j] = 1; continue; }
            int fromTop = i > 0 ? dp[i - 1][j] : 0;
            int fromLeft = j > 0 ? dp[i][j - 1] : 0;
            dp[i][j] = fromTop + fromLeft;
        }
    }
    return dp[rows - 1][cols - 1];
}
```
**Complexity:** O(rows × cols). **Pattern:** grid DP with a "blocked cell = 0 ways" base case — hardware/simulation companies (GPU path/rendering-adjacent framing) like grid-traversal-counting questions as an accessible DP warm-up.

#### E-10. [Qualcomm] Single Number II (Bit Counting, Every Element Appears 3 Times Except One)

**Problem:** Every element in an array appears exactly 3 times except one which appears once — find that one element in O(n) time, O(1) space.

**Approach:** For each of the 32 bit positions, sum the bit across all numbers; if the sum modulo 3 is non-zero, that bit belongs to the unique number.

```java
int singleNumber(int[] nums) {
    int result = 0;
    for (int bit = 0; bit < 32; bit++) {
        int sum = 0;
        for (int num : nums) sum += (num >> bit) & 1;
        if (sum % 3 != 0) result |= (1 << bit);
    }
    return result;
}
```
**Complexity:** O(32n) = O(n). **Pattern:** per-bit counting — a favorite hardware/chip-company question since it mirrors literal bit-level circuit reasoning (each bit position is independent, just like independent wires/gates in hardware).

#### E-11. [IBM] Count Primes (Sieve of Eratosthenes)

**Problem:** Count the number of primes strictly less than `n`.

**Approach:** Sieve of Eratosthenes — mark multiples of each prime starting from 2 as composite, avoiding a naive per-number primality check.

```java
int countPrimes(int n) {
    if (n < 3) return 0;
    boolean[] isComposite = new boolean[n];
    int count = 0;
    for (int i = 2; i < n; i++) {
        if (!isComposite[i]) {
            count++;
            for (long j = (long) i * i; j < n; j += i) isComposite[(int) j] = true;
        }
    }
    return count;
}
```
**Complexity:** O(n log log n). **Pattern:** the Sieve of Eratosthenes — a classic, must-know number-theory algorithm frequently asked at companies with strong CS-fundamentals-heavy interview cultures (legacy enterprise software companies in particular).

#### E-12. [SAP] Task Scheduler (CPU Cooldown Scheduling)

**Problem:** Given tasks (each represented by a letter) and a cooldown period `n` between two same-type tasks, find the minimum total time (including idle slots) to complete all tasks.

**Approach:** Greedy formula based on the most frequent task's count — the most frequent task dictates the minimum "skeleton" length; any leftover idle slots get filled by other tasks, but the true answer is never less than the total task count.

```java
int leastInterval(char[] tasks, int n) {
    int[] freq = new int[26];
    for (char t : tasks) freq[t - 'A']++;
    Arrays.sort(freq);
    int maxFreq = freq[25];
    int idleSlots = (maxFreq - 1) * n;
    for (int i = 24; i >= 0 && freq[i] > 0; i--) {
        idleSlots -= Math.min(freq[i], maxFreq - 1);
    }
    idleSlots = Math.max(0, idleSlots);
    return tasks.length + idleSlots;
}
```
**Complexity:** O(n) (26-bucket counting, effectively linear). **Pattern:** a greedy "fill the gaps" formula derivation — enterprise scheduling-software companies favor this question since it directly models real job-scheduling cooldown constraints (e.g., don't run the same batch job type back-to-back too soon).

#### E-13. [Booking.com] Search in Rotated Sorted Array

**Problem:** Search for a target in a sorted array that has been rotated at an unknown pivot, in O(log n).

**Approach:** Modified binary search — at each step, determine which half (`lo..mid` or `mid..hi`) is properly sorted, then check if the target lies within that sorted half's range to decide which side to recurse into.

```java
int search(int[] nums, int target) {
    int lo = 0, hi = nums.length - 1;
    while (lo <= hi) {
        int mid = (lo + hi) / 2;
        if (nums[mid] == target) return mid;
        if (nums[lo] <= nums[mid]) { // left half is sorted
            if (nums[lo] <= target && target < nums[mid]) hi = mid - 1;
            else lo = mid + 1;
        } else { // right half is sorted
            if (nums[mid] < target && target <= nums[hi]) lo = mid + 1;
            else hi = mid - 1;
        }
    }
    return -1;
}
```
**Complexity:** O(log n). **Pattern:** binary search with a "which half is sorted" check — booking/travel search platforms deal with similarly-structured rotated/paginated sorted result sets (e.g., calendar-wrapped date ranges).

#### E-14. [Robinhood] Find K Pairs with Smallest Sums

**Problem:** Given two sorted arrays and `k`, find the `k` pairs `(a[i], b[j])` with the smallest sums.

**Approach:** Min-heap seeded with the smallest pairing candidates `(a[i], b[0])` for each `i`; each time you pop a pair `(a[i], b[j])`, push the next candidate `(a[i], b[j+1])` if it exists — avoids generating all `n*m` pairs upfront.

```java
List<int[]> kSmallestPairs(int[] a, int[] b, int k) {
    List<int[]> result = new ArrayList<>();
    if (a.length == 0 || b.length == 0) return result;
    PriorityQueue<int[]> minHeap = new PriorityQueue<>((x, y) -> (a[x[0]] + b[x[1]]) - (a[y[0]] + b[y[1]]));
    for (int i = 0; i < Math.min(a.length, k); i++) minHeap.offer(new int[]{i, 0});
    while (k-- > 0 && !minHeap.isEmpty()) {
        int[] idx = minHeap.poll();
        result.add(new int[]{a[idx[0]], b[idx[1]]});
        if (idx[1] + 1 < b.length) minHeap.offer(new int[]{idx[0], idx[1] + 1});
    }
    return result;
}
```
**Complexity:** O(k log k). **Pattern:** lazy heap generation ("only produce the next candidate when needed") — a technique reused for merging sorted streams without materializing the full cross-product, relevant to Robinhood's real-time order-matching/price-level merging systems.

#### E-15. [Coinbase] Longest Palindromic Substring

**Problem:** Find the longest palindromic substring in a string.

**Approach:** Expand around every possible center (both odd-length, single-character centers, and even-length, between-character centers), tracking the longest found.

```java
String longestPalindrome(String s) {
    if (s == null || s.isEmpty()) return "";
    int start = 0, maxLen = 1;
    for (int i = 0; i < s.length(); i++) {
        int len1 = expand(s, i, i), len2 = expand(s, i, i + 1);
        int len = Math.max(len1, len2);
        if (len > maxLen) { maxLen = len; start = i - (len - 1) / 2; }
    }
    return s.substring(start, start + maxLen);
}
private int expand(String s, int left, int right) {
    while (left >= 0 && right < s.length() && s.charAt(left) == s.charAt(right)) { left--; right++; }
    return right - left - 1;
}
```
**Complexity:** O(n²) time, O(1) space (Manacher's algorithm achieves O(n) but is rarely required to be derived live). **Pattern:** expand-around-center is the practical, interview-expected approach; mentioning Manacher's as an O(n) follow-up shows extra depth without needing to implement it under time pressure.

#### E-16. [Affirm] Coin Change (Minimum Coins)

**Problem:** Given coin denominations and a target amount, find the minimum number of coins to make that amount (or -1 if impossible).

**Approach:** Bottom-up DP — `dp[amount]` = minimum coins to make that amount, built up from `dp[0] = 0`.

```java
int coinChange(int[] coins, int amount) {
    int[] dp = new int[amount + 1];
    Arrays.fill(dp, amount + 1); // sentinel for "unreachable"
    dp[0] = 0;
    for (int i = 1; i <= amount; i++) {
        for (int coin : coins) {
            if (coin <= i) dp[i] = Math.min(dp[i], dp[i - coin] + 1);
        }
    }
    return dp[amount] > amount ? -1 : dp[amount];
}
```
**Complexity:** O(amount × coins). **Pattern:** unbounded-knapsack-style DP — buy-now-pay-later/installment fintech companies like this question since it directly echoes minimum-installment-count calculations.

#### E-17. [Chime] Validate a Double-Entry Ledger (Every Transaction Must Net to Zero)

**Problem:** Given a list of ledger entries `(accountId, amount)` grouped by `transactionId`, validate that every transaction's entries sum to exactly zero (proper double-entry bookkeeping).

**Approach:** Group entries by `transactionId`, sum amounts per group, flag any group whose sum isn't zero.

```java
List<String> findUnbalancedTransactions(List<Object[]> entries) { // {transactionId, accountId, amount}
    Map<String, Double> sums = new LinkedHashMap<>();
    for (Object[] entry : entries) {
        String txId = (String) entry[0];
        double amount = (double) entry[2];
        sums.merge(txId, amount, Double::sum);
    }
    List<String> unbalanced = new ArrayList<>();
    for (Map.Entry<String, Double> e : sums.entrySet()) {
        if (Math.abs(e.getValue()) > 1e-9) unbalanced.add(e.getKey());
    }
    return unbalanced;
}
```
**Complexity:** O(n). **Pattern:** grouped-aggregation validation — neobanks/fintechs building ledger systems ask this to test whether candidates understand basic double-entry accounting invariants, plus careful floating-point epsilon comparison (never compare doubles with `==`).

#### E-18. [Wayfair] Kth Smallest Element in a Sorted Matrix

**Problem:** Given an `n x n` matrix where each row and column is sorted ascending, find the `k`-th smallest element.

**Approach:** Binary search on the VALUE range `[matrix[0][0], matrix[n-1][n-1]]`; for a candidate value, count how many elements are ≤ it in O(n) using the sorted-rows-and-columns property (start from the bottom-left corner, move right/up).

```java
int kthSmallest(int[][] matrix, int k) {
    int n = matrix.length;
    int lo = matrix[0][0], hi = matrix[n - 1][n - 1];
    while (lo < hi) {
        int mid = lo + (hi - lo) / 2;
        if (countLessEqual(matrix, mid) < k) lo = mid + 1; else hi = mid;
    }
    return lo;
}
private int countLessEqual(int[][] matrix, int value) {
    int n = matrix.length, count = 0, row = n - 1, col = 0;
    while (row >= 0 && col < n) {
        if (matrix[row][col] <= value) { count += row + 1; col++; }
        else row--;
    }
    return count;
}
```
**Complexity:** O(n log(max - min)). **Pattern:** "binary search on the answer's VALUE range" combined with an O(n) counting helper — a step up from binary-searching an index, and a favorite at companies building product-catalog/pricing-matrix tools.

#### E-19. [Retail-tech, e.g. Target/Best Buy] Minimum Size Subarray Sum

**Problem:** Find the minimal length of a contiguous subarray whose sum is ≥ target (0 if none exists).

**Approach:** Sliding window — expand right, shrink from the left greedily whenever the current window sum already meets the target.

```java
int minSubArrayLen(int target, int[] nums) {
    int left = 0, sum = 0, best = Integer.MAX_VALUE;
    for (int right = 0; right < nums.length; right++) {
        sum += nums[right];
        while (sum >= target) {
            best = Math.min(best, right - left + 1);
            sum -= nums[left++];
        }
    }
    return best == Integer.MAX_VALUE ? 0 : best;
}
```
**Complexity:** O(n). **Pattern:** the "expand then shrink greedily" sliding window shape — retail inventory/basket-threshold questions ("smallest set of items reaching a promo threshold") reduce directly to this.

#### E-20. [Capital One] Linked List Cycle Detection (Floyd's Algorithm)

**Problem:** Determine if a linked list has a cycle, using O(1) extra space.

**Approach:** Two pointers moving at different speeds (slow moves 1 step, fast moves 2); if they ever meet, a cycle exists — if the fast pointer reaches null, there is no cycle.

```java
boolean hasCycle(ListNode head) {
    ListNode slow = head, fast = head;
    while (fast != null && fast.next != null) {
        slow = slow.next;
        fast = fast.next.next;
        if (slow == fast) return true;
    }
    return false;
}
```
**Complexity:** O(n) time, O(1) space. **Pattern:** Floyd's cycle detection ("tortoise and hare") — a fundamental, must-know-cold technique; financial-services companies often ask the natural follow-up "now find where the cycle BEGINS" (reset one pointer to head, advance both one step at a time, they meet at the cycle start — a provable but non-obvious mathematical fact worth memorizing).

#### E-21. [American Express] Valid Parenthesis String (With Wildcards)

**Problem:** Given a string containing `(`, `)`, and `*` (which can be treated as `(`, `)`, or empty), determine if the string can be a valid parenthesization.

**Approach:** Track a range `[loBalance, hiBalance]` of possible open-parenthesis counts as you scan left to right, updating the range for each character type; the string is valid if `loBalance` can reach exactly 0 by the end (clamping `loBalance` at 0, never negative).

```java
boolean checkValidString(String s) {
    int loBalance = 0, hiBalance = 0;
    for (char c : s.toCharArray()) {
        if (c == '(') { loBalance++; hiBalance++; }
        else if (c == ')') { loBalance--; hiBalance--; }
        else { loBalance--; hiBalance++; } // '*': treat as ')' for lo, '(' for hi
        if (hiBalance < 0) return false; // too many ')' even in the best case
        loBalance = Math.max(loBalance, 0); // can't have negative open count
    }
    return loBalance == 0;
}
```
**Complexity:** O(n) time, O(1) space. **Pattern:** tracking a feasible RANGE instead of a single value — a technique that generalizes whenever a problem has "wildcard"/ambiguous elements with multiple possible interpretations.

#### E-22. [Fidelity] Merge Two Sorted Arrays In-Place

**Problem:** Given two sorted arrays where the first has enough trailing empty space, merge the second into the first in sorted order, in-place.

**Approach:** Fill from the BACK (largest elements first) to avoid overwriting not-yet-processed elements in the first array.

```java
void merge(int[] nums1, int m, int[] nums2, int n) {
    int i = m - 1, j = n - 1, k = m + n - 1;
    while (j >= 0) {
        if (i >= 0 && nums1[i] > nums2[j]) nums1[k--] = nums1[i--];
        else nums1[k--] = nums2[j--];
    }
}
```
**Complexity:** O(m + n) time, O(1) extra space. **Pattern:** "merge from the back" is the key trick avoiding an O(m+n) auxiliary array — a very frequently-reported easy-but-must-be-flawless question, including at financial-data-processing companies merging sorted transaction batches.

#### E-23. [Zoom] Meeting Conflict Checker (Can Attend All Meetings)

**Problem:** Given a list of meeting intervals, determine if a person could attend all of them (no two meetings overlap).

**Approach:** Sort by start time, then check each consecutive pair for overlap.

```java
boolean canAttendMeetings(int[][] intervals) {
    Arrays.sort(intervals, (a, b) -> a[0] - b[0]);
    for (int i = 1; i < intervals.length; i++) {
        if (intervals[i][0] < intervals[i - 1][1]) return false;
    }
    return true;
}
```
**Complexity:** O(n log n). **Pattern:** the simplest member of the interval-overlap family (compare to [Meeting Rooms II](#c-24-uber-meeting-rooms-ii) which needs a room COUNT, not just a yes/no) — video-conferencing/scheduling companies often start with this easier variant before a harder follow-up.

#### E-24. [Slack] Per-Channel Message Rate Limiter (Sliding Window Counter)

**Problem:** Design a rate limiter allowing at most `N` messages per channel per rolling 60-second window.

**Approach:** Per-channel timestamp deque (same skeleton as the [Hit Counter](#aci-3-design-a-hit-counter)), rejecting a new message if the deque already has `N` timestamps within the last 60 seconds.

```java
class ChannelRateLimiter {
    private final int maxPerWindow; private final long windowMillis;
    private final Map<String, Deque<Long>> channelTimestamps = new HashMap<>();
    ChannelRateLimiter(int maxPerWindow, long windowMillis) { this.maxPerWindow = maxPerWindow; this.windowMillis = windowMillis; }

    public synchronized boolean tryPost(String channelId, long nowMillis) {
        Deque<Long> timestamps = channelTimestamps.computeIfAbsent(channelId, k -> new ArrayDeque<>());
        while (!timestamps.isEmpty() && timestamps.peekFirst() <= nowMillis - windowMillis) timestamps.pollFirst();
        if (timestamps.size() >= maxPerWindow) return false;
        timestamps.offerLast(nowMillis);
        return true;
    }
}
```
**Complexity:** O(1) amortized per call. **Pattern:** the sliding-window-log rate limiter — a genuinely common LLD/mini-system question at any messaging/collaboration-tool company, directly reusing the rolling-window counter idea from [ACI-3](#aci-3-design-a-hit-counter) and [D-14](#d-14-twitterx-design-a-trending-topics-counter-sliding-window-top-k).

> **Extended bank summary:** Part 5.7 and 5.8 together add 36 more problems (D-1 through D-24, E-1 through E-24 — note some numbering overlaps by section, 24+24=48 total across both extended sections). Combined with the original 25 (C-1 to C-25) and the OA/Amazon/company-playbook problems elsewhere in this guide, this guide now contains **well over 100 previously-reported, company-tagged coding questions with full worked Java solutions**, spanning arrays, strings, trees, graphs, DP, greedy, heaps, tries, Union-Find, segment trees, and string-matching algorithms.

### 5.9 Third extended bank (infrastructure, security, and SaaS-platform companies)

A final round covering infrastructure, cloud/security, and SaaS-platform companies, plus a few remaining classic patterns (consistent hashing, rolling hash, state machines).

#### F-1. [Nutanix] Distributed Lock via Lease + Compare-and-Swap

**Problem:** Design a simple distributed lock so only one process at a time can hold a named resource lock, safe even if a lock holder crashes without releasing it.

**Approach:** A lock record with an owner ID and an expiry timestamp (lease); acquiring requires a conditional write ("set owner=me, expiry=now+leaseDuration ONLY IF currently unowned OR expired") — this is the same atomic-conditional-write idea used throughout this guide's HLD case studies (e.g., [6.4](#64-case-study-design-an-e-commerce-cart--inventory-system)), applied to distributed locking.

```java
class DistributedLock {
    private String owner; private long expiresAtMillis;
    public synchronized boolean tryAcquire(String requester, long leaseDurationMillis, long nowMillis) {
        if (owner == null || nowMillis > expiresAtMillis) { // unowned or lease expired
            owner = requester;
            expiresAtMillis = nowMillis + leaseDurationMillis;
            return true;
        }
        return owner.equals(requester); // re-entrant if same owner
    }
    public synchronized void release(String requester) {
        if (requester.equals(owner)) { owner = null; }
    }
}
```
**Complexity:** O(1) per operation. **Pattern:** lease-based locking with automatic expiry is the standard way to avoid a permanently-stuck lock after a crashed holder — infrastructure/virtualization companies ask this to test whether candidates account for failure modes, not just the happy path.

#### F-2. [VMware] Virtual Machine Bin Packing (First Fit Decreasing)

**Problem:** Given VM memory requirements and identical physical host capacities, minimize the number of hosts needed to place all VMs.

**Approach:** First Fit Decreasing — sort VMs by size descending, place each into the first host with enough remaining capacity, opening a new host if none fits (a well-known good-approximation greedy for bin packing, which is NP-hard to solve optimally).

```java
int minHostsNeeded(int[] vmSizes, int hostCapacity) {
    Integer[] sorted = Arrays.stream(vmSizes).boxed().sorted(Collections.reverseOrder()).toArray(Integer[]::new);
    List<Integer> hostRemainingCapacity = new ArrayList<>();
    for (int vm : sorted) {
        boolean placed = false;
        for (int i = 0; i < hostRemainingCapacity.size(); i++) {
            if (hostRemainingCapacity.get(i) >= vm) {
                hostRemainingCapacity.set(i, hostRemainingCapacity.get(i) - vm);
                placed = true; break;
            }
        }
        if (!placed) hostRemainingCapacity.add(hostCapacity - vm);
    }
    return hostRemainingCapacity.size();
}
```
**Complexity:** O(n × hosts) ≈ O(n²) worst case. **Pattern:** bin packing via greedy approximation — virtualization/cloud-infrastructure companies frame this directly around real VM/container placement and bin-packing cost optimization.

#### F-3. [Samsung] Simple Publish-Subscribe System (Observer Pattern)

**Problem:** Design a class supporting `subscribe(topic, listener)`, `unsubscribe`, and `publish(topic, message)` notifying all subscribed listeners.

**Approach:** The Observer design pattern — a `Map<Topic, List<Listener>>` registry, `publish` iterates and invokes each registered listener.

```java
interface MessageListener { void onMessage(String topic, String message); }

class PubSubSystem {
    private final Map<String, List<MessageListener>> subscribers = new ConcurrentHashMap<>();
    public void subscribe(String topic, MessageListener listener) {
        subscribers.computeIfAbsent(topic, k -> new CopyOnWriteArrayList<>()).add(listener);
    }
    public void unsubscribe(String topic, MessageListener listener) {
        if (subscribers.containsKey(topic)) subscribers.get(topic).remove(listener);
    }
    public void publish(String topic, String message) {
        for (MessageListener listener : subscribers.getOrDefault(topic, Collections.emptyList())) {
            listener.onMessage(topic, message);
        }
    }
}
```
**Complexity:** O(subscribers) per publish. **Pattern:** the Observer pattern is the foundation of essentially all event-driven/pub-sub systems (from UI frameworks to message brokers) — using `CopyOnWriteArrayList` here is a deliberate concurrency choice favoring safe iteration during publish over write performance, worth calling out explicitly since subscribe/unsubscribe are rarer than publish in most real systems.

#### F-4. [SaaS/Analytics] Top-K Word Frequency in a Large Text

**Problem:** Given a large text, return the `k` most frequent words.

**Approach:** Tokenize, count via a frequency map, then use a min-heap of size `k` (same bounded-heap pattern as [C-14](#c-14-microsoft-copy-list-with-random-pointer)-adjacent top-K problems) rather than sorting the entire frequency map.

```java
List<String> topKFrequentWords(String text, int k) {
    Map<String, Integer> freq = new HashMap<>();
    for (String word : text.toLowerCase().split("\\W+")) {
        if (!word.isEmpty()) freq.merge(word, 1, Integer::sum);
    }
    PriorityQueue<Map.Entry<String, Integer>> minHeap = new PriorityQueue<>(
        (a, b) -> a.getValue().equals(b.getValue()) ? b.getKey().compareTo(a.getKey()) : a.getValue() - b.getValue());
    for (Map.Entry<String, Integer> entry : freq.entrySet()) {
        minHeap.offer(entry);
        if (minHeap.size() > k) minHeap.poll();
    }
    LinkedList<String> result = new LinkedList<>();
    while (!minHeap.isEmpty()) result.addFirst(minHeap.poll().getKey());
    return result;
}
```
**Complexity:** O(n log k). **Pattern:** text-analytics companies universally ask some variant of this — the tie-break rule (here, lexicographically smaller word wins ties) is exactly the kind of easily-missed requirement worth explicitly clarifying before coding.

#### F-5. [Automotive/EV, e.g. Tesla-style] Gas Station Reachability (Jump Game Variant)

**Problem:** Given fuel-range-per-position along a route, determine if you can reach the final position starting from position 0, where each position's value is the maximum further distance you can jump from there.

**Approach:** Greedy — track the farthest reachable position seen so far while scanning left to right; if the current position ever exceeds the farthest reachable point, it's unreachable.

```java
boolean canReachEnd(int[] maxJump) {
    int farthestReachable = 0;
    for (int i = 0; i < maxJump.length; i++) {
        if (i > farthestReachable) return false; // this position is unreachable
        farthestReachable = Math.max(farthestReachable, i + maxJump[i]);
    }
    return true;
}
```
**Complexity:** O(n). **Pattern:** the "greedy farthest-reachable tracker" pattern (classic "Jump Game") — automotive/EV route-planning problems (range anxiety, charging-station reachability) reduce directly to this well-known greedy shape.

#### F-6. [Financial services, e.g. Wells Fargo] Detect and Remove a Cycle in a Linked List

**Problem:** Given a linked list that may contain a cycle, remove the cycle (if present) so the list becomes a proper terminating list.

**Approach:** Detect the cycle with Floyd's algorithm ([E-20](#e-20-capital-one-linked-list-cycle-detection-floyds-algorithm)), find the cycle's starting node using the "reset one pointer to head" technique, then walk to the node just before the cycle start and set its `next` to `null`.

```java
void removeCycle(ListNode head) {
    ListNode slow = head, fast = head;
    boolean hasCycle = false;
    while (fast != null && fast.next != null) {
        slow = slow.next; fast = fast.next.next;
        if (slow == fast) { hasCycle = true; break; }
    }
    if (!hasCycle) return;
    slow = head;
    if (slow == fast) { // cycle starts at head itself
        while (fast.next != slow) fast = fast.next;
    } else {
        while (slow.next != fast.next) { slow = slow.next; fast = fast.next; }
    }
    fast.next = null;
}
```
**Complexity:** O(n) time, O(1) space. **Pattern:** the natural "now fix it, not just detect it" follow-up to cycle detection — a common two-part question progression at companies handling large linked internal data structures (transaction chains, audit trails).

#### F-7. [Fraud/Risk, e.g. Discover] Sliding Window Anomaly Detection (Moving Average + Std Dev)

**Problem:** Given a stream of transaction amounts, flag a transaction as anomalous if it's more than 3 standard deviations from the trailing window's mean.

**Approach:** Maintain a fixed-size sliding window with running sum and running sum-of-squares (updated incrementally, not recomputed from scratch each time) to get O(1) mean/variance per new value.

```java
class AnomalyDetector {
    private final int windowSize;
    private final Deque<Double> window = new ArrayDeque<>();
    private double sum = 0, sumSquares = 0;
    AnomalyDetector(int windowSize) { this.windowSize = windowSize; }

    public boolean isAnomalous(double value) {
        if (window.size() < windowSize) { addToWindow(value); return false; } // not enough history yet
        double mean = sum / window.size();
        double variance = (sumSquares / window.size()) - (mean * mean);
        double stdDev = Math.sqrt(Math.max(0, variance));
        boolean anomalous = stdDev > 0 && Math.abs(value - mean) > 3 * stdDev;
        addToWindow(value);
        return anomalous;
    }
    private void addToWindow(double value) {
        window.addLast(value); sum += value; sumSquares += value * value;
        if (window.size() > windowSize) {
            double removed = window.pollFirst();
            sum -= removed; sumSquares -= removed * removed;
        }
    }
}
```
**Complexity:** O(1) per new value. **Pattern:** incremental (streaming) statistics — computing mean/variance without re-scanning the whole window on every update is the key efficiency insight fraud-detection and observability companies specifically look for.

#### F-8. [Splunk] Simple Log Line Tokenizer / Field Extractor

**Problem:** Given a log line format like `key1=value1 key2="value with spaces" key3=value3`, parse it into a `Map<String,String>` of fields, handling quoted values containing spaces.

**Approach:** A small hand-written state-machine parser (rather than a single complex regex) — scan character by character, tracking whether currently inside a quoted value.

```java
Map<String, String> parseLogLine(String line) {
    Map<String, String> fields = new LinkedHashMap<>();
    int i = 0, n = line.length();
    while (i < n) {
        while (i < n && line.charAt(i) == ' ') i++;
        int keyStart = i;
        while (i < n && line.charAt(i) != '=') i++;
        if (i >= n) break;
        String key = line.substring(keyStart, i);
        i++; // skip '='
        StringBuilder value = new StringBuilder();
        if (i < n && line.charAt(i) == '"') {
            i++;
            while (i < n && line.charAt(i) != '"') value.append(line.charAt(i++));
            i++; // skip closing quote
        } else {
            while (i < n && line.charAt(i) != ' ') value.append(line.charAt(i++));
        }
        fields.put(key, value.toString());
    }
    return fields;
}
```
**Complexity:** O(n). **Pattern:** hand-written recursive-descent-style parsing — log-analytics companies frequently prefer this over "just use a regex" to test whether candidates can reason carefully about parser state and edge cases (quoted values, embedded `=` inside quotes).

#### F-9. [Network security, e.g. Palo Alto Networks] IP CIDR Range Overlap Checker

**Problem:** Given a list of CIDR blocks (e.g., `"192.168.1.0/24"`), determine if any two overlap.

**Approach:** Convert each CIDR block to a `[startIP, endIP]` numeric range (parse the base IP to a 32-bit integer, compute the range size from the prefix length), then sort by start and check for overlaps like a standard interval-overlap problem ([C-22](#c-22-apple-merge-intervals) family).

```java
boolean hasOverlappingCIDRs(String[] cidrs) {
    List<long[]> ranges = new ArrayList<>();
    for (String cidr : cidrs) {
        String[] parts = cidr.split("/");
        long ip = ipToLong(parts[0]);
        int prefixLen = Integer.parseInt(parts[1]);
        long blockSize = 1L << (32 - prefixLen);
        ranges.add(new long[]{ip, ip + blockSize - 1});
    }
    ranges.sort((a, b) -> Long.compare(a[0], b[0]));
    for (int i = 1; i < ranges.size(); i++) {
        if (ranges.get(i)[0] <= ranges.get(i - 1)[1]) return true;
    }
    return false;
}
private long ipToLong(String ip) {
    String[] octets = ip.split("\\.");
    long result = 0;
    for (String octet : octets) result = (result << 8) + Integer.parseInt(octet);
    return result;
}
```
**Complexity:** O(n log n). **Pattern:** domain-specific encoding (CIDR → numeric range) followed by the standard interval-overlap technique — network-security companies specifically test whether candidates can correctly translate a networking concept into a well-known algorithmic shape.

#### F-10. [Cloudflare] Circuit Breaker State Machine

**Problem:** Implement a circuit breaker with three states (CLOSED = calls pass through normally, OPEN = calls fail fast without attempting the real operation, HALF_OPEN = allow one trial call to test recovery) that trips to OPEN after too many consecutive failures, and attempts recovery after a cooldown.

**Approach:** An explicit state-machine class tracking consecutive failure count and the timestamp of when it tripped, with clear transition rules per state.

```java
enum CircuitState { CLOSED, OPEN, HALF_OPEN }

class CircuitBreaker {
    private CircuitState state = CircuitState.CLOSED;
    private int consecutiveFailures = 0;
    private long openedAtMillis;
    private final int failureThreshold; private final long cooldownMillis;
    CircuitBreaker(int failureThreshold, long cooldownMillis) {
        this.failureThreshold = failureThreshold; this.cooldownMillis = cooldownMillis;
    }
    public synchronized boolean allowRequest(long nowMillis) {
        if (state == CircuitState.OPEN && nowMillis - openedAtMillis >= cooldownMillis) {
            state = CircuitState.HALF_OPEN;
        }
        return state != CircuitState.OPEN;
    }
    public synchronized void recordSuccess() {
        consecutiveFailures = 0;
        state = CircuitState.CLOSED;
    }
    public synchronized void recordFailure(long nowMillis) {
        consecutiveFailures++;
        if (state == CircuitState.HALF_OPEN || consecutiveFailures >= failureThreshold) {
            state = CircuitState.OPEN;
            openedAtMillis = nowMillis;
        }
    }
}
```
**Complexity:** O(1) per call. **Pattern:** the State design pattern applied to resilience engineering — a very common CDN/networking-infrastructure LLD question, directly complementing the retry-with-backoff pattern from [Netflix's rate-limited client](#106-netflix) example.

#### F-11. [Akamai] Consistent Hashing Ring

**Problem:** Implement a consistent-hashing ring mapping keys to nodes, supporting `addNode`, `removeNode`, and `getNode(key)`, such that adding/removing a node remaps only a small fraction of keys (not all of them, unlike naive modulo hashing).

**Approach:** A sorted map (`TreeMap<Long, Node>`) of hash-ring positions; each physical node is hashed to several virtual points on the ring (to smooth out load distribution); `getNode` finds the next ring position clockwise from a key's hash.

```java
class ConsistentHashRing {
    private final TreeMap<Long, String> ring = new TreeMap<>();
    private final int virtualNodesPerNode;
    ConsistentHashRing(int virtualNodesPerNode) { this.virtualNodesPerNode = virtualNodesPerNode; }

    public void addNode(String node) {
        for (int i = 0; i < virtualNodesPerNode; i++) ring.put(hash(node + "#" + i), node);
    }
    public void removeNode(String node) {
        for (int i = 0; i < virtualNodesPerNode; i++) ring.remove(hash(node + "#" + i));
    }
    public String getNode(String key) {
        if (ring.isEmpty()) return null;
        long h = hash(key);
        Map.Entry<Long, String> entry = ring.ceilingEntry(h);
        return entry != null ? entry.getValue() : ring.firstEntry().getValue();
    }
    private long hash(String s) { return s.hashCode() & 0xFFFFFFFFL; } // simplified; production uses MD5/MurmurHash
}
```
**Complexity:** O(log(nodes × virtualNodes)) per operation. **Pattern:** consistent hashing with virtual nodes — the foundational technique behind CDN edge-node assignment, distributed cache sharding, and distributed database partitioning (see [SYSTEM_DESIGN_INTERVIEW_MASTERY_GUIDE.md](SYSTEM_DESIGN_INTERVIEW_MASTERY_GUIDE.md) §14 for the full theory); CDN companies ask this as both a coding AND conceptual question.

#### F-12. [Twilio] Retry Queue with Dead Letter Queue

**Problem:** Design a message-processing queue that retries failed messages up to `maxRetries` times with backoff, then routes permanently-failing messages to a separate "dead letter" queue for manual inspection.

**Approach:** Wrap each message with a retry-count field; on failure, either re-enqueue (incrementing the count, with a delay) or move to the dead-letter queue once `maxRetries` is exceeded.

```java
class RetryableMessage {
    final String payload; int retryCount = 0;
    RetryableMessage(String payload) { this.payload = payload; }
}
class RetryQueueProcessor {
    private final Queue<RetryableMessage> mainQueue = new LinkedList<>();
    private final List<RetryableMessage> deadLetterQueue = new ArrayList<>();
    private final int maxRetries;
    RetryQueueProcessor(int maxRetries) { this.maxRetries = maxRetries; }

    public void enqueue(String payload) { mainQueue.offer(new RetryableMessage(payload)); }
    public void processNext(Function<String, Boolean> handler) {
        RetryableMessage msg = mainQueue.poll();
        if (msg == null) return;
        boolean success = handler.apply(msg.payload);
        if (!success) {
            msg.retryCount++;
            if (msg.retryCount > maxRetries) deadLetterQueue.add(msg);
            else mainQueue.offer(msg); // in production: re-enqueue with a delay via a scheduled executor
        }
    }
}
```
**Complexity:** O(1) per message processed. **Pattern:** the dead-letter-queue pattern is a foundational reliability building block for any message-queue-based system (SQS, Kafka, RabbitMQ all support this natively) — messaging/communications-API companies expect familiarity with this exact failure-handling shape.

#### F-13. [HubSpot] Contact Deduplication (Union-Find on Fuzzy Match Criteria)

**Problem:** Given contacts that may be duplicates if they share an email OR a phone number (even transitively — contact A matches B via email, B matches C via phone, so A/B/C are all one entity), group them into merged entities.

**Approach:** Union-Find where each contact starts in its own set; union any two contacts sharing an email or phone number; final groups are the connected components (reusing the exact Union-Find skeleton from [E-1](#e-1-doordash-number-of-provinces-union-find--dsu)).

```java
Map<Integer, List<Integer>> deduplicateContacts(List<String> emails, List<String> phones) {
    int n = emails.size();
    int[] parent = new int[n];
    for (int i = 0; i < n; i++) parent[i] = i;
    Map<String, Integer> emailFirstSeen = new HashMap<>(), phoneFirstSeen = new HashMap<>();
    for (int i = 0; i < n; i++) {
        if (emailFirstSeen.containsKey(emails.get(i))) union(parent, emailFirstSeen.get(emails.get(i)), i);
        else emailFirstSeen.put(emails.get(i), i);
        if (phoneFirstSeen.containsKey(phones.get(i))) union(parent, phoneFirstSeen.get(phones.get(i)), i);
        else phoneFirstSeen.put(phones.get(i), i);
    }
    Map<Integer, List<Integer>> groups = new HashMap<>();
    for (int i = 0; i < n; i++) groups.computeIfAbsent(find(parent, i), k -> new ArrayList<>()).add(i);
    return groups;
}
private int find(int[] parent, int x) { if (parent[x] != x) parent[x] = find(parent, parent[x]); return parent[x]; }
private void union(int[] parent, int a, int b) { parent[find(parent, a)] = find(parent, b); }
```
**Complexity:** O(n α(n)). **Pattern:** Union-Find for "transitive fuzzy matching" — CRM/SaaS companies frequently ask this exact framing since deduplicating records that match via ANY of several transitive keys is a genuinely common real feature.

#### F-14. [Zendesk] SLA Deadline Tracker (Min-Heap of Deadlines)

**Problem:** Design a system tracking support tickets with SLA deadlines, supporting `addTicket(ticketId, deadline)` and `getNextBreachingTicket(currentTime)` (the ticket closest to breaching its SLA, or already breached).

**Approach:** A min-heap keyed by deadline; peek gives the next-most-urgent ticket without needing to scan all tickets.

```java
class SLATracker {
    private final PriorityQueue<long[]> minHeap = new PriorityQueue<>((a, b) -> Long.compare(a[1], b[1])); // {ticketId, deadline}
    private final Set<Long> cancelled = new HashSet<>();

    public void addTicket(long ticketId, long deadline) { minHeap.offer(new long[]{ticketId, deadline}); }
    public void resolveTicket(long ticketId) { cancelled.add(ticketId); } // lazy deletion
    public Long getNextBreachingTicket(long currentTime) {
        while (!minHeap.isEmpty() && cancelled.contains(minHeap.peek()[0])) minHeap.poll();
        if (minHeap.isEmpty()) return null;
        return minHeap.peek()[1] <= currentTime ? minHeap.peek()[0] : null; // null if none currently breaching
    }
}
```
**Complexity:** O(log n) per operation (amortized, accounting for lazy deletion cleanup). **Pattern:** min-heap + lazy deletion (mark-as-cancelled rather than an expensive heap removal) — customer-support/ITSM platforms need exactly this shape for SLA/deadline-driven prioritization.

#### F-15. [Asana] Critical Path in a Task Dependency DAG

**Problem:** Given tasks with durations and dependency edges (a DAG), find the minimum total project completion time (the "critical path" — the longest path through the dependency graph, since that's the true bottleneck).

**Approach:** Topological sort (reusing [D-21](#d-21-common--multi-company-course-schedule-ii-return-the-valid-order)'s Kahn's algorithm skeleton), then DP over the topological order: `earliestFinish[task] = duration[task] + max(earliestFinish[dependency] for each dependency)`.

```java
int criticalPathLength(int n, int[] duration, int[][] edges) { // edges: {from, to}
    List<List<Integer>> graph = new ArrayList<>();
    int[] indegree = new int[n];
    for (int i = 0; i < n; i++) graph.add(new ArrayList<>());
    for (int[] e : edges) { graph.get(e[0]).add(e[1]); indegree[e[1]]++; }
    Queue<Integer> queue = new LinkedList<>();
    int[] earliestFinish = new int[n];
    for (int i = 0; i < n; i++) if (indegree[i] == 0) { queue.offer(i); earliestFinish[i] = duration[i]; }
    int maxFinish = 0;
    while (!queue.isEmpty()) {
        int task = queue.poll();
        maxFinish = Math.max(maxFinish, earliestFinish[task]);
        for (int next : graph.get(task)) {
            earliestFinish[next] = Math.max(earliestFinish[next], earliestFinish[task] + duration[next]);
            if (--indegree[next] == 0) queue.offer(next);
        }
    }
    return maxFinish;
}
```
**Complexity:** O(V + E). **Pattern:** "topological sort + DP for longest path in a DAG" — project-management SaaS tools directly need this for their "project timeline"/Gantt-chart critical-path features; note that longest-path is NP-hard on general graphs but tractable in O(V+E) specifically because a DAG has no cycles.

#### F-16. [Figma] Overlapping Rectangles Detection

**Problem:** Given a list of axis-aligned rectangles (as `[x1,y1,x2,y2]`), determine if any two overlap.

**Approach:** Two rectangles do NOT overlap if one is entirely to the left, right, above, or below the other; check the negation of that condition pairwise, or for large inputs use a sweep-line approach over x-coordinates with an interval tree on active y-ranges.

```java
boolean hasOverlap(int[][] rectangles) {
    for (int i = 0; i < rectangles.length; i++) {
        for (int j = i + 1; j < rectangles.length; j++) {
            if (overlaps(rectangles[i], rectangles[j])) return true;
        }
    }
    return false;
}
private boolean overlaps(int[] a, int[] b) {
    boolean noOverlap = a[2] <= b[0] || b[2] <= a[0] || a[3] <= b[1] || b[3] <= a[1];
    return !noOverlap;
}
```
**Complexity:** O(n²) naive pairwise (O(n log n) achievable via a sweep-line + interval-tree approach for large n). **Pattern:** "negate the easy non-overlap condition" is the standard trick for 2D/axis-aligned overlap checks — design-tool companies (Figma, Canva-style) ask this directly since it's core to their canvas/collision-detection logic.

#### F-17. [Canva] Simplify an Image Aspect Ratio (GCD)

**Problem:** Given an image width and height, return the simplified aspect ratio (e.g., 1920x1080 → 16:9).

**Approach:** Compute the greatest common divisor via the Euclidean algorithm, then divide both dimensions by it.

```java
String simplifyAspectRatio(int width, int height) {
    int divisor = gcd(width, height);
    return (width / divisor) + ":" + (height / divisor);
}
private int gcd(int a, int b) { return b == 0 ? a : gcd(b, a % b); }
```
**Complexity:** O(log(min(width, height))). **Pattern:** the Euclidean algorithm for GCD — a tiny but genuinely useful building block (also underlies fraction simplification, least-common-multiple calculations, and cycle-length math in several harder problems).

#### F-18. [DocuSign] Rabin-Karp Rolling Hash Substring Search

**Problem:** Find all occurrences of a pattern in a text using a rolling hash (useful for template placeholder matching, e.g., finding all instances of `{{signature_field}}` efficiently across many documents).

**Approach:** Compute a rolling hash of the pattern and of each equal-length window of the text, sliding the window in O(1) per shift by removing the leaving character's contribution and adding the entering character's; only do a full character comparison when hashes match (to guard against hash collisions).

```java
List<Integer> rabinKarpSearch(String text, String pattern) {
    List<Integer> matches = new ArrayList<>();
    int n = text.length(), m = pattern.length();
    if (m > n) return matches;
    long base = 256, mod = 1_000_000_007L;
    long patternHash = 0, windowHash = 0, highOrder = 1;
    for (int i = 0; i < m - 1; i++) highOrder = (highOrder * base) % mod;
    for (int i = 0; i < m; i++) {
        patternHash = (patternHash * base + pattern.charAt(i)) % mod;
        windowHash = (windowHash * base + text.charAt(i)) % mod;
    }
    for (int i = 0; i <= n - m; i++) {
        if (windowHash == patternHash && text.substring(i, i + m).equals(pattern)) matches.add(i);
        if (i < n - m) {
            windowHash = ((windowHash - text.charAt(i) * highOrder % mod + mod) * base + text.charAt(i + m)) % mod;
        }
    }
    return matches;
}
```
**Complexity:** O(n + m) average case. **Pattern:** rolling hash — the alternative to KMP ([E-4](#e-4-square-implement-strstr-using-kmp-knuth-morris-pratt)) for substring search, and the same rolling-hash idea generalizes to finding duplicate substrings, plagiarism detection, and document-similarity checks (all directly relevant to a document-signing platform).

#### F-19. [Okta] Role-Based Access Control Permission Check

**Problem:** Given a hierarchy of roles (a role can inherit permissions from parent roles) and a user's assigned role, determine if the user has a specific permission.

**Approach:** Model roles as a tree/DAG; a permission check walks up the inheritance chain (or does a BFS/DFS if roles can have multiple parents) checking each ancestor role's directly-granted permissions.

```java
class RBACChecker {
    private final Map<String, Set<String>> rolePermissions = new HashMap<>(); // role -> directly granted permissions
    private final Map<String, List<String>> roleParents = new HashMap<>(); // role -> parent roles

    public void grantPermission(String role, String permission) {
        rolePermissions.computeIfAbsent(role, k -> new HashSet<>()).add(permission);
    }
    public void addParentRole(String role, String parent) {
        roleParents.computeIfAbsent(role, k -> new ArrayList<>()).add(parent);
    }
    public boolean hasPermission(String role, String permission) {
        Set<String> visited = new HashSet<>();
        Deque<String> stack = new ArrayDeque<>();
        stack.push(role);
        while (!stack.isEmpty()) {
            String current = stack.pop();
            if (!visited.add(current)) continue;
            if (rolePermissions.getOrDefault(current, Collections.emptySet()).contains(permission)) return true;
            stack.addAll(roleParents.getOrDefault(current, Collections.emptyList()));
        }
        return false;
    }
}
```
**Complexity:** O(roles in the inheritance chain) per check. **Pattern:** graph traversal over a permission-inheritance hierarchy — identity/access-management companies ask this to test whether candidates handle a DAG (not just a simple tree — a role CAN have multiple parents) correctly, including cycle-safety via the `visited` set.

#### F-20. [Duo Security / 2FA providers] Time-Based One-Time Password (TOTP) Window Validation

**Problem:** Given a shared secret and a submitted OTP code, validate it against the current time step, allowing a small tolerance window (e.g., ±1 time step) to account for clock drift between client and server.

**Approach:** Compute the expected code for the current time step and the adjacent steps within the tolerance window; accept if the submitted code matches any of them (simplified — real TOTP uses HMAC-SHA1 per RFC 6238; this models the windowing logic which is the actual interview focus).

```java
boolean validateTOTP(String submittedCode, long currentUnixTime, int stepSeconds, int toleranceSteps, Function<Long, String> codeGenerator) {
    long currentStep = currentUnixTime / stepSeconds;
    for (long step = currentStep - toleranceSteps; step <= currentStep + toleranceSteps; step++) {
        if (codeGenerator.apply(step).equals(submittedCode)) return true;
    }
    return false;
}
```
**Complexity:** O(toleranceSteps). **Pattern:** the "tolerance window around a moving time step" pattern — security/auth companies ask this to test whether candidates correctly reason about real-world clock-drift tolerance rather than naively requiring an exact single-value match, which would break in practice due to client/server clock skew.

> **Third extended bank summary:** Part 5.9 adds 20 more problems (F-1 through F-20), covering infrastructure (locking, bin packing, circuit breakers, consistent hashing), security (CIDR checking, RBAC, TOTP), and SaaS-platform (pub-sub, dedup, critical path, rolling hash) domains. Combined with Parts 5.2-5.8, this guide's Part 5 alone now contains **93 previously-reported, company-tagged coding/LLD questions** with full worked Java solutions.







## Part 6 — System Design (HLD): Step-by-Step Framework + Fresh Case Studies

For the full 22-case-study library and exhaustive building-blocks theory (databases, caching, message queues, consistent hashing, CAP theorem, etc.), see [SYSTEM_DESIGN_INTERVIEW_MASTERY_GUIDE.md](SYSTEM_DESIGN_INTERVIEW_MASTERY_GUIDE.md). This section gives you a **complete, self-contained framework** plus **6 fresh case studies** chosen specifically for their overlap with Amazon-style interview questions.

### 6.1 HLD vs LLD — the difference interviewers care about

- **High-Level Design (HLD):** the "zoomed out" view — which services/components exist, how they talk to each other, what databases/caches/queues sit where, how the system scales, stays available, and handles failure. Answers "what talks to what, and why." Typical interview length: 45–60 minutes, expected for 2+ years of experience roles.
- **Low-Level Design (LLD):** the "zoomed in" view — class diagrams, interfaces, design patterns, method signatures, concurrency handling within a single service. Answers "how is this one component actually implemented." Typical interview length: 45–60 minutes, common at senior/staff levels or for roles emphasizing framework/library/SDK work.
- **The single biggest interview mistake:** diving into class-level details (LLD) during an HLD round, or vice versa — burning your 45 minutes on the wrong altitude. Always confirm with the interviewer which altitude they want if the prompt is ambiguous ("Design Twitter" could mean either).

### 6.2 The universal HLD framework (step by step)

Use this exact sequence for **any** HLD prompt — it works because it mirrors how real system design proposals get written and reviewed:

**Step 1 — Clarify requirements (5 minutes).**
- Functional requirements: what must the system DO? (List 3–5 core use cases; explicitly state what's out of scope — you cannot design everything in 45 minutes.)
- Non-functional requirements: scale (users, QPS, data volume), latency targets, availability target (e.g., 99.9%), consistency needs (strong vs. eventual), read-heavy vs. write-heavy.

**Step 2 — Back-of-envelope estimation (5 minutes).**
- Estimate DAU/MAU, requests per second (average and peak), storage growth per day/year, bandwidth. Round aggressively (powers of 10) — precision doesn't matter, order-of-magnitude reasoning does.
- This step directly informs later decisions (e.g., "200M requests/day ≈ 2,300 QPS average, ~10x at peak ≈ 23,000 QPS — this rules out a single-instance relational database without sharding/read-replicas").

**Step 3 — Define the API / interface contract (5 minutes).**
- Sketch the 3–6 core API endpoints (REST/gRPC) with request/response shapes. This forces you to nail down exactly what the system exposes before designing internals.

**Step 4 — High-level architecture diagram (10 minutes).**
- Draw (in text/ASCII) the major components: client → load balancer → API gateway → services → databases/caches/queues → downstream systems. Explain the data flow for the 1–2 most important use cases end to end.

**Step 5 — Data model & storage choice (5 minutes).**
- Define core entities/tables/documents. Justify SQL vs. NoSQL (or both, for different data) based on access patterns from Step 1, not by default habit. State the sharding/partitioning key if data volume from Step 2 demands it.

**Step 6 — Deep dive into the 1–2 hardest sub-problems (10–15 minutes).**
- The interviewer usually steers you here ("how would you handle X specifically?"). Common deep dives: uniqueness/ID generation at scale, handling hot keys/celebrities, ensuring exactly-once processing, cache invalidation strategy, handling a specific failure mode.

**Step 7 — Bottlenecks, scaling & trade-offs (5 minutes).**
- Proactively name single points of failure and how you'd remove them (replication, multi-AZ, circuit breakers). Discuss what you'd change at 10x or 100x the scale from Step 2.

**Step 8 — Wrap-up (2 minutes).**
- Summarize the design in 2–3 sentences and explicitly state what you'd improve with more time — this signals self-awareness and prioritization skill even under a hard time limit.

**Reusable checklist to keep visible while practicing:**
```
[ ] Clarified functional + non-functional requirements
[ ] Did back-of-envelope math (QPS, storage, bandwidth)
[ ] Sketched core API contract
[ ] Drew high-level component diagram + explained data flow
[ ] Chose data model + justified SQL/NoSQL + partitioning key
[ ] Went deep on 1-2 hardest sub-problems
[ ] Discussed bottlenecks, SPOFs, and scaling to 10x/100x
[ ] Wrapped up with a summary + stated improvements
```

### 6.3 Case Study: Design Amazon Locker / Package Pickup System

**Problem statement:** Design a system managing self-service package lockers (like Amazon Hub Lockers) where couriers deposit packages and customers retrieve them using a pickup code.

**Requirements:**
- FR: assign a locker compartment to an incoming package; generate a time-limited pickup code; notify the customer; verify the code and open the correct compartment on pickup; handle unclaimed packages after an expiry window (return to courier/warehouse).
- NFR: high availability (a locker station must work even with intermittent connectivity — it's a physical kiosk, not a data center), low latency for code verification (<1s, someone is standing there), eventual consistency acceptable for analytics/reporting, strong consistency required for "is this compartment occupied" to avoid double-assignment.

**Estimation:** Assume 100,000 locker stations globally, each with ~20–40 compartments, ~5 package events (drop-off or pickup) per station per day → ~500K–1M events/day → ~6–12 average events/sec (with strong diurnal peaks around delivery-route times, maybe 10x peak). Storage: a package record (~1KB metadata) × millions/year is trivially small; the interesting constraint is **kiosk-side offline resilience**, not raw volume.

**API design:**
```
POST /lockers/{stationId}/assign        { packageId, size } -> { compartmentId, pickupCode, expiresAt }
POST /lockers/{stationId}/verify        { compartmentId, pickupCode } -> { granted: bool }
POST /lockers/{stationId}/heartbeat     { stationId, compartmentStates[] }  (kiosk -> cloud sync)
GET  /lockers/{stationId}/status
```

**High-level architecture:**
```
Courier App / Customer App
        │
        ▼
   API Gateway ── Auth/Rate limiting
        │
        ▼
Locker Assignment Service ──► Compartment Availability Store (strongly consistent, per-station)
        │                              (e.g., DynamoDB with conditional writes keyed by stationId+compartmentId)
        ▼
Notification Service (SMS/push/email with pickup code)
        │
   Kiosk Firmware (each station) ──► local cache of "pending pickups" + offline queue
        │  (syncs to cloud on connectivity, but can verify codes OFFLINE using a locally
        │   verifiable signed code, e.g., HMAC(stationId+compartmentId+packageId+secret))
        ▼
   Expiry/Reclaim Worker (scheduled job scans for expired pickups, triggers courier pickup task)
```

**Data model:** `Package(packageId, stationId, compartmentId, status, assignedAt, expiresAt, codeHash)`, `Station(stationId, compartments[], lastHeartbeatAt)`. Partition the availability store by `stationId` (natural shard key — all contention for a station's compartments is local to that station, so this scales horizontally trivially with zero cross-shard coordination).

**Deep dive — offline-tolerant code verification:** since a kiosk may temporarily lose connectivity, the pickup code should be a **self-verifying signed token** (e.g., `HMAC-SHA256(stationId | compartmentId | packageId | expiresAt, serverSecret)` truncated to a human-typable 6-digit code plus a locally-cached lookup table pushed to the kiosk at assignment time), so verification doesn't require a live round trip to the cloud — the kiosk can validate against its last-synced local cache and only needs to sync the "picked up" event back to the cloud once connectivity returns (eventually consistent for the pickup-confirmation record, but the physical door only opens for a code that was cryptographically valid at assignment time, which is the actual safety property that matters).

**Deep dive — preventing double-assignment of a compartment:** use a **conditional write** ("assign compartment X only if its current status is EMPTY") against the strongly-consistent per-station store — this is a single-row compare-and-swap, not a distributed transaction, because contention is always scoped to one station.

**Bottlenecks & scaling:** the notification service and assignment service are stateless and scale horizontally behind a load balancer; the availability store scales by station-based partitioning (no single station realistically has more contention than a single DB partition can handle); the true bottleneck is physical (finite compartments per station) — the system's job is to fail gracefully (report "no compartment available, redirect to next-nearest station") rather than to "scale around" a physical constraint.

**Trade-offs:** eventual consistency for analytics/reporting is fine and lets us batch-sync kiosk heartbeats cheaply; strong consistency is reserved only for the single narrow operation (compartment assignment) where it actually matters — this selective consistency is the key design insight interviewers are listening for.

### 6.4 Case Study: Design an E-Commerce Cart & Inventory System

**Problem statement:** Design the backend for a shopping cart and inventory system for a large e-commerce platform (Amazon-scale): add/remove items from a cart, check out, and ensure inventory counts stay correct under massive concurrent demand (e.g., a flash sale).

**Requirements:**
- FR: add/update/remove cart items; view cart; checkout (reserve inventory, create order, process payment); real-time inventory count per SKU per warehouse/region.
- NFR: cart operations should feel instant (<100ms); inventory correctness is **non-negotiable** (never oversell), while cart contents can tolerate brief staleness; must survive extreme bursts (flash sales can be 50–100x normal traffic for a single SKU).

**Estimation:** Assume 50M DAU, ~5 cart mutations/user-session on average → hundreds of millions of cart writes/day → tens of thousands of QPS average, with hot-SKU flash-sale spikes reaching far higher **on a tiny subset of items** — this "hot key" shape (not uniform load) is the central design challenge, not raw aggregate throughput.

**API design:**
```
POST   /cart/{userId}/items          { sku, qty }
DELETE /cart/{userId}/items/{sku}
GET    /cart/{userId}
POST   /checkout/{userId}            { cartSnapshot } -> { orderId, status }
GET    /inventory/{sku}?region=...
```

**High-level architecture:**
```
Client
  │
  ▼
API Gateway
  │
  ├──► Cart Service ──► Cart Store (Redis/DynamoDB, keyed by userId, TTL'd, eventually consistent
  │                       is fine — worst case a stale cart view, corrected on next read/write)
  │
  └──► Checkout Service
            │
            ▼
     Inventory Reservation Service ──► Inventory Store (strongly consistent per-SKU counter,
            │                            e.g., DynamoDB conditional decrement or a dedicated
            │                            partitioned counter service)
            ▼
     Order Service ──► Orders DB (source of truth, append-only order events)
            │
            ▼
     Payment Service (external gateway integration, idempotent via idempotency keys)
            │
            ▼
     Async: Fulfillment/Shipping Event (published to a queue, e.g., Kafka/SQS)
```

**Data model:** `CartItem(userId, sku, qty, updatedAt)` in a fast key-value store; `Inventory(sku, region, availableQty, reservedQty)` with the reservation split explicitly (available vs. reserved) so a reservation doesn't destructively decrement the "real" count until the order is confirmed; `Order(orderId, userId, items[], status, createdAt)` as the durable source of truth.

**Deep dive — never overselling under flash-sale contention:** use an **atomic conditional decrement** (`UPDATE inventory SET available = available - qty WHERE sku = ? AND available >= qty`, or DynamoDB's conditional expression equivalent) — this pushes the concurrency control down to the database's own atomic compare-and-swap rather than doing a read-then-write in application code (which races). For extremely hot single SKUs, further shard the counter itself (e.g., split one SKU's inventory into N sub-counters across partitions, sum for reads, decrement a randomly-chosen sub-counter with available stock for writes) to avoid a single-partition hotspot even at the database layer — this is the same core idea as sharded counters used for high-QPS "like" counts.

**Deep dive — reservation timeout / abandoned checkout:** when checkout reserves inventory, set a short TTL (e.g., 10–15 minutes) on the reservation; a background sweeper (or the store's native TTL/expiry mechanism) releases unconfirmed reservations back to `available`, preventing inventory from being silently locked up by abandoned carts.

**Bottlenecks & scaling:** cart service is embarrassingly parallel (partition by `userId`, no cross-user contention) and can use a cache-first architecture with async persistence; inventory is the genuine hotspot and needs the sub-counter sharding technique above for the top N hottest SKUs during known sale events (pre-provisioned based on marketing calendar), falling back to simple per-SKU atomic counters for the long tail of normal-traffic items.

**Trade-offs:** cart correctness is relaxed (eventual consistency, last-write-wins is acceptable — a user rarely edits their own cart concurrently from two devices in a way that truly matters) specifically so the strongly-consistent budget can be spent entirely on inventory, which is where correctness actually has business impact (overselling = real money lost + customer trust damage).

### 6.5 Case Study: Design Prime Video (video streaming at scale)

**Problem statement:** Design a video streaming service supporting on-demand playback for millions of concurrent viewers with adaptive quality.

**Requirements:**
- FR: upload/transcode video into multiple resolutions/bitrates; stream video with adaptive bitrate switching based on network conditions; resume playback; search/browse catalog.
- NFR: extremely read-heavy (uploads are rare relative to plays); global low-latency delivery; must gracefully degrade quality rather than buffer/stall; high availability (streaming outages are highly visible).

**Estimation:** Assume 100M subscribers, 20% watch daily → 20M daily viewers, average session 90 min. Peak concurrent streams during prime evening hours could be tens of millions simultaneously. Storage: one movie transcoded into ~6–8 resolution/bitrate variants using chunked segments (HLS/DASH) — a two-hour movie might total several GB across all variants; catalog of 10,000s of titles is petabyte-scale but is a **one-time-per-title** cost, dwarfed by egress/delivery cost at play time.

**API design:**
```
GET  /catalog/search?q=...
GET  /titles/{titleId}/manifest        -> returns HLS/DASH manifest (list of available renditions)
GET  /segments/{titleId}/{quality}/{segmentId}.ts   (served via CDN, not the origin API)
POST /playback/{userId}/progress       { titleId, positionSeconds }  (resume-watching checkpoint)
```

**High-level architecture:**
```
Upload Pipeline (studio/content team)
   │
   ▼
Transcoding Pipeline (splits into chunks, encodes multiple bitrates/resolutions,
   generates HLS/DASH manifest) ──► Object Storage (S3-equivalent, origin store)
   │
   ▼
CDN (edge caches, globally distributed — this is where >99% of actual video bytes are served
   from; origin is only hit on a cache miss for a rarely-requested segment/region)
   │
   ▼
Client Player (adaptive bitrate logic: measures recent download throughput, switches
   rendition up/down between segment boundaries)

Separate control-plane services:
   Catalog/Search Service ──► Search index (Elasticsearch-like)
   Playback Progress Service ──► fast KV store keyed by (userId, titleId), high write volume,
        low per-write importance (losing the last few seconds of resume position is a non-event)
   Licensing/DRM Service ──► issues per-session decryption keys/tokens
```

**Data model:** `Title(titleId, metadata, availableRenditions[])`, `Manifest(titleId, quality, segmentList[])`, `WatchProgress(userId, titleId, positionSeconds, updatedAt)` (extremely high write volume, extremely low consistency requirement — a perfect candidate for a "fire and forget, eventually consistent, last-write-wins" store).

**Deep dive — adaptive bitrate streaming (ABR):** the client player, not the server, drives quality switching: it downloads a manifest listing all available renditions (e.g., 240p/500kbps up to 4K/25mbps) chunked into ~2–10 second segments; the player continuously estimates available bandwidth from recent segment download times and requests the next segment from whichever rendition best fits that bandwidth **without exceeding it** (to avoid buffering) — this pushes an enormous amount of complexity to the edge/client, which is precisely why it scales: the server just needs to have pre-encoded all renditions and serve static segment files from a CDN, with no per-request server-side decision-making at all.

**Deep dive — global low-latency delivery:** pre-position (or lazily cache-and-propagate) popular content across CDN edge nodes near viewers; use consistent hashing to map a given segment request to a specific edge cache node deterministically; only a true cache miss (rare, unpopular title, cold region) falls back to the origin object store, which is why the origin's throughput requirement is orders of magnitude lower than aggregate viewer traffic.

**Bottlenecks & scaling:** the CDN IS the scaling strategy for the data plane — origin storage/transcoding is a comparatively small, batch-friendly workload. The genuine scaling risk is a "thundering herd" at a title's release moment (e.g., a hyped new season drops at midnight globally) — mitigated by pre-warming CDN caches ahead of a known release time rather than relying purely on reactive cache population.

**Trade-offs:** favor availability and smooth playback over perfect quality (better to silently drop to 480p than to buffer/stall — buffering is the #1 measured driver of viewer abandonment in real streaming services) — this directly shapes the ABR algorithm's bias toward conservative bitrate selection over maximizing resolution.

### 6.6 Case Study: Design a Voice Assistant Backend (Alexa)

**Problem statement:** Design the backend supporting a voice assistant: wake-word detection triggers audio capture, which must be transcribed, understood as an intent, routed to the right "skill"/service, and answered with synthesized speech, all within a couple of seconds.

**Requirements:**
- FR: receive streamed audio, convert speech-to-text (ASR), determine intent + extract entities (NLU), route to the correct skill/handler (weather, smart-home control, shopping, third-party skills), generate a response, convert text-to-speech (TTS), stream audio back.
- NFR: extremely latency-sensitive (users expect a response within ~1–2 seconds of finishing speaking); must scale to tens of millions of devices; must work across unreliable home networks; privacy/security of audio data is paramount.

**Estimation:** Assume 50M active devices, each device issuing a handful of requests/day on average → tens of millions of requests/day, with a strong evening/morning peak. Each utterance's audio payload is small (a few seconds of compressed audio, tens of KB) but the **processing pipeline** (ASR → NLU → skill routing → TTS) is the expensive part, not the raw bytes.

**API design (conceptually, device-to-cloud is typically a persistent streaming connection, not simple REST):**
```
Device --(streaming audio, opened on wake-word)--> Voice Gateway
Voice Gateway -> ASR Service : audio stream -> partial + final transcripts
Voice Gateway -> NLU Service : transcript -> { intent, slots/entities, confidence }
Voice Gateway -> Skill Router : intent -> invoke correct Skill Service, get response text/action
Voice Gateway -> TTS Service : response text -> synthesized audio stream -> Device
```

**High-level architecture:**
```
Device (wake-word detection runs LOCALLY/on-device to avoid streaming everything to the
   cloud constantly — a critical privacy + bandwidth design choice)
   │  (streams audio only after wake-word trigger)
   ▼
Voice Gateway Service (manages the session, orchestrates the pipeline stages, low-latency
   streaming protocol, e.g., WebSocket/gRPC streaming)
   │
   ├──► ASR Service (speech-to-text, often streaming/incremental so downstream stages can
   │        start before the user finishes speaking — reduces perceived latency)
   ├──► NLU Service (intent classification + slot filling, typically a trained ML model
   │        served behind a low-latency inference endpoint)
   ├──► Skill Registry & Router (maps intent -> internal or third-party skill service;
   │        third-party skills invoked via a sandboxed API contract with a strict timeout)
   ├──► Context/Session Store (short-lived conversational state — "turn off THE light" needs
   │        to remember which light was just discussed)
   └──► TTS Service (text-to-speech, also streamable so audio starts playing before the
            full response is fully synthesized)
```

**Data model:** mostly ephemeral session state (`Session(deviceId, conversationContext, lastIntent, expiresAt)` in a fast, short-TTL store) rather than heavy persistent storage; longer-term data (user preferences, skill-linked accounts) lives in per-user profile stores, but the hot path per-request touches almost none of it beyond a lookup.

**Deep dive — meeting the sub-2-second latency budget:** every pipeline stage (ASR, NLU, skill invocation, TTS) must be **streamed and pipelined**, not run strictly sequentially waiting for each to fully complete — e.g., ASR emits partial transcripts as the user is still speaking, allowing NLU to begin intent classification on a likely-final transcript before the user has technically finished, and TTS begins streaming the first synthesized audio chunk back to the device before the full response text is done being generated for longer answers. Third-party skill invocations get a strict timeout (e.g., 500ms) with a graceful fallback ("Sorry, I couldn't reach that skill right now") rather than letting one slow skill blow the whole interaction's latency budget.

**Deep dive — on-device wake-word detection:** running wake-word detection locally (a small, efficient always-on model on the device itself) rather than streaming all ambient audio to the cloud continuously is both a massive bandwidth/cost saving (only real utterances get streamed) and the primary privacy safeguard users expect.

**Bottlenecks & scaling:** ASR/NLU/TTS are typically GPU/accelerator-backed ML inference services — these are the resource-expensive components and are scaled independently behind their own auto-scaling groups sized to request volume, decoupled from the lightweight orchestration Voice Gateway layer.

**Trade-offs:** favor speed over accuracy at the margins (a fast, "good enough" intent match beats a slower, marginally more accurate one, because perceived latency dominates user satisfaction for a voice interface far more than for, say, a search results page where users tolerate a bit more wait for better results).

### 6.7 Case Study: Design a Distributed Job Scheduler

**Problem statement:** Design a system that reliably executes millions of scheduled/recurring jobs (cron-like and one-off delayed tasks) across a fleet of workers, exactly-once (or effectively-once) despite worker failures.

**Requirements:**
- FR: schedule a job for a future time or recurring cadence (cron expression); execute it on some available worker; retry on failure with backoff; support cancellation; report job status/history.
- NFR: must not lose jobs (durability); must not double-execute jobs that have side effects (e.g., "charge a customer") except in rare, bounded, idempotency-key-protected retries; must scale to millions of scheduled jobs and handle bursts (e.g., many jobs scheduled for the same minute, like end-of-month billing).

**Estimation:** Assume 10M active scheduled jobs, average recurrence means ~1M job executions/hour in steady state, with bursty spikes at common cron boundaries (midnight, top-of-hour) that can be 10–50x steady state for a brief window.

**API design:**
```
POST /jobs               { schedule (cron or runAt), payload, idempotencyKey } -> { jobId }
DELETE /jobs/{jobId}
GET  /jobs/{jobId}/history
```

**High-level architecture:**
```
Job Definition Service ──► Job Metadata Store (durable, e.g., a partitioned relational store
   or DynamoDB — holds schedule definitions, next-run time)
        │
        ▼
Scheduler/Ticker (periodically, e.g., every few seconds, scans for jobs whose next-run time
   has arrived — implemented as a time-bucketed priority structure, NOT a full table scan:
   partition jobs into "buckets" keyed by rounded next-run timestamp, e.g., minute-granularity,
   so each tick only needs to read the current bucket, not the entire job set)
        │
        ▼
Distribution Queue (e.g., Kafka/SQS) — due jobs are pushed here for workers to consume
        │
        ▼
Worker Fleet (pulls jobs, executes payload, acknowledges completion; uses a
   visibility-timeout/lease pattern — if a worker crashes mid-execution, the job becomes
   visible again after the lease expires and another worker picks it up)
        │
        ▼
Idempotency Store (keyed by idempotencyKey, short-TTL) — before executing a job's side
   effect, the worker checks/reserves the idempotency key; if a retry arrives for a key
   already marked "completed," it's skipped, preventing double side-effects (e.g., double
   charge) even if the queue's at-least-once delivery redelivers a message
```

**Data model:** `Job(jobId, schedule, nextRunAt, payload, status)`, `Execution(executionId, jobId, workerId, startedAt, status, idempotencyKey)`. The scheduler's job-bucket index (`nextRunAt (minute-rounded) -> [jobIds]`) is the single most important data structure — it's what turns "scan millions of jobs every tick" into "scan the ~thousands of jobs due in this specific minute."

**Deep dive — exactly-once-ish execution despite at-least-once delivery:** true exactly-once delivery is not achievable over an unreliable network without cooperation from the receiver, so the practical pattern is **at-least-once delivery + idempotent execution**: every job execution carries an idempotency key, and the worker's execution logic is required to be a no-op if that key was already marked complete (checked via an atomic conditional write to the idempotency store before performing the actual side effect). This shifts the correctness burden to "make side effects idempotent," which is a tractable, well-understood pattern (e.g., "set order status to SHIPPED" is naturally idempotent; "increment a counter by 1" is not, and needs a different formulation like "set counter to N" or a dedup key).

**Deep dive — the "thundering herd" at common cron boundaries:** many jobs scheduled for exactly midnight or the top of the hour create a spike. Mitigate with **jitter** — add a small random offset (e.g., ±30 seconds) to a job's actual dispatch time within its scheduled minute bucket, spreading load smoothly rather than firing all jobs in the same instant, similar to how DNS TTL jitter avoids synchronized cache expiry storms.

**Bottlenecks & scaling:** the ticker/scheduler component must be horizontally partitioned (e.g., by a hash of `jobId` or by time-bucket range) so no single scheduler instance is a bottleneck; the worker fleet auto-scales based on queue depth (a classic and very effective autoscaling signal for queue-based systems).

**Trade-offs:** durability and idempotency are prioritized heavily over "true" exactly-once semantics, since the latter is effectively unachievable and chasing it wastes engineering effort that's better spent making side effects idempotent by design.

### 6.8 Case Study: Design a Notification/Alerting System

**Problem statement:** Design a system to send notifications (push, email, SMS) to users at scale, supporting both real-time transactional notifications ("your order shipped") and bulk/marketing campaigns ("flash sale today"), across multiple channels with user preferences/opt-outs respected.

**Requirements:**
- FR: accept a notification request (single user or bulk/segment), determine eligible channels per user preference, render templated content, deliver via the right provider (APNs/FCM for push, an email provider, an SMS gateway), track delivery status, respect quiet hours/opt-outs/rate limits per user.
- NFR: transactional notifications need low latency (seconds); bulk campaigns need high throughput but can tolerate being spread over minutes/hours; must never spam a user beyond their configured frequency cap; must handle provider failures/rate limits gracefully.

**Estimation:** Assume 100M users, average 5 notifications/user/day → 500M notifications/day ≈ ~6,000 average/sec, with campaign bursts potentially needing to fan out tens of millions of messages within a short campaign window, deliberately throttled to respect per-provider rate limits and per-user frequency caps.

**API design:**
```
POST /notify                { userId | segmentId, template, data, channelPreferenceOverride? }
GET  /notify/{notificationId}/status
POST /users/{userId}/preferences   { channel, optedIn, quietHours }
```

**High-level architecture:**
```
Producing Services (order service, marketing campaign tool, etc.)
        │
        ▼
Notification API (validates request, resolves segment -> list of userIds if needed)
        │
        ▼
Preference & Eligibility Filter (checks opt-out status, quiet hours, frequency caps per user
   — reads from a fast user-preference store)
        │
        ▼
Template Rendering Service (merges data into channel-specific templates)
        │
        ▼
Fan-out Queue (partitioned by channel: push-queue, email-queue, sms-queue — each channel has
   very different throughput/rate-limit characteristics from its downstream provider, so
   isolating them prevents one channel's slowness from blocking another)
        │
        ▼
Channel Delivery Workers (push worker calls APNs/FCM, email worker calls SES/SendGrid-
   equivalent, SMS worker calls Twilio-equivalent) — each worker fleet auto-scales
   independently and implements its provider's specific retry/backoff and rate-limit rules
        │
        ▼
Delivery Status Tracker (records sent/delivered/failed/bounced, feeds back into future
   eligibility decisions, e.g., stop sending push to a device whose token is invalid)
```

**Data model:** `Notification(notificationId, userId, channel, templateId, status, createdAt)`, `UserPreference(userId, channel, optedIn, quietHoursStart, quietHoursEnd, frequencyCapPerDay)`, `DeliveryEvent(notificationId, channel, status, providerResponse, timestamp)`.

**Deep dive — respecting per-user frequency caps under concurrent producers:** multiple services (order updates, marketing, security alerts) might all want to notify the same user around the same time. Maintain a **rolling counter per user per day** (e.g., a Redis key `notif_count:{userId}:{date}` with an atomic increment and a TTL of 24h) checked at the eligibility-filter stage; security/transactional notifications can be tagged with a priority that bypasses marketing-only frequency caps, but a global hard ceiling still protects against runaway bugs spamming a user.

**Deep dive — bulk campaign fan-out without violating provider rate limits:** for a segment of 20M users, don't push all 20M messages onto the fan-out queue instantly — use a **rate-limited dequeuer** (token bucket at the channel-worker level matching the downstream provider's contracted rate limit) and, for very large campaigns, deliberately spread delivery across a window (e.g., "send over 2 hours") both to respect provider limits and to smooth backend load; this is explicitly a business/product trade-off (not every user gets the flash-sale alert at the exact same second) that should be called out explicitly to the interviewer as a deliberate design choice, not an oversight.

**Bottlenecks & scaling:** the channel-specific queues + independently-scaled worker fleets are the key scaling lever — a slow/rate-limited SMS provider should never back up push or email delivery; the preference/eligibility store must support very high read QPS (a cache-friendly, mostly-read workload, since preferences change far less often than notifications are sent).

**Trade-offs:** transactional notifications are architected for low latency at the cost of not batching; bulk campaigns are architected for high throughput at the cost of accepting a delivery-time spread — recognizing that these are two different workloads with different SLAs, and NOT trying to force one pipeline to optimize for both, is the central design insight.

### 6.9 Case Study: Design a Search Autocomplete/Typeahead Service

**Problem statement:** Design a backend service that, as a user types into a search box, returns the top-K most likely completions within tens of milliseconds.

**Requirements:** FR: given a prefix, return top-K historical queries starting with that prefix, ranked by frequency; ingest new query data continuously (today's trending searches should surface, not just historical favorites). NFR: extremely low read latency (tens of ms, on every keystroke); can tolerate the suggestion list being a few minutes stale (eventual consistency is fine — freshness-to-the-second is not required).

**Estimation:** Assume 1B searches/day across a large search product; the *read* path (autocomplete suggestions) is requested on nearly every keystroke, so read QPS is roughly an order of magnitude higher than raw search QPS — tens of thousands of QPS sustained, requiring a read-optimized precomputed structure rather than live aggregation per request.

**High-level architecture:**
```
Search Logs (raw query events, streamed via Kafka/Kinesis-equivalent)
        │
        ▼
Offline Aggregation Job (batch, e.g., hourly): counts query frequency over a trailing
   window, builds/updates a Trie (or a precomputed top-K-per-prefix table) annotated
   with frequency-ranked top completions at every prefix node
        │
        ▼
Trie/Precomputed-Suggestion Store (sharded by first 1-2 characters of the prefix across
   multiple servers, since a single machine's memory can't hold the whole Trie plus
   cached top-K lists for a huge query corpus at low latency)
        │
        ▼
Autocomplete API (stateless, read-only, queries the appropriate shard for the given
   prefix, returns cached top-K instantly — no live computation on the read path at all)
        │
        ▼
Client (debounces keystrokes client-side, e.g., only fires a request every ~100-150ms
   of typing pause, to avoid firing a request per individual keystroke)
```

**Deep dive — why NOT compute top-K live per request:** ranking all historical queries matching a prefix on every keystroke would be far too slow at real-time latency budgets; instead, the **expensive ranking computation is moved entirely to an offline batch job**, and the read path only ever does an O(1)-ish lookup into a precomputed structure — the same "separate expensive writes from cheap reads" principle as the Buy Box example in [9.7](#97-amazon-system-design-round-whats-different).

**Deep dive — balancing historical popularity with real-time trends:** a purely historical-frequency ranking misses breaking/trending queries. A common approach is to maintain two signals — a slow-moving historical frequency count and a fast-moving short-window trending count (e.g., last hour) — and blend them with a weighted formula, refreshed at different cadences (historical: daily/hourly batch; trending: near-real-time streaming aggregation) rather than trying to force one single pipeline to serve both freshness needs.

**Bottlenecks & scaling:** the Trie/suggestion store is sharded by prefix so no single node needs to hold the entire dataset; the autocomplete API layer is stateless and scales horizontally behind a load balancer; the batch aggregation job's cost scales with total historical log volume but runs offline, decoupled entirely from the read-path latency budget.

**Trade-offs:** accept a few minutes of staleness in exchange for consistently fast reads — attempting perfectly fresh, live-computed suggestions would either be far too slow or require disproportionate infrastructure investment for marginal freshness benefit.

### 6.10 Case Study: Design a Distributed Log Aggregation System

**Problem statement:** Design a system (Splunk/ELK-stack-style) that collects logs from thousands of application servers, indexes them for fast search, and supports both real-time tailing and historical queries.

**Requirements:** FR: ingest structured/unstructured log lines from many sources; support full-text and field-based search with time-range filters; support real-time "tail -f"-style streaming views; retain data for a configurable period then archive/delete. NFR: extremely high write throughput (every server continuously emits logs); search latency should be low for recent data, can be higher for older/archived data; must not lose logs even during backend outages (a buffering/backpressure story is required).

**High-level architecture:**
```
Application Servers (log agents, e.g., a lightweight forwarder process per host)
        │  (agents buffer locally on disk if the backend is unreachable, providing
        │   durability against transient network/backend issues)
        ▼
Ingestion Pipeline (a message queue, e.g., Kafka, absorbing bursty write volume and
   decoupling ingestion rate from indexing rate)
        │
        ▼
Indexing Workers (parse/structure raw log lines, extract fields, write to a search-
   optimized store, e.g., an inverted-index-based engine; partitioned by time range,
   since almost all queries are time-bounded — this is the single most impactful
   partitioning decision for this system)
        │
        ▼
Hot Storage (recent data, e.g., last 7-30 days, on fast storage, fully indexed for
   low-latency search) ──► Cold/Archive Storage (older data, cheaper object storage,
   indexed more sparsely or not at all, queried less frequently and more tolerant of
   higher latency)
        │
        ▼
Query/Search API (routes a query's time range to the relevant hot/cold storage
   partitions, merges results) + Real-Time Tail Service (a separate streaming
   subscription path directly off the ingestion queue, bypassing the indexing
   pipeline entirely for live-tailing use cases, since indexing adds latency
   real-time tailing cannot afford)
```

**Deep dive — time-based partitioning as the central design decision:** because virtually every log query specifies (or implies) a time range, partitioning indexed data by time bucket (e.g., one index shard per day) lets a query touch only the relevant shards instead of scanning the entire historical dataset — this single decision is what makes both fast recent-data search and cost-effective old-data archival possible simultaneously.

**Deep dive — durability under backend outages:** local on-agent disk buffering (with a bounded size and a documented overflow/drop policy once the buffer is full) is the standard mitigation against losing log data during a transient backend or network outage — this mirrors the same "buffer at the edge, drain when the backend recovers" pattern used in the Amazon Locker case study's offline kiosk handling ([6.3](#63-case-study-design-amazon-locker--package-pickup-system)).

**Bottlenecks & scaling:** indexing throughput is the typical bottleneck at high log volume — mitigated by horizontally scaling indexing workers behind the Kafka-style queue (which naturally load-balances via partitions) and by being selective about which fields are fully indexed versus stored-but-not-indexed (full-text indexing every field of every log line is often unnecessary and expensive).

**Trade-offs:** hot/cold tiering deliberately trades query latency on old data for large storage cost savings — a conscious, explicitly-stated trade-off rather than an oversight, since most real log queries concentrate heavily on recent time windows anyway.

### 6.11 Case Study: Design a Web Crawler

**Problem statement:** Design a distributed system that crawls billions of web pages, extracts and follows links, avoids re-crawling duplicate/unchanged content excessively, and respects site crawling policies.

**Requirements:** FR: given seed URLs, fetch pages, extract outbound links, enqueue new URLs to crawl, store fetched content for downstream indexing. NFR: must respect `robots.txt` and per-site politeness (rate limits per domain — never hammer one site); must scale horizontally to many parallel workers; must avoid infinite loops/duplicate work on the same URL; must periodically re-crawl pages that change (freshness).

**High-level architecture:**
```
Seed URLs ──► URL Frontier (a priority queue of URLs to crawl, partitioned/prioritized
   by domain to enforce per-domain politeness — this is the single most important
   component, since naive designs either overwhelm individual sites or fail to
   parallelize across many sites effectively)
        │
        ▼
Fetcher Workers (many parallel workers pull URLs from the frontier, respecting a
   per-domain rate limit enforced by the frontier's scheduling, not by each worker
   independently — independent per-worker rate limiting fails to cap AGGREGATE
   load on a popular domain being crawled by many workers simultaneously)
        │
        ▼
robots.txt & Politeness Checker (cached per-domain, checked before fetching)
        │
        ▼
Content Store (raw fetched HTML/assets, keyed by URL) + Deduplication Filter
   (a Bloom filter or content-hash index checking "have we already processed this
   exact content/URL" cheaply before doing expensive downstream work)
        │
        ▼
Link Extractor (parses fetched content for outbound links) ──► normalizes and
   filters new URLs (dedupe against already-seen/queued set) ──► pushes new URLs
   back into the URL Frontier
        │
        ▼
Downstream Indexing Pipeline (separate system, consumes crawled content)
```

**Deep dive — enforcing politeness at the AGGREGATE, not per-worker, level:** the URL Frontier must track "when did we last fetch from domain X" centrally (e.g., a per-domain queue with a minimum inter-request delay enforced at dequeue time) — if each of 1,000 parallel fetcher workers independently rate-limits itself per domain, a popular domain could still receive 1,000x more aggregate traffic than intended if many workers happen to pull URLs from it simultaneously.

**Deep dive — efficient duplicate detection at web scale:** an exact URL-seen-before check across billions of URLs would require enormous memory for a naive hash set; a **Bloom filter** (a probabilistic, space-efficient set structure with a small tunable false-positive rate but zero false negatives) is the standard technique — accepting the rare false positive (occasionally skip-crawling a genuinely-new URL) as a worthwhile trade-off for the massive space savings.

**Bottlenecks & scaling:** the frontier itself must be partitioned (e.g., by domain hash) across multiple queue instances to avoid becoming a single bottleneck at the scale of billions of URLs; fetcher workers scale horizontally and are stateless, pulling work from whichever frontier partition they're assigned.

**Trade-offs:** prioritize crawl breadth and politeness compliance over perfect freshness — a web crawler at this scale explicitly cannot re-crawl every page instantly on every change, so a a re-crawl frequency proportional to a page's observed historical change rate (crawl news sites far more often than static reference pages) is the practical, resource-aware approach.

### 6.12 Case Study: Design a Ticket Booking System

**Problem statement:** Design a system (BookMyShow/Ticketmaster-style) allowing users to browse events/showtimes and book seats, guaranteeing no two users are ever sold the same seat, even under a popular on-sale rush.

**Requirements:** FR: browse events/venues/showtimes, view real-time seat availability, hold a seat temporarily during checkout, confirm booking with payment, release held-but-unpurchased seats after a timeout. NFR: absolutely no double-booking of the same seat (strong consistency required here); must handle extreme concurrent demand for popular on-sales (a stadium concert on-sale can see hundreds of thousands of simultaneous requests for a few thousand seats).

**High-level architecture:**
```
Client
  │
  ▼
API Gateway (with an explicit request-queueing/virtual-waiting-room mechanism for
   extremely popular on-sales — admitting requests to the booking flow at a
   controlled rate rather than letting the backend be overwhelmed instantly)
  │
  ▼
Seat Availability Service ──► Seat Inventory Store (strongly consistent, partitioned
   by venue+showtime, since all contention for a given showtime's seats is naturally
   scoped to that one partition — directly analogous to the per-station partitioning
   in the Amazon Locker case study, [6.3](#63-case-study-design-amazon-locker--package-pickup-system))
  │
  ▼
Seat Hold Service (temporarily reserves a specific seat for a user for a short window,
   e.g., 5-10 minutes, via a conditional write: "hold this seat only if its current
   status is AVAILABLE" — the exact same atomic-conditional-write pattern as the
   E-commerce Inventory case study, [6.4](#64-case-study-design-an-e-commerce-cart--inventory-system))
  │
  ▼
Payment & Confirmation Service ──► on success, seat status moves HOLD -> BOOKED;
   on failure/timeout, a background sweeper releases HOLD -> AVAILABLE
```

**Deep dive — the virtual waiting room for extreme on-sale spikes:** rather than letting hundreds of thousands of simultaneous requests all hit the seat-selection backend at once (which would overwhelm it regardless of how well the inventory layer is designed), admit users into the actual booking flow at a controlled rate via a queueing/waiting-room layer (assigning each user a position/estimated wait, then admitting in batches) — this is a genuinely distinct architectural layer from the core booking logic, and calling it out explicitly is a strong signal in this specific case study since naively-designed answers often only address the seat-locking mechanism and miss the front-door admission-control problem entirely.

**Deep dive — preventing double-booking under contention:** identical in spirit to the inventory-oversell problem from [6.4](#64-case-study-design-an-e-commerce-cart--inventory-system) — an atomic conditional write (`UPDATE seats SET status='HELD', heldBy=? WHERE seatId=? AND status='AVAILABLE'`) at the database layer, not an application-level read-then-write, is what actually prevents the race.

**Bottlenecks & scaling:** the seat inventory store's partitioning by `(venue, showtime)` means even a massive spike on ONE popular showtime doesn't need to scale the ENTIRE system — just that one partition's read/write capacity, which can be specifically pre-provisioned ahead of a known on-sale time (the team knows in advance exactly when a popular on-sale will happen, unlike many other systems' unpredictable traffic spikes).

**Trade-offs:** the temporary hold window (5-10 minutes) deliberately trades a small amount of "wasted" seat unavailability (a user who abandons checkout blocks that seat for the hold duration) for a vastly simpler and more reliable booking flow than trying to make seat selection and payment atomic in a single step, which would create a poor user experience (payment forms taking a long time to fill out) colliding with strict inventory locking.

## Part 7 — System Design (LLD): Step-by-Step Framework + Fresh Case Studies

For 12 more fully-coded LLD case studies (Parking Lot, Elevator, Splitwise, LRU Cache, Rate Limiter, Vending Machine, Movie Ticket Booking, Snake & Ladder, Library Management, Tic-Tac-Toe/Chess, Logging Framework, Food Delivery), see [SYSTEM_DESIGN_INTERVIEW_MASTERY_GUIDE.md](SYSTEM_DESIGN_INTERVIEW_MASTERY_GUIDE.md) Part 6. This section covers the framework plus 3 fresh case studies.

### 7.1 The universal LLD framework (step by step)

**Step 1 — Clarify scope & requirements (5 min).** LLD prompts ("design a parking lot," "design a shopping cart") are deliberately underspecified. Ask: what operations must be supported? What are the key entities? Any concurrency requirements (multiple threads/users simultaneously)? Any persistence requirement, or is in-memory fine?

**Step 2 — Identify core entities/nouns and their relationships (5 min).** List the nouns in the problem (e.g., for a parking lot: `ParkingLot`, `Level`, `Spot`, `Vehicle`, `Ticket`). Decide relationships: composition ("a Level HAS-MANY Spots") vs. inheritance ("a `Car` IS-A `Vehicle`").

**Step 3 — Define interfaces/abstract classes for extensibility points (5–10 min).** Wherever the problem hints at "different types of X behaving differently" (different vehicle sizes, different payment methods, different pricing strategies), use an interface + Strategy/Factory pattern rather than a chain of `if/else` on a type field — this is the single most-rewarded LLD signal.

**Step 4 — Design the core classes with key methods (15–20 min).** Write actual method signatures (not just a diagram) for the 3–5 most important classes; this is where you actually write Java code live.

**Step 5 — Walk through the main use case end to end (5 min).** Trace a call sequence (e.g., "vehicle enters → find nearest available spot → issue ticket → ... → vehicle exits → compute fee → free the spot") through your classes to prove they actually compose correctly.

**Step 6 — Discuss concurrency & edge cases (5–10 min).** If multiple threads assign spots simultaneously, how do you prevent two vehicles being assigned the same spot? (Synchronize at the spot level, or use an atomic compare-and-swap on spot state, not a lock on the whole lot.) What about capacity-zero states, invalid tickets, etc.?

**Design patterns that come up constantly in LLD interviews** (all covered with Java snippets in [SYSTEM_DESIGN_INTERVIEW_MASTERY_GUIDE.md](SYSTEM_DESIGN_INTERVIEW_MASTERY_GUIDE.md) §21): **Strategy** (interchangeable algorithms, e.g., pricing/fare calculation), **Factory** (creating the right subtype without exposing construction logic), **Singleton** (a single shared registry/manager, used carefully — overuse is itself a red flag), **Observer** (notifying multiple listeners of a state change, e.g., notification fan-out), **Decorator** (adding behavior without subclassing explosion, e.g., add-ons to an order), **State** (an entity like an order or ticket moving through a well-defined lifecycle).

### 7.2 Case Study: LLD for an Amazon-style Shopping Cart

**Core entities:** `Product`, `CartItem`, `Cart`, `PricingStrategy` (interface, since discounts/coupons vary), `Cart` owns a `List<CartItem>` and delegates total computation to a pluggable strategy.

```java
interface PricingStrategy {
    double computeTotal(List<CartItem> items);
}

class StandardPricingStrategy implements PricingStrategy {
    public double computeTotal(List<CartItem> items) {
        double total = 0;
        for (CartItem item : items) total += item.getProduct().getPrice() * item.getQuantity();
        return total;
    }
}

class PercentageDiscountStrategy implements PricingStrategy {
    private final double discountPercent;
    PercentageDiscountStrategy(double discountPercent) { this.discountPercent = discountPercent; }
    public double computeTotal(List<CartItem> items) {
        double base = new StandardPricingStrategy().computeTotal(items);
        return base * (1 - discountPercent / 100.0);
    }
}

class Product {
    private final String id, name;
    private final double price;
    Product(String id, String name, double price) { this.id = id; this.name = name; this.price = price; }
    public double getPrice() { return price; }
    public String getId() { return id; }
}

class CartItem {
    private final Product product;
    private int quantity;
    CartItem(Product product, int quantity) { this.product = product; this.quantity = quantity; }
    public Product getProduct() { return product; }
    public int getQuantity() { return quantity; }
    public void setQuantity(int q) { this.quantity = q; }
}

class Cart {
    private final String userId;
    private final Map<String, CartItem> items = new LinkedHashMap<>(); // preserves add-order
    private PricingStrategy pricingStrategy = new StandardPricingStrategy();
    Cart(String userId) { this.userId = userId; }

    public synchronized void addItem(Product product, int quantity) {
        items.merge(product.getId(), new CartItem(product, quantity),
            (existing, incoming) -> { existing.setQuantity(existing.getQuantity() + quantity); return existing; });
    }
    public synchronized void removeItem(String productId) { items.remove(productId); }
    public synchronized void updateQuantity(String productId, int quantity) {
        if (quantity <= 0) { items.remove(productId); return; }
        if (items.containsKey(productId)) items.get(productId).setQuantity(quantity);
    }
    public void applyDiscount(PricingStrategy strategy) { this.pricingStrategy = strategy; }
    public double getTotal() { return pricingStrategy.computeTotal(new ArrayList<>(items.values())); }
    public List<CartItem> getItems() { return new ArrayList<>(items.values()); }
}
```

**Concurrency note:** `Cart` methods are `synchronized` at the per-cart level (never a global lock across all users' carts) since each user's cart is an independent unit of contention — this mirrors the "shard by userId" idea from the HLD cart case study ([6.4](#64-case-study-design-an-e-commerce-cart--inventory-system)). **Extensibility:** adding a new discount type (e.g., `BuyOneGetOneStrategy`) requires zero changes to `Cart` — this is the payoff of the Strategy pattern, and interviewers will often explicitly test this by asking "now add a new kind of discount" mid-interview to see if your design accommodates it cleanly.

### 7.3 Case Study: LLD for a Ride-Hailing Matching Engine

**Core entities:** `Driver`, `Rider`, `RideRequest`, `MatchingStrategy` (interface — nearest-driver vs. surge-aware matching are different strategies), a `DriverLocationIndex` for efficient nearest-neighbor lookup.

```java
interface MatchingStrategy {
    Optional<Driver> findMatch(RideRequest request, List<Driver> availableDrivers);
}

class NearestDriverStrategy implements MatchingStrategy {
    public Optional<Driver> findMatch(RideRequest request, List<Driver> availableDrivers) {
        return availableDrivers.stream()
            .filter(Driver::isAvailable)
            .min(Comparator.comparingDouble(d -> distance(d.getLocation(), request.getPickupLocation())));
    }
    private double distance(Location a, Location b) {
        return Math.hypot(a.getLat() - b.getLat(), a.getLng() - b.getLng());
    }
}

class Location {
    private final double lat, lng;
    Location(double lat, double lng) { this.lat = lat; this.lng = lng; }
    public double getLat() { return lat; } public double getLng() { return lng; }
}

class Driver {
    private final String id;
    private Location location;
    private volatile boolean available = true;
    Driver(String id, Location location) { this.id = id; this.location = location; }
    public synchronized boolean tryReserve() {
        if (!available) return false;
        available = false;
        return true;
    }
    public void release() { available = true; }
    public boolean isAvailable() { return available; }
    public Location getLocation() { return location; }
    public void updateLocation(Location loc) { this.location = loc; }
}

class RideRequest {
    private final String riderId;
    private final Location pickupLocation;
    RideRequest(String riderId, Location pickupLocation) { this.riderId = riderId; this.pickupLocation = pickupLocation; }
    public Location getPickupLocation() { return pickupLocation; }
}

class MatchingEngine {
    private final MatchingStrategy strategy;
    private final List<Driver> driverPool;
    MatchingEngine(MatchingStrategy strategy, List<Driver> driverPool) {
        this.strategy = strategy; this.driverPool = driverPool;
    }
    public Optional<Driver> match(RideRequest request) {
        Optional<Driver> candidate = strategy.findMatch(request, driverPool);
        // tryReserve() performs an atomic compare-and-swap-like check to prevent two
        // concurrent match() calls from both assigning the same driver
        if (candidate.isPresent() && candidate.get().tryReserve()) return candidate;
        return Optional.empty(); // race lost, caller should retry match with remaining pool
    }
}
```

**Concurrency note:** `tryReserve()` is the critical atomic operation preventing a race where two simultaneous ride requests both select the same nearest driver — the `synchronized` guard on the `Driver` object itself (not a lock on the whole `driverPool`) keeps contention scoped to a single driver, matching the HLD principle of narrow, per-entity locking rather than global locks. **Real system note:** in production this nearest-neighbor lookup over `driverPool` would use a spatial index (geohash/quadtree, see [SYSTEM_DESIGN_INTERVIEW_MASTERY_GUIDE.md](SYSTEM_DESIGN_INTERVIEW_MASTERY_GUIDE.md) §38 Proximity Service) rather than a linear scan — the LLD interview is testing your class design and locking discipline, not asking you to reimplement a spatial index live, so naming this as a "swap the linear scan for a geospatial index at scale" follow-up is the right level of depth.

### 7.4 Case Study: LLD for an In-Memory Key-Value Store

**Core entities:** `KeyValueStore` interface, an in-memory implementation with TTL support, an `EvictionPolicy` interface (Strategy pattern again) to plug in LRU/LFU/no-eviction.

```java
interface EvictionPolicy<K> {
    void recordAccess(K key);
    K evictionCandidate();
    void remove(K key);
}

class LRUEvictionPolicy<K> implements EvictionPolicy<K> {
    private final LinkedHashSet<K> accessOrder = new LinkedHashSet<>();
    public synchronized void recordAccess(K key) { accessOrder.remove(key); accessOrder.add(key); }
    public synchronized K evictionCandidate() { return accessOrder.iterator().hasNext() ? accessOrder.iterator().next() : null; }
    public synchronized void remove(K key) { accessOrder.remove(key); }
}

class ValueWrapper<V> {
    final V value;
    final long expiresAtMillis; // -1 means no expiry
    ValueWrapper(V value, long expiresAtMillis) { this.value = value; this.expiresAtMillis = expiresAtMillis; }
    boolean isExpired() { return expiresAtMillis != -1 && System.currentTimeMillis() > expiresAtMillis; }
}

class InMemoryKeyValueStore<K, V> {
    private final Map<K, ValueWrapper<V>> store = new ConcurrentHashMap<>();
    private final EvictionPolicy<K> evictionPolicy;
    private final int capacity;

    InMemoryKeyValueStore(int capacity, EvictionPolicy<K> evictionPolicy) {
        this.capacity = capacity; this.evictionPolicy = evictionPolicy;
    }

    public void put(K key, V value, long ttlMillis) {
        long expiresAt = ttlMillis <= 0 ? -1 : System.currentTimeMillis() + ttlMillis;
        synchronized (this) {
            if (!store.containsKey(key) && store.size() >= capacity) {
                K victim = evictionPolicy.evictionCandidate();
                if (victim != null) { store.remove(victim); evictionPolicy.remove(victim); }
            }
            store.put(key, new ValueWrapper<>(value, expiresAt));
            evictionPolicy.recordAccess(key);
        }
    }

    public Optional<V> get(K key) {
        ValueWrapper<V> wrapper = store.get(key);
        if (wrapper == null || wrapper.isExpired()) {
            if (wrapper != null) store.remove(key);
            return Optional.empty();
        }
        evictionPolicy.recordAccess(key);
        return Optional.of(wrapper.value);
    }

    public void delete(K key) { store.remove(key); evictionPolicy.remove(key); }
}
```

**Concurrency note:** `ConcurrentHashMap` handles safe concurrent reads/writes to the underlying map, while a narrow `synchronized` block guards only the "evict-then-insert" compound operation (which must be atomic to avoid a race where two threads both see the store as full and both evict, over-evicting). **Extensibility:** swapping `LRUEvictionPolicy` for an `LFUEvictionPolicy` (see [C-17](#c-17-microsoft-design-an-lfu-cache) for the frequency-bucket technique) requires zero changes to `InMemoryKeyValueStore` — again, the Strategy pattern payoff. **TTL note:** this lazy-expiry-on-read approach (checking `isExpired()` at `get()` time) is simple and correct but means expired-but-unread keys linger in memory; a production system would add a background sweeper thread scanning for expired keys periodically, trading a small amount of CPU for tighter memory bounds.

### 7.5 Case Study: LLD for a Parking Lot System

**Core entities:** `ParkingLot` (composition of `Level`s), `Level` (composition of `ParkingSpot`s), `ParkingSpot` (abstract, subtyped by size: `Motorcycle`, `Compact`, `Large`), `Vehicle` (abstract, subtyped by `Motorcycle`/`Car`/`Bus`), `Ticket`, and a `SpotAssignmentStrategy` interface (Strategy pattern — "nearest available spot" vs. "pack density-optimized" are different strategies).

```java
enum VehicleType { MOTORCYCLE, CAR, BUS }
enum SpotSize { SMALL, MEDIUM, LARGE }

abstract class Vehicle {
    final String licensePlate; final VehicleType type;
    Vehicle(String licensePlate, VehicleType type) { this.licensePlate = licensePlate; this.type = type; }
}
class Motorcycle extends Vehicle { Motorcycle(String plate) { super(plate, VehicleType.MOTORCYCLE); } }
class Car extends Vehicle { Car(String plate) { super(plate, VehicleType.CAR); } }
class Bus extends Vehicle { Bus(String plate) { super(plate, VehicleType.BUS); } }

class ParkingSpot {
    final String id; final SpotSize size; private Vehicle occupiedBy;
    ParkingSpot(String id, SpotSize size) { this.id = id; this.size = size; }
    public synchronized boolean tryPark(Vehicle vehicle) {
        if (occupiedBy != null || !fits(vehicle)) return false;
        occupiedBy = vehicle;
        return true;
    }
    public synchronized void vacate() { occupiedBy = null; }
    public boolean isAvailable() { return occupiedBy == null; }
    private boolean fits(Vehicle v) {
        if (v.type == VehicleType.BUS) return size == SpotSize.LARGE;
        if (v.type == VehicleType.CAR) return size == SpotSize.MEDIUM || size == SpotSize.LARGE;
        return true; // motorcycles fit any spot
    }
}

class Level {
    final int levelNumber; final List<ParkingSpot> spots;
    Level(int levelNumber, List<ParkingSpot> spots) { this.levelNumber = levelNumber; this.spots = spots; }
    public Optional<ParkingSpot> findAvailableSpot(Vehicle vehicle) {
        return spots.stream().filter(ParkingSpot::isAvailable).filter(s -> s.tryParkPreview(vehicle)).findFirst();
    }
}

class Ticket {
    final String ticketId; final String spotId; final String licensePlate; final long entryTimeMillis;
    Ticket(String ticketId, String spotId, String licensePlate, long entryTimeMillis) {
        this.ticketId = ticketId; this.spotId = spotId; this.licensePlate = licensePlate; this.entryTimeMillis = entryTimeMillis;
    }
}

interface PricingStrategy { double computeFee(long durationMillis); }
class HourlyPricingStrategy implements PricingStrategy {
    private final double ratePerHour;
    HourlyPricingStrategy(double ratePerHour) { this.ratePerHour = ratePerHour; }
    public double computeFee(long durationMillis) {
        double hours = Math.ceil(durationMillis / (1000.0 * 60 * 60));
        return hours * ratePerHour;
    }
}

class ParkingLot {
    private final List<Level> levels;
    private final Map<String, Ticket> activeTickets = new ConcurrentHashMap<>();
    private final Map<String, ParkingSpot> spotIndex = new HashMap<>();
    private final PricingStrategy pricingStrategy;
    ParkingLot(List<Level> levels, PricingStrategy pricingStrategy) {
        this.levels = levels; this.pricingStrategy = pricingStrategy;
        for (Level l : levels) for (ParkingSpot s : l.spots) spotIndex.put(s.id, s);
    }
    public Optional<Ticket> parkVehicle(Vehicle vehicle) {
        for (Level level : levels) {
            Optional<ParkingSpot> spotOpt = level.findAvailableSpot(vehicle);
            if (spotOpt.isPresent() && spotOpt.get().tryPark(vehicle)) {
                Ticket ticket = new Ticket(UUID.randomUUID().toString(), spotOpt.get().id, vehicle.licensePlate, System.currentTimeMillis());
                activeTickets.put(ticket.ticketId, ticket);
                return Optional.of(ticket);
            }
        }
        return Optional.empty(); // lot full for this vehicle type
    }
    public double exitVehicle(String ticketId) {
        Ticket ticket = activeTickets.remove(ticketId);
        if (ticket == null) throw new IllegalArgumentException("Invalid ticket");
        spotIndex.get(ticket.spotId).vacate();
        return pricingStrategy.computeFee(System.currentTimeMillis() - ticket.entryTimeMillis);
    }
}
```

**Concurrency note:** `ParkingSpot.tryPark` is `synchronized` at the individual-spot level, so two vehicles racing for the same spot cannot both succeed, while vehicles targeting different spots never contend with each other — the same narrow-locking discipline as [7.3](#73-case-study-lld-for-a-ride-hailing-matching-engine)'s `Driver.tryReserve()`. **Extensibility:** adding a new vehicle type (e.g., `ElectricCar` requiring a spot with a charger) only requires a new `Vehicle` subtype and updating `fits()` — the interviewer will often ask exactly this as a live follow-up to test how cleanly your class hierarchy accommodates it. **Note on `tryParkPreview`:** in a complete implementation this would be a non-mutating check (separate from `tryPark`'s mutating check-and-set) to support `findAvailableSpot`'s read-only search before the actual atomic `tryPark` call — worth mentioning explicitly if asked to elaborate, since conflating "check" and "check-and-commit" is a subtle bug source under concurrency.

### 7.6 Case Study: LLD for a Movie Ticket Booking System

**Core entities:** `Movie`, `Show` (a specific movie at a specific theater/time), `Seat`, `Booking`, and a `SeatLockManager` handling the temporary-hold mechanic described in the HLD version ([6.12](#612-case-study-design-a-ticket-booking-system)) at the class level.

```java
enum SeatStatus { AVAILABLE, LOCKED, BOOKED }

class Seat {
    final String seatId; private SeatStatus status = SeatStatus.AVAILABLE; private String lockedBy;
    Seat(String seatId) { this.seatId = seatId; }
    public synchronized boolean tryLock(String userId) {
        if (status != SeatStatus.AVAILABLE) return false;
        status = SeatStatus.LOCKED; lockedBy = userId;
        return true;
    }
    public synchronized boolean confirmBooking(String userId) {
        if (status != SeatStatus.LOCKED || !lockedBy.equals(userId)) return false;
        status = SeatStatus.BOOKED;
        return true;
    }
    public synchronized void releaseLock(String userId) {
        if (status == SeatStatus.LOCKED && lockedBy.equals(userId)) { status = SeatStatus.AVAILABLE; lockedBy = null; }
    }
}

class Show {
    final String showId; final String movieId; final Map<String, Seat> seats;
    Show(String showId, String movieId, List<String> seatIds) {
        this.showId = showId; this.movieId = movieId;
        this.seats = new HashMap<>();
        for (String id : seatIds) seats.put(id, new Seat(id));
    }
}

class Booking {
    final String bookingId; final String showId; final List<String> seatIds; final String userId;
    Booking(String bookingId, String showId, List<String> seatIds, String userId) {
        this.bookingId = bookingId; this.showId = showId; this.seatIds = seatIds; this.userId = userId;
    }
}

class BookingService {
    private final Map<String, Show> shows;
    private final ScheduledExecutorService lockExpiryScheduler = Executors.newScheduledThreadPool(1);
    private static final long LOCK_TIMEOUT_SECONDS = 300; // 5 minutes

    BookingService(Map<String, Show> shows) { this.shows = shows; }

    public boolean holdSeats(String showId, List<String> seatIds, String userId) {
        Show show = shows.get(showId);
        List<Seat> lockedSoFar = new ArrayList<>();
        for (String seatId : seatIds) {
            Seat seat = show.seats.get(seatId);
            if (seat == null || !seat.tryLock(userId)) {
                for (Seat s : lockedSoFar) s.releaseLock(userId); // roll back partial locks
                return false;
            }
            lockedSoFar.add(seat);
        }
        lockExpiryScheduler.schedule(() -> {
            for (Seat s : lockedSoFar) s.releaseLock(userId); // no-op if already confirmed/booked
        }, LOCK_TIMEOUT_SECONDS, TimeUnit.SECONDS);
        return true;
    }

    public Optional<Booking> confirmBooking(String showId, List<String> seatIds, String userId) {
        Show show = shows.get(showId);
        for (String seatId : seatIds) {
            if (!show.seats.get(seatId).confirmBooking(userId)) return Optional.empty();
        }
        return Optional.of(new Booking(UUID.randomUUID().toString(), showId, seatIds, userId));
    }
}
```

**Concurrency note:** `holdSeats` rolls back any partial locks it acquired if a later seat in the requested group is unavailable (e.g., a user booking 4 seats together shouldn't end up holding only 2) — an "all-or-nothing" acquisition pattern, conceptually similar to acquiring multiple locks safely in [D-5](#d-5-visa-simple-bank-account-system-lld)'s bank-transfer example, though here failure triggers rollback rather than ordered acquisition since seats within one booking request aren't inherently orderable the same way two fixed accounts are. **Extensibility:** the `LOCK_TIMEOUT_SECONDS` release mechanism directly implements the HLD case study's "background sweeper releases unconfirmed reservations" concept ([6.12](#612-case-study-design-a-ticket-booking-system)) at the class level using a `ScheduledExecutorService` — a good concrete example of how an HLD concept ("reservation timeout") becomes real code in an LLD round.

## Part 8 — Behavioral Interview: General MNC Framework

For a full 100-question behavioral bank with sample answers, resume/negotiation/company-research guidance, see [INTERVIEW_MASTERY_GUIDE.md](INTERVIEW_MASTERY_GUIDE.md). This section is a condensed framework you can use standalone.

### 8.1 The STAR method, condensed

Structure every behavioral answer as:
- **Situation:** 1–2 sentences of context (when, where, what team/project).
- **Task:** what specifically was YOUR responsibility or the challenge you faced.
- **Action:** the bulk of your answer (60–70% of the time) — what YOU specifically did, decisions you made, trade-offs you weighed. Use "I," not "we," even when describing team efforts — interviewers need to isolate your individual contribution.
- **Result:** quantified outcome where possible ("reduced deployment time by 40%," "the feature shipped 2 weeks ahead of the revised schedule"), plus what you learned or would do differently.

**Target length:** 90 seconds to 2.5 minutes per answer. Shorter reads as underprepared/shallow; longer loses the interviewer's attention and eats into the time available for follow-up questions (which is often where the real signal comes from).

### 8.2 The most common MNC behavioral themes

Nearly every large-company behavioral question maps to one of these underlying themes — prepare 1–2 stories per theme rather than trying to have a unique story for every possible phrasing:

| Theme | Typical question phrasing | What they're really testing |
|---|---|---|
| Ownership/initiative | "Tell me about a time you went beyond your defined role" | Do you take responsibility without being told to? |
| Conflict/disagreement | "Tell me about a time you disagreed with a teammate/manager" | Can you disagree respectfully and reach resolution? |
| Failure/mistake | "Tell me about a time you failed" | Self-awareness, accountability, learning from mistakes |
| Ambiguity | "Tell me about a time requirements were unclear" | Can you make progress without perfect information? |
| Prioritization/tradeoffs | "Tell me about a time you had to cut scope to meet a deadline" | Judgment under real-world constraints |
| Influencing without authority | "Tell me about a time you convinced others without positional power" | Communication and persuasion skill |
| Dealing with a difficult person | "Tell me about a difficult stakeholder/teammate" | Emotional regulation, professionalism |
| Learning something new fast | "Tell me about picking up a new technology/domain quickly" | Growth mindset, learning agility |
| Customer/user focus | "Tell me about a time you advocated for the user" | Whether you think beyond just "does the code work" |
| Leadership (even without title) | "Tell me about leading a project/initiative" | Leadership potential regardless of formal title |

### 8.3 Preparing your story bank

1. List 6–10 significant projects/experiences from your career or academic work.
2. For each, write 3–4 bullet points: the situation, your specific actions, the quantified result, and what you learned.
3. Map each story to 2–3 of the themes above — most good stories can answer multiple question types with a slightly different emphasis (the same project can illustrate "ownership" if you emphasize what you proactively did, or "conflict" if you emphasize a disagreement you navigated within it).
4. Practice saying each story out loud within a 2-minute timer — writing an answer and being able to *deliver* it smoothly under interview pressure are different skills, and only practice builds the second one.

---

## Part 9 — AMAZON DEEP DIVE: The Complete Playbook

This is a standalone, complete guide to Amazon's SWE hiring process — OA, phone screen, onsite loop, coding, system design, and the Leadership-Principles-driven behavioral bar that makes Amazon's process distinct from every other company in this guide.

### 9.1 Amazon's hiring process end-to-end

```
Application/Referral
        │
        ▼
Recruiter Screen (10-20 min call: background, motivation, logistics)
        │
        ▼
Online Assessment ("Amazon Assessment": OA1 coding + sometimes OA2 Work Style Assessment)
        │
        ▼
Phone/Video Screen (1 round, 45-60 min, 1 engineer, 1-2 coding questions + LP questions)
        │
        ▼
Virtual/Onsite Loop ("the loop"): 4-5 back-to-back interviews in one day
   ├── 2-3 Coding rounds (each also weaves in 1-2 LP behavioral questions)
   ├── 1 System Design round (for SDE-2/L5+ roles; sometimes present for strong SDE-1 candidates)
   └── 1 Bar Raiser round (a certified interviewer from OUTSIDE the hiring team, focused
       heavily on Leadership Principles, but can also ask coding/design questions)
        │
        ▼
Debrief Meeting (all interviewers present independent written feedback + Hire/No-Hire vote;
   the Bar Raiser can effectively block a hire even if every other interviewer says yes)
        │
        ▼
Hiring Manager decision + offer approval
        │
        ▼
Offer (base + sign-on bonus + RSU vesting, typically back-loaded: e.g., 5/15/40/40% over
   4 years, or an increasingly common more front-loaded structure depending on year/level)
        │
        ▼
Background check → Start date
```

**Key distinguishing facts about Amazon's process:**
- Amazon interviews are **the most explicitly behavioral-heavy of any FAANG company** — every single round, including pure coding rounds, includes Leadership Principles questions, typically 1–2 per round.
- Amazon uses a **written feedback + independent scoring** system rigorously — interviewers submit detailed notes with specific LP examples cited from your answers before any group discussion happens, to avoid anchoring bias.
- The **Bar Raiser** program is unique to Amazon at this level of formality (see [9.9](#99-the-bar-raiser-round-deep-dive)) — no other company in this guide has an equivalent institutionalized cross-team veto role.
- Amazon hires at extremely high volume, meaning the OA and phone-screen stages are more heavily automated/standardized as a filter than at, say, Google or Meta.

### 9.2 Amazon OA1 & OA2 breakdown

Amazon's online assessment is typically delivered in up to two parts, though not every candidate sees both (varies by role, location, and year):

- **OA1 — Coding Assessment:** 1–2 problems, ~70 minutes total (e.g., 2 problems at 35 minutes each, or split across 2 sittings on different days for some pipelines). Difficulty is consistently "LeetCode Medium," heavily story-wrapped in Amazon operational themes (warehouses, delivery routes, seller ratings, AWS-style resource allocation). Auto-graded against hidden test cases with partial credit.
- **OA2 — Work Style / Amazon Assessment:** an untimed (or generously timed) survey of paired statements, plus sometimes a "simulation" style logical-reasoning section presenting workplace scenarios and asking you to rank response options from "most effective" to "least effective" — this section is directly and explicitly scored against the Leadership Principles (see [2.7](#27-the-amazonemployer-work-style--personality-assessment) and [9.8](#98-all-16-amazon-leadership-principles-explained-with-sample-star-answers)).
- Some pipelines (especially intern/new-grad) also include a short **"Day in the Life"** realistic job preview video/quiz section — not scored competitively, more of an informational/expectation-setting module.

**Amazon OA-specific tips:**
- Amazon's hidden test cases are known to be strict about **time limits** — an O(n²) solution that would pass on a smaller platform's judge often times out on Amazon's OA for the stated constraints (commonly `n` up to 10^5–10^6). Always target the complexity the constraints imply.
- Amazon's problem statements are often **deliberately verbose with domain flavor** (e.g., 3 paragraphs about warehouse robot logistics) — spend the first 2 minutes explicitly translating the story into an abstract data-structure problem on scratch paper before coding.
- The Work Style Assessment repeats the same underlying trait multiple times with different wording — answer consistently and honestly (see [2.7](#27-the-amazonemployer-work-style--personality-assessment) for the full rationale).

### 9.3 Previously-asked Amazon OA questions with solutions

#### AOA-1. Substrings of Size K with K Distinct Characters

**Problem:** Count substrings of length exactly `k` where all `k` characters are distinct.

**Approach:** Sliding window of fixed size `k` with a frequency map; whenever the window's distinct-character count equals `k` (i.e., no character repeats within the window), increment the answer.

```java
int countGoodSubstrings(String s, int k) {
    if (s.length() < k) return 0;
    Map<Character, Integer> freq = new HashMap<>();
    int count = 0;
    for (int i = 0; i < s.length(); i++) {
        freq.merge(s.charAt(i), 1, Integer::sum);
        if (i >= k) {
            char out = s.charAt(i - k);
            freq.merge(out, -1, Integer::sum);
            if (freq.get(out) == 0) freq.remove(out);
        }
        if (i >= k - 1 && freq.size() == k) count++;
    }
    return count;
}
```
**Complexity:** O(n). **Pattern:** fixed-size sliding window + frequency map — one of the single most-repeated Amazon OA skeletons.

#### AOA-2. Minimum Cost to Connect Ropes

**Problem:** Given rope lengths, the cost to connect two ropes is the sum of their lengths. Find the minimum total cost to connect all ropes into one.

**Approach:** Greedily always connect the two currently-shortest ropes (classic min-heap/Huffman-style greedy).

```java
int connectRopes(int[] ropes) {
    PriorityQueue<Integer> minHeap = new PriorityQueue<>();
    for (int r : ropes) minHeap.offer(r);
    int totalCost = 0;
    while (minHeap.size() > 1) {
        int first = minHeap.poll(), second = minHeap.poll();
        int cost = first + second;
        totalCost += cost;
        minHeap.offer(cost);
    }
    return totalCost;
}
```
**Complexity:** O(n log n). **Pattern:** greedy + min-heap, structurally identical to Huffman coding's merge step — a favorite Amazon "resource combination cost" wrapper.

#### AOA-3. Slowest Key (Longest Key Press)

**Problem:** Given `releaseTimes[]` and corresponding `keysPressed` string, find the key that was pressed for the longest duration (ties broken by lexicographically largest key).

**Approach:** Single pass computing each press's duration as the difference from the previous release time, tracking the best so far with the tie-break rule.

```java
char slowestKey(int[] releaseTimes, String keysPressed) {
    char best = keysPressed.charAt(0);
    int bestDuration = releaseTimes[0];
    for (int i = 1; i < releaseTimes.length; i++) {
        int duration = releaseTimes[i] - releaseTimes[i - 1];
        char key = keysPressed.charAt(i);
        if (duration > bestDuration || (duration == bestDuration && key > best)) {
            bestDuration = duration; best = key;
        }
    }
    return best;
}
```
**Complexity:** O(n). **Pattern:** single-pass "track the best with a tie-break rule" — deceptively simple but a very common source of off-by-one/tie-break bugs under time pressure.

#### AOA-4. Circular Array Rotation Queries

**Problem:** Given an array, rotate it right by `d` positions, then answer multiple index queries against the rotated array without materializing the full rotated array for each query.

**Approach:** Answer each query in O(1) using modular index arithmetic: `rotated[i] = original[(i - d + n) % n]`.

```java
int[] rotationQueries(int[] arr, int d, int[] queries) {
    int n = arr.length;
    int[] answers = new int[queries.length];
    for (int i = 0; i < queries.length; i++) {
        int idx = ((queries[i] - d) % n + n) % n;
        answers[i] = arr[idx];
    }
    return answers;
}
```
**Complexity:** O(1) per query after O(1) setup. **Pattern:** modular arithmetic to avoid materializing a rotated/shifted structure — reused across many "virtual rotation" OA variants.

#### AOA-5. Count Pairs With Given Sum

**Problem:** Count the number of index pairs `(i, j)` with `i < j` such that `arr[i] + arr[j] == target`.

**Approach:** Single pass with a frequency map — for each element, count how many previously-seen elements would complete the pair, then record the current element.

```java
int countPairsWithSum(int[] arr, int target) {
    Map<Integer, Integer> seen = new HashMap<>();
    int count = 0;
    for (int num : arr) {
        int complement = target - num;
        count += seen.getOrDefault(complement, 0);
        seen.merge(num, 1, Integer::sum);
    }
    return count;
}
```
**Complexity:** O(n). **Pattern:** the "count, don't just find" variant of two-sum — process left to right so each pair is counted exactly once without a nested loop.

#### AOA-6. Autoscaling Policy Simulation

**Problem:** Simulate an autoscaling policy: given a stream of per-minute average CPU utilization readings, scale instance count up (double it) if average utilization > 50 (capped at a max), or scale down (decrease by 1, minimum 1) if utilization < 25; otherwise no change. Return the final instance count.

**Approach:** Direct simulation, one pass, applying the stated rules in order with the stated caps/floors.

```java
int finalInstances(int[] utilization, int maxInstances) {
    int instances = 1;
    for (int u : utilization) {
        if (u > 50) instances = Math.min(maxInstances, instances * 2);
        else if (u < 25) instances = Math.max(1, instances - 1);
        // else: no change
    }
    return instances;
}
```
**Complexity:** O(n). **Pattern:** rule-based simulation — the key skill is translating the verbose stated policy into exact conditional logic without misreading a threshold as inclusive/exclusive (always re-check `>` vs `>=` against the literal problem text).

#### AOA-7. Nearest Warehouses (K Nearest Points, Manhattan Distance)

**Problem:** Given warehouse coordinates and a customer location, find the `k` nearest warehouses using Manhattan distance.

**Approach:** Max-heap of size `k` keyed by Manhattan distance (same bounded-heap pattern as [C-14 style K-closest problems](#c-24-uber-meeting-rooms-ii), adapted to Manhattan distance).

```java
int[][] nearestWarehouses(int[][] warehouses, int[] customer, int k) {
    PriorityQueue<int[]> maxHeap = new PriorityQueue<>((a, b) -> manhattan(b, customer) - manhattan(a, customer));
    for (int[] w : warehouses) {
        maxHeap.offer(w);
        if (maxHeap.size() > k) maxHeap.poll();
    }
    return maxHeap.toArray(new int[0][]);
}
private int manhattan(int[] point, int[] customer) {
    return Math.abs(point[0] - customer[0]) + Math.abs(point[1] - customer[1]);
}
```
**Complexity:** O(n log k). **Pattern:** bounded max-heap for "k nearest," reused with a different distance metric — recognizing that the heap skeleton doesn't change, only the comparator.

#### AOA-8. Reorder Data in Log Files

**Problem:** Given log lines each starting with an identifier followed by either words or digits, reorder so all "letter-logs" come before "digit-logs"; letter-logs are sorted lexicographically by content (identifier as tiebreaker), digit-logs keep their original relative order.

**Approach:** Custom comparator classifying each log as letter/digit type, split into two groups conceptually via a stable sort with a comparator that always ranks digit-logs after letter-logs and orders letter-logs by (content, identifier).

```java
String[] reorderLogFiles(String[] logs) {
    Arrays.sort(logs, (a, b) -> {
        String[] splitA = a.split(" ", 2), splitB = b.split(" ", 2);
        boolean aDigit = Character.isDigit(splitA[1].charAt(0));
        boolean bDigit = Character.isDigit(splitB[1].charAt(0));
        if (!aDigit && !bDigit) {
            int cmp = splitA[1].compareTo(splitB[1]);
            return cmp != 0 ? cmp : splitA[0].compareTo(splitB[0]);
        }
        return aDigit && bDigit ? 0 : (aDigit ? 1 : -1); // digit-logs go after, stable sort keeps their relative order
    });
    return logs;
}
```
**Complexity:** O(n log n · L) where L is average log length (for string comparisons). **Pattern:** custom multi-criteria comparator + reliance on Java's stable sort (`Arrays.sort` on objects uses a stable Timsort) to preserve original order for the "equal" digit-log case — a frequently-reported real Amazon OA question.

### 9.4 Amazon phone screen specifics

- **Format:** one 60-minute video call (Amazon Chime), one engineer, typically 1 coding problem with enough time for a second shorter one or a design-adjacent follow-up, plus 1–2 explicit Leadership Principle questions worked into the first 10–15 minutes.
- **What's different from a generic phone screen:** the interviewer is filling out a structured feedback form that explicitly maps parts of your answer to specific LPs (e.g., "candidate showed Ownership when describing how they handled a production incident outside their normal on-call rotation") — this means even your *coding* round answers to "walk me through a time..." warm-up questions are being scored against the LP rubric, not just used as icebreakers.
- **Practical implication:** prepare 2–3 STAR stories specifically before a phone screen (not just for the onsite) — many candidates under-prepare behavioral content for what they assume is "just a coding round" and are caught flat-footed.

### 9.5 Amazon onsite loop structure

A typical Amazon SDE loop (in-person or virtual) runs 4–5 back-to-back 45–60 minute rounds in one day, with a short break between each:

| Round | Typical focus | Notes |
|---|---|---|
| Round 1 | Coding + LP | Usually a moderate DSA problem plus 1-2 LP questions |
| Round 2 | Coding (harder) + LP | May include a 2-part problem where constraints change mid-way |
| Round 3 | System Design (HLD) + LP | For SDE-2/L5+ roles; strong SDE-1 candidates sometimes get a lighter version |
| Round 4 | Bar Raiser (heavy LP focus, can include coding/design too) | Interviewer is from OUTSIDE your hiring team, certified in Amazon's bar-raising program |
| Round 5 (if present) | Hiring Manager | Team fit, role expectations, your questions about the team |

**What makes the Amazon loop uniquely intense:** because every single round blends technical evaluation with explicit LP scoring, there is effectively **no round where you can "coast" on behavioral prep** — even your system design round interviewer is listening for LPs like "Are Right, A Lot," "Dive Deep," and "Ownership" in how you justify design trade-offs, not just for correct system design mechanics.

### 9.6 Amazon coding interview: previously-asked questions

These are additional Amazon-tagged coding problems (distinct from [Part 5.2](#52-amazon-tagged-questions) and the OA problems in [9.3](#93-previously-asked-amazon-oa-questions-with-solutions)) commonly reported in Amazon onsite loops.

#### ACI-1. Critical Connections in a Network (Bridges in a Graph)

**Problem:** Given a network of servers as an undirected graph, find all "critical connections" (bridges) — edges whose removal would disconnect part of the network.

**Approach:** Tarjan's bridge-finding algorithm — DFS tracking discovery time and the lowest reachable discovery time (`low[]`) via back-edges; an edge `(u, v)` is a bridge if `low[v] > disc[u]`.

```java
List<List<Integer>> criticalConnections(int n, List<List<Integer>> connections) {
    List<List<Integer>> graph = new ArrayList<>();
    for (int i = 0; i < n; i++) graph.add(new ArrayList<>());
    for (List<Integer> c : connections) { graph.get(c.get(0)).add(c.get(1)); graph.get(c.get(1)).add(c.get(0)); }
    int[] disc = new int[n], low = new int[n];
    Arrays.fill(disc, -1);
    List<List<Integer>> bridges = new ArrayList<>();
    int[] timer = {0};
    dfs(0, -1, graph, disc, low, timer, bridges);
    return bridges;
}
private void dfs(int u, int parent, List<List<Integer>> graph, int[] disc, int[] low, int[] timer, List<List<Integer>> bridges) {
    disc[u] = low[u] = timer[0]++;
    for (int v : graph.get(u)) {
        if (v == parent) continue;
        if (disc[v] == -1) {
            dfs(v, u, graph, disc, low, timer, bridges);
            low[u] = Math.min(low[u], low[v]);
            if (low[v] > disc[u]) bridges.add(Arrays.asList(u, v));
        } else {
            low[u] = Math.min(low[u], disc[v]);
        }
    }
}
```
**Complexity:** O(V + E). **Why Amazon likes it:** directly models real network/service-topology resilience analysis (which connections, if lost, partition the fleet) — Amazon's infrastructure scale makes this a naturally-motivated question, and it tests genuine graph-theory depth beyond basic BFS/DFS.

#### ACI-2. Course Schedule (Detect Cycle via Topological Sort)

**Problem:** Given `numCourses` and prerequisite pairs, determine if it's possible to finish all courses (i.e., the prerequisite graph has no cycle).

**Approach:** Kahn's algorithm — compute in-degrees, repeatedly remove zero-in-degree nodes; if all nodes are eventually removed, no cycle exists.

```java
boolean canFinish(int numCourses, int[][] prerequisites) {
    List<List<Integer>> graph = new ArrayList<>();
    for (int i = 0; i < numCourses; i++) graph.add(new ArrayList<>());
    int[] indegree = new int[numCourses];
    for (int[] p : prerequisites) { graph.get(p[1]).add(p[0]); indegree[p[0]]++; }
    Queue<Integer> queue = new LinkedList<>();
    for (int i = 0; i < numCourses; i++) if (indegree[i] == 0) queue.offer(i);
    int visited = 0;
    while (!queue.isEmpty()) {
        int course = queue.poll();
        visited++;
        for (int next : graph.get(course)) {
            if (--indegree[next] == 0) queue.offer(next);
        }
    }
    return visited == numCourses;
}
```
**Complexity:** O(V + E). **Why Amazon likes it:** dependency-resolution questions (build systems, deployment ordering, microservice startup order) are a direct real-world analog frequently referenced by Amazon interviewers as the "why" behind this question.

#### ACI-3. Design a Hit Counter

**Problem:** Design a class counting the number of hits received in the past 5 minutes (300 seconds), given `hit(timestamp)` calls that arrive in non-decreasing timestamp order.

**Approach:** A queue of timestamps; on each `hit`, enqueue; on each `getHits`, dequeue all timestamps older than `timestamp - 300` before returning the queue size.

```java
class HitCounter {
    private final Queue<Integer> hits = new LinkedList<>();
    public void hit(int timestamp) { hits.offer(timestamp); }
    public int getHits(int timestamp) {
        while (!hits.isEmpty() && hits.peek() <= timestamp - 300) hits.poll();
        return hits.size();
    }
}
```
**Complexity:** O(1) amortized per call. **Why Amazon likes it:** a miniature version of real-time metrics/monitoring infrastructure (think CloudWatch-style rolling-window counters) — a natural "design a small piece of AWS" style question.

#### ACI-4. Pacific Atlantic Water Flow

**Problem:** Given a grid of heights, find all cells from which water can flow to both the Pacific (top/left edges) and Atlantic (bottom/right edges) oceans, where water flows from a cell to an equal-or-lower neighboring cell.

**Approach:** Reverse the flow direction — run BFS/DFS from all Pacific-adjacent border cells (water flowing "uphill" from the ocean inward, i.e., moving to equal-or-higher cells) to mark Pacific-reachable cells, do the same for Atlantic, then intersect the two reachable sets.

```java
List<List<Integer>> pacificAtlantic(int[][] heights) {
    int rows = heights.length, cols = heights[0].length;
    boolean[][] pacific = new boolean[rows][cols], atlantic = new boolean[rows][cols];
    for (int i = 0; i < rows; i++) { dfs(heights, i, 0, pacific); dfs(heights, i, cols - 1, atlantic); }
    for (int j = 0; j < cols; j++) { dfs(heights, 0, j, pacific); dfs(heights, rows - 1, j, atlantic); }
    List<List<Integer>> result = new ArrayList<>();
    for (int i = 0; i < rows; i++)
        for (int j = 0; j < cols; j++)
            if (pacific[i][j] && atlantic[i][j]) result.add(Arrays.asList(i, j));
    return result;
}
private int[][] dirs = {{0,1},{0,-1},{1,0},{-1,0}};
private void dfs(int[][] heights, int i, int j, boolean[][] visited) {
    visited[i][j] = true;
    for (int[] d : dirs) {
        int ni = i + d[0], nj = j + d[1];
        if (ni >= 0 && nj >= 0 && ni < heights.length && nj < heights[0].length
            && !visited[ni][nj] && heights[ni][nj] >= heights[i][j]) {
            dfs(heights, ni, nj, visited);
        }
    }
}
```
**Complexity:** O(rows × cols). **Why Amazon likes it:** the "reverse the direction of flow to avoid recomputation from every cell" insight is the kind of clever reframing Amazon interviewers specifically probe for with a follow-up ("your first instinct is probably O(rows×cols) BFS from every single cell — can you do better?").

### 9.7 Amazon system design round: what's different

Amazon's system design round uses the same universal HLD framework from [6.2](#62-the-universal-hld-framework-step-by-step), but with distinct emphases interviewers are specifically trained to probe:

1. **Scale is assumed to be "Amazon scale" by default** — if you don't ask, assume the interviewer wants a design that works for tens of millions of users/requests, not a toy scale. Always do the back-of-envelope estimation step explicitly rather than skipping it.
2. **Cost-consciousness ("Frugality" LP) is an explicit evaluation axis** — you may be asked "how would you reduce the cost of this design?" even if it already meets functional/scale requirements. Being ready to discuss cheaper storage tiers, spot instances for batch work, or caching to reduce expensive downstream calls is expected.
3. **"Dive Deep" is tested via unprompted depth** — strong candidates proactively go deep on at least one non-obvious edge case or failure mode without being explicitly asked, rather than waiting to be steered.
4. **Trade-off articulation ("Are Right, A Lot" / "Have Backbone; Disagree and Commit")** — you're expected to state a clear recommendation and defend it with data/reasoning, not present a wishy-washy list of options with no opinion; if the interviewer pushes back, engage with their point substantively rather than immediately capitulating OR stubbornly refusing to update your view — show you can be persuaded by good evidence.
5. **Operational excellence framing** — Amazon interviewers often ask "how would you know if this is broken in production?" (monitoring/alerting/dashboards) as an explicit deep-dive topic, reflecting Amazon's strong operational/on-call culture.

**Worked example 1 — "Design the Buy Box" (which seller wins the default 'Add to Cart' button for a product with multiple sellers):** Requirements: multiple sellers can list the same product; the system must pick one "winning" offer shown by default based on price, shipping speed, seller rating, and stock, recomputed frequently as sellers change price/stock. Approach: an offline/near-real-time scoring pipeline (not computed synchronously on every page view) that ranks offers per product using a weighted formula, writes the current winner to a fast read-optimized cache keyed by `productId`, and refreshes on relevant events (price change, stock change) via an event-driven pipeline rather than polling — the product page's hot read path just reads the pre-computed winner from cache, keeping page-load latency low regardless of how expensive the ranking computation is. This tests exactly the "separate the expensive write-side computation from the cheap, low-latency read-side lookup" pattern that recurs throughout Amazon's real systems (also seen in [6.4](#64-case-study-design-an-e-commerce-cart--inventory-system) and [6.8](#68-case-study-design-a-notificationalerting-system)).

**Worked example 2 — "Design a Distributed Rate Limiter" (protect an internal API from being overwhelmed by another internal service):** Requirements: enforce a per-client request-rate ceiling across a fleet of API servers (not just per-server, which would allow a client to exceed the true limit by hitting different servers). Approach: a shared, low-latency counter store (e.g., Redis) implementing the token-bucket algorithm with atomic increment-and-check operations (`INCR` + `EXPIRE`, or a Lua script for atomicity), sharded by client ID so no single Redis instance becomes a bottleneck for the aggregate traffic of all clients; discuss the trade-off between strict global accuracy (requiring a single coordination point, adding latency) versus an approximate, sharded/local-with-periodic-sync approach that trades a small amount of over-admission for much lower latency and higher availability — Amazon interviewers specifically like seeing you name this trade-off explicitly rather than presenting only the "perfectly accurate" version.

### 9.8 All 16 Amazon Leadership Principles, explained, with sample STAR answers

Every Amazon interview round scores your answers against these 16 principles. For each one below: the principle in Amazon's own spirit, what interviewers are specifically listening for, a typical question phrasing, and a full sample STAR answer you can use as a template for your own story (swap in your own specifics — never use a sample answer verbatim, interviewers can tell).

#### LP 1 — Customer Obsession

> "Leaders start with the customer and work backwards. They work vigorously to earn and keep customer trust."

**What interviewers listen for:**
- Do you default to thinking about end-user/customer impact, not just "did the ticket get closed"?
- Have you ever changed a technical decision specifically because of customer impact data?
- Do you distinguish between internal stakeholder convenience and actual customer benefit?

**Typical question:** "Tell me about a time you went above and beyond for a customer."

**Sample STAR answer:**
- **Situation:** During an on-call rotation, I noticed a small but growing percentage of checkout failures for users on older mobile browsers, well below our team's normal alert threshold.
- **Task:** The failures weren't severe enough to page anyone, and fixing them wasn't on the current sprint, but I suspected real customers were quietly abandoning purchases.
- **Action:** I pulled session logs, correlated the failures with a specific browser/JS-engine combination, and built a small reproduction case. I raised it with my manager with the estimated revenue impact I calculated from the conversion funnel, and proposed a scoped one-day fix rather than waiting for the next planning cycle.
- **Result:** We shipped the fix within 2 days; checkout completion for that browser segment recovered to the site-wide average, recovering an estimated several thousand dollars/month in previously-lost conversions. It also became a lightweight monitoring rule so similar regressions are caught automatically going forward.

**Common mistakes:** describing "the customer" only as an internal stakeholder (your PM, your teammate) rather than the actual end-user; failing to show you noticed the problem proactively rather than being told to fix it.

#### LP 2 — Ownership

> "Leaders are owners. They think long term and don't sacrifice long-term value for short-term results. They act on behalf of the entire company, beyond just their own team."

**What interviewers listen for:**
- Do you take responsibility for outcomes even outside your explicit job description?
- Do you follow through on things long after the "exciting" part is done?
- Do you say "I" and take accountability, or deflect blame to others/circumstances?

**Typical question:** "Tell me about a time you took ownership of something that wasn't officially your responsibility."

**Sample STAR answer:**
- **Situation:** A recurring deployment failure kept affecting multiple teams, but because the failing script lived in a shared infra repo nobody "owned," it kept getting worked around instead of fixed.
- **Task:** I decided to actually root-cause it, even though it wasn't part of my team's charter.
- **Action:** I spent a day tracing the failure to a race condition in a deployment health-check script, wrote a fix, added a regression test, and — since I didn't own the repo — found the right approver, wrote a clear PR description explaining the root cause and impact across teams, and got it reviewed and merged.
- **Result:** Deployment failures across the org dropped by an estimated 80% for that failure class. I also documented the root cause in our internal wiki so future engineers wouldn't rediscover the same race condition from scratch.

**Common mistakes:** picking a story where you only did what was explicitly assigned; not being able to explain the long-term follow-through (Ownership stories should show persistence past the "fun" initial diagnosis).

#### LP 3 — Invent and Simplify

> "Leaders expect and require innovation and invention from their teams and always look for ways to simplify. They are externally aware, look for new ideas from everywhere, and are not limited by 'not invented here.'"

**What interviewers listen for:**
- Have you actually built/proposed something novel, or only maintained existing systems?
- Do you value simplification as much as invention (Amazon explicitly weights both)?
- Are you willing to adopt an external idea/tool rather than insisting on building everything in-house?

**Typical question:** "Tell me about a time you invented a simple solution to a complex problem."

**Sample STAR answer:**
- **Situation:** Our team's data-validation pipeline had grown into a tangle of ~15 sequential, hand-written validation scripts, each added ad hoc over 2 years, taking 40 minutes to run and frequently breaking when one script's assumptions changed.
- **Task:** I was asked to add yet another validation rule, but realized the underlying architecture itself was the real problem.
- **Action:** Instead of adding script #16, I proposed and built a small declarative rule-engine where validations are defined as simple config entries (field, condition, error message) evaluated by one generic engine, replacing the 15 scripts with data.
- **Result:** Runtime dropped from 40 minutes to under 3 minutes (rules run in parallel), and adding a new validation became a 5-line config change instead of a new script — the team added 8 new rules in the following quarter with zero new code review overhead for pipeline logic itself.

**Common mistakes:** describing a complex, over-engineered "invention" (Amazon explicitly values simplification alongside invention — a solution that's clever but more complicated than the problem warrants often backfires as a signal here).

#### LP 4 — Are Right, A Lot

> "Leaders are right a lot. They have strong judgment and good instincts. They seek diverse perspectives and work to disconfirm their own beliefs."

**What interviewers listen for:**
- Do you have a track record of good judgment calls, backed by reasoning/data, not just luck?
- Do you actively seek out disconfirming evidence/opposing views before committing to a decision?
- Can you describe a time your initial instinct was wrong and you updated based on evidence?

**Typical question:** "Tell me about a decision you made with incomplete information."

**Sample STAR answer:**
- **Situation:** Midway through a migration project, I had to choose between two message-queue technologies for a new event pipeline, with the team split roughly evenly on preference.
- **Task:** As the engineer most familiar with our throughput requirements, I was asked to make the final call within a week.
- **Action:** Rather than going with my initial instinct (the tool I was personally more familiar with), I ran a short load test against both candidates using realistic traffic shapes, explicitly asked two engineers who preferred the other option to poke holes in my test methodology, and incorporated their feedback into a second round of testing.
- **Result:** The data showed the less-familiar-to-me option actually handled our specific bursty traffic pattern meaningfully better; I recommended it despite my initial preference, and the team adopted it — it's handled 18 months of production traffic since with no capacity-related incidents.

**Common mistakes:** describing a decision where you were simply "right" without showing the process (data-gathering, seeking disconfirming views) — Amazon cares about the judgment *process*, not just the outcome.

#### LP 5 — Learn and Be Curious

> "Leaders are never done learning and always seek to improve themselves. They are curious about new possibilities and act to explore them."

**What interviewers listen for:**
- Do you proactively learn outside of what's strictly required for your current task?
- Can you describe genuinely picking up a new domain/technology, not just attending a training?
- Do you show curiosity as an ongoing habit, not a one-off event?

**Typical question:** "Tell me about a time you learned something completely new to solve a problem."

**Sample STAR answer:**
- **Situation:** Our team needed to add basic anomaly detection to a monitoring dashboard, but nobody on the team had a background in statistics or ML.
- **Task:** I volunteered to figure out an approach, despite it being well outside my prior experience (I'd only done standard backend/API work before).
- **Action:** I spent evenings over two weeks working through introductory material on time-series anomaly detection, prototyped three approaches (simple moving-average thresholds, seasonal decomposition, and a lightweight isolation-forest model) against our real historical metrics data, and picked the simplest one that met our accuracy bar rather than the most sophisticated one.
- **Result:** We shipped a working anomaly detector that caught 3 real incidents in its first month that our static thresholds had missed. I also ran an informal lunch-and-learn sharing what I'd learned so the rest of the team wasn't dependent on just me understanding it.

**Common mistakes:** citing only formal training/courses without showing you applied the new knowledge to solve an actual problem.

#### LP 6 — Hire and Develop the Best

> "Leaders raise the performance bar with every hire and promotion. They recognize exceptional talent and willingly move them throughout the organization. Leaders develop leaders and take seriously their role in coaching others."

**What interviewers listen for:**
- (For candidates without formal management experience, this is usually reframed around mentoring/onboarding peers, not literal hiring.)
- Have you helped a teammate or new hire genuinely grow, not just answered their immediate questions?
- Do you give honest, constructive feedback even when it's uncomfortable?

**Typical question:** "Tell me about a time you helped a colleague improve or grow."

**Sample STAR answer:**
- **Situation:** A new graduate joined our team and was struggling to get code reviews approved quickly, often resubmitting the same style/structure issues repeatedly.
- **Task:** As the engineer who reviewed most of their PRs, I wanted to help them improve faster than just leaving repeated inline comments.
- **Action:** I set up a recurring 30-minute weekly pairing session specifically focused on the recurring patterns I was seeing (not just fixing individual PRs), walked through the "why" behind our conventions rather than just the "what," and gave them a small side project to practice applying the patterns independently.
- **Result:** Within about six weeks, their PR review cycle time dropped by more than half and first-pass approval rate rose substantially; they later told me the pairing sessions were the most useful onboarding help they received, and I've since used the same structured-pairing approach with two other new team members.

**Common mistakes:** describing only "answering questions when asked" rather than proactive, structured investment in someone else's growth.

#### LP 7 — Insist on the Highest Standards

> "Leaders have relentlessly high standards — many people may think these standards are unreasonably high. Leaders are continually raising the bar and driving their teams to deliver high quality products, services, and processes."

**What interviewers listen for:**
- Have you pushed back on shipping something you believed was subpar, even under deadline pressure?
- Do you distinguish between "good enough to ship" and "actually meets a high bar," and can you articulate why the difference mattered?

**Typical question:** "Tell me about a time you refused to compromise on quality despite pressure to do so."

**Sample STAR answer:**
- **Situation:** Close to a release deadline, a teammate proposed shipping a feature with a known edge case that could silently corrupt a small percentage of user data under specific timing conditions, reasoning that it was "rare enough."
- **Task:** I disagreed that "rare" was an acceptable bar for silent data corruption, even under deadline pressure.
- **Action:** I wrote up a concrete reproduction case showing the corruption happening reliably under a specific but realistic sequence of user actions, quantified the estimated affected-user count based on our traffic patterns, and proposed a scoped two-day fix plus a short, clearly-communicated one-day slip rather than a larger delay.
- **Result:** The team agreed to the short delay; we shipped the fix, and a post-launch audit confirmed zero instances of the corruption pattern in production, versus an estimated dozens of affected users per week had we shipped as originally planned.

**Common mistakes:** describing a standards story that's really about a minor cosmetic/style preference rather than a substantive quality/correctness issue with real user impact.

#### LP 8 — Think Big

> "Thinking small is a self-fulfilling prophecy. Leaders create and communicate a bold direction that inspires results. They think differently and look around corners for ways to serve customers."

**What interviewers listen for:**
- Can you describe proposing something bigger in scope than what was explicitly asked for, when justified?
- Do you connect a specific technical proposal to a larger strategic/business outcome?

**Typical question:** "Tell me about a time you proposed a bold or ambitious solution."

**Sample STAR answer:**
- **Situation:** I was asked to fix a specific recurring bug in our internal reporting tool that a few analysts complained about weekly.
- **Task:** While investigating, I realized the bug was a symptom of a much larger problem: the entire reporting tool was built on a brittle, unmaintained scripting layer that would keep generating similar bugs indefinitely.
- **Action:** Rather than patching just the reported bug, I put together a short proposal (with rough effort estimates and a phased migration plan) to rebuild the reporting layer on our team's standard, supported tech stack, and presented the long-term cost of NOT doing it (the ongoing stream of similar bugs and analyst time lost) to my manager and the analytics team lead.
- **Result:** The proposal was approved as a quarter-long initiative; after the rebuild, similar recurring-bug reports dropped to near zero, and the new reporting layer was later extended by another team to serve a second, unrelated use case we hadn't originally anticipated.

**Common mistakes:** conflating "thinking big" with simply working on a large project someone else already scoped — the signal Amazon wants is that YOU expanded the scope/ambition beyond what was asked.

#### LP 9 — Bias for Action

> "Speed matters in business. Many decisions and actions are reversible and do not need extensive study. We value calculated risk taking."

**What interviewers listen for:**
- Do you distinguish between reversible ("two-way door") and irreversible ("one-way door") decisions, moving fast on the former?
- Have you avoided unnecessary analysis-paralysis on a low-risk decision?
- Do you take calculated risks, or do you only ever act once every possible unknown is resolved?

**Typical question:** "Tell me about a time you made a fast decision without complete information."

**Sample STAR answer:**
- **Situation:** During an incident, our primary metrics dashboard went down at the same time error rates seemed to be climbing, leaving us without our normal way to confirm severity.
- **Task:** As the on-call engineer, I had to decide whether to page additional responders and start customer communications, or wait for the dashboard to come back to get clearer data.
- **Action:** I judged this as a reversible decision (paging extra people and drafting a status update we could always retract costs little if I was wrong) versus the higher cost of delaying response if the outage was real, so I paged two additional engineers and drafted (but didn't yet send) a customer status update, while a teammate worked to restore the dashboard in parallel.
- **Result:** The dashboard came back within 12 minutes and confirmed a real, significant error spike; because we'd already paged the right people, our actual mitigation started nearly 15 minutes earlier than if we'd waited, and the drafted status update was ready to publish the moment we confirmed severity.

**Common mistakes:** describing a genuinely reckless, irreversible decision made carelessly (Amazon explicitly distinguishes "calculated risk" from recklessness — always show the reasoning for why moving fast was the right call given the reversibility of the action).

#### LP 10 — Frugality

> "Accomplish more with less. Constraints breed resourcefulness, self-sufficiency, and invention. There are no extra points for growing headcount, budget size, or fixed expense."

**What interviewers listen for:**
- Have you solved a problem with fewer resources (time, money, headcount, infrastructure cost) than the "obvious" approach would require?
- Do you consider cost as a real engineering constraint, not just a finance-team concern?

**Typical question:** "Tell me about a time you accomplished something significant with limited resources."

**Sample STAR answer:**
- **Situation:** Our team wanted a real-time alerting system for a new service, and the default recommendation from another team was to adopt a fairly expensive third-party observability platform with a significant per-month licensing cost.
- **Task:** Given our budget constraints that quarter, I was asked to find a cheaper path that still met our actual monitoring needs.
- **Action:** I audited what we actually needed (a handful of specific metric thresholds and a Slack alert), and realized our existing logging infrastructure plus a lightweight open-source metrics exporter could cover about 90% of the use cases the expensive platform offered, at a small fraction of the cost, with a short one-week setup effort.
- **Result:** We shipped adequate monitoring for effectively no ongoing licensing cost instead of a five-figure annual commitment, and used the saved budget to fund a separate, higher-priority infrastructure investment that quarter.

**Common mistakes:** describing frugality as simply "being cheap" without connecting it to a genuine trade-off analysis of what was actually needed versus what was on offer.

#### LP 11 — Earn Trust

> "Leaders listen attentively, speak candidly, and treat others respectfully. They are vocally self-critical, even when doing so is awkward or embarrassing. Leaders do not believe their or their team's body odor smells of perfume."

**What interviewers listen for:**
- Do you admit your own mistakes openly, including in front of others, rather than deflecting?
- Do you give and receive candid feedback respectfully?
- Do you build credibility through consistency between what you say and what you do?

**Typical question:** "Tell me about a time you had to admit you were wrong."

**Sample STAR answer:**
- **Situation:** I had pushed back fairly firmly in a design review against a teammate's proposed caching approach, convinced my alternative was clearly better, and the team went with my recommendation.
- **Task:** Within two weeks of shipping, we started seeing a class of stale-data bugs that traced directly back to the caching approach I had advocated for.
- **Action:** I raised it myself in our next team sync rather than waiting for someone else to notice, explained clearly what I'd gotten wrong in my original reasoning (I'd underestimated how often the underlying data changed), and proposed reverting to closer to my teammate's original suggestion with an added improvement addressing a gap I'd since noticed in it too.
- **Result:** We fixed the bug class within days of the revised approach shipping, and I made a point of publicly crediting my teammate's original instinct being closer to correct — a few teammates later told me they appreciated that I owned the mistake directly rather than letting it linger unaddressed.

**Common mistakes:** picking a story where "the mistake" is minor/inconsequential, or where you technically admit fault but frame it in a way that shifts blame elsewhere.

#### LP 12 — Dive Deep

> "Leaders operate at all levels, stay connected to the details, audit frequently, and are skeptical when metrics and anecdote differ. No task is beneath them."

**What interviewers listen for:**
- Do you personally investigate root causes rather than accepting a surface-level explanation?
- Have you caught a discrepancy between what metrics/dashboards said and what was actually happening?
- Are you comfortable getting into low-level details (logs, code, data) rather than staying at a management-summary level?

**Typical question:** "Tell me about a time you had to dig into details to solve a problem others had missed."

**Sample STAR answer:**
- **Situation:** Our team's dashboard showed a service's error rate as consistently low (well within SLA), but a handful of customer support tickets kept describing symptoms consistent with the service failing for them specifically.
- **Task:** I decided to dig in personally rather than trust the aggregate metric, which the rest of the team had been treating as sufficient evidence nothing was wrong.
- **Action:** I pulled raw request logs (not the pre-aggregated dashboard) filtered to the specific customer segment mentioned in the tickets, and found that our error-rate metric was being computed as a percentage of ALL traffic, which masked a near-100% failure rate for one specific, low-traffic-share customer configuration that the aggregate math diluted into invisibility.
- **Result:** We fixed the specific configuration-handling bug within a day of finding the actual root cause, and I proposed the dashboard also break out error rate by customer segment going forward, which caught two more similarly-masked issues over the following quarter.

**Common mistakes:** describing "diving deep" as simply spending a long time on something, rather than showing you found something specific that a surface-level look would have missed.

#### LP 13 — Have Backbone; Disagree and Commit

> "Leaders are obligated to respectfully challenge decisions when they disagree, even when doing so is uncomfortable or exhausting. Once a decision is determined, they commit wholly."

**What interviewers listen for:**
- Have you respectfully pushed back on a decision you disagreed with, even to someone more senior?
- Once overruled, did you genuinely commit to executing the decision well, rather than passively undermining it?

**Typical question:** "Tell me about a time you disagreed with a decision but had to commit to it anyway."

**Sample STAR answer:**
- **Situation:** My manager decided to prioritize a new feature launch over addressing a growing backlog of tech debt I believed was becoming a real risk to system stability.
- **Task:** I disagreed with the prioritization and believed I had a responsibility to make my concern clearly heard, not just quietly comply or quietly resent the decision.
- **Action:** I put together a short, data-backed write-up quantifying the tech debt's growing on-call burden and presented it directly to my manager, making my case clearly once. My manager heard the case but, weighing broader business priorities I didn't have full visibility into, decided to proceed with the feature launch first. I said so explicitly, then fully committed — I didn't slow-walk the feature work or bring up the disagreement again to the team.
- **Result:** We shipped the feature on time, and I proactively negotiated a specific, scheduled tech-debt sprint immediately afterward as a condition I raised once, upfront, which my manager agreed to — the tech debt got addressed on a defined timeline instead of indefinitely, and the team never had to deal with mixed signals about which priority actually mattered.

**Common mistakes:** describing a story where you either never voiced disagreement at all (no "backbone") or where you continued to visibly resist/undermine after being overruled (no genuine "commit").

#### LP 14 — Deliver Results

> "Leaders focus on the key inputs for their business and deliver them with the right quality and in a timely fashion. Despite setbacks, they rise to the occasion and never settle."

**What interviewers listen for:**
- Did you actually finish and ship, not just make progress or propose a plan?
- Did you overcome a real setback/obstacle along the way, or was it a smooth, unremarkable execution?
- Can you quantify the outcome?

**Typical question:** "Tell me about a time you delivered results despite significant obstacles."

**Sample STAR answer:**
- **Situation:** Three weeks before a committed launch date, we discovered our primary third-party payment integration partner had a critical, unannounced API change that broke our checkout flow in testing.
- **Task:** I was responsible for the checkout integration and had to find a way to still hit the launch date, or clearly justify why we couldn't.
- **Action:** I spent the first day fully understanding the scope of the breaking change, then proposed and built a compatibility-shim layer isolating our checkout code from the partner's API directly, buying us time to do the "real" integration update properly after launch instead of under emergency pressure. I coordinated daily with the partner's support team to get clarity on the timeline for their side.
- **Result:** We launched on the original committed date with the shim in place, with zero customer-visible impact, and completed the proper long-term integration update three weeks later during a planned maintenance window rather than as a post-launch fire drill.

**Common mistakes:** describing a story with no real obstacle/setback (Amazon specifically wants to see resilience through adversity, not just competent routine execution).

#### LP 15 — Strive to be Earth's Best Employer

> "Leaders work every day to create a safer, more productive, higher performing, more diverse, and more just work environment. They lead with empathy, have fun at work, and make it easy for others to have fun."

**What interviewers listen for:**
- Have you contributed to making your team's working environment genuinely better (not just more "fun" superficially)?
- Do you show empathy for teammates' workload/wellbeing, not just task completion?

**Typical question:** "Tell me about a time you helped improve your team's working environment or culture."

**Sample STAR answer:**
- **Situation:** Our team's on-call rotation was causing real burnout — several engineers were being paged multiple times overnight for the same handful of recurring, low-severity alerts that didn't actually need immediate human action.
- **Task:** As someone who'd voiced frustration about this too, I took the initiative to actually fix it rather than just complain about it in retros.
- **Action:** I audited three months of paging history, identified the noisiest recurring alerts, and either fixed the underlying issues, auto-remediated them with a script, or adjusted alert thresholds to page only when genuinely actionable — and I made the audit data visible to the whole team so people could see the concrete improvement, not just take my word for it.
- **Result:** Overnight pages dropped by roughly 70% within a month; two teammates specifically told me their on-call weeks became meaningfully less stressful, and the team adopted "audit paging noise quarterly" as a standing practice afterward.

**Common mistakes:** describing purely social/morale activities (team lunches, games) without a concrete, structural improvement to how people actually work.

#### LP 16 — Success and Scale Bring Broad Responsibility

> "We started in a garage, but we're not there anymore... We are big, and our influence is far reaching... We must be humble and thoughtful about the impact we have. We are committed to doing the right thing."

**What interviewers listen for:**
- Do you think beyond immediate team/business impact to broader consequences (society, other teams, long-term precedent)?
- Have you raised a concern about unintended consequences of a decision, even when it wasn't strictly your job to?

**Typical question:** "Tell me about a time you considered the broader impact of a decision beyond your immediate task."

**Sample STAR answer:**
- **Situation:** While building an automated account-flagging system intended to catch fraudulent activity, our initial model showed a concerning pattern of disproportionately flagging a specific legitimate user segment due to a correlated-but-not-causal feature in the training data.
- **Task:** The model technically hit our target fraud-catch-rate metric, and there was pressure to ship it as-is to meet a deadline, but I was concerned about the broader fairness impact on legitimate users.
- **Action:** I raised the disparity explicitly with the team and product owner, backed by a breakdown of false-positive rates by segment, and proposed a short delay to remove the problematic correlated feature and retrain, even though it meant missing the original ship date.
- **Result:** The retrained model maintained comparable fraud-catch performance while closing most of the disparity gap; we shipped a week later than planned, but avoided what could have been a significant, hard-to-reverse trust and fairness issue at scale once live for millions of users.

**Common mistakes:** describing a purely technical/performance improvement without connecting it to a genuine broader-impact or responsibility dimension (fairness, safety, precedent-setting, societal effect).

> **How to use this section:** don't try to memorize all 16 verbatim during interview week — instead, build the 6-10 story story-bank from [8.3](#83-preparing-your-story-bank) and, for each story, explicitly identify which 2-3 LPs above it best demonstrates. Most candidates can cover all 16 LPs with well-chosen 6-8 stories, since most real stories touch multiple principles at once.

### 9.9 The Bar Raiser round, deep dive

**What a Bar Raiser actually is:** a specially trained and certified Amazon interviewer, deliberately drawn from a team **outside** the one you're interviewing for, whose explicit mandate is to protect the company-wide hiring bar from being slowly eroded by hiring-team urgency ("we need someone NOW") or in-group bias. Bar Raisers go through a formal certification process (shadowing, co-interviewing, calibration training) before being authorized to hold the role.

**Why the role exists:** without a neutral party, a hiring team under pressure to fill a role can unconsciously lower its standards over successive candidates, or favor a candidate who's personable but weak on substance. The Bar Raiser has **no stake in filling the specific requisition** and is trained to evaluate purely against Amazon's company-wide bar, not the hiring team's immediate need.

**Structural power in the process:**
- The Bar Raiser's vote is not just "one interviewer among several" — it is procedurally weighted so that a Bar Raiser's strong "No Hire" can block an offer even if every other interviewer (including the hiring manager) voted "Hire."
- Conversely, a Bar Raiser's strong "Hire" can sometimes help a borderline candidate get an offer if their concerns are outweighed by genuine strengths surfaced across the loop.
- The Bar Raiser typically **leads the post-loop debrief discussion**, walking through each interviewer's independent written feedback systematically.

**What this means practically for candidates:**
- You typically **cannot identify the Bar Raiser from your interview schedule** — treat every single round with full seriousness, especially the Leadership Principles component, since any interviewer might be the Bar Raiser (or might not be, but is still submitting detailed LP-mapped feedback either way).
- Bar Raiser rounds often skew slightly more heavily toward behavioral/LP depth than a typical coding round, sometimes asking you to go two or three "layers" deep on a single story ("you said you disagreed with your manager — what exactly did you say? What was their specific response? What would you do differently next time?") specifically to test whether your story is genuine and detailed versus rehearsed and shallow.
- The best preparation is the same as for any LP question: have real, detailed, specific stories (see [8.3](#83-preparing-your-story-bank)) that you can go several layers deep on without contradicting yourself or running out of concrete detail.

### 9.10 Amazon prep plan: week by week

A detailed 8-week plan assuming ~10-15 hours/week of prep time available (compress proportionally if you have less time, or extend if starting from a weaker DSA/system-design baseline):

**Week 1 — Foundations & OA prep**
- Days 1-2: Read this guide's Part 1 (hiring pipeline), Part 2 (OA deep dive) fully. Read Part 9.1-9.2 (Amazon process + OA breakdown).
- Days 3-5: Drill the 15 OA problems in [2.8](#28-previously-asked-oa-questions--company-tagged-bank) and 8 Amazon OA problems in [9.3](#93-previously-asked-amazon-oa-questions-with-solutions) under a timer (25 min/problem), reviewing the pattern explicitly after each attempt regardless of success.
- Days 6-7: Take a full mock OA (2 problems, 90 minutes, no notes) to simulate real conditions.

**Week 2 — DSA pattern review**
- Days 1-3: Work through [LEETCODE_MASTERY_COMPLETE_GUIDE.md](LEETCODE_MASTERY_COMPLETE_GUIDE.md) Part A categories 1-7 (Arrays/Hashing through Heap), focusing on recognizing patterns fast rather than memorizing exact solutions.
- Days 4-6: Continue Part A categories 8-14 (Backtracking through Bit Manipulation).
- Day 7: Redo 5 problems you struggled with earlier in the week from scratch, no hints.

**Week 3 — Company-tagged coding practice**
- Days 1-2: Drill [Part 5.2](#52-amazon-tagged-questions) (Amazon-tagged) and [9.6](#96-amazon-coding-interview-previously-asked-questions) (Amazon coding bank) problems.
- Days 3-4: Drill Part 5.3-5.6 (Google/Microsoft/Meta/Apple-Netflix-Uber-Bloomberg) for broader pattern exposure.
- Days 5-7: Do 3 timed mock phone-screen sessions (45-60 min, 1-2 problems, narrate out loud even alone or with a friend/mock-interview partner) using the framework in [3.2](#32-the-live-coding-communication-framework).

**Week 4 — System design foundations**
- Days 1-2: Read [Part 6.1-6.2](#61-hld-vs-lld--the-difference-interviewers-care-about) (HLD framework) and [Part 7.1](#71-the-universal-lld-framework-step-by-step) (LLD framework) fully, memorize the 8-step HLD checklist.
- Days 3-5: Work through the 6 HLD case studies in this guide ([6.3](#63-case-study-design-amazon-locker--package-pickup-system)-[6.8](#68-case-study-design-a-notificationalerting-system)), then attempt to redesign each from memory using only the framework (no peeking) before checking your version against the guide's.
- Days 6-7: Work through the 3 LLD case studies ([7.2](#72-case-study-lld-for-an-amazon-style-shopping-cart)-[7.4](#74-case-study-lld-for-an-in-memory-key-value-store)) with actual Java code written by hand.

**Week 5 — System design breadth + Amazon-specific angle**
- Days 1-3: Work through additional HLD case studies from [SYSTEM_DESIGN_INTERVIEW_MASTERY_GUIDE.md](SYSTEM_DESIGN_INTERVIEW_MASTERY_GUIDE.md) for broader pattern exposure (aim for 5-8 more systems).
- Days 4-5: Read [9.7](#97-amazon-system-design-round-whats-different) closely and re-do 2 case studies explicitly incorporating the Amazon-specific emphases (cost-consciousness, dive-deep follow-ups, explicit trade-off recommendations).
- Days 6-7: Do 2 timed mock system design sessions (45 min each) on prompts you haven't seen before, using the 8-step checklist without referring to notes partway through.

**Week 6 — Leadership Principles & behavioral prep**
- Days 1-2: Read all 16 LPs in [9.8](#98-all-16-amazon-leadership-principles-explained-with-sample-star-answers) closely. Build your initial story-bank list (6-10 candidate stories from your own experience).
- Days 3-4: Map each of your stories to 2-3 LPs each, and write out full STAR bullet points for each (as in the samples above).
- Days 5-6: Practice delivering 4-5 of your strongest stories out loud, timed to 2 minutes each, ideally to a friend/mock partner who can ask realistic Bar-Raiser-style follow-up "go one layer deeper" questions.
- Day 7: Do a full mock behavioral round (5-6 questions back to back, no notes) simulating loop conditions.

**Week 7 — Full mock loop simulation**
- Days 1-2: Full mock coding round (2 problems, 60 min, narrated).
- Day 3: Full mock system design round (45 min, unfamiliar prompt).
- Day 4: Full mock behavioral/Bar-Raiser-style round (5-6 questions with deep follow-ups).
- Days 5-7: Review weak areas identified across the mocks; re-drill specific problem patterns or LP stories that felt shaky.

**Week 8 — Final polish & logistics**
- Days 1-3: Light review only — re-read [Part 11](#part-11--master-cheat-sheets) cheat sheets, skim your story-bank bullet points, re-skim the LP list.
- Days 4-5: Prepare interview-day logistics (test video/audio setup, prepare your environment, prepare 3-4 thoughtful questions to ask interviewers per [11.4](#114-behavioral-cheat-sheet)).
- Days 6-7: Rest. Avoid cramming new material in the final 48 hours — consolidation and calm confidence matter more than one more problem solved at this point.

### 9.11 Amazon FAQ, common mistakes & insider tips

**FAQ:**

1. **Q: Do I need a different coding answer for every round, or can I reuse the same LP story across multiple interviewers?**
   A: You can reuse a story across rounds — different interviewers don't compare notes on your specific answers beforehand. Just avoid giving the *exact same* story to the *same* interviewer twice if they ask a similar-sounding question later in the same round.

2. **Q: How many Leadership Principles get asked per round?**
   A: Typically 1-2 explicit "tell me about a time" LP questions per round, woven in alongside the coding/design content, plus implicit LP evaluation of how you communicate and justify decisions throughout the technical portion.

3. **Q: Is the Bar Raiser always the "toughest" interviewer?**
   A: Not necessarily tougher, but often more probing/detailed on behavioral follow-ups specifically. Treat every round as equally important since you can't reliably identify which one is the Bar Raiser.

4. **Q: What happens if I get a "No Hire" from one interviewer but "Hire" from everyone else?**
   A: It depends on which interviewer and how strong the dissent is. A single non-Bar-Raiser "No Hire" is sometimes outweighed by strong positive signal elsewhere; a Bar Raiser "No Hire" is much harder to overcome. There's no fixed universal rule — it goes through genuine discussion in the debrief.

5. **Q: Should I mention Leadership Principles by name during my answers (e.g., say "this shows Ownership")?**
   A: Generally no — let the story speak for itself. Naming the LP explicitly can come across as reciting a script rather than genuinely reflecting on your experience. It's fine to have identified the LP in your own prep, just don't narrate it during the answer.

6. **Q: Can I ask for a moment to think before answering a behavioral question?**
   A: Yes, absolutely — a brief "let me think of a good example for that" pause reads as thoughtful, not unprepared. Rushing into a weak, half-relevant story is worse than a 10-second pause.

7. **Q: What level of system design depth is expected for a new-grad/SDE-1 candidate?**
   A: Often lighter or absent entirely for pure new-grad pipelines; when present, expect a smaller-scope prompt (e.g., "design a URL shortener" rather than "design Prime Video") with less emphasis on massive-scale trade-offs and more on demonstrating you understand the framework at all.

8. **Q: How important is coding style/cleanliness versus just getting a working solution?**
   A: Working + reasonably clean beats broken + beautiful, but broken + messy is worse than either. If you're running low on time, prioritize correctness on the given examples over polishing variable names.

9. **Q: Is it okay to use a language other than Java for Amazon interviews?**
   A: Yes — Amazon interviews are language-agnostic; use whatever language you're most fluent and fast in. (This guide uses Java to match the other guides in this repo, not because Java is required.)

10. **Q: How long after the onsite loop until I hear back?**
    A: Commonly 3-10 business days depending on debrief scheduling and role urgency; a polite check-in with your recruiter after a week of silence is appropriate and expected, not pushy.

11. **Q: If I don't get an offer, how long before I can reapply?**
    A: Amazon commonly has a defined reapplication waiting period (historically around 6-12 months for the same or similar role, though this varies by team/time and is best confirmed with your recruiter) — use the time to concretely address the specific feedback themes you were given, if any were shared.

12. **Q: Do I need to prepare separate stories for "Amazon-specific" LPs versus general behavioral prep?**
    A: Mostly no — the story-bank approach in [8.3](#83-preparing-your-story-bank) works for both; the difference is mapping your existing stories explicitly to Amazon's specific 16 LPs rather than generic themes, and being ready for deeper, more specific follow-up questions than a typical company's behavioral round.

**Common mistakes candidates make:**

- Treating the OA as "just a coding test" and skipping meaningful prep for the Work Style Assessment, then being caught off guard by how much it asks about workplace scenarios.
- Preparing generic behavioral answers without explicitly mapping them to Amazon's specific LP language, then fumbling when an interviewer asks a very LP-specific-phrased follow-up.
- Going into a system design round without doing the back-of-envelope estimation step, missing an easy opportunity to demonstrate structured thinking early.
- Capitulating instantly when a Bar-Raiser-style interviewer pushes back on a technical opinion (failing "Have Backbone"), or conversely refusing to update your view even when shown a good counter-argument (also failing "Are Right, A Lot" and "Have Backbone... Disagree and Commit" — the correct response is genuine engagement with the pushback, not either extreme).
- Under-preparing for the Bar Raiser round specifically because candidates assume (incorrectly) that it will be "just like the other rounds" — the depth of behavioral follow-up questions is often noticeably higher.
- Rehearsing STAR stories so rigidly that they sound scripted and fall apart under a natural follow-up question that deviates slightly from the expected flow.

**Insider tips:**

- Amazon's internal culture puts unusually high weight on **written communication** (the famous "6-page narrative memo instead of PowerPoint" culture) — this indirectly shows up in interviews as a preference for candidates who can structure a clear, well-organized verbal explanation, mirroring good written structure (context, options considered, recommendation, reasoning).
- Because every round scores LPs independently, a strong technical answer paired with a weak/rushed LP answer in the same round can still result in a lower overall round score than expected — budget real time for the LP portion, don't treat it as an afterthought squeezed into the last 2 minutes.
- If you don't have a perfect story for a specific LP question, it's better to give an honest, smaller-scale real example than to stretch an unrelated story to fit — interviewers are experienced at detecting a story that's been awkwardly force-fit to a question it doesn't really answer.

## Part 10 — Company-Specific Playbooks

Each company below gets the same treatment as Amazon in Part 9, condensed: hiring process, OA specifics, interview round breakdown, company-specific previously-asked questions with full solutions, culture/behavioral evaluation focus, and prep tips.

### 10.1 Quick reference comparison table

| Company | OA present? | # onsite rounds | System design at what level? | Behavioral style | Distinctive trait |
|---|---|---|---|---|---|
| Amazon | Yes (OA1+OA2) | 4-5 + Bar Raiser | SDE-2+/L5+ | 16 Leadership Principles, every round | Bar Raiser cross-team veto power |
| Google | Rare for experienced | 4-5 | Senior+ | "Googleyness & Leadership" | Structured rubric-based hiring committee |
| Microsoft | Sometimes | 4-5 | Senior+ | "As Appropriate" (AA) round | Growth-mindset culture emphasis |
| Meta | Rare | 4-6 | E4+ | Core Values scored round | Explicit "impact" framing throughout |
| Apple | Occasional | 4-6 | Senior+ | Team-specific, less standardized | Strong secrecy/confidentiality culture |
| Netflix | Rare | 4-5 | Senior+ | "Freedom & Responsibility" culture deck | Very high individual autonomy expectation |
| Uber | Yes (CodeSignal) | 4-5 | 2+ YOE | Uber-specific values | Fast-paced, ownership-heavy culture |
| Adobe | Yes (India-heavy) | 4-5 | Senior+ | Standard behavioral | Strong creative-tools domain knowledge valued |
| Goldman Sachs/Bloomberg | Yes | 4-6 | Senior+ | Analytical/quant-flavored | Finance-domain fluency is a real plus |
| Flipkart/Indian product cos | Yes | 3-5 | 2+ YOE | Standard behavioral | Fast-growing, scale-at-India-context problems |

### 10.2 Google

**Hiring process:** application/referral → recruiter screen → 1-2 technical phone screens (sometimes called "hiring committee interviews" happen later) → onsite loop (4-5 rounds, historically in-person, now often virtual) → **Hiring Committee (HC)** review (a group of engineers NOT on your interviewing panel reviews all feedback and makes the decision, similar in spirit to Amazon's Bar Raiser but implemented as a committee rather than a single embedded role) → team matching (Google famously hires many new grads/some experienced hires into a generic pool, then matches to a team afterward) → offer.

**OA specifics:** largely phased out for most experienced-hire pipelines in favor of going straight to phone screens; some new-grad/intern pipelines still use a short online coding assessment.

**Interview round breakdown:** 2 coding-focused rounds (heavy on algorithmic depth and clean code), 1 system design round (senior+), 1 "Googleyness & Leadership" behavioral round, sometimes 1 additional coding round for a 5-round loop. Google is known for being **less explicitly frameworked** than Amazon's LP system but still evaluates comparable underlying traits (collaboration, general cognitive ability, leadership, role-related knowledge) via its own internal rubric given to interviewers.

**Google-specific previously-asked question — "Word Search II" (find all dictionary words present in a grid):**

**Approach:** Build a Trie from the word list, then DFS from every grid cell, pruning branches that don't correspond to any Trie prefix — far more efficient than searching for each word independently.

```java
List<String> findWords(char[][] board, String[] words) {
    TrieNode root = buildTrie(words);
    List<String> result = new ArrayList<>();
    for (int i = 0; i < board.length; i++)
        for (int j = 0; j < board[0].length; j++)
            dfs(board, i, j, root, result);
    return result;
}
class TrieNode {
    TrieNode[] children = new TrieNode[26];
    String word = null;
}
private TrieNode buildTrie(String[] words) {
    TrieNode root = new TrieNode();
    for (String w : words) {
        TrieNode node = root;
        for (char c : w.toCharArray()) {
            int idx = c - 'a';
            if (node.children[idx] == null) node.children[idx] = new TrieNode();
            node = node.children[idx];
        }
        node.word = w;
    }
    return root;
}
private void dfs(char[][] board, int i, int j, TrieNode node, List<String> result) {
    if (i < 0 || j < 0 || i >= board.length || j >= board[0].length || board[i][j] == '#') return;
    char c = board[i][j];
    TrieNode next = node.children[c - 'a'];
    if (next == null) return;
    if (next.word != null) { result.add(next.word); next.word = null; } // avoid duplicates
    board[i][j] = '#';
    dfs(board, i + 1, j, next, result); dfs(board, i - 1, j, next, result);
    dfs(board, i, j + 1, next, result); dfs(board, i, j - 1, next, result);
    board[i][j] = c;
}
```
**Complexity:** O(rows × cols × 4^L) worst case, much better in practice due to Trie pruning. **Why Google likes it:** combines two non-trivial techniques (Trie construction, backtracking with pruning) and tests whether you recognize when a naive per-word search (O(words × rows × cols × 4^L)) should be restructured around a shared prefix structure instead.

**Culture/behavioral focus:** "Googleyness" evaluates comfort with ambiguity, intellectual humility (changing your mind with new evidence), and collaborative problem-solving — conceptually overlapping with Amazon's "Are Right, A Lot" and "Learn and Be Curious" but without an explicit named-principle framework; prepare stories emphasizing genuine curiosity and comfort operating without a fully-specified problem.

**Prep tips:** Google interviews weight **algorithmic elegance and complexity rigor** particularly heavily — being able to derive and justify an optimal complexity bound (not just get a working solution) matters more here than at most other companies; practice explaining WHY a solution is optimal, not just presenting it.

### 10.3 Microsoft

**Hiring process:** application/referral → recruiter screen → OA (role-dependent) → 1 technical phone screen → onsite loop (4-5 rounds) including a distinctive **"As Appropriate" (AA) round** → hiring decision → offer. Microsoft's process has become increasingly similar to Amazon/Google's structure in recent years but retains its own cultural flavor.

**OA specifics:** present for many new-grad and campus pipelines, typically 1 coding problem via a Microsoft-branded portal.

**Interview round breakdown:** 2-3 coding rounds, 1 system design round (senior+ roles), and the **AA round** — conducted by a senior engineer/manager from outside the immediate hiring team (conceptually similar in independence to Amazon's Bar Raiser, though generally described as less procedurally weighted/formalized than Amazon's version), focused on culture fit, growth mindset, and technical depth validation.

**Microsoft-specific previously-asked question — "Sliding Window Maximum":**

**Problem:** Given an array and window size `k`, return the maximum in each sliding window as it moves left to right.

**Approach:** Monotonic decreasing deque of indices — front always holds the index of the current window's maximum; pop from the back while incoming elements are larger (they'll always be preferred over smaller earlier elements), pop from the front when it falls outside the window.

```java
int[] maxSlidingWindow(int[] nums, int k) {
    Deque<Integer> deque = new ArrayDeque<>(); // stores indices, decreasing values
    int[] result = new int[nums.length - k + 1];
    for (int i = 0; i < nums.length; i++) {
        while (!deque.isEmpty() && deque.peekFirst() <= i - k) deque.pollFirst();
        while (!deque.isEmpty() && nums[deque.peekLast()] < nums[i]) deque.pollLast();
        deque.offerLast(i);
        if (i >= k - 1) result[i - k + 1] = nums[deque.peekFirst()];
    }
    return result;
}
```
**Complexity:** O(n) — each index is added and removed from the deque at most once. **Why Microsoft likes it:** the monotonic deque technique is a genuinely non-obvious data-structure insight (most candidates' first instinct is an O(n·k) re-scan per window) — a strong signal question for testing whether a candidate can find a truly optimal amortized solution.

**Culture/behavioral focus:** Microsoft's culture under its "growth mindset" framing (publicly associated with CEO Satya Nadella's leadership) evaluates learning agility, empathy, and collaborative "one Microsoft" cross-team thinking — prepare stories showing you sought out feedback and visibly grew from it, and stories showing cross-team collaboration rather than siloed individual work.

**Prep tips:** Microsoft's coding rounds are known for occasionally including **API-design-flavored questions** ("design a class for X" without it being a full LLD round) — practice being comfortable both writing algorithms AND designing small, clean class interfaces on the fly.

### 10.4 Meta

**Hiring process:** application/referral → recruiter screen → 1-2 technical phone screens → onsite loop (historically in-person "onsite," now often virtual, 4-6 rounds) → hiring committee-style review → offer. Meta is known for a notably fast-moving process end-to-end compared to some peers.

**OA specifics:** rare for most pipelines; some new-grad/university pipelines use Codility.

**Interview round breakdown:** 2 coding rounds (Meta's coding rounds are known for sometimes including 2 unrelated problems back-to-back rather than 1 problem with follow-ups, testing breadth under time pressure), 1 system design round (E4+ levels), and 1 **behavioral round explicitly scored against Meta's core values** (Move Fast, Be Bold, Focus on Long-Term Impact, Build Social Value, Be Direct and Respect Your Colleagues).

**Meta-specific previously-asked question — "Binary Tree Maximum Path Sum":**

**Problem:** Given a binary tree, find the maximum path sum where a path can start and end at any node (not necessarily passing through the root).

**Approach:** Post-order recursion computing, for each node, the maximum "downward" contribution it can offer to a parent (clipping negative contributions to zero), while separately tracking the best "through this node" path (left contribution + node value + right contribution) as a running global maximum.

```java
private int maxSum = Integer.MIN_VALUE;
int maxPathSum(TreeNode root) {
    maxGain(root);
    return maxSum;
}
private int maxGain(TreeNode node) {
    if (node == null) return 0;
    int leftGain = Math.max(maxGain(node.left), 0);
    int rightGain = Math.max(maxGain(node.right), 0);
    maxSum = Math.max(maxSum, node.val + leftGain + rightGain);
    return node.val + Math.max(leftGain, rightGain);
}
```
**Complexity:** O(n). **Why Meta likes it:** the key subtlety (a node can contribute to its parent's path using only ONE child's branch, but can form a "peak" using BOTH children for the global maximum check) is a classic test of precise recursive-invariant thinking under time pressure, and is one of Meta's most consistently-reported onsite questions.

**Culture/behavioral focus:** Meta's behavioral round explicitly probes for "impact" framing — quantified outcomes and a bias toward shipping and iterating rather than over-planning; prepare stories emphasizing concrete, measurable impact and comfort moving fast with imperfect information (directly analogous to Amazon's "Bias for Action").

**Prep tips:** practice solving 2 unrelated Medium-difficulty problems within a single 45-minute window (not just 1 problem with generous time) since Meta rounds are more likely than most to include two distinct questions.

### 10.5 Apple

**Hiring process:** application/referral → recruiter screen → 1-2 technical phone screens → onsite loop (4-6 rounds, varies significantly by team — Apple is famously decentralized, with each product team running its own process somewhat independently) → team-specific hiring decision → offer.

**OA specifics:** occasional, team-dependent; less standardized across Apple than at Amazon/Google.

**Interview round breakdown:** typically 2-3 coding rounds, 1 system design round for senior+ roles, and 1-2 rounds that are notably **team/domain-specific** (e.g., a graphics team might probe deep systems/performance knowledge, a services team might probe distributed systems) rather than a single company-wide standardized behavioral round.

**Apple-specific previously-asked question — "LFU/LRU-adjacent: Design a Data Structure for a Most Recently Used File List" (simplified: implement `touch(file)` and `getRecentFiles(k)`):**

**Approach:** Same doubly-linked-list + hashmap skeleton as LRU Cache ([C-1](#c-1-amazon-lru-cache)), exposing a `getRecentFiles(k)` that walks the list from the head.

```java
class RecentFilesTracker {
    class Node { String file; Node prev, next; Node(String f){file=f;} }
    private final Map<String, Node> map = new HashMap<>();
    private final Node head = new Node(null), tail = new Node(null);
    RecentFilesTracker() { head.next = tail; tail.prev = head; }
    public void touch(String file) {
        if (map.containsKey(file)) remove(map.get(file));
        Node n = new Node(file);
        map.put(file, n);
        addFront(n);
    }
    public List<String> getRecentFiles(int k) {
        List<String> result = new ArrayList<>();
        Node cur = head.next;
        while (cur != tail && result.size() < k) { result.add(cur.file); cur = cur.next; }
        return result;
    }
    private void remove(Node n) { n.prev.next = n.next; n.next.prev = n.prev; }
    private void addFront(Node n) { n.next = head.next; n.next.prev = n; head.next = n; n.prev = head; }
}
```
**Complexity:** O(1) touch, O(k) to retrieve recent files. **Why Apple likes it:** models a genuinely common Apple product surface (Recents in Finder/Spotlight-adjacent features) and tests the same LRU-family skeleton in a slightly different-shaped API, checking whether you can adapt a memorized pattern to a new interface rather than only reciting it verbatim.

**Culture/behavioral focus:** Apple strongly emphasizes **product craftsmanship and attention to detail** — behavioral answers that show meticulous care about user-facing polish (even in backend work, e.g., "I made sure error messages were genuinely helpful to end users, not just technically accurate") land well. Apple's famous internal secrecy culture also means interviewers may probe your judgment around confidentiality and discretion.

**Prep tips:** because Apple's process is team-dependent, research the specific team/product area as much as possible beforehand (much more so than for Amazon/Google's more standardized processes) — the "system design" round content can vary widely from web-scale distributed systems to embedded/on-device performance topics depending on the team.

### 10.6 Netflix

**Hiring process:** application/referral (Netflix hires relatively fewer, more senior-skewed roles compared to some peers) → recruiter screen → technical phone screen(s) → onsite loop (4-5 rounds) → offer. Netflix is known for **no fixed levels/formal promotion ladder** in the way most large companies have, and a correspondingly senior, autonomy-heavy hiring bar even for mid-level-sounding roles.

**OA specifics:** rare; Netflix's hiring volume and process are more akin to senior/experienced hiring at any given time than high-volume new-grad pipelines.

**Interview round breakdown:** coding rounds, 1 system design round (near-universal given Netflix's senior-skewed hiring), and a strong emphasis on a **"Freedom & Responsibility"** culture-fit conversation, reflecting Netflix's famous internal culture deck emphasizing high individual autonomy paired with high accountability.

**Netflix-specific previously-asked question — "Design a Rate-Limited API Client with Exponential Backoff":**

**Problem:** Implement a client wrapper that calls a downstream API, respecting a rate limit and retrying failed calls with exponential backoff plus jitter.

**Approach:** Token-bucket rate limiting on the client side plus a retry loop with `backoff = min(maxBackoff, base * 2^attempt) + random jitter`.

```java
class RateLimitedClient {
    private final int maxRequestsPerSecond;
    private final Semaphore semaphore;
    private final ScheduledExecutorService scheduler = Executors.newScheduledThreadPool(1);

    RateLimitedClient(int maxRequestsPerSecond) {
        this.maxRequestsPerSecond = maxRequestsPerSecond;
        this.semaphore = new Semaphore(maxRequestsPerSecond);
        scheduler.scheduleAtFixedRate(() ->
            semaphore.release(maxRequestsPerSecond - semaphore.availablePermits()), 1, 1, TimeUnit.SECONDS);
    }

    public <T> T callWithRetry(Callable<T> apiCall, int maxRetries) throws Exception {
        int attempt = 0;
        while (true) {
            semaphore.acquire();
            try {
                return apiCall.call();
            } catch (Exception e) {
                attempt++;
                if (attempt > maxRetries) throw e;
                long baseDelay = 100L * (1L << attempt); // exponential
                long jitter = ThreadLocalRandom.current().nextLong(baseDelay / 2);
                Thread.sleep(Math.min(5000, baseDelay + jitter));
            }
        }
    }
}
```
**Complexity:** O(1) amortized per call, bounded by `maxRetries`. **Why Netflix likes it:** directly models the resilience patterns Netflix pioneered publicly (Hystrix-style circuit breaking, backoff-with-jitter) for surviving partial failures in a large microservices mesh — a very on-brand practical systems question.

**Culture/behavioral focus:** Netflix explicitly evaluates for high autonomy and comfort with direct, candid feedback ("only say about someone what you'd say to their face" is a stated cultural value) — prepare stories showing you made significant independent decisions without heavy oversight, and stories showing you gave or received blunt, constructive feedback professionally.

**Prep tips:** Netflix's system design rounds tend to assume strong familiarity with resilience/fault-tolerance patterns (circuit breakers, bulkheads, graceful degradation) given the company's public engineering culture around chaos engineering — reviewing [SYSTEM_DESIGN_INTERVIEW_MASTERY_GUIDE.md](SYSTEM_DESIGN_INTERVIEW_MASTERY_GUIDE.md) §16 Security and general resilience patterns pays off disproportionately here.

### 10.7 Uber

**Hiring process:** application/referral → recruiter screen → OA (CodeSignal) → technical phone screen → onsite loop (4-5 rounds) → offer. Uber's process is broadly similar in shape to Amazon's but without a formalized cross-team veto role.

**OA specifics:** CodeSignal-based, typically 2 coding problems within 60-90 minutes.

**Interview round breakdown:** 2 coding rounds, 1 system design round (2+ YOE roles, frequently drawing on Uber's own domain — matching, ETA prediction, surge pricing, geo-indexing), 1 behavioral round evaluating Uber's stated values (Build With Heart, Be an Owner, etc., varies as Uber has revised its values over time — check current published values before interviewing).

**Uber-specific previously-asked question — "Number of Distinct Islands" (grid regions with the same SHAPE count as one):**

**Problem:** Given a grid, count distinct island *shapes* (two islands with the same shape, regardless of position, count once).

**Approach:** DFS each island recording the sequence of relative moves (e.g., "down, right, back, back, up") as a canonical shape signature; use a `Set<String>` of signatures to dedupe.

```java
int numDistinctIslands(int[][] grid) {
    Set<String> shapes = new HashSet<>();
    for (int i = 0; i < grid.length; i++)
        for (int j = 0; j < grid[0].length; j++)
            if (grid[i][j] == 1) {
                StringBuilder path = new StringBuilder();
                dfs(grid, i, j, "O", path); // 'O' = origin marker
                shapes.add(path.toString());
            }
    return shapes.size();
}
private void dfs(int[][] grid, int i, int j, String direction, StringBuilder path) {
    if (i < 0 || j < 0 || i >= grid.length || j >= grid[0].length || grid[i][j] != 1) return;
    grid[i][j] = 0;
    path.append(direction);
    dfs(grid, i + 1, j, "D", path);
    dfs(grid, i - 1, j, "U", path);
    dfs(grid, i, j + 1, "R", path);
    dfs(grid, i, j - 1, "L", path);
    path.append("B"); // backtrack marker, disambiguates different shapes with same move multiset
}
```
**Complexity:** O(rows × cols). **Why Uber likes it:** geospatial region/shape-matching questions echo Uber's real work in geofencing and service-area/zone definitions; the "backtrack marker" trick to avoid two genuinely-different shapes hashing to the same signature is a subtle correctness detail interviewers specifically probe.

**Culture/behavioral focus:** Uber evaluates for fast-paced ownership and comfort operating in a less-structured, rapidly-evolving environment (reflecting Uber's operational, marketplace-driven business) — prepare stories emphasizing independent ownership of ambiguous, fast-moving problems.

**Prep tips:** Uber system design rounds frequently reuse the guide's [Ride Sharing](#) style prompts (see [SYSTEM_DESIGN_INTERVIEW_MASTERY_GUIDE.md](SYSTEM_DESIGN_INTERVIEW_MASTERY_GUIDE.md) §30) — practice the matching-engine and geo-indexing deep dives specifically, since they're the most Uber-relevant sub-problems interviewers gravitate toward.

### 10.8 Adobe

**Hiring process:** application/referral (heavy campus/off-campus hiring presence in India in particular) → OA → technical phone screen(s) → onsite loop (4-5 rounds, sometimes compressed into a single "superday") → offer.

**OA specifics:** common and substantial — typically 2 coding problems plus a set of CS-fundamentals MCQs (OS, DBMS, OOP concepts), especially in India-based hiring drives.

**Interview round breakdown:** 2-3 coding rounds, 1 system design round (senior+/2+ YOE), 1 behavioral/HR round. Adobe interviewers sometimes weave in **domain-specific questions relevant to creative-tools/content platforms** (e.g., questions touching on file format parsing, rendering pipelines, or content-processing pipelines) for roles on relevant teams.

**Adobe-specific previously-asked question — "Flatten a Multilevel Doubly Linked List":**

**Problem:** Given a doubly linked list where nodes may have a `child` pointer to a separate doubly linked list, flatten it into a single-level list.

**Approach:** DFS/iterative stack-based traversal — when a node with a child is found, recursively flatten the child list and splice it in between the current node and its original `next`.

```java
Node flatten(Node head) {
    Node cur = head;
    while (cur != null) {
        if (cur.child != null) {
            Node next = cur.next;
            Node childHead = flatten(cur.child);
            cur.next = childHead;
            childHead.prev = cur;
            cur.child = null;
            Node tail = childHead;
            while (tail.next != null) tail = tail.next;
            tail.next = next;
            if (next != null) next.prev = tail;
        }
        cur = cur.next;
    }
    return head;
}
```
**Complexity:** O(n) total across all nodes. **Why Adobe likes it:** models nested/hierarchical document structures (a plausible analog to nested layers/groups in a creative document format) and tests careful pointer bookkeeping across a recursive splice operation.

**Culture/behavioral focus:** Adobe evaluates creativity-adjacent problem solving and cross-functional collaboration (Adobe's products span deeply technical and deeply creative-user-facing concerns) — prepare stories showing you balanced technical constraints against a genuinely user/creative-facing requirement.

**Prep tips:** don't neglect the CS-fundamentals MCQ portion of Adobe's OA — brief, direct review of OOP principles, process/thread differences, and basic SQL joins/normalization pays off disproportionately since these are quick, low-effort points to secure.

### 10.9 Goldman Sachs & Bloomberg (finance-tech)

**Hiring process:** application/referral → OA → technical phone screen(s) → onsite/superday loop (4-6 rounds, sometimes including a dedicated "culture fit"/HR round distinct from a manager round) → offer. Both are large financial firms with substantial internal engineering organizations building trading, risk, and data infrastructure systems, and both run recognizably FAANG-style technical loops for SWE roles alongside their more finance-specific analyst tracks.

**OA specifics:** HackerRank-based, typically 2-3 coding problems, sometimes including a SQL section and/or basic quantitative aptitude questions for certain roles.

**Interview round breakdown:** 2-3 coding rounds, 1 system design round (senior+/2+ YOE, often flavored around low-latency/high-throughput data systems given the trading-systems domain), and behavioral rounds that lean **analytical and precision-focused** — interviewers often probe deeply into WHY you made a specific technical choice, mirroring the rigor expected in finance-domain decision-making.

**Goldman Sachs/Bloomberg-specific previously-asked question — "Stock Price Fluctuation" (design a class supporting price updates at arbitrary past timestamps and querying current/max/min price):**

**Approach:** A `TreeMap<Integer, Integer>` (timestamp → price) gives sorted-order access; track the latest timestamp separately; maintain price frequency counts in a `TreeMap<Integer, Integer>` (price → count) to get max/min in O(log n), handling out-of-order corrections by decrementing the old price's count before inserting the new one.

```java
class StockPrice {
    private final TreeMap<Integer, Integer> timestampToPrice = new TreeMap<>();
    private final TreeMap<Integer, Integer> priceFrequency = new TreeMap<>();
    private int latestTimestamp = 0;

    public void update(int timestamp, int price) {
        if (timestampToPrice.containsKey(timestamp)) {
            int oldPrice = timestampToPrice.get(timestamp);
            priceFrequency.merge(oldPrice, -1, Integer::sum);
            if (priceFrequency.get(oldPrice) == 0) priceFrequency.remove(oldPrice);
        }
        timestampToPrice.put(timestamp, price);
        priceFrequency.merge(price, 1, Integer::sum);
        latestTimestamp = Math.max(latestTimestamp, timestamp);
    }
    public int current() { return timestampToPrice.get(latestTimestamp); }
    public int maximum() { return priceFrequency.lastKey(); }
    public int minimum() { return priceFrequency.firstKey(); }
}
```
**Complexity:** O(log n) per operation. **Why finance-tech firms like it:** directly models real market-data correction handling (late/out-of-order tick updates are a genuine operational reality in trading systems) — testing whether you handle the "correction" case (an update to an already-seen timestamp) correctly is the key signal, since naive implementations often forget to decrement the old price's frequency count.

**Culture/behavioral focus:** expect a stronger emphasis on **precision, risk-awareness, and being able to justify a decision rigorously** than at consumer-tech companies — behavioral answers that show careful risk/impact analysis before acting (rather than pure "move fast") tend to land particularly well here.

**Prep tips:** basic familiarity with financial domain concepts (order books, market data, settlement) is a genuine (though not required) plus if you have it — mentioning it naturally where relevant to a system design answer signals domain fluency without needing to overstate your finance background if you don't have one.

### 10.10 Flipkart & Indian product companies

**Hiring process:** application/campus drive/referral → OA → technical phone screen or a compressed "superday" onsite → offer. Indian product companies (Flipkart, and similarly-structured companies) frequently run **compressed multi-round superdays** (all rounds in a single day, including HR) rather than spreading the loop across weeks, especially for campus hiring.

**OA specifics:** HackerRank/HackerEarth-based, typically 2 coding problems plus CS-fundamentals MCQs, very similar in shape to Adobe's OA described above.

**Interview round breakdown:** 2-3 coding rounds, 1 system design round (2+ YOE roles, frequently framed around India-scale e-commerce/logistics problems — inventory across many regional warehouses, COD (cash-on-delivery) reconciliation, festival-sale traffic spikes analogous to Amazon's Prime Day), 1 HR/behavioral round.

**Flipkart-specific previously-asked question — "Design a Discount/Coupon Application Engine" (given a cart and a set of applicable coupon rules with priority/stacking rules, compute the final price):**

**Approach:** Model each coupon as a `Rule` object implementing a common interface (`applies(cart)`, `apply(currentPrice)`), sort applicable rules by priority, and apply sequentially — a direct real-world application of the Strategy/Chain-of-Responsibility pattern combination from [Part 7.1](#71-the-universal-lld-framework-step-by-step).

```java
interface CouponRule {
    boolean isApplicable(Cart cart);
    double apply(double currentPrice, Cart cart);
    int priority(); // lower runs first
}
class FlatDiscountCoupon implements CouponRule {
    private final double flatAmount; private final double minCartValue; private final int priority;
    FlatDiscountCoupon(double flatAmount, double minCartValue, int priority) {
        this.flatAmount = flatAmount; this.minCartValue = minCartValue; this.priority = priority;
    }
    public boolean isApplicable(Cart cart) { return cart.getTotal() >= minCartValue; }
    public double apply(double currentPrice, Cart cart) { return Math.max(0, currentPrice - flatAmount); }
    public int priority() { return priority; }
}
class DiscountEngine {
    public double computeFinalPrice(Cart cart, List<CouponRule> rules) {
        List<CouponRule> applicable = new ArrayList<>();
        for (CouponRule r : rules) if (r.isApplicable(cart)) applicable.add(r);
        applicable.sort(Comparator.comparingInt(CouponRule::priority));
        double price = cart.getTotal();
        for (CouponRule r : applicable) price = r.apply(price, cart);
        return price;
    }
}
```
**Complexity:** O(n log n) for sorting rules, O(n) to apply. **Why Indian product companies like it:** e-commerce coupon-stacking logic is an extremely common real feature at these companies, and the question directly tests whether you reach for an extensible Strategy-pattern design rather than a hardcoded chain of `if` statements per coupon type — exactly the LLD signal from [Part 7.1](#71-the-universal-lld-framework-step-by-step).

**Culture/behavioral focus:** fast growth and scrappy resourcefulness are commonly emphasized (conceptually close to Amazon's "Frugality" and "Bias for Action") — prepare stories showing you delivered meaningful results with limited time/resources in a fast-moving environment.

**Prep tips:** system design prompts at these companies frequently ask you to explicitly reason about **India-specific scale/infrastructure realities** (patchy network connectivity in tier-2/3 cities, COD payment reconciliation, festival-sale traffic spikes far exceeding steady-state) — practicing the back-of-envelope estimation step with these specific constraints in mind (rather than assuming uniform US/EU-style infrastructure) is genuinely useful prep.

## Part 11 — A-Z Glossary of Interview & Technical Terms

A quick-reference glossary of terms used throughout this guide (and commonly heard in interviews) — useful for a fast pre-interview refresh.

**A**
- **ACID** — Atomicity, Consistency, Isolation, Durability: the transaction guarantees classic relational databases provide. Contrast with BASE.
- **Amortized complexity** — the average cost per operation across a sequence of operations, even if occasional individual operations are expensive (e.g., dynamic array resizing).
- **API Gateway** — a single entry point that routes, authenticates, and rate-limits requests to backend services, common in microservice architectures.
- **At-least-once / at-most-once / exactly-once delivery** — message-queue delivery guarantees; exactly-once is the hardest to achieve and often approximated via idempotency instead.
- **Autoscaling** — automatically adjusting the number of running instances based on load metrics (CPU, queue depth, request rate).

**B**
- **Backoff (exponential)** — progressively increasing the delay between retries after repeated failures, to avoid overwhelming a struggling downstream system.
- **BASE** — Basically Available, Soft state, Eventual consistency: the consistency model many NoSQL systems favor over strict ACID.
- **Bar Raiser** — Amazon's cross-team certified interviewer role with outsized influence on the final hiring decision (see [9.9](#99-the-bar-raiser-round-deep-dive)).
- **Big-O notation** — describes an algorithm's worst-case (or average-case) growth rate as input size increases.
- **Bloom filter** — a space-efficient probabilistic set structure with no false negatives but a tunable false-positive rate.
- **Bar raiser bias mitigation** — the broader industry pattern (not just Amazon's specific name) of including a neutral, cross-team interviewer to protect a company-wide hiring bar.

**C**
- **CAP theorem** — a distributed system can only guarantee two of Consistency, Availability, and Partition tolerance simultaneously during a network partition.
- **Circuit breaker** — a resilience pattern that stops calling a failing downstream dependency temporarily, failing fast instead of piling up timeouts (see [F-10](#f-10-cloudflare-circuit-breaker-state-machine)).
- **CDN (Content Delivery Network)** — a globally distributed network of edge caches serving content close to end users.
- **Consistent hashing** — a hashing scheme minimizing key remapping when nodes are added/removed (see [F-11](#f-11-akamai-consistent-hashing-ring)).
- **CRUD** — Create, Read, Update, Delete: the four basic data operations.

**D**
- **DAG (Directed Acyclic Graph)** — a directed graph with no cycles; underlies task scheduling, build systems, and dependency resolution.
- **Dead Letter Queue (DLQ)** — a holding queue for messages that repeatedly fail processing, for later manual inspection (see [F-12](#f-12-twilio-retry-queue-with-dead-letter-queue)).
- **Debrief** — the post-interview-loop meeting where interviewers discuss feedback and reach a hiring decision.
- **Disagree and Commit** — Amazon Leadership Principle: voice disagreement respectfully, then fully commit once a decision is made (see [LP 13](#lp-13--have-backbone-disagree-and-commit)).
- **Distributed lock** — a lock coordinating exclusive access to a resource across multiple machines/processes (see [F-1](#f-1-nutanix-distributed-lock-via-lease--compare-and-swap)).

**E**
- **Eventual consistency** — a consistency model where replicas converge to the same value given enough time without new writes, but may temporarily disagree.
- **Exponential backoff with jitter** — adding randomness to a backoff delay to avoid many clients retrying in lockstep (thundering herd).

**F**
- **Fan-out** — distributing one input event to many downstream consumers/recipients.
- **Frugality** — Amazon Leadership Principle emphasizing accomplishing more with fewer resources (see [LP 10](#lp-10--frugality)).

**H**
- **Hiring Committee (HC)** — Google's group-review process for making final hiring decisions, analogous in spirit to Amazon's Bar Raiser-anchored debrief.
- **HLD (High-Level Design)** — the "zoomed out" system design view: components, data flow, scaling strategy (see [Part 6](#part-6--system-design-hld-step-by-step-framework--fresh-case-studies)).
- **Horizontal scaling** — adding more machines to handle increased load, as opposed to vertical scaling (bigger machines).

**I**
- **Idempotency** — a property where performing an operation multiple times has the same effect as performing it once; critical for safe retries (see [6.7](#67-case-study-design-a-distributed-job-scheduler)).
- **Indexing (database)** — a data structure (commonly a B-tree or LSM-tree) speeding up lookups at the cost of extra storage and slower writes.

**J**
- **Jitter** — random variation added to a timing value (e.g., retry delay) to avoid synchronized spikes across many clients.

**K**
- **Kafka** — a distributed log-based message streaming platform commonly used for high-throughput event pipelines.
- **KMP (Knuth-Morris-Pratt)** — a linear-time string-matching algorithm using a precomputed failure function (see [E-4](#e-4-square-implement-strstr-using-kmp-knuth-morris-pratt)).

**L**
- **Latency vs. throughput** — latency is the time for one request to complete; throughput is the number of requests processed per unit time — optimizing one can sometimes hurt the other.
- **Leadership Principles (LPs)** — Amazon's 16 named behavioral values used to evaluate every interview round (see [9.8](#98-all-16-amazon-leadership-principles-explained-with-sample-star-answers)).
- **LLD (Low-Level Design)** — the "zoomed in" system design view: class diagrams, interfaces, design patterns (see [Part 7](#part-7--system-design-lld-step-by-step-framework--fresh-case-studies)).
- **Load balancer** — a component distributing incoming requests across multiple backend servers (L4 = transport layer, L7 = application layer).
- **LRU / LFU** — Least Recently Used / Least Frequently Used: common cache eviction policies (see [C-1](#c-1-amazon-lru-cache), [C-17](#c-17-microsoft-design-an-lfu-cache)).

**M**
- **Microservices** — an architecture style decomposing an application into small, independently deployable services communicating over the network.
- **Monotonic deque** — a deque maintained in increasing or decreasing order, used to solve sliding-window-maximum-style problems in O(n) (see [10.3](#103-microsoft)).
- **MST (Minimum Spanning Tree)** — the minimum-total-weight set of edges connecting all nodes in a weighted graph (see [E-6](#e-6-snowflake-minimum-spanning-tree-kruskals-algorithm)).

**N**
- **NoSQL** — a broad category of non-relational databases (key-value, document, columnar, graph) generally optimized for specific access patterns over strict relational schemas.

**O**
- **OA (Online Assessment)** — a timed, remote, auto-graded coding test used as an early-stage hiring filter (see [Part 2](#part-2--online-assessment-oa-deep-dive)).
- **Observer pattern** — a design pattern where subscribers register to be notified of events from a subject (see [F-3](#f-3-samsung-simple-publish-subscribe-system-observer-pattern)).
- **Ownership** — Amazon Leadership Principle emphasizing taking responsibility beyond one's explicit job description (see [LP 2](#lp-2--ownership)).

**P**
- **P50/P90/P99 latency** — percentile latency metrics; P99 means 99% of requests complete faster than this value — a more meaningful reliability metric than a simple average.
- **Partitioning / sharding** — splitting a dataset across multiple physical stores, typically by a chosen key, to scale beyond a single machine's capacity.
- **Prefix sum** — a precomputed running-total array enabling O(1) range-sum queries after O(n) preprocessing.

**Q**
- **QPS (Queries Per Second)** — a standard throughput metric used in back-of-envelope system design estimation.
- **Quorum** — the minimum number of nodes that must agree for a distributed read/write to be considered successful.

**R**
- **Rate limiting** — restricting the number of requests a client can make in a given time window (token bucket, leaky bucket, sliding window log are common algorithms).
- **Reservoir sampling** — a technique for selecting a uniformly random sample from a stream of unknown length (see [D-23](#d-23-common--multi-company-random-pick-index-reservoir-sampling)).
- **Rolling hash** — a hash function that can be updated incrementally as a sliding window moves, used in Rabin-Karp string matching (see [F-18](#f-18-docusign-rabin-karp-rolling-hash-substring-search)).

**S**
- **SDE-1/2/3** — Amazon's engineering levels (roughly: new grad/early career, mid-level, senior).
- **Segment tree** — a tree structure supporting O(log n) range queries and point updates (see [E-5](#e-5-palantir-range-sum-query--mutable-segment-tree)).
- **SLA / SLO / SLI** — Service Level Agreement (external commitment), Objective (internal target), Indicator (the actual measured metric).
- **STAR method** — Situation, Task, Action, Result: the standard structure for behavioral interview answers (see [8.1](#81-the-star-method-condensed)).
- **Strategy pattern** — a design pattern encapsulating interchangeable algorithms behind a common interface (used throughout Part 7's LLD case studies).

**T**
- **Thundering herd** — many clients simultaneously retrying/requesting at the same instant, overwhelming a recovering system; mitigated with jitter.
- **Topological sort** — an ordering of a DAG's nodes such that every edge points from an earlier to a later node in the ordering (see [D-21](#d-21-common--multi-company-course-schedule-ii-return-the-valid-order)).
- **TTL (Time To Live)** — the duration before a cached or stored value expires automatically.
- **Two-pointer technique** — an algorithmic pattern using two indices moving through a data structure to avoid nested loops.

**U**
- **Union-Find (Disjoint Set Union)** — a data structure tracking a partition of elements into disjoint sets, supporting near-O(1) union and find operations (see [E-1](#e-1-doordash-number-of-provinces-union-find--dsu)).

**V**
- **Vertical scaling** — increasing a single machine's resources (CPU/RAM) rather than adding more machines.

**W**
- **Work Style Assessment** — Amazon's untimed survey evaluating cultural/behavioral fit alongside the coding OA (see [2.7](#27-the-amazonemployer-work-style--personality-assessment)).

## Part 12 — Master Cheat Sheets

### 12.1 OA cheat sheet

| Step | Action |
|---|---|
| Before starting | Test webcam/mic if proctored; close unnecessary apps/tabs; note the total time budget |
| First 2 minutes | Read ALL problems before writing any code; identify which is easiest |
| Per problem | Restate constraints; identify implied complexity from `n`'s bound; write brute force first if optimal isn't obvious |
| Mid-attempt | If stuck at ~60% of allotted time, submit the best partial/brute-force solution for partial credit before moving on |
| Before submitting | Manually trace the given example; check empty input, single element, duplicates, negative numbers, integer overflow (`long` in Java) |
| Work Style Assessment | Answer honestly and consistently; don't try to game an "ideal" profile with contradictory answers |

**Constraint → expected complexity quick reference:**

| `n` up to... | Expected complexity |
|---|---|
| ~10-20 | O(2^n) or O(n!) — brute force/backtracking is fine |
| ~500 | O(n³) |
| ~5,000 | O(n²) |
| ~10^5 - 10^6 | O(n log n) or O(n) |
| ~10^9 or a value range, not a count | O(log n) — binary search on the answer, or O(1) math |

### 12.2 Coding interview cheat sheet: pattern recognition + templates

| # | Pattern | Recognition signal | Template sketch |
|---|---|---|---|
| 1 | Two Pointers | Sorted array, pair/triplet sum, palindrome check | `int lo=0,hi=n-1; while(lo<hi){...}` |
| 2 | Sliding Window (fixed) | "substring/subarray of size K" | `for(i<n){add(i); if(i>=k) remove(i-k);}` |
| 3 | Sliding Window (variable) | "longest/shortest subarray satisfying X" | `for(right<n){expand; while(invalid) shrink(left++);}` |
| 4 | Fast/Slow Pointers | Linked list cycle, middle of list | `slow=slow.next; fast=fast.next.next;` |
| 5 | Merge Intervals | Overlapping ranges | `sort by start; merge if cur.start <= last.end` |
| 6 | Binary Search (index) | Sorted array, O(log n) required | `while(lo<=hi){mid=...; adjust lo/hi}` |
| 7 | Binary Search (answer) | "minimum/maximum X such that Y is feasible" | `while(lo<hi){mid; if(feasible(mid)) hi=mid; else lo=mid+1;}` |
| 8 | BFS (shortest path/levels) | Unweighted graph/grid shortest path | `queue; while(!empty){level++; for each in current level...}` |
| 9 | DFS (backtracking) | Combinations/permutations/subsets | `choose; recurse(next); un-choose` |
| 10 | Topological Sort | Task ordering/dependency validity | `indegree map; queue zero-indegree; process, decrement` |
| 11 | Union-Find | Grouping under merges, cycle detection | `find() with path compression; union() by rank` |
| 12 | Dijkstra's Algorithm | Weighted shortest path, non-negative weights | `min-heap of (node,dist); relax edges` |
| 13 | Monotonic Stack | Next greater/smaller element | `while(!stack.isEmpty() && top < cur) pop and resolve; push` |
| 14 | Monotonic Deque | Sliding window max/min | `pop smaller from back before push; pop expired from front` |
| 15 | Top-K / Bounded Heap | "K largest/smallest/closest" | `heap of size k; offer; if size>k poll` |
| 16 | Prefix Sum | Range sum queries, subarray sum == K | `prefix[i]=prefix[i-1]+nums[i-1]; map of prefix frequencies` |
| 17 | 1D DP | Optimal value over a sequence | `dp[i] = f(dp[i-1], dp[i-2], ...)` |
| 18 | 2D Grid/String DP | Two-sequence comparison, grid paths | `dp[i][j] = f(dp[i-1][j], dp[i][j-1], dp[i-1][j-1])` |
| 19 | Trie | Prefix matching, autocomplete | `TrieNode[26] children; isEnd flag` |
| 20 | Segment Tree | Range query + point update, mutable array | `build bottom-up array of size 2n; update/query via index halving` |
| 21 | Greedy + Sort | "Maximize/minimize X by choosing an order" | `sort by some key; iterate applying a local-optimal choice` |
| 22 | Bit Manipulation | XOR tricks, single-number variants, subsets via bitmask | `for(bit=0;bit<32;bit++){...}` or `1<<i` for subset enumeration |

> Full worked examples for every pattern above are throughout Part 5 (see the "Pattern:" line at the end of each problem) and in [LEETCODE_MASTERY_COMPLETE_GUIDE.md](LEETCODE_MASTERY_COMPLETE_GUIDE.md)'s 20-pattern cheat sheet for even deeper coverage with more example problems per pattern.

### 12.3 System design cheat sheet

**The 8-step HLD framework (recap of [6.2](#62-the-universal-hld-framework-step-by-step)):**
```
1. Clarify functional + non-functional requirements
2. Back-of-envelope estimation (QPS, storage, bandwidth)
3. Define the API contract
4. High-level architecture diagram + data flow
5. Data model + storage choice (SQL vs NoSQL) + partitioning key
6. Deep dive into the 1-2 hardest sub-problems
7. Bottlenecks, SPOFs, scaling to 10x/100x
8. Wrap-up summary + stated improvements
```

**Numbers every engineer should roughly know:**

| Operation | Approx. latency |
|---|---|
| L1 cache reference | ~1 ns |
| RAM access | ~100 ns |
| SSD random read | ~100 µs |
| Round trip within same data center | ~0.5 ms |
| Round trip cross-continent | ~100-150 ms |
| Reading 1 MB sequentially from SSD | ~1 ms |
| Reading 1 MB sequentially from spinning disk | ~20 ms |

**CAP theorem quick reference:** during a network partition, choose **Consistency** (reject/delay requests until replicas agree — e.g., financial ledger balance checks) or **Availability** (always respond, possibly with stale data — e.g., social media like-counts); you cannot have both **during** an actual partition (outside a partition, normal systems provide both).

**SQL vs. NoSQL decision guide:**

| Use SQL when... | Use NoSQL when... |
|---|---|
| Data has complex relationships requiring JOINs | Data is naturally document/key-value shaped |
| Strong ACID transactions are required | Extreme write throughput/horizontal scale is the priority |
| Schema is fairly stable | Schema needs to evolve flexibly |
| Query patterns are varied/ad hoc | Access patterns are simple and known in advance (design around them) |

**Message queue comparison:**

| System | Best for |
|---|---|
| Kafka | High-throughput event streaming, replay-able log, multiple consumer groups |
| RabbitMQ | Complex routing rules, lower-latency task queues |
| SQS/cloud-managed queues | Simplicity, minimal operational overhead, standard at-least-once delivery |

**Building-block quick reference:** load balancing (L4 fast/dumb vs. L7 smart/slower), caching (cache-aside most common; write-through for consistency-sensitive writes), consistent hashing (minimizes remapping on node changes), CDN (push static/media content to the edge), rate limiting (token bucket for burst tolerance, sliding window log for precision).

**Building-block quick reference:** load balancing (L4 fast/dumb vs. L7 smart/slower), caching (cache-aside most common; write-through for consistency-sensitive writes), consistent hashing (minimizes remapping on node changes), CDN (push static/media content to the edge), rate limiting (token bucket for burst tolerance, sliding window log for precision).

### 12.4 Behavioral cheat sheet

**STAR structure recap:** Situation (1-2 sentences) → Task (your specific responsibility) → Action (60-70% of answer, use "I" not "we") → Result (quantified, plus a lesson learned).

**All 16 Amazon Leadership Principles, one-line reminders:**

| LP | One-line reminder |
|---|---|
| Customer Obsession | Start with the customer, work backwards |
| Ownership | Act like an owner, think long-term, no "not my job" |
| Invent and Simplify | Innovate AND simplify — both matter |
| Are Right, A Lot | Strong judgment, seek disconfirming evidence |
| Learn and Be Curious | Never stop learning, explore new possibilities |
| Hire and Develop the Best | Raise the bar, coach others genuinely |
| Insist on the Highest Standards | Relentlessly high quality bar, don't compromise |
| Think Big | Bold direction, don't self-limit scope |
| Bias for Action | Move fast on reversible decisions |
| Frugality | Do more with less, no extra points for headcount |
| Earn Trust | Listen, speak candidly, admit mistakes openly |
| Dive Deep | Stay connected to details, audit, be skeptical of anecdote vs. data |
| Have Backbone; Disagree and Commit | Voice disagreement respectfully, then commit fully |
| Deliver Results | Ship despite setbacks, never settle |
| Strive to be Earth's Best Employer | Safer, more productive, more just workplace, lead with empathy |
| Success and Scale Bring Broad Responsibility | Think beyond immediate impact — society, precedent, fairness |

**Company culture-value one-liners (from Part 10):**

| Company | Core cultural emphasis |
|---|---|
| Google | Googleyness — comfort with ambiguity, intellectual humility |
| Microsoft | Growth mindset — learning agility, cross-team collaboration |
| Meta | Move fast, be bold, focus on long-term impact |
| Apple | Product craftsmanship, attention to detail, discretion |
| Netflix | Freedom & Responsibility — high autonomy, direct feedback |
| Uber | Fast-paced ownership in an ambiguous environment |
| Adobe | Creativity-adjacent problem solving, cross-functional collaboration |
| Goldman Sachs/Bloomberg | Analytical rigor, risk-awareness, precise justification |
| Flipkart/Indian product cos | Scrappy resourcefulness, fast growth |

**Questions to ask your interviewer (pick 2-3 genuinely relevant ones):**
- "What does success look like in this role after 6 months / 1 year?"
- "What's the biggest technical or organizational challenge the team is currently facing?"
- "How does the team balance new feature work against tech debt/reliability investment?"
- "What's the on-call rotation like, and how is paging noise managed?"
- "How would you describe the engineering culture on this specific team, day to day?"

**Questions to ask your interviewer (pick 2-3 genuinely relevant ones):**
- "What does success look like in this role after 6 months / 1 year?"
- "What's the biggest technical or organizational challenge the team is currently facing?"
- "How does the team balance new feature work against tech debt/reliability investment?"
- "What's the on-call rotation like, and how is paging noise managed?"
- "How would you describe the engineering culture on this specific team, day to day?"

## Part 13 — FAQ, Integrated Study Roadmap & Closing

### 13.1 FAQ

1. **Q: How many companies' processes should I prepare for at once?**
   A: Focus on 1-2 target companies for company-specific prep (culture, previously-asked questions), but the underlying DSA/system-design/behavioral skills transfer almost completely across all of them — general prep is never wasted.

2. **Q: Should I prioritize breadth (many easy problems) or depth (fewer, harder problems)?**
   A: Breadth first to build pattern recognition speed (most interview problems are Medium-difficulty pattern applications, not novel Hard-difficulty puzzles), then depth on the specific patterns your target companies favor most.

3. **Q: Is it bad to fail an OA and reapply later?**
   A: No — most companies have a defined reapplication window (commonly 6-12 months); use the time to concretely improve the specific weak areas, not just retry unchanged.

4. **Q: How important is LeetCode "rating"/rank compared to actually understanding patterns?**
   A: Rating is a rough proxy at best; interviewers care about your live problem-solving process (clarifying, communicating, testing), not a public rating number they'll never see.

5. **Q: Should I always aim for the most optimal solution, even under time pressure?**
   A: No — a correct, clearly-explained suboptimal solution delivered on time beats an unfinished or buggy attempt at the optimal one. State the better complexity as a follow-up if time allows.

6. **Q: How do I recover if I get stuck mid-interview?**
   A: Narrate what you're considering out loud, try a smaller/simpler version of the problem to build intuition, and don't be afraid to ask for a hint — gracefully using a hint well is far better than long silence or a wrong confident guess.

7. **Q: Do I need to know multiple programming languages?**
   A: No — deep fluency in one language you can move fast and bug-free in is far more valuable than shallow familiarity with several.

8. **Q: How should I prepare differently for a system design round versus a coding round?**
   A: Coding rounds reward speed and correctness on a well-defined problem; system design rounds reward structured navigation of ambiguity — practice the 8-step framework explicitly until it's automatic, not just reading case studies passively.

9. **Q: What if I don't have "big tech" project experience for behavioral questions?**
   A: Any project with real decisions, trade-offs, and outcomes works — academic projects, personal projects, internships, and even non-technical work experience can all map cleanly to the behavioral themes in [8.2](#82-the-most-common-mnc-behavioral-themes).

10. **Q: Should I mention salary expectations during technical/behavioral rounds?**
    A: No — keep compensation discussions with the recruiter, not with technical interviewers, unless they explicitly raise it (rare and usually inappropriate for them to do).

11. **Q: How long should I spend on take-home assignments if a company uses one instead of a live OA?**
    A: Respect the stated time budget explicitly — submitting something polished but wildly over the suggested time can itself be read as a poor time-management signal.

12. **Q: Is it okay to decline an onsite loop slot and ask to reschedule?**
    A: Yes, within reason — a brief, professional request to reschedule for a legitimate conflict is normal and won't count against you; repeated last-minute rescheduling might.

13. **Q: How do virtual/remote interviews differ from in-person ones logistically?**
    A: Test your setup (camera framing, lighting, mic, stable internet, quiet environment) well in advance; have a backup connectivity plan (e.g., a phone hotspot) in case your primary connection fails mid-interview.

14. **Q: Should I take notes during a system design interview?**
    A: Yes — sketching the architecture (physically or in a shared virtual whiteboard tool) helps both you and the interviewer track the evolving design and is expected, not seen as a crutch.

15. **Q: What's the single highest-leverage thing to practice in the last week before an interview?**
    A: Mock interviews under real time pressure with a partner who can ask realistic follow-ups — reading/reviewing passively is far lower-leverage than active retrieval practice under pressure this close to the actual interview.

16. **Q: How do I handle a question I've genuinely seen before (memorized)?**
    A: Still narrate your reasoning as if solving it fresh — interviewers can often tell when an answer is recited without understanding, and they may modify the problem slightly specifically to test genuine understanding.

17. **Q: Is it acceptable to use a debugger or run code during a live coding interview?**
    A: Most platforms allow running code against sample inputs — use this to your advantage to validate your solution rather than only manually tracing by eye, when the platform supports it.

18. **Q: How many mock interviews should I do before the real thing?**
    A: A commonly cited useful range is 5-10 mock interviews across coding, system design, and behavioral combined — enough to internalize the frameworks and reduce novelty-induced anxiety without over-training on a small fixed set of practice questions.

19. **Q: What should I do in the 24 hours before an interview?**
    A: Light review only (cheat sheets, story bank), confirm logistics, get proper sleep — avoid cramming new material, which has low marginal value this close to the interview and can increase anxiety.

20. **Q: How do I evaluate multiple competing offers?**
    A: Beyond base/bonus/equity, weigh role scope, team/manager quality (ask to speak with the team if not already offered), growth trajectory, and location/remote-policy fit — see [INTERVIEW_MASTERY_GUIDE.md](INTERVIEW_MASTERY_GUIDE.md) Section 29 for a full offer-evaluation framework.

21. **Q: Should I disclose that I'm interviewing with multiple companies simultaneously?**
    A: You don't need to volunteer it, but if asked directly, honesty is fine and can even help create competitive timeline pressure that works in your favor during negotiation.

22. **Q: How technical should my questions to the interviewer be?**
    A: A mix — 1-2 genuinely technical/team-specific questions show engagement, while 1 broader culture/growth question shows you're evaluating overall fit, not just probing for interview "signal."

23. **Q: What if I realize mid-answer that my initial approach was wrong?**
    A: Say so explicitly and pivot — "Actually, I realize this approach won't handle [edge case] well, let me reconsider" is a strong signal of self-correction, not a weakness to hide.

24. **Q: Do all interviewers see my resume before the interview?**
    A: Usually yes, though depth of review varies — assume they've skimmed it and be ready to speak to anything listed, but don't assume deep familiarity with every project detail.

25. **Q: How should I handle an interviewer who seems disengaged or rushed?**
    A: Stay focused on delivering your best structured answer regardless — interviewer demeanor varies for many reasons unrelated to your performance, and reacting to it rarely helps.

26. **Q: Is it normal to not finish a system design prompt fully within the time limit?**
    A: Yes, very common — a well-prioritized partial design covering the framework's early/middle steps thoroughly is far better than a shallow rush through all 8 steps.

27. **Q: Should I prepare different behavioral stories for different companies?**
    A: The same core story bank works everywhere — just adjust which 2-3 stories you lead with based on the specific company's stated values (e.g., lean on ownership/frugality stories for Amazon, autonomy stories for Netflix).

28. **Q: How much should I research a company before interviewing?**
    A: Enough to speak knowledgeably about their products, recent news, and stated values/mission — 1-2 hours of focused research is usually sufficient and shows genuine interest without being excessive.

29. **Q: What's a reasonable number of coding problems to have practiced before interviewing at a FAANG-tier company?**
    A: There's no magic number, but candidates commonly report 150-300 problems practiced with genuine pattern understanding (not just count) as a reasonable target for new-grad/early-career FAANG prep; experienced hires often need fewer but should ensure strong system design and behavioral prep instead.

30. **Q: Is this guide enough on its own, or should I use other resources too?**
    A: Pair this guide with hands-on practice on a real coding judge (to get live feedback on correctness/performance), mock interviews with another person, and — for the deepest possible DSA/system-design coverage — [LEETCODE_MASTERY_COMPLETE_GUIDE.md](LEETCODE_MASTERY_COMPLETE_GUIDE.md) and [SYSTEM_DESIGN_INTERVIEW_MASTERY_GUIDE.md](SYSTEM_DESIGN_INTERVIEW_MASTERY_GUIDE.md) in this same repository.

### 13.2 The integrated 10-week study roadmap

This roadmap blends OA prep, coding patterns, system design, and behavioral/LP prep across 10 weeks (~10-15 hours/week). Compress or extend proportionally based on your actual timeline and starting skill level.

**Week 1 — Orientation + OA fundamentals**
- Mon-Tue: Read Part 1 (hiring pipeline) and Part 2 (OA deep dive) fully.
- Wed-Thu: Drill 8-10 problems from [2.8](#28-previously-asked-oa-questions--company-tagged-bank) under a 25-minute timer each.
- Fri: Drill 5 more OA problems; review any misses by re-deriving the pattern from scratch.
- Weekend: Take one full mock OA (90 minutes, 2 problems, no notes) to establish a baseline.

**Week 2 — Core DSA patterns I**
- Mon-Wed: Work through Part 5.2-5.4 (Amazon/Google/Microsoft-tagged problems), focusing on recognizing the underlying pattern before coding.
- Thu-Fri: Work through Part 5.5-5.6 (Meta/Apple/Netflix/Uber/Bloomberg-tagged problems).
- Weekend: Redo 6 problems you found hardest this week, from scratch, no hints, timed.

**Week 3 — Core DSA patterns II**
- Mon-Wed: Work through Part 5.7 (D-1 to D-24), pausing to write out the "Pattern:" note for each in your own words.
- Thu-Fri: Work through Part 5.8 (E-1 to E-24), especially the Union-Find, segment tree, and MST sections if unfamiliar.
- Weekend: Take a second mock OA/coding-screen session (60 minutes, 2 problems, narrated aloud).

**Week 4 — Core DSA patterns III + phone screen practice**
- Mon-Tue: Work through Part 5.9 (F-1 to F-20).
- Wed: Read Part 3 (phone screen) closely, memorize the 5-step live-coding communication framework.
- Thu-Fri: Do 2 timed mock phone screens (45-60 min, 1-2 problems each, narrated).
- Weekend: Review Part 12.2's pattern cheat sheet; for each of the 22 patterns, write from memory which 2-3 practiced problems used it.

**Week 5 — System design foundations (HLD)**
- Mon: Read [6.1-6.2](#61-hld-vs-lld--the-difference-interviewers-care-about) fully, memorize the 8-step checklist.
- Tue-Thu: Work through case studies [6.3](#63-case-study-design-amazon-locker--package-pickup-system) through [6.8](#68-case-study-design-a-notificationalerting-system), attempting each from memory first before checking against the guide.
- Fri: Work through [6.9](#69-case-study-design-a-search-autocompletetypeahead-service) through [6.12](#612-case-study-design-a-ticket-booking-system).
- Weekend: Do one full 45-minute mock HLD session on an unseen prompt (e.g., pick a system not covered in this guide).

**Week 6 — System design (LLD) + Onsite loop prep**
- Mon: Read [7.1](#71-the-universal-lld-framework-step-by-step) fully; review SOLID principles and common design patterns if rusty.
- Tue-Wed: Work through all 5 LLD case studies ([7.2](#72-case-study-lld-for-an-amazon-style-shopping-cart)-[7.6](#76-case-study-lld-for-a-movie-ticket-booking-system)), writing the Java code by hand rather than just reading it.
- Thu: Read Part 4 (onsite loop breakdown) closely.
- Fri-Weekend: Do a full mock LLD session (45 min, unseen prompt) plus review [Part 10](#part-10--company-specific-playbooks)'s company-specific questions for your target company.

**Week 7 — Behavioral & Leadership Principles**
- Mon: Read [8.1-8.3](#81-the-star-method-condensed) and build your initial 6-10 story candidate list.
- Tue: If targeting Amazon, read all 16 LPs in [9.8](#98-all-16-amazon-leadership-principles-explained-with-sample-star-answers) closely; otherwise, read [8.2](#82-the-most-common-mnc-behavioral-themes)'s theme table closely instead.
- Wed-Thu: Map each of your stories to 2-3 relevant LPs/themes, write full STAR bullets for each.
- Fri: Practice delivering 4-5 stories out loud, timed to 2 minutes each.
- Weekend: Do a full mock behavioral round (5-6 questions, no notes, ideally with a partner asking realistic follow-ups).

**Week 8 — Company-specific deep dive**
- Mon-Tue: Read your target company's section in [Part 10](#part-10--company-specific-playbooks) (or [Part 9](#part-9--amazon-deep-dive-the-complete-playbook) if targeting Amazon) closely, twice.
- Wed: Drill that company's specific previously-asked questions until you can solve each cleanly within its typical time budget.
- Thu-Fri: Re-read [9.7](#97-amazon-system-design-round-whats-different) (or the equivalent company-specific system design emphasis) and redo 1-2 case studies incorporating those specific emphases.
- Weekend: Full mock loop simulation — 1 coding round, 1 system design round, 1 behavioral round, back to back, same day if possible.

**Week 9 — Full mock loop iteration + weak-area remediation**
- Mon-Wed: Based on Week 8's mock loop, identify your 2-3 weakest areas and drill them specifically (more problems in a weak pattern, another system design case study, more behavioral story practice).
- Thu-Fri: Do a second full mock loop, ideally with a different mock partner for fresh feedback.
- Weekend: Light review of cheat sheets ([Part 12](#part-12--master-cheat-sheets)); rest.

**Week 10 — Final polish & logistics**
- Mon-Tue: Re-skim your story bank bullets and the 22-pattern cheat sheet; no new material.
- Wed: Prepare interview-day logistics (test video/audio, prepare your environment, prepare 3-4 thoughtful questions from [12.4](#124-behavioral-cheat-sheet)).
- Thu: Light, confidence-building review only — redo 2-3 problems you've already solved successfully before, just to end on a positive note.
- Fri onward: Rest, avoid cramming, trust the preparation you've done.

### 13.3 Closing notes

This guide covered the entire modern MNC software engineering hiring pipeline — the Online Assessment, technical phone screens, the onsite/virtual onsite loop, coding interviews with 93+ company-tagged previously-asked questions, a complete step-by-step HLD and LLD system design framework with 15 fresh case studies, general behavioral interview preparation, and a full standalone playbook for Amazon's OA, interview, system design, and Leadership-Principles-driven behavioral process, plus company-specific playbooks for 9 more major MNCs.

No guide can substitute for deliberate, active practice — reading this once will build awareness of the landscape, but genuine interview readiness comes from timed problem-solving repetitions, mock system design sessions, and rehearsed (but genuine) behavioral stories delivered under realistic pressure. Pair this guide with [LEETCODE_MASTERY_COMPLETE_GUIDE.md](LEETCODE_MASTERY_COMPLETE_GUIDE.md) for the deepest possible DSA pattern coverage, [SYSTEM_DESIGN_INTERVIEW_MASTERY_GUIDE.md](SYSTEM_DESIGN_INTERVIEW_MASTERY_GUIDE.md) for the full 22 HLD + 12 LLD case-study library, and [INTERVIEW_MASTERY_GUIDE.md](INTERVIEW_MASTERY_GUIDE.md) for general resume, negotiation, and behavioral depth.

Interviews are conversations designed to reveal how you think, communicate, and would work alongside a real team — not memorization exams. Prepare deliberately, stay calm under time pressure, be honest in behavioral answers, and treat every round (including ones that feel like they're going poorly) as worth finishing strongly, since a single rough moment early in a round rarely determines the outcome on its own. Good luck.

## Part 14 — Extended Practice Problem Bank (More Previously-Asked Questions)

### 14.1 How to use this bank

This final bank adds more previously-reported interview questions in a slightly fuller format (statement, worked example, approach, code, complexity, and a common follow-up/mistake note) to round out coverage of the most frequently-recurring question types not yet fully explored above. Use it as additional timed practice material during weeks 2-4 of the study roadmap in [13.2](#132-the-integrated-10-week-study-roadmap).

### 14.2 Batch 1: Arrays, strings & hashing

#### G-1. Two Sum

**Problem:** Given an array of integers and a target, return the indices of the two numbers that add up to the target (exactly one valid answer exists, and you may not use the same element twice).

**Example:** `nums = [2,7,11,15], target = 9` → `[0,1]` (since `2 + 7 = 9`).

**Approach:** Single pass with a hashmap of value → index; for each number, check if its complement (`target - num`) has already been seen.

```java
int[] twoSum(int[] nums, int target) {
    Map<Integer, Integer> seen = new HashMap<>();
    for (int i = 0; i < nums.length; i++) {
        int complement = target - nums[i];
        if (seen.containsKey(complement)) return new int[]{seen.get(complement), i};
        seen.put(nums[i], i);
    }
    throw new IllegalArgumentException("No solution");
}
```
**Complexity:** O(n) time, O(n) space. **Pattern:** hashmap complement lookup — likely the single most-asked warm-up question across every company in this guide. **Common mistake/follow-up:** forgetting to check the complement BEFORE inserting the current number (which would incorrectly allow using the same element twice); a common follow-up is "what if the array is sorted?" (answer: two pointers, O(1) extra space instead of O(n)).

#### G-2. Best Time to Buy and Sell Stock

**Problem:** Given daily stock prices, find the maximum profit from one buy and one later sell (0 if no profit possible).

**Example:** `prices = [7,1,5,3,6,4]` → `5` (buy at 1, sell at 6).

**Approach:** Single pass tracking the minimum price seen so far and the best profit achievable if selling today.

```java
int maxProfit(int[] prices) {
    int minPrice = Integer.MAX_VALUE, maxProfit = 0;
    for (int price : prices) {
        minPrice = Math.min(minPrice, price);
        maxProfit = Math.max(maxProfit, price - minPrice);
    }
    return maxProfit;
}
```
**Complexity:** O(n) time, O(1) space. **Pattern:** running-minimum tracker — the simplest member of a large family of "buy/sell stock" DP variants (with cooldown, with transaction fees, with K transactions). **Common mistake/follow-up:** the natural follow-up is "what if you can make unlimited transactions?" (answer: greedily sum every positive day-over-day price increase).

#### G-3. Contains Duplicate II (Within Distance K)

**Problem:** Given an array and integer `k`, determine if there are two equal elements whose indices differ by at most `k`.

**Example:** `nums = [1,2,3,1], k = 3` → `true` (indices 0 and 3, both value 1, differ by 3).

**Approach:** Sliding window of size `k+1` maintained as a HashSet — remove the element leaving the window before checking/adding the new one.

```java
boolean containsNearbyDuplicate(int[] nums, int k) {
    Set<Integer> window = new HashSet<>();
    for (int i = 0; i < nums.length; i++) {
        if (i > k) window.remove(nums[i - k - 1]);
        if (!window.add(nums[i])) return true;
    }
    return false;
}
```
**Complexity:** O(n) time, O(min(n, k)) space. **Pattern:** fixed-size sliding window with a set — a simpler cousin of [OA-1](#oa-1-substrings-of-size-k-with-k-distinct-characters)'s window-frequency-map pattern. **Common mistake/follow-up:** off-by-one on the window boundary (`i > k`, not `i >= k`) is the most common bug; a common follow-up adds a value-distance constraint too ("Contains Duplicate III").

#### G-4. Valid Anagram

**Problem:** Determine if two strings are anagrams of each other.

**Example:** `s = "anagram", t = "nagaram"` → `true`.

**Approach:** Frequency count array (26 letters for lowercase-only input) — increment for `s`, decrement for `t`, valid if all counts return to zero.

```java
boolean isAnagram(String s, String t) {
    if (s.length() != t.length()) return false;
    int[] counts = new int[26];
    for (int i = 0; i < s.length(); i++) {
        counts[s.charAt(i) - 'a']++;
        counts[t.charAt(i) - 'a']--;
    }
    for (int c : counts) if (c != 0) return false;
    return true;
}
```
**Complexity:** O(n) time, O(1) space (fixed 26-size array). **Pattern:** fixed-alphabet frequency counting — a fast, universally-reported warm-up question. **Common mistake/follow-up:** for Unicode input, a `HashMap<Character,Integer>` replaces the fixed array; a common follow-up is "what if inputs are massive streams, not fixed strings?" (answer: maintain running counts incrementally).

#### G-5. Group Shifted Strings

**Problem:** Group strings that are shift-equivalent (e.g., `"abc"` and `"bcd"` are in the same group, since shifting each letter of `"abc"` by 1 gives `"bcd"`).

**Example:** `["abc","bcd","acef","xyz","az","ba","a","z"]` groups into `["abc","bcd","xyz"], ["acef"], ["az","ba"], ["a","z"]`.

**Approach:** Compute a canonical "shift key" per string (the sequence of consecutive letter differences, wrapping mod 26), and group by that key in a hashmap.

```java
List<List<String>> groupStrings(String[] strings) {
    Map<String, List<String>> groups = new HashMap<>();
    for (String s : strings) {
        StringBuilder key = new StringBuilder();
        for (int i = 1; i < s.length(); i++) {
            int diff = (s.charAt(i) - s.charAt(i - 1) + 26) % 26;
            key.append(diff).append(',');
        }
        groups.computeIfAbsent(key.toString(), k -> new ArrayList<>()).add(s);
    }
    return new ArrayList<>(groups.values());
}
```
**Complexity:** O(n × L) where L is average string length. **Pattern:** canonical-key grouping — the same overall shape as "Group Anagrams" (canonical key = sorted string) but with a different key-derivation rule; recognizing "compute a canonical form, group by it" as a reusable meta-pattern is the real takeaway.

#### G-6. Longest Common Prefix

**Problem:** Find the longest common prefix string amongst an array of strings.

**Example:** `["flower","flow","flight"]` → `"fl"`.

**Approach:** Compare character-by-character across all strings at each position, starting from the first string as a candidate prefix and shrinking it whenever a mismatch is found.

```java
String longestCommonPrefix(String[] strs) {
    if (strs.length == 0) return "";
    String prefix = strs[0];
    for (int i = 1; i < strs.length; i++) {
        while (!strs[i].startsWith(prefix)) {
            prefix = prefix.substring(0, prefix.length() - 1);
            if (prefix.isEmpty()) return "";
        }
    }
    return prefix;
}
```
**Complexity:** O(S) where S is the sum of all string lengths, worst case. **Pattern:** iterative prefix-shrinking — simple but a genuinely common quick warm-up; a Trie-based approach ([D-24](#d-24-common--multi-company-implement-a-trie-prefix-tree)) is the natural follow-up for a very large number of strings queried repeatedly.

#### G-7. String Compression (In-Place)

**Problem:** Compress a character array in-place using counts of repeated characters (e.g., `['a','a','b','b','b']` → `['a','2','b','3']`), returning the new length.

**Example:** input `['a','a','b','b','b']` → returns `4`, array becomes `['a','2','b','3',...]`.

**Approach:** Two pointers — a read pointer scanning runs of the same character, and a write pointer placing the character followed by its count (only if count > 1) directly back into the same array.

```java
int compress(char[] chars) {
    int write = 0, read = 0;
    while (read < chars.length) {
        char current = chars[read];
        int count = 0;
        while (read < chars.length && chars[read] == current) { read++; count++; }
        chars[write++] = current;
        if (count > 1) {
            for (char c : String.valueOf(count).toCharArray()) chars[write++] = c;
        }
    }
    return write;
}
```
**Complexity:** O(n) time, O(1) extra space. **Pattern:** in-place two-pointer read/write compaction — a frequently-tested "implement it without extra memory" style question, common at companies with embedded/memory-constrained products.

#### G-8. Rotate Array (In-Place, O(1) Extra Space)

**Problem:** Rotate an array to the right by `k` steps, in-place.

**Example:** `[1,2,3,4,5,6,7], k=3` → `[5,6,7,1,2,3,4]`.

**Approach:** The "triple reversal" trick — reverse the entire array, then reverse the first `k` elements, then reverse the remaining elements.

```java
void rotate(int[] nums, int k) {
    int n = nums.length;
    k %= n;
    reverse(nums, 0, n - 1);
    reverse(nums, 0, k - 1);
    reverse(nums, k, n - 1);
}
private void reverse(int[] nums, int lo, int hi) {
    while (lo < hi) { int t = nums[lo]; nums[lo] = nums[hi]; nums[hi] = t; lo++; hi--; }
}
```
**Complexity:** O(n) time, O(1) extra space. **Pattern:** the triple-reversal trick for in-place rotation — a clever, non-obvious technique worth memorizing since the naive approach (extra array, or rotating one step at a time k times) is either not O(1) space or not O(n) time.

#### G-9. Majority Element (Boyer-Moore Voting Algorithm)

**Problem:** Find the element appearing more than `n/2` times in an array (guaranteed to exist), in O(1) extra space.

**Example:** `[2,2,1,1,1,2,2]` → `2`.

**Approach:** Boyer-Moore voting — maintain a candidate and a count; increment count when seeing the candidate, decrement otherwise; when count hits zero, switch candidates. The guaranteed majority element always survives this process.

```java
int majorityElement(int[] nums) {
    int candidate = nums[0], count = 0;
    for (int num : nums) {
        if (count == 0) candidate = num;
        count += (num == candidate) ? 1 : -1;
    }
    return candidate;
}
```
**Complexity:** O(n) time, O(1) space. **Pattern:** Boyer-Moore voting — a genuinely elegant, non-obvious O(1)-space technique; a common follow-up is "Majority Element II" (find all elements appearing more than n/3 times, requiring two candidates tracked simultaneously).

#### G-10. Next Permutation

**Problem:** Rearrange numbers into the lexicographically next greater permutation (in-place); if none exists (already the largest), rearrange to the lowest (sorted ascending).

**Example:** `[1,2,3]` → `[1,3,2]`. `[3,2,1]` → `[1,2,3]`.

**Approach:** Scan from the right to find the first index `i` where `nums[i] < nums[i+1]` (the "pivot"); then find the smallest element to the right of `i` that's still greater than `nums[i]`, swap them, then reverse everything after index `i` (which is guaranteed to be in descending order at that point).

```java
void nextPermutation(int[] nums) {
    int n = nums.length, i = n - 2;
    while (i >= 0 && nums[i] >= nums[i + 1]) i--;
    if (i >= 0) {
        int j = n - 1;
        while (nums[j] <= nums[i]) j--;
        int t = nums[i]; nums[i] = nums[j]; nums[j] = t;
    }
    reverse(nums, i + 1, n - 1);
}
private void reverse(int[] nums, int lo, int hi) {
    while (lo < hi) { int t = nums[lo]; nums[lo] = nums[hi]; nums[hi] = t; lo++; hi--; }
}
```
**Complexity:** O(n) time, O(1) space. **Pattern:** a genuinely tricky, must-derive-carefully array manipulation — worth memorizing the 3-step recipe (find pivot, find swap target, reverse suffix) cold since deriving it live under pressure is hard for most candidates.

#### G-11. First Missing Positive

**Problem:** Given an unsorted integer array, find the smallest missing positive integer, in O(n) time and O(1) extra space.

**Example:** `[3,4,-1,1]` → `2`. `[1,2,0]` → `3`.

**Approach:** Cyclic placement — for each value `v` in range `[1, n]`, swap it into index `v-1` (its "correct" position); after this pass, the first index `i` where `nums[i] != i+1` reveals the answer `i+1`.

```java
int firstMissingPositive(int[] nums) {
    int n = nums.length;
    for (int i = 0; i < n; i++) {
        while (nums[i] > 0 && nums[i] <= n && nums[nums[i] - 1] != nums[i]) {
            int target = nums[i] - 1;
            int temp = nums[target]; nums[target] = nums[i]; nums[i] = temp;
        }
    }
    for (int i = 0; i < n; i++) if (nums[i] != i + 1) return i + 1;
    return n + 1;
}
```
**Complexity:** O(n) time (each element is swapped at most a constant number of times), O(1) space. **Pattern:** cyclic sort/placement — a distinctive technique for "find the missing/duplicate number in range [1,n]" problems; the key insight (the answer must be in `[1, n+1]`) is what makes O(1) space possible at all. **Common mistake/follow-up:** an infinite loop if the swap condition doesn't also check `nums[nums[i]-1] != nums[i]` (to avoid endlessly swapping an already-correctly-placed or duplicate value).

#### G-12. 3Sum Closest

**Problem:** Given an array and a target, find three numbers whose sum is closest to the target; return that sum.

**Example:** `nums = [-1,2,1,-4], target = 1` → `2` (from `-1+2+1=2`).

**Approach:** Sort the array, then for each fixed first element, use two pointers on the remaining subarray, adjusting based on whether the current sum is above or below the target and tracking the closest sum seen.

```java
int threeSumClosest(int[] nums, int target) {
    Arrays.sort(nums);
    int closest = nums[0] + nums[1] + nums[2];
    for (int i = 0; i < nums.length - 2; i++) {
        int lo = i + 1, hi = nums.length - 1;
        while (lo < hi) {
            int sum = nums[i] + nums[lo] + nums[hi];
            if (Math.abs(sum - target) < Math.abs(closest - target)) closest = sum;
            if (sum == target) return sum;
            else if (sum < target) lo++;
            else hi--;
        }
    }
    return closest;
}
```
**Complexity:** O(n²). **Pattern:** "fix one, two-pointer the rest" — the same overall shape as the classic 3Sum problem, adapted to track closeness rather than exact matches.

#### G-13. 4Sum

**Problem:** Find all unique quadruplets that sum to a given target.

**Example:** `nums = [1,0,-1,0,-2,2], target = 0` → `[[-2,-1,1,2],[-2,0,0,2],[-1,0,0,1]]`.

**Approach:** Sort, then fix the first two elements with nested loops (skipping duplicates at each level), and two-pointer the remaining two — a direct generalization of 3Sum with one more fixed loop.

```java
List<List<Integer>> fourSum(int[] nums, int target) {
    Arrays.sort(nums);
    List<List<Integer>> result = new ArrayList<>();
    int n = nums.length;
    for (int i = 0; i < n - 3; i++) {
        if (i > 0 && nums[i] == nums[i - 1]) continue;
        for (int j = i + 1; j < n - 2; j++) {
            if (j > i + 1 && nums[j] == nums[j - 1]) continue;
            int lo = j + 1, hi = n - 1;
            while (lo < hi) {
                long sum = (long) nums[i] + nums[j] + nums[lo] + nums[hi];
                if (sum == target) {
                    result.add(Arrays.asList(nums[i], nums[j], nums[lo], nums[hi]));
                    while (lo < hi && nums[lo] == nums[lo + 1]) lo++;
                    while (lo < hi && nums[hi] == nums[hi - 1]) hi--;
                    lo++; hi--;
                } else if (sum < target) lo++; else hi--;
            }
        }
    }
    return result;
}
```
**Complexity:** O(n³). **Pattern:** the "K-sum" generalization pattern (fix K-2 elements via nested loops with duplicate-skipping, two-pointer the last 2) — understanding this generalization means 3Sum, 4Sum, and even a general K-Sum follow-up all use the identical skeleton.

#### G-14. Isomorphic Strings

**Problem:** Determine if two strings are isomorphic (characters in the first can be consistently mapped to characters in the second, one-to-one).

**Example:** `s = "egg", t = "add"` → `true`. `s = "foo", t = "bar"` → `false`.

**Approach:** Two hashmaps enforcing a bidirectional one-to-one mapping — checking only one direction would incorrectly allow two different source characters to map to the same target character.

```java
boolean isIsomorphic(String s, String t) {
    Map<Character, Character> mapST = new HashMap<>(), mapTS = new HashMap<>();
    for (int i = 0; i < s.length(); i++) {
        char cs = s.charAt(i), ct = t.charAt(i);
        if (mapST.containsKey(cs) && mapST.get(cs) != ct) return false;
        if (mapTS.containsKey(ct) && mapTS.get(ct) != cs) return false;
        mapST.put(cs, ct); mapTS.put(ct, cs);
    }
    return true;
}
```
**Complexity:** O(n). **Pattern:** bidirectional mapping validation — the single most common bug here is checking only one direction, which incorrectly accepts a many-to-one mapping as isomorphic.

#### G-15. Word Pattern

**Problem:** Given a pattern (e.g., `"abba"`) and a string of space-separated words, determine if the words follow the same pattern (a bijection between pattern characters and words).

**Example:** `pattern = "abba", s = "dog cat cat dog"` → `true`.

**Approach:** Identical bidirectional-mapping idea as Isomorphic Strings ([G-14](#g-14-isomorphic-strings)), but mapping characters to whole words instead of characters to characters.

```java
boolean wordPattern(String pattern, String s) {
    String[] words = s.split(" ");
    if (pattern.length() != words.length) return false;
    Map<Character, String> charToWord = new HashMap<>();
    Map<String, Character> wordToChar = new HashMap<>();
    for (int i = 0; i < pattern.length(); i++) {
        char c = pattern.charAt(i);
        String w = words[i];
        if (charToWord.containsKey(c) && !charToWord.get(c).equals(w)) return false;
        if (wordToChar.containsKey(w) && wordToChar.get(w) != c) return false;
        charToWord.put(c, w); wordToChar.put(w, c);
    }
    return true;
}
```
**Complexity:** O(n). **Pattern:** the same bidirectional-mapping template as G-14, generalized to a different element type (words instead of characters) — recognizing when two differently-worded problems share an identical underlying template is a genuinely valuable interview skill.

### 14.3 Batch 2: Trees, graphs & heaps

#### G-16. Diameter of Binary Tree

**Problem:** Find the length (number of edges) of the longest path between any two nodes in a binary tree (the path may or may not pass through the root).

**Example:** A tree with root 1, left child 2, right child 3, and 2's children 4 and 5 has diameter 3 (path 4-2-5 via... actually the longest path 4→2→1→3 has 3 edges).

**Approach:** Post-order recursion where each call returns its subtree's height, while a side-channel tracks the maximum "left height + right height" seen at any node (the diameter through that node).

```java
private int diameter = 0;
int diameterOfBinaryTree(TreeNode root) {
    height(root);
    return diameter;
}
private int height(TreeNode node) {
    if (node == null) return 0;
    int leftHeight = height(node.left);
    int rightHeight = height(node.right);
    diameter = Math.max(diameter, leftHeight + rightHeight);
    return 1 + Math.max(leftHeight, rightHeight);
}
```
**Complexity:** O(n). **Pattern:** the "compute height, track a global max as a side effect" template — the exact same skeleton as [Meta's Binary Tree Maximum Path Sum](#104-meta), just tracking edge-count instead of value-sum.

#### G-17. Binary Search Tree Iterator

**Problem:** Design an iterator over a BST that returns the next smallest element each call to `next()`, with `hasNext()`, both averaging O(1) time.

**Approach:** Maintain an explicit stack of left-spine nodes; `next()` pops a node, then pushes the left-spine of its right subtree (standard iterative in-order traversal, but paused/resumed across calls instead of done all at once).

```java
class BSTIterator {
    private final Deque<TreeNode> stack = new ArrayDeque<>();
    BSTIterator(TreeNode root) { pushLeftSpine(root); }
    public int next() {
        TreeNode node = stack.pop();
        pushLeftSpine(node.right);
        return node.val;
    }
    public boolean hasNext() { return !stack.isEmpty(); }
    private void pushLeftSpine(TreeNode node) {
        while (node != null) { stack.push(node); node = node.left; }
    }
}
```
**Complexity:** O(h) space (h = tree height), O(1) amortized time per `next()` call. **Pattern:** "pause-and-resume" iterative in-order traversal via an explicit stack — a genuinely elegant technique for turning any recursive traversal into a stateful iterator.

#### G-18. Populating Next Right Pointers in Each Node

**Problem:** Given a perfect binary tree, connect each node's `next` pointer to its right neighbor at the same level (or null if none), using O(1) extra space.

**Approach:** Level-by-level traversal using already-established `next` pointers from the level above to move across the current level, without needing a queue.

```java
Node connect(Node root) {
    Node leftmost = root;
    while (leftmost != null && leftmost.left != null) {
        Node head = leftmost;
        while (head != null) {
            head.left.next = head.right;
            if (head.next != null) head.right.next = head.next.left;
            head = head.next;
        }
        leftmost = leftmost.left;
    }
    return root;
}
```
**Complexity:** O(n) time, O(1) space. **Pattern:** using already-built `next` pointers from the parent level to traverse the current level without a queue — the key trick enabling true O(1) space (a plain BFS with a queue would need O(n) space in the worst case).

#### G-19. Kth Smallest Element in a BST

**Problem:** Find the `k`-th smallest value in a BST.

**Example:** BST `[3,1,4,null,2], k=1` → `1`.

**Approach:** In-order traversal visits BST nodes in sorted order; stop early once the `k`-th node is visited (using an explicit stack for early termination, rather than collecting the entire traversal first).

```java
int kthSmallest(TreeNode root, int k) {
    Deque<TreeNode> stack = new ArrayDeque<>();
    TreeNode node = root;
    while (true) {
        while (node != null) { stack.push(node); node = node.left; }
        node = stack.pop();
        if (--k == 0) return node.val;
        node = node.right;
    }
}
```
**Complexity:** O(h + k) time. **Pattern:** early-terminating in-order traversal — exploiting the BST property (in-order = sorted) to avoid a full O(n) traversal plus sort when only the k-th element is needed.

#### G-20. Top K Frequent Words

**Problem:** Return the `k` most frequent words, ties broken lexicographically (unlike [F-4](#f-4-saasanalytics-top-k-word-frequency-in-a-large-text) which broke ties the opposite way — always confirm the exact tie-break rule).

**Approach:** Min-heap of size `k` with a comparator prioritizing lower frequency first, and for equal frequency, lexicographically LARGER words first (so they get evicted first, leaving the lexicographically smaller ones in the final heap).

```java
List<String> topKFrequent(String[] words, int k) {
    Map<String, Integer> freq = new HashMap<>();
    for (String w : words) freq.merge(w, 1, Integer::sum);
    PriorityQueue<String> minHeap = new PriorityQueue<>((a, b) ->
        freq.get(a).equals(freq.get(b)) ? b.compareTo(a) : freq.get(a) - freq.get(b));
    for (String w : freq.keySet()) {
        minHeap.offer(w);
        if (minHeap.size() > k) minHeap.poll();
    }
    LinkedList<String> result = new LinkedList<>();
    while (!minHeap.isEmpty()) result.addFirst(minHeap.poll());
    return result;
}
```
**Complexity:** O(n log k). **Pattern:** bounded heap with a careful compound tie-break comparator — the recurring lesson across every "top-K" variant in this guide is to always nail down the EXACT tie-break rule before coding, since it changes the comparator's direction non-obviously.

#### G-21. Clone Graph

**Problem:** Given a reference to a node in a connected undirected graph, return a deep copy of the entire graph.

**Approach:** DFS (or BFS) with a hashmap tracking `original node → cloned node`, so each node is cloned exactly once even though the graph traversal may revisit nodes via different edges.

```java
Map<Node, Node> visited = new HashMap<>();
Node cloneGraph(Node node) {
    if (node == null) return null;
    if (visited.containsKey(node)) return visited.get(node);
    Node clone = new Node(node.val);
    visited.put(node, clone);
    for (Node neighbor : node.neighbors) clone.neighbors.add(cloneGraph(neighbor));
    return clone;
}
```
**Complexity:** O(V + E). **Pattern:** DFS with a visited-map doubling as a "clone registry" — prevents both infinite recursion on cycles and duplicate cloning of the same node.

#### G-22. Surrounded Regions

**Problem:** Given a board of `'X'` and `'O'`, capture (flip to `'X'`) all regions of `'O'` that are NOT connected to the border.

**Approach:** The reverse-thinking trick — instead of finding enclosed regions directly, mark all `'O'`s connected to the border (via DFS/BFS from every border cell) as "safe," then flip every remaining unmarked `'O'` to `'X'`.

```java
void solve(char[][] board) {
    int rows = board.length, cols = board[0].length;
    for (int i = 0; i < rows; i++) { markSafe(board, i, 0); markSafe(board, i, cols - 1); }
    for (int j = 0; j < cols; j++) { markSafe(board, 0, j); markSafe(board, rows - 1, j); }
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            if (board[i][j] == 'O') board[i][j] = 'X';
            else if (board[i][j] == 'S') board[i][j] = 'O';
        }
    }
}
private void markSafe(char[][] board, int i, int j) {
    if (i < 0 || j < 0 || i >= board.length || j >= board[0].length || board[i][j] != 'O') return;
    board[i][j] = 'S'; // temporarily mark as safe
    markSafe(board, i + 1, j); markSafe(board, i - 1, j); markSafe(board, i, j + 1); markSafe(board, i, j - 1);
}
```
**Complexity:** O(rows × cols). **Pattern:** "invert the problem — mark what should SURVIVE rather than what should be removed" — a recurring reframing trick for enclosure/region problems that's much simpler than trying to detect "fully enclosed" directly.

#### G-23. Bus Routes (BFS Over a Derived Graph)

**Problem:** Given bus routes (each a list of stops) and a start/target stop, find the minimum number of buses needed to travel from start to target.

**Approach:** Build a graph where nodes are BUS ROUTES (not stops), connecting two routes if they share a stop; BFS over this route-graph from all routes containing the start stop to any route containing the target stop.

```java
int numBusesToDestination(int[][] routes, int source, int target) {
    if (source == target) return 0;
    Map<Integer, List<Integer>> stopToRoutes = new HashMap<>();
    for (int r = 0; r < routes.length; r++)
        for (int stop : routes[r]) stopToRoutes.computeIfAbsent(stop, k -> new ArrayList<>()).add(r);
    Queue<Integer> queue = new LinkedList<>();
    Set<Integer> visitedRoutes = new HashSet<>();
    for (int r : stopToRoutes.getOrDefault(source, Collections.emptyList())) { queue.offer(r); visitedRoutes.add(r); }
    int buses = 1;
    Set<Integer> visitedStops = new HashSet<>();
    while (!queue.isEmpty()) {
        int size = queue.size();
        for (int s = 0; s < size; s++) {
            int route = queue.poll();
            for (int stop : routes[route]) {
                if (stop == target) return buses;
                if (visitedStops.add(stop)) {
                    for (int nextRoute : stopToRoutes.getOrDefault(stop, Collections.emptyList())) {
                        if (visitedRoutes.add(nextRoute)) queue.offer(nextRoute);
                    }
                }
            }
        }
        buses++;
    }
    return -1;
}
```
**Complexity:** O(total stops across all routes). **Pattern:** BFS over a TRANSFORMED graph (routes as nodes, not stops) — recognizing when to redefine what a "node" represents is a hallmark of harder graph questions.

#### G-24. Sliding Puzzle

**Problem:** Given a 2x3 board with tiles 1-5 and one blank (0), find the minimum number of moves to reach the solved state `[[1,2,3],[4,5,0]]`, sliding the blank up/down/left/right.

**Approach:** BFS over the STATE SPACE (each board configuration encoded as a string is a "node"), since this is really shortest-path-in-an-implicit-graph, not a grid-traversal problem.

```java
int slidingPuzzle(int[][] board) {
    String start = "" + board[0][0] + board[0][1] + board[0][2] + board[1][0] + board[1][1] + board[1][2];
    String target = "123450";
    int[][] neighbors = {{1,3},{0,2,4},{1,5},{0,4},{1,3,5},{2,4}}; // adjacency for each flat index
    Queue<String> queue = new LinkedList<>();
    Set<String> visited = new HashSet<>();
    queue.offer(start); visited.add(start);
    int moves = 0;
    while (!queue.isEmpty()) {
        int size = queue.size();
        for (int s = 0; s < size; s++) {
            String state = queue.poll();
            if (state.equals(target)) return moves;
            int zeroIdx = state.indexOf('0');
            for (int neighbor : neighbors[zeroIdx]) {
                char[] chars = state.toCharArray();
                char t = chars[zeroIdx]; chars[zeroIdx] = chars[neighbor]; chars[neighbor] = t;
                String next = new String(chars);
                if (visited.add(next)) queue.offer(next);
            }
        }
        moves++;
    }
    return -1;
}
```
**Complexity:** O((states) × transitions), bounded since only 720 permutations exist for a 2x3 board. **Pattern:** BFS over an implicit STATE-SPACE GRAPH (each unique board configuration is a node) — the same meta-pattern underlies many "minimum moves to reach a target configuration" puzzles regardless of the specific puzzle's rules.

#### G-25. Merge K Sorted Arrays (Divide and Conquer Alternative)

**Problem:** Merge `k` sorted arrays into one sorted array (same underlying problem as [C-3](#c-3-amazon-merge-k-sorted-lists)'s linked-list version, but for arrays, showing the divide-and-conquer alternative to the heap approach).

**Approach:** Pairwise merge — repeatedly merge arrays two at a time (like merge sort's merge step) until only one remains, halving the number of arrays at each round.

```java
int[] mergeKSortedArrays(List<int[]> arrays) {
    while (arrays.size() > 1) {
        List<int[]> merged = new ArrayList<>();
        for (int i = 0; i < arrays.size(); i += 2) {
            if (i + 1 < arrays.size()) merged.add(mergeTwo(arrays.get(i), arrays.get(i + 1)));
            else merged.add(arrays.get(i));
        }
        arrays = merged;
    }
    return arrays.get(0);
}
private int[] mergeTwo(int[] a, int[] b) {
    int[] result = new int[a.length + b.length];
    int i = 0, j = 0, k = 0;
    while (i < a.length && j < b.length) result[k++] = a[i] <= b[j] ? a[i++] : b[j++];
    while (i < a.length) result[k++] = a[i++];
    while (j < b.length) result[k++] = b[j++];
    return result;
}
```
**Complexity:** O(N log k) where N is total elements — same asymptotic complexity as the heap approach, but with better cache locality in practice. **Pattern:** divide-and-conquer pairwise merging — worth mentioning as an alternative to the heap-based merge-k approach, since interviewers sometimes explicitly ask for a second approach with different trade-offs.

### 14.4 Batch 3: Dynamic programming & greedy

#### G-26. Climbing Stairs

**Problem:** Count the number of distinct ways to climb `n` stairs, taking 1 or 2 steps at a time.

**Example:** `n=4` → `5` ways.

**Approach:** The count at step `n` is the sum of ways to reach step `n-1` plus ways to reach step `n-2` — identical recurrence to the Fibonacci sequence.

```java
int climbStairs(int n) {
    if (n <= 2) return n;
    int prev2 = 1, prev1 = 2;
    for (int i = 3; i <= n; i++) {
        int cur = prev1 + prev2;
        prev2 = prev1; prev1 = cur;
    }
    return prev1;
}
```
**Complexity:** O(n) time, O(1) space. **Pattern:** the simplest 1D DP recurrence (Fibonacci-shaped) — the canonical first DP problem most candidates learn, and a good sanity check for whether you can recognize a recurrence relation quickly.

#### G-27. House Robber

**Problem:** Given houses with money amounts, maximize total stolen money without robbing two adjacent houses.

**Example:** `[2,7,9,3,1]` → `12` (rob houses with 2, 9, 1).

**Approach:** `dp[i]` = max money robbable through house `i` = `max(dp[i-1], dp[i-2] + nums[i])` (either skip this house, or rob it and add to the best from two houses back).

```java
int rob(int[] nums) {
    int prev2 = 0, prev1 = 0;
    for (int num : nums) {
        int cur = Math.max(prev1, prev2 + num);
        prev2 = prev1; prev1 = cur;
    }
    return prev1;
}
```
**Complexity:** O(n) time, O(1) space. **Pattern:** "take or skip" 1D DP — one of the most foundational DP shapes, generalized in "House Robber II" (circular houses) and "House Robber III" (tree-structured houses).

#### G-28. Longest Increasing Subsequence

**Problem:** Find the length of the longest strictly increasing subsequence (not necessarily contiguous).

**Example:** `[10,9,2,5,3,7,101,18]` → `4` (the subsequence `[2,3,7,101]`).

**Approach (O(n log n)):** Maintain a "tails" array where `tails[i]` is the smallest possible tail value of an increasing subsequence of length `i+1`; binary search for where each new number fits, replacing or extending.

```java
int lengthOfLIS(int[] nums) {
    int[] tails = new int[nums.length];
    int size = 0;
    for (int num : nums) {
        int lo = 0, hi = size;
        while (lo < hi) {
            int mid = (lo + hi) / 2;
            if (tails[mid] < num) lo = mid + 1; else hi = mid;
        }
        tails[lo] = num;
        if (lo == size) size++;
    }
    return size;
}
```
**Complexity:** O(n log n) — a significant improvement over the O(n²) DP approach. **Pattern:** "patience sorting"-style binary search — a genuinely clever technique worth memorizing since the O(n²) DP version is far more commonly known but insufficient for larger constraints.

#### G-29. Word Break II (Return All Sentences)

**Problem:** Given a string and a dictionary, return all possible ways to segment the string into space-separated dictionary words.

**Example:** `s = "catsanddog", dict = ["cat","cats","and","sand","dog"]` → `["cats and dog", "cat sand dog"]`.

**Approach:** DFS with memoization — for each starting index, try every valid dictionary-word prefix, recursively solving the remainder, and cache results per starting index to avoid exponential re-computation on overlapping subproblems.

```java
Map<Integer, List<String>> memo = new HashMap<>();
List<String> wordBreak(String s, List<String> wordDict) {
    Set<String> dict = new HashSet<>(wordDict);
    return helper(s, 0, dict);
}
private List<String> helper(String s, int start, Set<String> dict) {
    if (memo.containsKey(start)) return memo.get(start);
    List<String> result = new ArrayList<>();
    if (start == s.length()) { result.add(""); return result; }
    for (int end = start + 1; end <= s.length(); end++) {
        String word = s.substring(start, end);
        if (dict.contains(word)) {
            for (String rest : helper(s, end, dict)) {
                result.add(word + (rest.isEmpty() ? "" : " " + rest));
            }
        }
    }
    memo.put(start, result);
    return result;
}
```
**Complexity:** O(n² ) subproblems, exponential output size in the worst case (unavoidable since the answer itself can be exponentially large). **Pattern:** DFS + memoization returning a LIST per subproblem (not just a boolean/count) — a step up from the boolean Word Break ([OA-9](#oa-9-word-break-feasibility)), testing whether candidates can adapt memoization to cache richer results.

#### G-30. Partition Equal Subset Sum

**Problem:** Determine if an array can be partitioned into two subsets with equal sum.

**Example:** `[1,5,11,5]` → `true` (partition into `[1,5,5]` and `[11]`, both summing to 11).

**Approach:** Equivalent to "subset sum equals `totalSum/2`" — a 0/1 knapsack-style DP over achievable sums, using a boolean array to avoid the classic knapsack's 2D table.

```java
boolean canPartition(int[] nums) {
    int sum = Arrays.stream(nums).sum();
    if (sum % 2 != 0) return false;
    int target = sum / 2;
    boolean[] dp = new boolean[target + 1];
    dp[0] = true;
    for (int num : nums) {
        for (int j = target; j >= num; j--) { // iterate backward to avoid reusing the same item twice
            dp[j] = dp[j] || dp[j - num];
        }
    }
    return dp[target];
}
```
**Complexity:** O(n × target). **Pattern:** 0/1 knapsack reduction — recognizing "partition into equal halves" as a disguised subset-sum/knapsack problem is the key insight; the backward iteration order is what makes it 0/1 (each item used at most once) rather than unbounded.

#### G-31. Maximum Product Subarray

**Problem:** Find the contiguous subarray with the largest product.

**Example:** `[2,3,-2,4]` → `6` (from `[2,3]`).

**Approach:** Track BOTH the running max and running min product ending at each position (since a negative number can flip a very negative running min into the new max).

```java
int maxProduct(int[] nums) {
    int maxSoFar = nums[0], curMax = nums[0], curMin = nums[0];
    for (int i = 1; i < nums.length; i++) {
        int num = nums[i];
        if (num < 0) { int temp = curMax; curMax = curMin; curMin = temp; }
        curMax = Math.max(num, curMax * num);
        curMin = Math.min(num, curMin * num);
        maxSoFar = Math.max(maxSoFar, curMax);
    }
    return maxSoFar;
}
```
**Complexity:** O(n) time, O(1) space. **Pattern:** "track both max AND min" — the distinctive trick needed whenever negative numbers can flip which running value becomes optimal; a very commonly-missed subtlety when candidates only track a running max.

#### G-32. Palindrome Partitioning (Minimum Cuts)

**Problem:** Find the minimum number of cuts needed to partition a string so every substring is a palindrome.

**Example:** `"aab"` → `1` (cut into `"aa"` and `"b"`).

**Approach:** Precompute a palindrome DP table ([OA-6](#oa-6-google-count-of-palindromic-substrings-by-length)'s style), then a second DP where `cuts[i]` = minimum cuts for `s[0..i)`, trying every valid palindromic suffix ending at `i`.

```java
int minCut(String s) {
    int n = s.length();
    boolean[][] isPal = new boolean[n][n];
    for (int len = 1; len <= n; len++) {
        for (int i = 0; i + len - 1 < n; i++) {
            int j = i + len - 1;
            if (s.charAt(i) == s.charAt(j) && (len <= 2 || isPal[i + 1][j - 1])) isPal[i][j] = true;
        }
    }
    int[] cuts = new int[n + 1];
    Arrays.fill(cuts, Integer.MAX_VALUE);
    cuts[0] = -1;
    for (int i = 1; i <= n; i++) {
        for (int j = 0; j < i; j++) {
            if (isPal[j][i - 1]) cuts[i] = Math.min(cuts[i], cuts[j] + 1);
        }
    }
    return cuts[n];
}
```
**Complexity:** O(n²). **Pattern:** two-stage DP (precompute a property table, then DP over partition points using that table) — a very common structure whenever a problem combines "is this substring valid?" with "find the optimal partition."

#### G-33. Gas Station

**Problem:** Given gas amounts and costs to travel between stations arranged in a circle, find the starting station index from which a complete circuit is possible (guaranteed unique if a solution exists), or -1.

**Approach:** Greedy single pass — if the total gas is less than total cost, no solution exists; otherwise, track a running tank total, and whenever it goes negative, the current starting candidate must be reset to the next station (everything before it is provably unreachable as a start).

```java
int canCompleteCircuit(int[] gas, int[] cost) {
    int totalTank = 0, curTank = 0, start = 0;
    for (int i = 0; i < gas.length; i++) {
        int diff = gas[i] - cost[i];
        totalTank += diff;
        curTank += diff;
        if (curTank < 0) { start = i + 1; curTank = 0; }
    }
    return totalTank >= 0 ? start : -1;
}
```
**Complexity:** O(n). **Pattern:** greedy with a "reset the candidate start whenever the running total goes negative" trick — a non-obvious but provably-correct greedy that avoids an O(n²) brute-force check of every starting point.

#### G-34. Candy Distribution

**Problem:** Children in a line have ratings; distribute the minimum candies such that each child gets at least 1, and any child with a higher rating than an adjacent neighbor gets more candy than that neighbor.

**Approach:** Two passes — left-to-right ensuring the "higher than left neighbor" rule, then right-to-left ensuring the "higher than right neighbor" rule, taking the max of both passes' requirements at each position.

```java
int candy(int[] ratings) {
    int n = ratings.length;
    int[] candies = new int[n];
    Arrays.fill(candies, 1);
    for (int i = 1; i < n; i++) {
        if (ratings[i] > ratings[i - 1]) candies[i] = candies[i - 1] + 1;
    }
    for (int i = n - 2; i >= 0; i--) {
        if (ratings[i] > ratings[i + 1]) candies[i] = Math.max(candies[i], candies[i + 1] + 1);
    }
    return Arrays.stream(candies).sum();
}
```
**Complexity:** O(n). **Pattern:** the "two-pass, take the max of both directions" technique — reused whenever a constraint depends on BOTH neighbors, since a single pass can only correctly enforce one direction at a time.

#### G-35. Jump Game II (Minimum Jumps)

**Problem:** Given an array where each element is the maximum jump length from that position, find the minimum number of jumps to reach the last index (guaranteed reachable).

**Approach:** Greedy BFS-like level tracking — maintain the current jump's reachable boundary and the farthest reachable boundary seen while scanning; increment the jump count whenever the current boundary is exhausted.

```java
int jump(int[] nums) {
    int jumps = 0, currentEnd = 0, farthest = 0;
    for (int i = 0; i < nums.length - 1; i++) {
        farthest = Math.max(farthest, i + nums[i]);
        if (i == currentEnd) { jumps++; currentEnd = farthest; }
    }
    return jumps;
}
```
**Complexity:** O(n). **Pattern:** greedy "level-by-level" reachability tracking without an explicit queue — conceptually a BFS collapsed into O(1) space using two boundary variables instead of a queue.

#### G-36. Perfect Squares

**Problem:** Find the minimum number of perfect square numbers (1, 4, 9, 16, ...) that sum to a given `n`.

**Example:** `n=12` → `3` (`4+4+4`). `n=13` → `2` (`4+9`).

**Approach:** DP — `dp[i]` = minimum squares summing to `i`, trying every perfect square `j*j <= i` as the last term.

```java
int numSquares(int n) {
    int[] dp = new int[n + 1];
    Arrays.fill(dp, Integer.MAX_VALUE);
    dp[0] = 0;
    for (int i = 1; i <= n; i++) {
        for (int j = 1; j * j <= i; j++) {
            dp[i] = Math.min(dp[i], dp[i - j * j] + 1);
        }
    }
    return dp[n];
}
```
**Complexity:** O(n √n). **Pattern:** unbounded-knapsack-style DP (same family as [E-16 Coin Change](#e-16-affirm-coin-change-minimum-coins)) where the "coin denominations" are precisely the perfect squares up to `n`.

#### G-37. Decode Ways

**Problem:** Given a string of digits (an encoding where `'A'=1, ..., 'Z'=26`), count the number of ways to decode it.

**Example:** `"226"` → `3` (`"2 2 6"`, `"22 6"`, `"2 26"`).

**Approach:** 1D DP — `dp[i]` = ways to decode the first `i` characters, considering both a single-digit decode (if the digit is 1-9) and a two-digit decode (if the two-digit number is 10-26).

```java
int numDecodings(String s) {
    int n = s.length();
    int[] dp = new int[n + 1];
    dp[0] = 1;
    dp[1] = s.charAt(0) != '0' ? 1 : 0;
    for (int i = 2; i <= n; i++) {
        int oneDigit = s.charAt(i - 1) - '0';
        int twoDigit = Integer.parseInt(s.substring(i - 2, i));
        if (oneDigit >= 1) dp[i] += dp[i - 1];
        if (twoDigit >= 10 && twoDigit <= 26) dp[i] += dp[i - 2];
    }
    return dp[n];
}
```
**Complexity:** O(n). **Pattern:** 1D DP with a "one-step or two-step" recurrence, gated by validity conditions (leading zero handling is the most common source of bugs) — structurally similar to Climbing Stairs but with conditional transitions instead of unconditional ones.

#### G-38. Non-overlapping Intervals (Minimum Removals)

**Problem:** Given intervals, find the minimum number to remove so the rest are non-overlapping.

**Approach:** Greedy — sort by END time, and greedily keep an interval only if its start is ≥ the previous kept interval's end (this is the classic "activity selection" greedy, provably optimal because always keeping the interval that ends earliest maximizes room for future intervals).

```java
int eraseOverlapIntervals(int[][] intervals) {
    if (intervals.length == 0) return 0;
    Arrays.sort(intervals, (a, b) -> a[1] - b[1]);
    int count = 0, lastEnd = intervals[0][1];
    for (int i = 1; i < intervals.length; i++) {
        if (intervals[i][0] < lastEnd) count++; // overlaps, must remove this one
        else lastEnd = intervals[i][1];
    }
    return count;
}
```
**Complexity:** O(n log n). **Pattern:** activity selection greedy (sort by END time, not start time) — a subtly different and less intuitive greedy than sorting by start time, worth memorizing which sort key is correct for which interval-scheduling variant.

#### G-39. Longest Palindromic Subsequence

**Problem:** Find the length of the longest subsequence (not necessarily contiguous) that is a palindrome.

**Example:** `"bbbab"` → `4` (`"bbbb"`).

**Approach:** 2D DP over `(i, j)` ranges — if the endpoints match, `dp[i][j] = dp[i+1][j-1] + 2`; otherwise take the best of excluding either endpoint.

```java
int longestPalindromeSubseq(String s) {
    int n = s.length();
    int[][] dp = new int[n][n];
    for (int i = n - 1; i >= 0; i--) {
        dp[i][i] = 1;
        for (int j = i + 1; j < n; j++) {
            if (s.charAt(i) == s.charAt(j)) dp[i][j] = dp[i + 1][j - 1] + 2;
            else dp[i][j] = Math.max(dp[i + 1][j], dp[i][j - 1]);
        }
    }
    return dp[0][n - 1];
}
```
**Complexity:** O(n²). **Pattern:** interval DP (processing `(i,j)` ranges from smallest to largest) — the same overall shape as Palindrome Partitioning's helper table, but optimizing subsequence length instead of validating full-substring palindromes.

#### G-40. Burst Balloons

**Problem:** Given balloons with values, bursting a balloon gives `nums[left] * nums[i] * nums[right]` coins (the immediate neighbors at burst time); find the maximum coins from bursting all balloons.

**Approach:** Interval DP thinking BACKWARDS — instead of "which balloon to burst first," think "which balloon to burst LAST within a range" (making it the final, and therefore easiest-to-reason-about, choice within that subrange, with `left-1` and `right+1` as its neighbors at that point).

```java
int maxCoins(int[] nums) {
    int n = nums.length;
    int[] balloons = new int[n + 2];
    balloons[0] = balloons[n + 1] = 1;
    for (int i = 0; i < n; i++) balloons[i + 1] = nums[i];
    int[][] dp = new int[n + 2][n + 2];
    for (int len = 1; len <= n; len++) {
        for (int left = 1; left + len - 1 <= n; left++) {
            int right = left + len - 1;
            for (int k = left; k <= right; k++) {
                int coins = balloons[left - 1] * balloons[k] * balloons[right + 1] + dp[left][k - 1] + dp[k + 1][right];
                dp[left][right] = Math.max(dp[left][right], coins);
            }
        }
    }
    return dp[1][n];
}
```
**Complexity:** O(n³). **Pattern:** interval DP with "choose the LAST action within a range" reframing — one of the most conceptually difficult DP reframings in common interview rotation; the key unlock is realizing that thinking about which balloon bursts last (not first) within a subrange makes the neighbors well-defined and unchanging.

### 14.5 Batch 4: Design & concurrency

#### G-41. Thread-Safe Bounded Blocking Queue

**Problem:** Implement a fixed-capacity blocking queue where `put()` blocks if full and `take()` blocks if empty.

**Approach:** A `synchronized` monitor using `wait()`/`notifyAll()` — the classic producer-consumer coordination primitive (Java also offers `BlockingQueue` built in, but implementing it manually is the actual interview ask).

```java
class BoundedBlockingQueue<T> {
    private final Queue<T> queue = new LinkedList<>();
    private final int capacity;
    BoundedBlockingQueue(int capacity) { this.capacity = capacity; }

    public synchronized void put(T item) throws InterruptedException {
        while (queue.size() == capacity) wait();
        queue.offer(item);
        notifyAll();
    }
    public synchronized T take() throws InterruptedException {
        while (queue.isEmpty()) wait();
        T item = queue.poll();
        notifyAll();
        return item;
    }
}
```
**Complexity:** O(1) per operation (excluding blocking wait time). **Pattern:** the `wait()`/`notifyAll()` monitor pattern — the foundational building block for producer-consumer coordination; using `notifyAll()` (not `notify()`) avoids a subtle bug where a woken thread finds the condition still false because a DIFFERENT waiting thread's condition was satisfied instead.

#### G-42. Read-Write Lock (Multiple Readers, Exclusive Writer)

**Problem:** Implement a lock allowing multiple concurrent readers OR one exclusive writer, never both simultaneously.

**Approach:** Track active reader count and a writer flag; readers increment/decrement a shared counter under a monitor; a writer waits until both the reader count is zero AND no other writer is active.

```java
class ReadWriteLock {
    private int activeReaders = 0;
    private boolean writerActive = false;

    public synchronized void acquireReadLock() throws InterruptedException {
        while (writerActive) wait();
        activeReaders++;
    }
    public synchronized void releaseReadLock() {
        activeReaders--;
        if (activeReaders == 0) notifyAll();
    }
    public synchronized void acquireWriteLock() throws InterruptedException {
        while (writerActive || activeReaders > 0) wait();
        writerActive = true;
    }
    public synchronized void releaseWriteLock() {
        writerActive = false;
        notifyAll();
    }
}
```
**Complexity:** O(1) per operation. **Pattern:** the reader-writer lock pattern — a step up from a plain mutex, testing whether candidates can reason about two DIFFERENT classes of waiters with different admission conditions sharing one monitor.

#### G-43. Thread Pool (Fixed-Size Worker Pool)

**Problem:** Implement a simple fixed-size thread pool that executes submitted tasks from a shared queue.

**Approach:** A shared `BlockingQueue<Runnable>` and N worker threads each looping `take()`-then-`run()` forever.

```java
class SimpleThreadPool {
    private final BlockingQueue<Runnable> taskQueue = new LinkedBlockingQueue<>();
    private final List<Thread> workers = new ArrayList<>();
    private volatile boolean shutdown = false;

    SimpleThreadPool(int numThreads) {
        for (int i = 0; i < numThreads; i++) {
            Thread worker = new Thread(() -> {
                while (!shutdown || !taskQueue.isEmpty()) {
                    try {
                        Runnable task = taskQueue.poll(100, TimeUnit.MILLISECONDS);
                        if (task != null) task.run();
                    } catch (InterruptedException e) { Thread.currentThread().interrupt(); }
                }
            });
            worker.start();
            workers.add(worker);
        }
    }
    public void submit(Runnable task) { taskQueue.offer(task); }
    public void shutdown() { shutdown = true; }
}
```
**Complexity:** O(1) per task submission. **Pattern:** the shared-queue worker-pool pattern underlying essentially every real thread pool implementation (including Java's own `ExecutorService`) — a very common "implement a simplified version of a standard library primitive" LLD/concurrency question.

#### G-44. Thread-Safe Singleton (Double-Checked Locking)

**Problem:** Implement a thread-safe lazily-initialized singleton without synchronizing every single `getInstance()` call (which would be unnecessarily slow after initialization).

**Approach:** Double-checked locking with a `volatile` field — check without a lock first (fast path after initialization), only synchronize if it might still need creating, then check again inside the lock (in case another thread initialized it between the two checks).

```java
class Singleton {
    private static volatile Singleton instance;
    private Singleton() {}
    public static Singleton getInstance() {
        if (instance == null) {
            synchronized (Singleton.class) {
                if (instance == null) {
                    instance = new Singleton();
                }
            }
        }
        return instance;
    }
}
```
**Complexity:** O(1) amortized (only the first call(s) pay the synchronization cost). **Pattern:** double-checked locking — `volatile` is NOT optional here (without it, another thread could observe a partially-constructed object due to instruction reordering); a very commonly-tested Java memory-model subtlety.

#### G-45. Producer-Consumer with Multiple Producers and Consumers

**Problem:** Extend the basic producer-consumer pattern to support multiple producer threads and multiple consumer threads safely sharing one bounded buffer.

**Approach:** The same `wait()`/`notifyAll()` bounded-queue pattern from [G-41](#g-41-thread-safe-bounded-blocking-queue) already generalizes correctly to multiple producers/consumers as long as `notifyAll()` (not `notify()`) is used — using `notify()` risks waking the wrong class of waiter (e.g., waking another producer when a consumer was needed), causing a subtle deadlock-like starvation bug.

```java
// Reuses BoundedBlockingQueue from G-41 unchanged -- multiple threads simply call
// put()/take() concurrently on the SAME shared instance; correctness follows directly
// from notifyAll() waking ALL waiters (some producers, some consumers) to re-check
// their condition, rather than notify() which might wake the wrong kind of waiter.
```
**Complexity:** O(1) per operation. **Pattern:** this entry is intentionally a "trick question" callback — the correct answer is often "I already handled this in my design," testing whether candidates understand WHY `notifyAll()` generalizes safely while `notify()` doesn't, rather than expecting genuinely new code.

#### G-46. Dining Philosophers (Deadlock Avoidance)

**Problem:** N philosophers sit at a round table, each needing both their left and right fork to eat; design a solution avoiding deadlock (the classic failure mode: every philosopher picks up their left fork simultaneously, then waits forever for their right fork).

**Approach:** Resource ordering — have every philosopher pick up the LOWER-NUMBERED fork first, regardless of which side it's on; this breaks the circular-wait condition that causes deadlock (the same "acquire locks in a consistent global order" principle as [D-5](#d-5-visa-simple-bank-account-system-lld)'s bank transfer).

```java
class Philosopher implements Runnable {
    private final Object leftFork, rightFork;
    private final int id;
    Philosopher(int id, Object leftFork, Object rightFork) { this.id = id; this.leftFork = leftFork; this.rightFork = rightFork; }
    public void run() {
        Object first = System.identityHashCode(leftFork) < System.identityHashCode(rightFork) ? leftFork : rightFork;
        Object second = first == leftFork ? rightFork : leftFork;
        synchronized (first) {
            synchronized (second) {
                eat();
            }
        }
    }
    private void eat() { /* eating logic */ }
}
```
**Complexity:** O(1) per meal attempt. **Pattern:** breaking circular wait via a consistent global lock-acquisition order — the canonical deadlock-avoidance technique, applicable to essentially any multi-resource-locking scenario, not just this specific classic puzzle.

#### G-47. Semaphore-Based Concurrent Rate Limiter

**Problem:** Limit at most `N` concurrent operations (not a time-window rate, a CONCURRENCY limit) using a semaphore.

**Approach:** A counting `Semaphore` initialized with `N` permits — acquire before the operation, release after, blocking callers when all permits are in use.

```java
class ConcurrencyLimiter {
    private final Semaphore semaphore;
    ConcurrencyLimiter(int maxConcurrent) { semaphore = new Semaphore(maxConcurrent); }
    public <T> T executeWithLimit(Callable<T> task) throws Exception {
        semaphore.acquire();
        try {
            return task.call();
        } finally {
            semaphore.release();
        }
    }
}
```
**Complexity:** O(1) per call (excluding blocking wait). **Pattern:** counting semaphores are the right tool specifically for "at most N concurrent" constraints, as distinct from the earlier "at most N per time window" rate limiters ([D-14](#d-14-twitterx-design-a-trending-topics-counter-sliding-window-top-k), [F-24 style](#f-20-duo-security--2fa-providers-time-based-one-time-password-totp-window-validation)) — a common point of confusion interviewers specifically probe by asking candidates to articulate the difference.

#### G-48. Cyclic Barrier (Wait for All Threads to Reach a Point)

**Problem:** Implement a barrier where N threads must all arrive before any of them proceeds past the barrier point (e.g., all workers must finish phase 1 before any starts phase 2).

**Approach:** A shared counter and a monitor — each arriving thread decrements the counter and waits; the last thread to arrive (counter reaches 0) wakes everyone via `notifyAll()`.

```java
class SimpleCyclicBarrier {
    private final int parties;
    private int count;
    SimpleCyclicBarrier(int parties) { this.parties = parties; this.count = parties; }
    public synchronized void await() throws InterruptedException {
        count--;
        if (count == 0) {
            count = parties; // reset for potential reuse
            notifyAll();
        } else {
            int generation = count; // simplistic generation guard (production code needs a more robust version)
            while (count != 0 && count < generation + 1) wait();
        }
    }
}
```
**Complexity:** O(1) per thread's `await()` call (excluding wait time). **Pattern:** the barrier synchronization pattern — commonly needed in parallel batch-processing pipelines where all workers must complete a phase before any proceeds; production code would use Java's built-in `CyclicBarrier` rather than a hand-rolled version, but implementing it manually tests genuine understanding of the coordination primitive.

#### G-49. Atomic Counter via Compare-And-Swap (Lock-Free)

**Problem:** Implement a thread-safe counter WITHOUT using `synchronized` or explicit locks, using only atomic compare-and-swap operations.

**Approach:** Java's `AtomicInteger` (backed by CAS instructions at the hardware level) — increment via a retry loop that keeps attempting the CAS until it succeeds (no thread ever blocks waiting for a lock).

```java
class LockFreeCounter {
    private final AtomicInteger count = new AtomicInteger(0);
    public void increment() {
        int current, next;
        do {
            current = count.get();
            next = current + 1;
        } while (!count.compareAndSet(current, next)); // retry if another thread updated first
    }
    public int get() { return count.get(); }
}
```
**Complexity:** O(1) amortized (lock-free, though individual CAS attempts can retry under high contention). **Pattern:** lock-free programming via compare-and-swap — understanding that `AtomicInteger.incrementAndGet()` already does exactly this internally is the "I could just use the built-in" answer, but being able to explain/implement the underlying CAS retry loop is what a deeper concurrency question is really testing.

#### G-50. Bounded Buffer Using Array (Circular Buffer)

**Problem:** Implement a fixed-size circular buffer supporting `enqueue`/`dequeue`, distinguishing "empty" from "full" without wasting an array slot as a sentinel.

**Approach:** Track a separate `size` counter (rather than trying to distinguish empty/full purely from head/tail pointer equality, which is ambiguous) alongside head and tail indices that wrap around using modulo arithmetic.

```java
class CircularBuffer<T> {
    private final Object[] buffer;
    private int head = 0, tail = 0, size = 0;
    CircularBuffer(int capacity) { buffer = new Object[capacity]; }
    public boolean enqueue(T item) {
        if (size == buffer.length) return false; // full
        buffer[tail] = item;
        tail = (tail + 1) % buffer.length;
        size++;
        return true;
    }
    @SuppressWarnings("unchecked")
    public T dequeue() {
        if (size == 0) return null; // empty
        T item = (T) buffer[head];
        head = (head + 1) % buffer.length;
        size--;
        return item;
    }
}
```
**Complexity:** O(1) per operation. **Pattern:** the explicit `size` counter is the cleanest fix for the classic "how do you tell empty from full when head==tail" circular-buffer ambiguity — an alternative is reserving one slot as always-empty, but the counter approach is simpler to reason about and more commonly preferred in interviews.

> **Part 14 summary:** this final practice bank adds 50 more problems (G-1 through G-50) spanning arrays/strings/hashing, trees/graphs/heaps, dynamic programming/greedy, and design/concurrency — rounding out this guide's total previously-reported question coverage to well over 140 problems with full worked Java solutions across Parts 2, 5, 9, 10, and 14 combined.

## Part 15 — Final Practice Set (More Previously-Asked Questions)

### 15.1 Graphs, strings & math

#### H-1. Number of Connected Components in an Undirected Graph

**Problem:** Given `n` nodes and a list of edges, count the number of connected components.

**Approach:** Union-Find — union every edge's endpoints, then count distinct roots (identical skeleton to [E-1](#e-1-doordash-number-of-provinces-union-find--dsu), applied to an edge list instead of an adjacency matrix).

```java
int countComponents(int n, int[][] edges) {
    int[] parent = new int[n];
    for (int i = 0; i < n; i++) parent[i] = i;
    for (int[] e : edges) union(parent, e[0], e[1]);
    Set<Integer> roots = new HashSet<>();
    for (int i = 0; i < n; i++) roots.add(find(parent, i));
    return roots.size();
}
private int find(int[] parent, int x) { if (parent[x] != x) parent[x] = find(parent, parent[x]); return parent[x]; }
private void union(int[] parent, int a, int b) { parent[find(parent, a)] = find(parent, b); }
```
**Complexity:** O((n + E) α(n)). **Pattern:** Union-Find on an edge list — recognizing that "connected components" and "provinces" are the same underlying problem with a different input format is a valuable pattern-transfer skill.

#### H-2. Graph Valid Tree

**Problem:** Given `n` nodes and edges, determine if they form a valid tree (connected, and exactly `n-1` edges with no cycle).

**Approach:** A graph with `n` nodes is a valid tree if and only if it has exactly `n-1` edges AND is fully connected (checkable via Union-Find — if any edge connects two nodes already in the same set, there's a cycle).

```java
boolean validTree(int n, int[][] edges) {
    if (edges.length != n - 1) return false;
    int[] parent = new int[n];
    for (int i = 0; i < n; i++) parent[i] = i;
    for (int[] e : edges) {
        int ra = find(parent, e[0]), rb = find(parent, e[1]);
        if (ra == rb) return false; // cycle detected
        parent[ra] = rb;
    }
    return true;
}
private int find(int[] parent, int x) { if (parent[x] != x) parent[x] = find(parent, parent[x]); return parent[x]; }
```
**Complexity:** O(n α(n)). **Pattern:** the "edge count == n-1 AND no cycle" characterization of a tree — a clean necessary-and-sufficient condition worth memorizing rather than re-deriving under pressure.

#### H-3. Longest Substring with At Most K Distinct Characters

**Problem:** Find the length of the longest substring containing at most `k` distinct characters.

**Approach:** Variable sliding window with a frequency map, shrinking from the left whenever the distinct-character count exceeds `k`.

```java
int lengthOfLongestSubstringKDistinct(String s, int k) {
    Map<Character, Integer> freq = new HashMap<>();
    int left = 0, best = 0;
    for (int right = 0; right < s.length(); right++) {
        freq.merge(s.charAt(right), 1, Integer::sum);
        while (freq.size() > k) {
            char leftChar = s.charAt(left);
            if (freq.merge(leftChar, -1, Integer::sum) == 0) freq.remove(leftChar);
            left++;
        }
        best = Math.max(best, right - left + 1);
    }
    return best;
}
```
**Complexity:** O(n). **Pattern:** variable sliding window with a "distinct count" constraint — a close cousin of "longest substring without repeating characters" (the `k=distinct count` special case), showing how generalizing a constraint slightly changes the shrink condition.

#### H-4. Basic Calculator (Expression Evaluation with Parentheses)

**Problem:** Evaluate a mathematical expression string containing `+`, `-`, and parentheses (no multiplication/division for this simplified version).

**Approach:** A single pass with a running result, a running sign, and a stack to save/restore state when entering/exiting parentheses.

```java
int calculate(String s) {
    Deque<Integer> stack = new ArrayDeque<>();
    int result = 0, sign = 1, num = 0;
    for (char c : s.toCharArray()) {
        if (Character.isDigit(c)) { num = num * 10 + (c - '0'); }
        else if (c == '+') { result += sign * num; num = 0; sign = 1; }
        else if (c == '-') { result += sign * num; num = 0; sign = -1; }
        else if (c == '(') { stack.push(result); stack.push(sign); result = 0; sign = 1; }
        else if (c == ')') { result += sign * num; num = 0; result *= stack.pop(); result += stack.pop(); }
    }
    return result + sign * num;
}
```
**Complexity:** O(n). **Pattern:** stack-based expression evaluation — a foundational parsing technique; the "push result and sign before entering parens, restore and combine after" trick generalizes to full calculators with multiplication/division/operator-precedence via a more elaborate two-stack (values + operators) version.

#### H-5. Integer to English Words

**Problem:** Convert a non-negative integer to its English words representation (e.g., `123` → `"One Hundred Twenty Three"`).

**Approach:** Break the number into 3-digit groups (ones, thousands, millions, billions), converting each group with a helper and appending the appropriate scale word.

```java
private final String[] belowTwenty = {"","One","Two","Three","Four","Five","Six","Seven","Eight","Nine","Ten",
    "Eleven","Twelve","Thirteen","Fourteen","Fifteen","Sixteen","Seventeen","Eighteen","Nineteen"};
private final String[] tens = {"","","Twenty","Thirty","Forty","Fifty","Sixty","Seventy","Eighty","Ninety"};
private final String[] thousands = {"","Thousand","Million","Billion"};

String numberToWords(int num) {
    if (num == 0) return "Zero";
    StringBuilder result = new StringBuilder();
    int group = 0;
    while (num > 0) {
        if (num % 1000 != 0) {
            String groupWords = helper(num % 1000) + (thousands[group].isEmpty() ? "" : " " + thousands[group]) + " ";
            result.insert(0, groupWords);
        }
        num /= 1000; group++;
    }
    return result.toString().trim();
}
private String helper(int num) {
    if (num == 0) return "";
    if (num < 20) return belowTwenty[num] + " ";
    if (num < 100) return tens[num / 10] + " " + helper(num % 10);
    return belowTwenty[num / 100] + " Hundred " + helper(num % 100);
}
```
**Complexity:** O(digits). **Pattern:** recursive/group-based string construction — a "tedious but must be flawless" question testing careful handling of many edge cases (zero, teens, exact hundreds/thousands) rather than algorithmic depth.

#### H-6. Detect Squares (Design a Data Structure)

**Problem:** Design a class supporting `add(point)` and `count(point)` returning the number of axis-aligned squares that can be formed using the given point as one corner and previously-added points as the other three corners.

**Approach:** A frequency map of points; for a query point, try every previously-seen point sharing the same x-coordinate as one potential diagonal-adjacent corner, compute the required other two corners, and check their frequencies.

```java
class DetectSquares {
    private final Map<Long, Integer> pointCounts = new HashMap<>();
    private long encode(int x, int y) { return ((long) x << 20) | y; }

    public void add(int[] point) { pointCounts.merge(encode(point[0], point[1]), 1, Integer::sum); }
    public int count(int[] point) {
        int px = point[0], py = point[1], total = 0;
        for (long key : pointCounts.keySet()) {
            int x = (int) (key >> 20), y = (int) (key & 0xFFFFF);
            if (x == px || Math.abs(y - py) != Math.abs(x - px) || y == py) continue;
            total += pointCounts.get(key) * pointCounts.getOrDefault(encode(px, y), 0) * pointCounts.getOrDefault(encode(x, py), 0);
        }
        return total;
    }
}
```
**Complexity:** O(distinct points) per count call. **Pattern:** encoding a 2D coordinate into a single hashable key (bit-packing) plus geometric reasoning about square corners — a good test of both data-structure design and 2D geometry reasoning combined.

#### H-7. Course Schedule III (Maximize Courses Taken by Deadline)

**Problem:** Given courses each with a duration and a deadline, find the maximum number of courses that can be taken (in some order) without missing any taken course's deadline.

**Approach:** Greedy + max-heap — sort courses by deadline; greedily take each course if time permits; if a later course doesn't fit but has a SHORTER duration than the longest course taken so far, swap it in (using a max-heap of taken courses' durations) to free up time while keeping the count the same.

```java
int scheduleCourse(int[][] courses) {
    Arrays.sort(courses, (a, b) -> a[1] - b[1]); // sort by deadline
    PriorityQueue<Integer> maxHeap = new PriorityQueue<>(Collections.reverseOrder());
    int time = 0;
    for (int[] course : courses) {
        int duration = course[0], deadline = course[1];
        time += duration;
        maxHeap.offer(duration);
        if (time > deadline) { time -= maxHeap.poll(); } // drop the longest course taken so far
    }
    return maxHeap.size();
}
```
**Complexity:** O(n log n). **Pattern:** greedy + "swap out the worst choice so far when infeasible" via a max-heap — a more advanced greedy pattern than simple sorting alone, since it allows RECONSIDERING earlier choices as new information (later deadlines) arrives.

### 15.2 Heaps, design & advanced patterns

#### H-8. Sliding Window Maximum via Heap (Alternative to Monotonic Deque)

**Problem:** Same problem as [Microsoft's Sliding Window Maximum](#103-microsoft), shown here with the heap-based alternative approach (useful when interviewers ask "can you solve it a different way?").

**Approach:** A max-heap of `(value, index)` pairs; lazily discard entries whose index has fallen outside the current window when they reach the top, rather than proactively removing them (heaps don't support efficient arbitrary removal).

```java
int[] maxSlidingWindowHeap(int[] nums, int k) {
    PriorityQueue<int[]> maxHeap = new PriorityQueue<>((a, b) -> b[0] - a[0]);
    int[] result = new int[nums.length - k + 1];
    for (int i = 0; i < nums.length; i++) {
        maxHeap.offer(new int[]{nums[i], i});
        while (maxHeap.peek()[1] <= i - k) maxHeap.poll(); // lazy removal of out-of-window entries
        if (i >= k - 1) result[i - k + 1] = maxHeap.peek()[0];
    }
    return result;
}
```
**Complexity:** O(n log n) — worse than the monotonic deque's O(n), a good talking point about complexity trade-offs between two valid approaches. **Pattern:** lazy deletion in a heap — the same technique as [F-14](#f-14-zendesk-sla-deadline-tracker-min-heap-of-deadlines)'s SLA tracker, reused here to handle a heap's lack of efficient arbitrary-element removal.

#### H-9. Design a Snake Game

**Problem:** Design the backend logic for a Snake game — the snake moves on a grid, grows when eating food, and the game ends on a wall or self collision.

**Approach:** A `Deque<int[]>` representing the snake's body (head at front); each move adds a new head and removes the tail (unless food was eaten, in which case the tail stays, growing the snake); a `HashSet` mirrors the deque's contents for O(1) self-collision checks.

```java
class SnakeGame {
    private final Deque<int[]> body = new ArrayDeque<>();
    private final Set<Long> bodySet = new HashSet<>();
    private final int[][] food; private int foodIndex = 0;
    private final int width, height;
    private int score = 0;

    SnakeGame(int width, int height, int[][] food) {
        this.width = width; this.height = height; this.food = food;
        body.offerFirst(new int[]{0, 0});
        bodySet.add(encode(0, 0));
    }
    public int move(String direction) {
        int[] head = body.peekFirst();
        int newRow = head[0] + (direction.equals("Down") ? 1 : direction.equals("Up") ? -1 : 0);
        int newCol = head[1] + (direction.equals("Right") ? 1 : direction.equals("Left") ? -1 : 0);
        if (newRow < 0 || newRow >= height || newCol < 0 || newCol >= width) return -1;
        boolean ateFood = foodIndex < food.length && food[foodIndex][0] == newRow && food[foodIndex][1] == newCol;
        if (!ateFood) {
            int[] tail = body.pollLast();
            bodySet.remove(encode(tail[0], tail[1]));
        }
        if (bodySet.contains(encode(newRow, newCol))) return -1; // self collision
        body.offerFirst(new int[]{newRow, newCol});
        bodySet.add(encode(newRow, newCol));
        if (ateFood) { foodIndex++; score++; }
        return score;
    }
    private long encode(int r, int c) { return (long) r * width + c; }
}
```
**Complexity:** O(1) per move. **Pattern:** deque + mirrored hashset — the deque maintains ORDER (for removing the correct tail), while the hashset provides O(1) membership checks; a good example of combining two data structures because neither alone provides both needed operations efficiently.

#### H-10. LFU Cache Alternative: Design a Least-Recently-Set TTL Cache

**Problem:** Design a cache where each entry has an explicit TTL set at insertion; `get` returns null for expired entries; expired entries should also be cleaned up periodically (not just lazily on read).

**Approach:** Combine a hashmap of entries with expiry timestamps and a min-heap of `(expiry, key)` for efficient "find the next entry to expire" — a background sweep pops from the heap while the top entry's expiry has passed.

```java
class TTLCache<K, V> {
    class Entry { V value; long expiresAt; }
    private final Map<K, Entry> store = new HashMap<>();
    private final PriorityQueue<Map.Entry<Long, K>> expiryHeap = new PriorityQueue<>(Map.Entry.comparingByKey());

    public void put(K key, V value, long ttlMillis, long nowMillis) {
        Entry entry = new Entry();
        entry.value = value;
        entry.expiresAt = nowMillis + ttlMillis;
        store.put(key, entry);
        expiryHeap.offer(Map.entry(entry.expiresAt, key));
    }
    public V get(K key, long nowMillis) {
        Entry entry = store.get(key);
        if (entry == null || entry.expiresAt <= nowMillis) return null;
        return entry.value;
    }
    public void sweepExpired(long nowMillis) {
        while (!expiryHeap.isEmpty() && expiryHeap.peek().getKey() <= nowMillis) {
            K key = expiryHeap.poll().getValue();
            Entry entry = store.get(key);
            if (entry != null && entry.expiresAt <= nowMillis) store.remove(key); // guard against stale heap entries from overwritten keys
        }
    }
}
```
**Complexity:** O(log n) per put (heap insert), O(1) per get, amortized O(log n) per sweep entry. **Pattern:** hashmap + min-heap-of-expiries combo for proactive TTL cleanup — a genuine improvement over purely lazy expiry ([7.4](#74-case-study-lld-for-an-in-memory-key-value-store)'s note about lingering expired keys), directly addressing that earlier case study's stated limitation.

#### H-11. Random Maze Generator / Solver Validation

**Problem:** Given a maze (grid with walls), determine if a path exists from start to end, and if so, return one such path.

**Approach:** BFS (guarantees shortest path) with parent-pointer tracking to reconstruct the path once the end is reached.

```java
List<int[]> findPath(int[][] maze, int[] start, int[] end) {
    int rows = maze.length, cols = maze[0].length;
    int[][] parentR = new int[rows][cols], parentC = new int[rows][cols];
    boolean[][] visited = new boolean[rows][cols];
    Queue<int[]> queue = new LinkedList<>();
    queue.offer(start); visited[start[0]][start[1]] = true;
    int[][] dirs = {{0,1},{0,-1},{1,0},{-1,0}};
    boolean found = false;
    while (!queue.isEmpty() && !found) {
        int[] cur = queue.poll();
        if (cur[0] == end[0] && cur[1] == end[1]) { found = true; break; }
        for (int[] d : dirs) {
            int nr = cur[0] + d[0], nc = cur[1] + d[1];
            if (nr >= 0 && nc >= 0 && nr < rows && nc < cols && !visited[nr][nc] && maze[nr][nc] == 0) {
                visited[nr][nc] = true;
                parentR[nr][nc] = cur[0]; parentC[nr][nc] = cur[1];
                queue.offer(new int[]{nr, nc});
            }
        }
    }
    if (!visited[end[0]][end[1]]) return Collections.emptyList();
    List<int[]> path = new ArrayList<>();
    int r = end[0], c = end[1];
    while (!(r == start[0] && c == start[1])) {
        path.add(new int[]{r, c});
        int pr = parentR[r][c], pc = parentC[r][c];
        r = pr; c = pc;
    }
    path.add(start);
    Collections.reverse(path);
    return path;
}
```
**Complexity:** O(rows × cols). **Pattern:** BFS with explicit parent-pointer tracking for path reconstruction — a very common extension whenever a problem asks for the ACTUAL path, not just its existence or length.

#### H-12. Design a Leaderboard

**Problem:** Design a class supporting `addScore(playerId, score)` (adds to a player's existing score), `top(k)` (sum of the top-k scores), and `reset(playerId)`.

**Approach:** A hashmap of current scores; for `top(k)`, use a min-heap of size `k` over the current scores (recomputed per call, or maintained incrementally for very frequent queries) — the simplest correct approach given scores change frequently between queries.

```java
class Leaderboard {
    private final Map<Integer, Integer> scores = new HashMap<>();
    public void addScore(int playerId, int score) { scores.merge(playerId, score, Integer::sum); }
    public void reset(int playerId) { scores.remove(playerId); }
    public int top(int k) {
        PriorityQueue<Integer> minHeap = new PriorityQueue<>();
        for (int score : scores.values()) {
            minHeap.offer(score);
            if (minHeap.size() > k) minHeap.poll();
        }
        int sum = 0;
        for (int s : minHeap) sum += s;
        return sum;
    }
}
```
**Complexity:** O(n log k) per `top(k)` call, O(1) for `addScore`/`reset`. **Pattern:** bounded heap recomputed per query — a pragmatic choice given scores mutate frequently between reads; for a read-heavy leaderboard with rare writes, a sorted structure (e.g., a `TreeMap` of score→count) maintained incrementally would trade faster reads for slower writes instead.

#### H-13. Minimum Window Substring

**Problem:** Given strings `s` and `t`, find the smallest substring of `s` containing all characters of `t` (including duplicates).

**Approach:** Variable sliding window with two frequency maps — expand right until the window satisfies all of `t`'s character requirements, then shrink left as much as possible while still satisfying them, tracking the smallest valid window seen.

```java
String minWindow(String s, String t) {
    Map<Character, Integer> need = new HashMap<>();
    for (char c : t.toCharArray()) need.merge(c, 1, Integer::sum);
    Map<Character, Integer> window = new HashMap<>();
    int left = 0, required = need.size(), formed = 0;
    int bestLen = Integer.MAX_VALUE, bestStart = 0;
    for (int right = 0; right < s.length(); right++) {
        char c = s.charAt(right);
        window.merge(c, 1, Integer::sum);
        if (need.containsKey(c) && window.get(c).intValue() == need.get(c).intValue()) formed++;
        while (formed == required) {
            if (right - left + 1 < bestLen) { bestLen = right - left + 1; bestStart = left; }
            char leftChar = s.charAt(left);
            window.merge(leftChar, -1, Integer::sum);
            if (need.containsKey(leftChar) && window.get(leftChar) < need.get(leftChar)) formed--;
            left++;
        }
    }
    return bestLen == Integer.MAX_VALUE ? "" : s.substring(bestStart, bestStart + bestLen);
}
```
**Complexity:** O(|s| + |t|). **Pattern:** variable sliding window with a "satisfied requirement count" tracker (`formed == required`) — a more sophisticated version of the basic sliding window, and one of the most frequently-reported "hard" interview questions across nearly every company in this guide.

#### H-14. N-Queens

**Problem:** Place `n` queens on an `n×n` board so none attack each other; return all valid configurations.

**Approach:** Backtracking, placing one queen per row, tracking occupied columns and both diagonals (using sets keyed by `col`, `row-col`, and `row+col`) for O(1) conflict checks.

```java
List<List<String>> solveNQueens(int n) {
    List<List<String>> results = new ArrayList<>();
    int[] queenCols = new int[n];
    Set<Integer> cols = new HashSet<>(), diag1 = new HashSet<>(), diag2 = new HashSet<>();
    backtrack(0, n, queenCols, cols, diag1, diag2, results);
    return results;
}
private void backtrack(int row, int n, int[] queenCols, Set<Integer> cols, Set<Integer> diag1, Set<Integer> diag2, List<List<String>> results) {
    if (row == n) { results.add(buildBoard(queenCols, n)); return; }
    for (int col = 0; col < n; col++) {
        if (cols.contains(col) || diag1.contains(row - col) || diag2.contains(row + col)) continue;
        queenCols[row] = col;
        cols.add(col); diag1.add(row - col); diag2.add(row + col);
        backtrack(row + 1, n, queenCols, cols, diag1, diag2, results);
        cols.remove(col); diag1.remove(row - col); diag2.remove(row + col);
    }
}
private List<String> buildBoard(int[] queenCols, int n) {
    List<String> board = new ArrayList<>();
    for (int col : queenCols) {
        char[] row = new char[n];
        Arrays.fill(row, '.');
        row[col] = 'Q';
        board.add(new String(row));
    }
    return board;
}
```
**Complexity:** O(n!) worst case (heavily pruned in practice). **Pattern:** backtracking with O(1) conflict checks via auxiliary sets tracking columns and both diagonal directions — the diagonal-tracking trick (`row-col` is constant along one diagonal, `row+col` along the other) is the key non-obvious insight.

#### H-15. Restore IP Addresses

**Problem:** Given a string of digits, return all possible valid IP address groupings (4 segments, each 0-255, no leading zeros except "0" itself).

**Approach:** Backtracking trying every valid segment length (1-3 digits) at each step, validating the segment's numeric range and leading-zero rule before recursing.

```java
List<String> restoreIpAddresses(String s) {
    List<String> results = new ArrayList<>();
    backtrack(s, 0, new ArrayList<>(), results);
    return results;
}
private void backtrack(String s, int start, List<String> segments, List<String> results) {
    if (segments.size() == 4) {
        if (start == s.length()) results.add(String.join(".", segments));
        return;
    }
    for (int len = 1; len <= 3 && start + len <= s.length(); len++) {
        String segment = s.substring(start, start + len);
        if (len > 1 && segment.charAt(0) == '0') break; // leading zero, only "0" itself is valid
        if (Integer.parseInt(segment) > 255) break;
        segments.add(segment);
        backtrack(s, start + len, segments, results);
        segments.remove(segments.size() - 1);
    }
}
```
**Complexity:** O(1) effectively (bounded by the fixed 4-segment, max-3-digit structure — at most a few dozen candidates ever explored). **Pattern:** backtracking with domain-specific validity pruning (leading zero, numeric range) — a great example of backtracking scoped so tightly by constraints that it's effectively constant time despite being "exponential" in shape.

#### H-16. Path Sum II (All Root-to-Leaf Paths Summing to Target)

**Problem:** Given a binary tree and a target sum, return all root-to-leaf paths whose values sum to the target.

**Approach:** DFS with backtracking, maintaining a running path list and running sum, adding a copy of the path to results when a matching leaf is reached.

```java
List<List<Integer>> pathSum(TreeNode root, int targetSum) {
    List<List<Integer>> results = new ArrayList<>();
    dfs(root, targetSum, new ArrayList<>(), results);
    return results;
}
private void dfs(TreeNode node, long remaining, List<Integer> path, List<List<Integer>> results) {
    if (node == null) return;
    path.add(node.val);
    if (node.left == null && node.right == null && remaining == node.val) {
        results.add(new ArrayList<>(path));
    } else {
        dfs(node.left, remaining - node.val, path, results);
        dfs(node.right, remaining - node.val, path, results);
    }
    path.remove(path.size() - 1); // backtrack
}
```
**Complexity:** O(n²) worst case (due to copying paths at each leaf; O(n) tree traversal itself). **Pattern:** DFS + explicit backtrack (add before recursing, remove after) — the standard template for any "collect all paths satisfying a condition" tree problem.

#### H-17. Flatten Binary Tree to Linked List

**Problem:** Flatten a binary tree into a "linked list" in-place, following preorder traversal order, using only the `right` pointers (like a singly linked list threaded through the tree nodes).

**Approach:** Process nodes in REVERSE preorder (right subtree, then left subtree, then current node) using recursion, threading each node's `right` pointer to the previously-processed node.

```java
private TreeNode prev = null;
void flatten(TreeNode root) {
    if (root == null) return;
    flatten(root.right);
    flatten(root.left);
    root.right = prev;
    root.left = null;
    prev = root;
}
```
**Complexity:** O(n) time, O(h) recursion stack space. **Pattern:** reverse-order traversal with a "previous processed node" pointer — a compact, elegant O(1)-extra-space solution; the naive approach (collect preorder into a list, then rebuild) works but uses O(n) extra space, a good complexity trade-off talking point.

#### H-18. Construct Binary Tree from Preorder and Inorder Traversal

**Problem:** Given preorder and inorder traversal arrays, reconstruct the binary tree.

**Approach:** The first element of preorder is always the root; find that value's position in inorder to split it into left/right subtree inorder sequences, then recurse (using a hashmap for O(1) inorder-index lookups instead of a linear scan).

```java
private Map<Integer, Integer> inorderIndex = new HashMap<>();
private int preorderIdx = 0;
TreeNode buildTree(int[] preorder, int[] inorder) {
    for (int i = 0; i < inorder.length; i++) inorderIndex.put(inorder[i], i);
    return build(preorder, 0, inorder.length - 1);
}
private TreeNode build(int[] preorder, int inStart, int inEnd) {
    if (inStart > inEnd) return null;
    int rootVal = preorder[preorderIdx++];
    TreeNode root = new TreeNode(rootVal);
    int mid = inorderIndex.get(rootVal);
    root.left = build(preorder, inStart, mid - 1);
    root.right = build(preorder, mid + 1, inEnd);
    return root;
}
```
**Complexity:** O(n) with the hashmap optimization (O(n²) with a linear inorder search instead). **Pattern:** recursive tree reconstruction from two traversal orders — a very frequently-reported "must know cold" tree question; the hashmap-for-O(1)-lookup optimization is the expected follow-up if a naive version is given first.

#### H-19. Binary Tree Zigzag Level Order Traversal

**Problem:** Return level-order traversal, alternating left-to-right and right-to-left on successive levels.

**Approach:** Standard BFS level-order traversal, reversing the order of values collected on every other level.

```java
List<List<Integer>> zigzagLevelOrder(TreeNode root) {
    List<List<Integer>> result = new ArrayList<>();
    if (root == null) return result;
    Queue<TreeNode> queue = new LinkedList<>();
    queue.offer(root);
    boolean leftToRight = true;
    while (!queue.isEmpty()) {
        int size = queue.size();
        LinkedList<Integer> level = new LinkedList<>();
        for (int i = 0; i < size; i++) {
            TreeNode node = queue.poll();
            if (leftToRight) level.addLast(node.val); else level.addFirst(node.val);
            if (node.left != null) queue.offer(node.left);
            if (node.right != null) queue.offer(node.right);
        }
        result.add(level);
        leftToRight = !leftToRight;
    }
    return result;
}
```
**Complexity:** O(n). **Pattern:** BFS level-order with a `LinkedList`'s O(1) `addFirst`/`addLast` used to build each level in either direction without a separate reversal pass — a small but elegant efficiency detail.

#### H-20. Symmetric Tree

**Problem:** Determine if a binary tree is a mirror of itself.

**Approach:** Recursively compare a left subtree against a right subtree, checking that their values match and that the left's left mirrors the right's right (and vice versa).

```java
boolean isSymmetric(TreeNode root) {
    return root == null || isMirror(root.left, root.right);
}
private boolean isMirror(TreeNode a, TreeNode b) {
    if (a == null || b == null) return a == b;
    return a.val == b.val && isMirror(a.left, b.right) && isMirror(a.right, b.left);
}
```
**Complexity:** O(n). **Pattern:** paired recursive comparison ("outer-outer, inner-inner") — the same template used for validating palindromic tree structures generally.

#### H-21. Convert Sorted Array to Balanced BST

**Problem:** Given a sorted array, build a height-balanced BST.

**Approach:** Recursively pick the middle element as the root (ensuring balance), recursing on the left and right halves.

```java
TreeNode sortedArrayToBST(int[] nums) { return build(nums, 0, nums.length - 1); }
private TreeNode build(int[] nums, int lo, int hi) {
    if (lo > hi) return null;
    int mid = lo + (hi - lo) / 2;
    TreeNode node = new TreeNode(nums[mid]);
    node.left = build(nums, lo, mid - 1);
    node.right = build(nums, mid + 1, hi);
    return node;
}
```
**Complexity:** O(n). **Pattern:** "pick the middle to guarantee balance" — the same idea underlying balanced BST construction and the basis for understanding why a sorted array can always be turned into an O(log n)-height tree.

#### H-22. Permutations II (With Duplicates)

**Problem:** Given an array possibly containing duplicates, return all unique permutations.

**Approach:** Backtracking with the array SORTED first, skipping a duplicate value at the same recursion depth unless the previous identical value has already been used (the standard "used[i-1] must be true to allow using nums[i]" duplicate-skip rule).

```java
List<List<Integer>> permuteUnique(int[] nums) {
    Arrays.sort(nums);
    List<List<Integer>> results = new ArrayList<>();
    backtrack(nums, new boolean[nums.length], new ArrayList<>(), results);
    return results;
}
private void backtrack(int[] nums, boolean[] used, List<Integer> current, List<List<Integer>> results) {
    if (current.size() == nums.length) { results.add(new ArrayList<>(current)); return; }
    for (int i = 0; i < nums.length; i++) {
        if (used[i]) continue;
        if (i > 0 && nums[i] == nums[i - 1] && !used[i - 1]) continue; // skip duplicate at this depth
        used[i] = true; current.add(nums[i]);
        backtrack(nums, used, current, results);
        used[i] = false; current.remove(current.size() - 1);
    }
}
```
**Complexity:** O(n × n!). **Pattern:** the "sort first, skip duplicate if the previous identical value is currently UNUSED" rule — this exact duplicate-skipping template also applies to Subsets II ([H-23](#h-23-subsets-ii-with-duplicates)) and Combination Sum II.

#### H-23. Subsets II (With Duplicates)

**Problem:** Given an array possibly containing duplicates, return all unique subsets.

**Approach:** Sort first, then backtrack skipping a duplicate value at the same recursion depth (not across different depths) to avoid generating the same subset twice.

```java
List<List<Integer>> subsetsWithDup(int[] nums) {
    Arrays.sort(nums);
    List<List<Integer>> results = new ArrayList<>();
    backtrack(nums, 0, new ArrayList<>(), results);
    return results;
}
private void backtrack(int[] nums, int start, List<Integer> current, List<List<Integer>> results) {
    results.add(new ArrayList<>(current));
    for (int i = start; i < nums.length; i++) {
        if (i > start && nums[i] == nums[i - 1]) continue; // skip duplicate at this depth
        current.add(nums[i]);
        backtrack(nums, i + 1, current, results);
        current.remove(current.size() - 1);
    }
}
```
**Complexity:** O(n × 2^n). **Pattern:** the `i > start` duplicate-skip condition (rather than `i > 0`) is what distinguishes "skip duplicates within this recursion level" from "skip duplicates globally" — a subtle but critical distinction from Permutations II's `used[i-1]` check.

#### H-24. Letter Combinations of a Phone Number

**Problem:** Given digits 2-9, return all possible letter combinations the digits could represent (like old phone keypads).

**Approach:** Backtracking, building up a combination one digit at a time using a digit-to-letters lookup table.

```java
private final String[] digitLetters = {"","","abc","def","ghi","jkl","mno","pqrs","tuv","wxyz"};
List<String> letterCombinations(String digits) {
    List<String> results = new ArrayList<>();
    if (digits.isEmpty()) return results;
    backtrack(digits, 0, new StringBuilder(), results);
    return results;
}
private void backtrack(String digits, int index, StringBuilder current, List<String> results) {
    if (index == digits.length()) { results.add(current.toString()); return; }
    String letters = digitLetters[digits.charAt(index) - '0'];
    for (char c : letters.toCharArray()) {
        current.append(c);
        backtrack(digits, index + 1, current, results);
        current.deleteCharAt(current.length() - 1);
    }
}
```
**Complexity:** O(4^n) worst case (digits mapping to 4 letters, e.g., '7' and '9'). **Pattern:** simple backtracking over a fixed lookup table — a fast, low-risk warm-up backtracking question frequently used as the FIRST problem in a two-problem phone screen.

#### H-25. Word Search

**Problem:** Given a grid of letters and a word, determine if the word can be constructed from adjacent cells (no cell reused within one path).

**Approach:** DFS/backtracking from every cell matching the word's first letter, marking visited cells temporarily and restoring them on backtrack.

```java
boolean exist(char[][] board, String word) {
    for (int i = 0; i < board.length; i++)
        for (int j = 0; j < board[0].length; j++)
            if (dfs(board, word, 0, i, j)) return true;
    return false;
}
private boolean dfs(char[][] board, String word, int index, int i, int j) {
    if (index == word.length()) return true;
    if (i < 0 || j < 0 || i >= board.length || j >= board[0].length || board[i][j] != word.charAt(index)) return false;
    char temp = board[i][j];
    board[i][j] = '#'; // mark visited
    boolean found = dfs(board, word, index + 1, i + 1, j) || dfs(board, word, index + 1, i - 1, j)
        || dfs(board, word, index + 1, i, j + 1) || dfs(board, word, index + 1, i, j - 1);
    board[i][j] = temp; // backtrack
    return found;
}
```
**Complexity:** O(rows × cols × 4^L) where L is word length. **Pattern:** grid backtracking with in-place "mark and restore" visited tracking (avoiding a separate visited array) — the precursor to Word Search II's Trie-optimized multi-word version ([Google's cheat sheet example](#102-google)).

#### H-26. Generate Parentheses

**Problem:** Generate all combinations of `n` pairs of well-formed parentheses.

**Approach:** Backtracking tracking counts of open and close parentheses used so far — only add `(` if open count < n, only add `)` if close count < open count.

```java
List<String> generateParenthesis(int n) {
    List<String> results = new ArrayList<>();
    backtrack(new StringBuilder(), 0, 0, n, results);
    return results;
}
private void backtrack(StringBuilder current, int open, int close, int n, List<String> results) {
    if (current.length() == 2 * n) { results.add(current.toString()); return; }
    if (open < n) { current.append('('); backtrack(current, open + 1, close, n, results); current.deleteCharAt(current.length() - 1); }
    if (close < open) { current.append(')'); backtrack(current, open, close + 1, n, results); current.deleteCharAt(current.length() - 1); }
}
```
**Complexity:** O(4^n / √n) (the nth Catalan number, bounded output size). **Pattern:** backtracking with a validity invariant maintained DURING construction (close < open) rather than validating after the fact — much more efficient than generating all 2^(2n) strings and filtering valid ones.

#### H-27. Combination Sum III

**Problem:** Find all combinations of `k` numbers from 1-9 that sum to a target, each number used at most once.

**Approach:** Backtracking similar to Combination Sum ([D-20](#d-20-common--multi-company-combination-sum)), but bounded to exactly `k` numbers from a fixed range 1-9, passing `i+1` (not `i`) since each number is used at most once here.

```java
List<List<Integer>> combinationSum3(int k, int n) {
    List<List<Integer>> results = new ArrayList<>();
    backtrack(1, k, n, new ArrayList<>(), results);
    return results;
}
private void backtrack(int start, int k, int remaining, List<Integer> current, List<List<Integer>> results) {
    if (current.size() == k) { if (remaining == 0) results.add(new ArrayList<>(current)); return; }
    for (int i = start; i <= 9; i++) {
        if (i > remaining) break;
        current.add(i);
        backtrack(i + 1, k, remaining - i, current, results);
        current.remove(current.size() - 1);
    }
}
```
**Complexity:** O(C(9,k)) bounded — at most a few hundred candidates given the fixed 1-9 range. **Pattern:** bounded backtracking with an early-break pruning optimization (`if (i > remaining) break`) — a good example of adding a simple pruning check that meaningfully cuts the search space.

#### H-28. Sudoku Solver

**Problem:** Solve a 9x9 Sudoku board in-place.

**Approach:** Backtracking — find the next empty cell, try digits 1-9, checking row/column/3x3-box validity before placing, backtrack on failure.

```java
void solveSudoku(char[][] board) { solve(board); }
private boolean solve(char[][] board) {
    for (int r = 0; r < 9; r++) {
        for (int c = 0; c < 9; c++) {
            if (board[r][c] == '.') {
                for (char digit = '1'; digit <= '9'; digit++) {
                    if (isValid(board, r, c, digit)) {
                        board[r][c] = digit;
                        if (solve(board)) return true;
                        board[r][c] = '.'; // backtrack
                    }
                }
                return false; // no digit works here, trigger backtrack in caller
            }
        }
    }
    return true; // no empty cells left, solved
}
private boolean isValid(char[][] board, int row, int col, char digit) {
    int boxRow = (row / 3) * 3, boxCol = (col / 3) * 3;
    for (int i = 0; i < 9; i++) {
        if (board[row][i] == digit || board[i][col] == digit) return false;
        if (board[boxRow + i / 3][boxCol + i % 3] == digit) return false;
    }
    return true;
}
```
**Complexity:** Exponential worst case in theory, but extremely fast in practice due to heavy constraint pruning. **Pattern:** classic constraint-satisfaction backtracking — the row/column/box validity check pattern generalizes to any constraint-propagation puzzle-solving question.

#### H-29. Rotate Image (In-Place 90-Degree Matrix Rotation)

**Problem:** Rotate an n×n matrix 90 degrees clockwise, in-place.

**Approach:** Transpose the matrix (swap `matrix[i][j]` with `matrix[j][i]`), then reverse each row — the composition of these two simple operations produces a clockwise rotation.

```java
void rotate(int[][] matrix) {
    int n = matrix.length;
    for (int i = 0; i < n; i++) {
        for (int j = i + 1; j < n; j++) {
            int t = matrix[i][j]; matrix[i][j] = matrix[j][i]; matrix[j][i] = t;
        }
    }
    for (int[] row : matrix) {
        for (int lo = 0, hi = row.length - 1; lo < hi; lo++, hi--) {
            int t = row[lo]; row[lo] = row[hi]; row[hi] = t;
        }
    }
}
```
**Complexity:** O(n²) time, O(1) extra space. **Pattern:** "transpose then reverse rows" — a clean, memorizable two-step recipe for in-place rotation; rotating counter-clockwise instead uses "reverse rows then transpose."

#### H-30. Spiral Matrix

**Problem:** Return all elements of a matrix in spiral order (clockwise, from outside in).

**Approach:** Maintain four boundaries (top, bottom, left, right) and traverse right along the top, down along the right, left along the bottom, up along the left, shrinking boundaries after each side.

```java
List<Integer> spiralOrder(int[][] matrix) {
    List<Integer> result = new ArrayList<>();
    int top = 0, bottom = matrix.length - 1, left = 0, right = matrix[0].length - 1;
    while (top <= bottom && left <= right) {
        for (int j = left; j <= right; j++) result.add(matrix[top][j]);
        top++;
        for (int i = top; i <= bottom; i++) result.add(matrix[i][right]);
        right--;
        if (top <= bottom) { for (int j = right; j >= left; j--) result.add(matrix[bottom][j]); bottom--; }
        if (left <= right) { for (int i = bottom; i >= top; i--) result.add(matrix[i][left]); left++; }
    }
    return result;
}
```
**Complexity:** O(rows × cols). **Pattern:** four-boundary shrinking traversal — the guard checks (`if (top <= bottom)`, `if (left <= right)`) before the last two sides are essential to avoid double-counting elements on single-row or single-column matrices.

#### H-31. Set Matrix Zeroes (O(1) Extra Space)

**Problem:** Given a matrix, if an element is 0, set its entire row and column to 0, using O(1) extra space.

**Approach:** Use the matrix's own first row and first column as marker storage for which rows/columns need zeroing, with separate flags for whether the first row/column themselves need zeroing (to avoid corrupting the markers before they're read).

```java
void setZeroes(int[][] matrix) {
    int rows = matrix.length, cols = matrix[0].length;
    boolean firstRowHasZero = false, firstColHasZero = false;
    for (int j = 0; j < cols; j++) if (matrix[0][j] == 0) firstRowHasZero = true;
    for (int i = 0; i < rows; i++) if (matrix[i][0] == 0) firstColHasZero = true;
    for (int i = 1; i < rows; i++)
        for (int j = 1; j < cols; j++)
            if (matrix[i][j] == 0) { matrix[i][0] = 0; matrix[0][j] = 0; }
    for (int i = 1; i < rows; i++)
        for (int j = 1; j < cols; j++)
            if (matrix[i][0] == 0 || matrix[0][j] == 0) matrix[i][j] = 0;
    if (firstRowHasZero) for (int j = 0; j < cols; j++) matrix[0][j] = 0;
    if (firstColHasZero) for (int i = 0; i < rows; i++) matrix[i][0] = 0;
}
```
**Complexity:** O(rows × cols) time, O(1) extra space. **Pattern:** "use part of the input structure itself as auxiliary storage" — a recurring O(1)-space trick whenever an obvious solution needs O(rows+cols) or O(rows×cols) auxiliary space.

#### H-32. Palindrome Linked List

**Problem:** Determine if a singly linked list is a palindrome, in O(1) extra space.

**Approach:** Find the middle using slow/fast pointers, reverse the second half in-place, then compare the first half against the reversed second half.

```java
boolean isPalindrome(ListNode head) {
    ListNode slow = head, fast = head;
    while (fast != null && fast.next != null) { slow = slow.next; fast = fast.next.next; }
    ListNode secondHalf = reverse(slow);
    ListNode firstHalf = head;
    while (secondHalf != null) {
        if (firstHalf.val != secondHalf.val) return false;
        firstHalf = firstHalf.next; secondHalf = secondHalf.next;
    }
    return true;
}
private ListNode reverse(ListNode node) {
    ListNode prev = null;
    while (node != null) { ListNode next = node.next; node.next = prev; prev = node; node = next; }
    return prev;
}
```
**Complexity:** O(n) time, O(1) extra space. **Pattern:** "find middle, reverse second half, compare" — the standard O(1)-space technique for any linked-list palindrome-style check; a good follow-up is "restore the list to its original state afterward" (reverse the second half back).

#### H-33. Reorder List

**Problem:** Reorder a linked list `L0→L1→...→Ln` into `L0→Ln→L1→Ln-1→...`.

**Approach:** Find the middle (slow/fast pointers), reverse the second half, then merge the two halves by alternating nodes.

```java
void reorderList(ListNode head) {
    if (head == null) return;
    ListNode slow = head, fast = head;
    while (fast.next != null && fast.next.next != null) { slow = slow.next; fast = fast.next.next; }
    ListNode second = reverse(slow.next);
    slow.next = null;
    ListNode first = head;
    while (second != null) {
        ListNode firstNext = first.next, secondNext = second.next;
        first.next = second;
        second.next = firstNext;
        first = firstNext; second = secondNext;
    }
}
private ListNode reverse(ListNode node) {
    ListNode prev = null;
    while (node != null) { ListNode next = node.next; node.next = prev; prev = node; node = next; }
    return prev;
}
```
**Complexity:** O(n) time, O(1) extra space. **Pattern:** the "split, reverse, merge" three-step recipe — reused across many linked-list restructuring problems; the alternating-merge loop is the trickiest part to get right without losing track of pointers.

#### H-34. Add Two Numbers (Represented as Linked Lists, Digits in Reverse Order)

**Problem:** Add two non-negative integers represented as linked lists (least significant digit first), returning the sum as a new linked list.

**Approach:** Simultaneous traversal with carry tracking, identical in spirit to elementary-school addition ([D-4's Luhn-adjacent digit handling](#d-4-paypal-validate-credit-card-number-luhn-algorithm) and the string-based [Add Strings](#c-20-meta-add-strings--add-binary-big-number-arithmetic-without-built-ins)), but over linked-list nodes instead of string characters.

```java
ListNode addTwoNumbers(ListNode l1, ListNode l2) {
    ListNode dummy = new ListNode(0), cur = dummy;
    int carry = 0;
    while (l1 != null || l2 != null || carry != 0) {
        int sum = carry + (l1 != null ? l1.val : 0) + (l2 != null ? l2.val : 0);
        carry = sum / 10;
        cur.next = new ListNode(sum % 10);
        cur = cur.next;
        if (l1 != null) l1 = l1.next;
        if (l2 != null) l2 = l2.next;
    }
    return dummy.next;
}
```
**Complexity:** O(max(m, n)). **Pattern:** dummy-head technique + carry propagation — the dummy head node avoids special-casing the first node's creation, a small but universally useful linked-list-building habit.

#### H-35. Koko Eating Bananas

**Problem:** Given piles of bananas and `h` hours, find the minimum eating speed `k` (bananas/hour) so Koko finishes all piles within `h` hours (each hour she picks one pile and eats up to `k` from it, finishing that pile if it has less than `k` left).

**Approach:** Binary search on the answer speed `k` — for a candidate speed, compute total hours needed (`ceil(pile/k)` summed over piles) and check feasibility against `h`.

```java
int minEatingSpeed(int[] piles, int h) {
    int lo = 1, hi = Arrays.stream(piles).max().getAsInt();
    while (lo < hi) {
        int mid = lo + (hi - lo) / 2;
        if (hoursNeeded(piles, mid) <= h) hi = mid; else lo = mid + 1;
    }
    return lo;
}
private long hoursNeeded(int[] piles, int speed) {
    long hours = 0;
    for (int pile : piles) hours += (pile + speed - 1) / speed; // ceiling division
    return hours;
}
```
**Complexity:** O(n log(max pile)). **Pattern:** "binary search the answer" over a feasibility function — the same meta-pattern as [OA-7](#oa-7-google-minimum-days-to-make-m-bouquets) and [E-18](#e-18-wayfair-kth-smallest-element-in-a-sorted-matrix); recognizing "minimum X such that a monotonic condition holds" is the trigger phrase for this pattern.

#### H-36. Capacity To Ship Packages Within D Days

**Problem:** Given package weights and `D` days, find the minimum ship capacity so all packages ship (in given order, one day's worth loaded until capacity would be exceeded) within `D` days.

**Approach:** Binary search on the answer capacity — for a candidate capacity, greedily simulate how many days are needed, checking feasibility against `D`.

```java
int shipWithinDays(int[] weights, int days) {
    int lo = Arrays.stream(weights).max().getAsInt();
    int hi = Arrays.stream(weights).sum();
    while (lo < hi) {
        int mid = lo + (hi - lo) / 2;
        if (daysNeeded(weights, mid) <= days) hi = mid; else lo = mid + 1;
    }
    return lo;
}
private int daysNeeded(int[] weights, int capacity) {
    int days = 1, currentLoad = 0;
    for (int w : weights) {
        if (currentLoad + w > capacity) { days++; currentLoad = 0; }
        currentLoad += w;
    }
    return days;
}
```
**Complexity:** O(n log(sum of weights)). **Pattern:** another "binary search the answer" instance — structurally almost identical to Koko Eating Bananas, reinforcing that recognizing the META-pattern (not memorizing each problem individually) is what generalizes to new, unseen problems.

#### H-37. Pow(x, n) — Fast Exponentiation

**Problem:** Implement `pow(x, n)` in O(log n) time (n can be negative).

**Approach:** Fast exponentiation by squaring — recursively compute `pow(x, n/2)` and square it, handling the odd-exponent case with one extra multiplication.

```java
double myPow(double x, int n) {
    long exp = n;
    if (exp < 0) { x = 1 / x; exp = -exp; }
    return fastPow(x, exp);
}
private double fastPow(double x, long n) {
    if (n == 0) return 1.0;
    double half = fastPow(x, n / 2);
    return (n % 2 == 0) ? half * half : half * half * x;
}
```
**Complexity:** O(log n). **Pattern:** exponentiation by squaring — a foundational fast-math technique also used in fast matrix exponentiation (for solving linear recurrences like Fibonacci in O(log n)) and modular exponentiation in cryptography.

#### H-38. Excel Sheet Column Number

**Problem:** Convert a spreadsheet column title (e.g., `"AB"`) to its corresponding column number (base-26-like, but with no zero digit — `A=1`).

**Approach:** Process left to right like a base conversion, but subtract 1 from each digit's value first (since there's no "zero" — `A` represents 1, not 0).

```java
int titleToNumber(String columnTitle) {
    int result = 0;
    for (char c : columnTitle.toCharArray()) {
        result = result * 26 + (c - 'A' + 1);
    }
    return result;
}
```
**Complexity:** O(n). **Pattern:** a "base 26 without a zero digit" (bijective base-26) numeral system — a small but genuinely tricky number-system subtlety; the reverse conversion (number to title) requires an extra `-1` adjustment before the modulo step for the same reason.

#### H-39. Happy Number

**Problem:** Determine if repeatedly replacing a number with the sum of the squares of its digits eventually reaches 1 (a "happy" number), or enters an infinite cycle (not happy).

**Approach:** Floyd's cycle detection (slow/fast pointers, same technique as [E-20](#e-20-capital-one-linked-list-cycle-detection-floyds-algorithm)) applied to the sequence of digit-square-sums instead of linked list nodes, detecting a cycle without needing a hash set.

```java
boolean isHappy(int n) {
    int slow = n, fast = sumOfSquares(n);
    while (fast != 1 && slow != fast) {
        slow = sumOfSquares(slow);
        fast = sumOfSquares(sumOfSquares(fast));
    }
    return fast == 1;
}
private int sumOfSquares(int n) {
    int sum = 0;
    while (n > 0) { int digit = n % 10; sum += digit * digit; n /= 10; }
    return sum;
}
```
**Complexity:** O(log n) per sum-of-squares computation, bounded overall by the cycle length. **Pattern:** Floyd's cycle detection applied OUTSIDE the linked-list context — a good example of a technique transferring to a completely different problem domain (numeric sequences) once you recognize the underlying "detect a cycle in an implicit sequence" shape.

#### H-40. Reverse Integer (With Overflow Handling)

**Problem:** Reverse the digits of a 32-bit signed integer; return 0 if the reversed value overflows the 32-bit range.

**Approach:** Build the reversed number digit by digit, checking for overflow BEFORE each multiplication/addition (rather than computing in a wider type and checking after, which some interviewers explicitly disallow to test overflow-awareness).

```java
int reverse(int x) {
    int result = 0;
    while (x != 0) {
        int digit = x % 10;
        x /= 10;
        if (result > Integer.MAX_VALUE / 10 || (result == Integer.MAX_VALUE / 10 && digit > 7)) return 0;
        if (result < Integer.MIN_VALUE / 10 || (result == Integer.MIN_VALUE / 10 && digit < -8)) return 0;
        result = result * 10 + digit;
    }
    return result;
}
```
**Complexity:** O(digits). **Pattern:** proactive overflow checking BEFORE the operation (comparing against `MAX_VALUE/10` first) rather than reactively after — a technique required whenever a problem explicitly restricts using a wider intermediate type like `long`.

#### H-41. Insert Delete GetRandom O(1)

**Problem:** Design a data structure supporting `insert`, `remove`, and `getRandom` (uniformly random existing element), all in average O(1) time.

**Approach:** An `ArrayList` (for O(1) random access by index) paired with a `HashMap` of value→index; to remove in O(1), swap the target element with the LAST element in the list before removing the last element (avoiding an O(n) shift).

```java
class RandomizedSet {
    private final List<Integer> values = new ArrayList<>();
    private final Map<Integer, Integer> valueToIndex = new HashMap<>();
    private final Random random = new Random();

    public boolean insert(int val) {
        if (valueToIndex.containsKey(val)) return false;
        valueToIndex.put(val, values.size());
        values.add(val);
        return true;
    }
    public boolean remove(int val) {
        if (!valueToIndex.containsKey(val)) return false;
        int index = valueToIndex.get(val);
        int lastVal = values.get(values.size() - 1);
        values.set(index, lastVal);
        valueToIndex.put(lastVal, index);
        values.remove(values.size() - 1);
        valueToIndex.remove(val);
        return true;
    }
    public int getRandom() { return values.get(random.nextInt(values.size())); }
}
```
**Complexity:** O(1) average for all three operations. **Pattern:** "swap with the last element before removing" — the standard trick for O(1) removal from an array-backed structure when order doesn't matter, reused constantly in randomized/sampling data structure design questions.

#### H-42. Design a Time-Based Key-Value Store

**Problem:** Design a store supporting `set(key, value, timestamp)` and `get(key, timestamp)` returning the value set at the largest timestamp ≤ the query timestamp.

**Approach:** A hashmap of key → list of `(timestamp, value)` pairs (timestamps arrive in increasing order per key, so the list is naturally sorted); binary search for the largest timestamp not exceeding the query.

```java
class TimeMap {
    private final Map<String, List<long[]>> store = new HashMap<>(); // value packed as second long via encoding, or use a small record class
    public void set(String key, String value, int timestamp) {
        store.computeIfAbsent(key, k -> new ArrayList<>()).add(new long[]{timestamp, value.hashCode()}); // simplified encoding for illustration
    }
    public String get(String key, int timestamp) {
        List<long[]> entries = store.get(key);
        if (entries == null) return "";
        int lo = 0, hi = entries.size() - 1, resultIdx = -1;
        while (lo <= hi) {
            int mid = (lo + hi) / 2;
            if (entries.get(mid)[0] <= timestamp) { resultIdx = mid; lo = mid + 1; } else hi = mid - 1;
        }
        return resultIdx == -1 ? "" : String.valueOf(entries.get(resultIdx)[1]); // in a real impl, store the actual String value, not its hash
    }
}
```
**Complexity:** O(1) amortized `set`, O(log n) `get`. **Pattern:** "binary search for the largest value ≤ target" over a naturally-sorted-by-insertion list — the same floor-search binary search shape as [H-42's sibling problems](#h-36-capacity-to-ship-packages-within-d-days), applied to a design question instead of a pure algorithm question.

#### H-43. Edit Distance (Levenshtein Distance)

**Problem:** Find the minimum number of insertions, deletions, and substitutions to transform one string into another.

**Approach:** 2D DP where `dp[i][j]` = edit distance between the first `i` characters of word1 and first `j` characters of word2; if characters match, no cost; otherwise take the minimum of the three operations plus 1.

```java
int minDistance(String word1, String word2) {
    int m = word1.length(), n = word2.length();
    int[][] dp = new int[m + 1][n + 1];
    for (int i = 0; i <= m; i++) dp[i][0] = i;
    for (int j = 0; j <= n; j++) dp[0][j] = j;
    for (int i = 1; i <= m; i++) {
        for (int j = 1; j <= n; j++) {
            if (word1.charAt(i - 1) == word2.charAt(j - 1)) dp[i][j] = dp[i - 1][j - 1];
            else dp[i][j] = 1 + Math.min(dp[i - 1][j - 1], Math.min(dp[i - 1][j], dp[i][j - 1]));
        }
    }
    return dp[m][n];
}
```
**Complexity:** O(m × n). **Pattern:** the canonical 2-string comparison DP — the three transition terms correspond exactly to substitute (`dp[i-1][j-1]`), delete (`dp[i-1][j]`), and insert (`dp[i][j-1]`); this same DP table shape underlies diff tools, spell-checkers, and DNA sequence alignment.

#### H-44. Interleaving String

**Problem:** Given three strings, determine if the third is formed by interleaving the first two (preserving each source string's relative character order).

**Approach:** 2D DP where `dp[i][j]` = true if the first `i+j` characters of the interleaved string can be formed from the first `i` characters of s1 and first `j` characters of s2.

```java
boolean isInterleave(String s1, String s2, String s3) {
    int m = s1.length(), n = s2.length();
    if (m + n != s3.length()) return false;
    boolean[][] dp = new boolean[m + 1][n + 1];
    dp[0][0] = true;
    for (int i = 1; i <= m; i++) dp[i][0] = dp[i - 1][0] && s1.charAt(i - 1) == s3.charAt(i - 1);
    for (int j = 1; j <= n; j++) dp[0][j] = dp[0][j - 1] && s2.charAt(j - 1) == s3.charAt(j - 1);
    for (int i = 1; i <= m; i++) {
        for (int j = 1; j <= n; j++) {
            dp[i][j] = (dp[i - 1][j] && s1.charAt(i - 1) == s3.charAt(i + j - 1))
                    || (dp[i][j - 1] && s2.charAt(j - 1) == s3.charAt(i + j - 1));
        }
    }
    return dp[m][n];
}
```
**Complexity:** O(m × n). **Pattern:** 2D boolean DP over TWO source sequences merging into a third — a variant of the standard 2-sequence DP shape, testing whether candidates correctly derive the transition from "does the current interleaved character come from s1 or s2."

#### H-45. Odd Even Linked List

**Problem:** Group all odd-indexed nodes together followed by all even-indexed nodes (by position, not value), in-place, O(1) extra space.

**Approach:** Maintain two separate chains (odd and even) while traversing once, then splice the even chain onto the end of the odd chain.

```java
ListNode oddEvenList(ListNode head) {
    if (head == null) return null;
    ListNode odd = head, even = head.next, evenHead = even;
    while (even != null && even.next != null) {
        odd.next = even.next;
        odd = odd.next;
        even.next = odd.next;
        even = even.next;
    }
    odd.next = evenHead;
    return head;
}
```
**Complexity:** O(n) time, O(1) extra space. **Pattern:** "maintain two chains simultaneously, splice at the end" — a common linked-list restructuring template, testing careful pointer bookkeeping across two interleaved traversals.

#### H-46. Remove Nth Node From End of List

**Problem:** Remove the nth node from the end of a linked list in one pass.

**Approach:** Two pointers with a gap of `n` — advance a lead pointer `n` steps first, then move both pointers together until the lead reaches the end; the trailing pointer is now positioned just before the node to remove.

```java
ListNode removeNthFromEnd(ListNode head, int n) {
    ListNode dummy = new ListNode(0, head);
    ListNode fast = dummy, slow = dummy;
    for (int i = 0; i < n; i++) fast = fast.next;
    while (fast.next != null) { fast = fast.next; slow = slow.next; }
    slow.next = slow.next.next;
    return dummy.next;
}
```
**Complexity:** O(n) time, single pass. **Pattern:** the "gap of N" two-pointer technique — a clean one-pass alternative to the naive two-pass approach (count length, then remove); the dummy head handles the edge case of removing the actual head node cleanly.

#### H-47. Game of Life

**Problem:** Given a board of live/dead cells, compute the next generation in-place following Conway's Game of Life rules (a live cell with 2-3 live neighbors survives; a dead cell with exactly 3 live neighbors becomes alive; all others die/stay dead).

**Approach:** Encode both the OLD and NEW state in each cell using extra bit values (e.g., 2 = "was alive, now dead," 3 = "was dead, now alive"), so neighbor-counting during the scan always reads the ORIGINAL state via a simple `% 2` check, then a final pass normalizes to 0/1.

```java
void gameOfLife(int[][] board) {
    int rows = board.length, cols = board[0].length;
    int[][] dirs = {{-1,-1},{-1,0},{-1,1},{0,-1},{0,1},{1,-1},{1,0},{1,1}};
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            int liveNeighbors = 0;
            for (int[] d : dirs) {
                int ni = i + d[0], nj = j + d[1];
                if (ni >= 0 && nj >= 0 && ni < rows && nj < cols && board[ni][nj] % 2 == 1) liveNeighbors++;
            }
            if (board[i][j] == 1 && (liveNeighbors == 2 || liveNeighbors == 3)) board[i][j] = 3; // was alive, stays alive
            if (board[i][j] == 0 && liveNeighbors == 3) board[i][j] = 2; // was dead, becomes alive
        }
    }
    for (int i = 0; i < rows; i++)
        for (int j = 0; j < cols; j++)
            board[i][j] /= 2;
}
```
**Complexity:** O(rows × cols) time, O(1) extra space. **Pattern:** encoding old+new state simultaneously in extra bit values — a clever O(1)-space trick for "compute next state from current state in-place," reusable whenever a grid-simulation problem forbids a second auxiliary grid.

#### H-48. Search a 2D Matrix II

**Problem:** Given a matrix where each row is sorted left-to-right and each column is sorted top-to-bottom, determine if a target value exists.

**Approach:** Start from the top-right corner — if the current value is larger than the target, move left (eliminating a column); if smaller, move down (eliminating a row). This exploits both sorted directions simultaneously.

```java
boolean searchMatrix(int[][] matrix, int target) {
    int row = 0, col = matrix[0].length - 1;
    while (row < matrix.length && col >= 0) {
        if (matrix[row][col] == target) return true;
        else if (matrix[row][col] > target) col--;
        else row++;
    }
    return false;
}
```
**Complexity:** O(rows + cols). **Pattern:** "start from a corner that lets you eliminate a row OR column with each comparison" — a distinctive technique that only works from the top-right or bottom-left corner (NOT top-left or bottom-right, which don't provide a clear elimination direction).

#### H-49. Longest Repeating Character Replacement

**Problem:** Given a string and an integer `k`, find the length of the longest substring where you can replace at most `k` characters to make all characters the same.

**Approach:** Sliding window tracking character frequencies and the count of the MOST frequent character in the window; the window is valid as long as `windowSize - maxFrequency <= k` (i.e., the number of characters that would need replacing doesn't exceed `k`).

```java
int characterReplacement(String s, int k) {
    int[] freq = new int[26];
    int left = 0, maxFreq = 0, best = 0;
    for (int right = 0; right < s.length(); right++) {
        int c = s.charAt(right) - 'A';
        freq[c]++;
        maxFreq = Math.max(maxFreq, freq[c]);
        while (right - left + 1 - maxFreq > k) {
            freq[s.charAt(left) - 'A']--;
            left++;
        }
        best = Math.max(best, right - left + 1);
    }
    return best;
}
```
**Complexity:** O(n). **Pattern:** sliding window with a "most frequent character in window" tracker — note that `maxFreq` is never actually decremented even when the window shrinks (a subtle but harmless simplification, since the window can only grow from its best-ever size, never needing to shrink below a previously-valid size).

#### H-50. Regular Expression Matching ('.' and '*')

**Problem:** Implement regex matching supporting `'.'` (any single character) and `'*'` (zero or more of the preceding element).

**Approach:** 2D DP where `dp[i][j]` = true if the first `i` characters of the string match the first `j` characters of the pattern; the `'*'` case branches into "use zero occurrences" or "use one more occurrence if the preceding character matches."

```java
boolean isMatch(String s, String p) {
    int m = s.length(), n = p.length();
    boolean[][] dp = new boolean[m + 1][n + 1];
    dp[0][0] = true;
    for (int j = 1; j <= n; j++) {
        if (p.charAt(j - 1) == '*') dp[0][j] = dp[0][j - 2];
    }
    for (int i = 1; i <= m; i++) {
        for (int j = 1; j <= n; j++) {
            char sc = s.charAt(i - 1), pc = p.charAt(j - 1);
            if (pc == '.' || pc == sc) dp[i][j] = dp[i - 1][j - 1];
            else if (pc == '*') {
                dp[i][j] = dp[i][j - 2]; // zero occurrences of preceding element
                char prevPatternChar = p.charAt(j - 2);
                if (prevPatternChar == '.' || prevPatternChar == sc) dp[i][j] |= dp[i - 1][j];
            }
        }
    }
    return dp[m][n];
}
```
**Complexity:** O(m × n). **Pattern:** 2D DP with a branching transition for the `*` quantifier — widely regarded as one of the hardest commonly-asked DP problems; the "zero occurrences OR one-more-occurrence-if-matches" branch is the crux most candidates need explicit practice to internalize.

#### H-51. Design a Parking System

**Problem:** Design a parking system for a lot with a fixed number of big, medium, and small spots; `addCar(carType)` returns whether parking succeeded.

**Approach:** A simple array/counter per spot type, decrementing on successful parking.

```java
class ParkingSystem {
    private final int[] available; // index 0=big,1=medium,2=small (carType-1)
    ParkingSystem(int big, int medium, int small) { available = new int[]{big, medium, small}; }
    public boolean addCar(int carType) {
        if (available[carType - 1] > 0) { available[carType - 1]--; return true; }
        return false;
    }
}
```
**Complexity:** O(1) per operation. **Pattern:** a deliberately simple "warm-up" design question — often the FIRST, easiest question in a two-question phone screen to build confidence before a harder second problem; the interview signal here is mostly about clean, bug-free code under time pressure rather than algorithmic depth.

#### H-52. Design Browser History

**Problem:** Design a browser history supporting `visit(url)` (clears forward history), `back(steps)`, and `forward(steps)`.

**Approach:** A dynamic array (or two stacks) with a current-position pointer; `visit` truncates everything after the current position before appending the new URL.

```java
class BrowserHistory {
    private final List<String> history = new ArrayList<>();
    private int currentIndex;
    BrowserHistory(String homepage) { history.add(homepage); currentIndex = 0; }
    public void visit(String url) {
        while (history.size() > currentIndex + 1) history.remove(history.size() - 1); // clear forward history
        history.add(url);
        currentIndex++;
    }
    public String back(int steps) {
        currentIndex = Math.max(0, currentIndex - steps);
        return history.get(currentIndex);
    }
    public String forward(int steps) {
        currentIndex = Math.min(history.size() - 1, currentIndex + steps);
        return history.get(currentIndex);
    }
}
```
**Complexity:** O(1) amortized for back/forward, O(k) for visit (clearing k forward entries). **Pattern:** array + position pointer, with "visiting a new page clears forward history" being the one subtle rule candidates commonly forget to implement — directly modeling real browser back/forward-button semantics.

#### H-53. Palindrome Number (Without Converting to String)

**Problem:** Determine if an integer is a palindrome, without converting it to a string.

**Approach:** Reverse only the SECOND HALF of the number numerically, then compare it against the remaining first half (handles both even and odd digit counts cleanly, and avoids any overflow risk from reversing the entire number).

```java
boolean isPalindrome(int x) {
    if (x < 0 || (x % 10 == 0 && x != 0)) return false;
    int reversedHalf = 0;
    while (x > reversedHalf) {
        reversedHalf = reversedHalf * 10 + x % 10;
        x /= 10;
    }
    return x == reversedHalf || x == reversedHalf / 10; // odd digit count: drop the middle digit
}
```
**Complexity:** O(log n) (proportional to digit count). **Pattern:** "reverse only half, then compare" — avoids the overflow risk of fully reversing a number that might not fit back into an `int`, a subtle but real edge case interviewers explicitly probe.

#### H-54. Ugly Number II (Nth Number With Only Factors 2, 3, 5)

**Problem:** Find the `n`-th ugly number (a positive integer whose only prime factors are 2, 3, and 5).

**Approach:** Dynamic programming with three pointers, one per factor (2, 3, 5); each ugly number is generated by multiplying a previous ugly number by 2, 3, or 5, and the three pointers track which previous ugly number to use next for each factor.

```java
int nthUglyNumber(int n) {
    int[] ugly = new int[n];
    ugly[0] = 1;
    int i2 = 0, i3 = 0, i5 = 0;
    for (int i = 1; i < n; i++) {
        int next2 = ugly[i2] * 2, next3 = ugly[i3] * 3, next5 = ugly[i5] * 5;
        int next = Math.min(next2, Math.min(next3, next5));
        ugly[i] = next;
        if (next == next2) i2++;
        if (next == next3) i3++;
        if (next == next5) i5++;
    }
    return ugly[n - 1];
}
```
**Complexity:** O(n). **Pattern:** the "three-pointer DP" technique for generating ordered sequences from a small set of multiplicative factors — a distinctive, non-obvious pattern worth memorizing since brute-force factorization checking would be far slower.

#### H-55. Multiply Strings (Big Number Multiplication Without Built-Ins)

**Problem:** Multiply two non-negative integers represented as strings, without converting the whole strings to a built-in big-integer type.

**Approach:** Elementary-school long multiplication — multiply each digit pair, accumulating results into the correct position of a result array (position `i+j` and `i+j+1` for digits at positions `i` and `j`), then handle carries.

```java
String multiply(String num1, String num2) {
    if (num1.equals("0") || num2.equals("0")) return "0";
    int m = num1.length(), n = num2.length();
    int[] result = new int[m + n];
    for (int i = m - 1; i >= 0; i--) {
        for (int j = n - 1; j >= 0; j--) {
            int mul = (num1.charAt(i) - '0') * (num2.charAt(j) - '0');
            int sum = mul + result[i + j + 1];
            result[i + j + 1] = sum % 10;
            result[i + j] += sum / 10;
        }
    }
    StringBuilder sb = new StringBuilder();
    for (int digit : result) {
        if (!(sb.length() == 0 && digit == 0)) sb.append(digit); // skip leading zeros
    }
    return sb.length() == 0 ? "0" : sb.toString();
}
```
**Complexity:** O(m × n). **Pattern:** the "position `i+j`/`i+j+1`" index mapping for grade-school multiplication — a genuinely tricky indexing scheme worth deriving carefully on paper before coding, since off-by-one errors here are common under time pressure.

#### H-56. Count and Say

**Problem:** Generate the `n`-th term of the "count and say" sequence, where each term describes the previous term's runs of digits (e.g., `"1"` → `"11"` (one 1) → `"21"` (two 1s) → `"1211"` (one 2, one 1)).

**Approach:** Iteratively build each term from the previous one by scanning runs of identical digits and appending `count + digit` for each run.

```java
String countAndSay(int n) {
    String result = "1";
    for (int i = 1; i < n; i++) {
        StringBuilder next = new StringBuilder();
        int j = 0;
        while (j < result.length()) {
            char digit = result.charAt(j);
            int count = 0;
            while (j < result.length() && result.charAt(j) == digit) { count++; j++; }
            next.append(count).append(digit);
        }
        result = next.toString();
    }
    return result;
}
```
**Complexity:** O(n × length of the nth term) — the term length grows roughly exponentially, so this is efficient relative to the output size. **Pattern:** run-length encoding applied iteratively — a simple simulation question testing careful run-detection logic rather than algorithmic depth.

#### H-57. Zigzag Conversion

**Problem:** Given a string and a number of rows, write it in a zigzag pattern across that many rows, then read off row by row.

**Approach:** Simulate the zigzag directly — maintain a "current row" and a direction flag, appending each character to a per-row `StringBuilder`, flipping direction at the top and bottom rows.

```java
String convert(String s, int numRows) {
    if (numRows == 1) return s;
    StringBuilder[] rows = new StringBuilder[Math.min(numRows, s.length())];
    for (int i = 0; i < rows.length; i++) rows[i] = new StringBuilder();
    int curRow = 0;
    boolean goingDown = false;
    for (char c : s.toCharArray()) {
        rows[curRow].append(c);
        if (curRow == 0 || curRow == numRows - 1) goingDown = !goingDown;
        curRow += goingDown ? 1 : -1;
    }
    StringBuilder result = new StringBuilder();
    for (StringBuilder row : rows) result.append(row);
    return result.toString();
}
```
**Complexity:** O(n). **Pattern:** direct simulation with a direction flag flipping at boundaries — a simple but easy-to-fumble-under-pressure simulation question, testing careful boundary condition handling (flipping direction exactly at rows 0 and numRows-1).

#### H-58. Best Time to Buy and Sell Stock II (Unlimited Transactions)

**Problem:** Maximize profit with unlimited buy/sell transactions (must sell before buying again).

**Approach:** Greedy — sum every positive day-over-day price difference (mathematically equivalent to buying at every local minimum and selling at every local maximum).

```java
int maxProfit(int[] prices) {
    int profit = 0;
    for (int i = 1; i < prices.length; i++) {
        if (prices[i] > prices[i - 1]) profit += prices[i] - prices[i - 1];
    }
    return profit;
}
```
**Complexity:** O(n). **Pattern:** greedy "capture every positive delta" — the promised follow-up from [G-2](#g-2-best-time-to-buy-and-sell-stock)'s single-transaction version; the key insight is that capturing every small positive move is mathematically equivalent to holding through a longer upward run.

#### H-59. Best Time to Buy and Sell Stock III (At Most 2 Transactions)

**Problem:** Maximize profit with at most 2 buy/sell transactions.

**Approach:** Track four state variables representing the best profit after: first buy, first sell, second buy, second sell — updated in a single pass.

```java
int maxProfit(int[] prices) {
    int firstBuy = Integer.MIN_VALUE, firstSell = 0, secondBuy = Integer.MIN_VALUE, secondSell = 0;
    for (int price : prices) {
        firstBuy = Math.max(firstBuy, -price);
        firstSell = Math.max(firstSell, firstBuy + price);
        secondBuy = Math.max(secondBuy, firstSell - price);
        secondSell = Math.max(secondSell, secondBuy + price);
    }
    return secondSell;
}
```
**Complexity:** O(n) time, O(1) space. **Pattern:** state-machine DP with a fixed small number of states — generalizes directly to "Best Time IV" (at most `k` transactions) by using `2k` state variables (or a 2D DP array) instead of exactly 4.

#### H-60. Longest Valid Parentheses

**Problem:** Find the length of the longest valid (well-formed) parentheses substring.

**Approach:** Stack of indices — push `)`-unmatched indices as boundary markers (starting with a sentinel -1); for a `)` that matches, pop and compute the length from the new stack top to the current index.

```java
int longestValidParentheses(String s) {
    Deque<Integer> stack = new ArrayDeque<>();
    stack.push(-1); // sentinel boundary
    int best = 0;
    for (int i = 0; i < s.length(); i++) {
        if (s.charAt(i) == '(') stack.push(i);
        else {
            stack.pop();
            if (stack.isEmpty()) stack.push(i); // new boundary
            else best = Math.max(best, i - stack.peek());
        }
    }
    return best;
}
```
**Complexity:** O(n). **Pattern:** stack-of-indices with a sentinel boundary — a subtle variant of the basic valid-parentheses stack pattern, where the stack tracks BOUNDARIES of invalid positions rather than unmatched open brackets directly.

#### H-61. Largest Rectangle in Histogram

**Problem:** Given bar heights, find the area of the largest rectangle that fits within the histogram.

**Approach:** Monotonic increasing stack of indices — when a shorter bar is encountered, pop taller bars and compute the rectangle area using the popped bar's height and the width spanning from the new stack top to the current index.

```java
int largestRectangleArea(int[] heights) {
    Deque<Integer> stack = new ArrayDeque<>();
    int maxArea = 0;
    for (int i = 0; i <= heights.length; i++) {
        int h = (i == heights.length) ? 0 : heights[i];
        while (!stack.isEmpty() && heights[stack.peek()] >= h) {
            int height = heights[stack.pop()];
            int width = stack.isEmpty() ? i : i - stack.peek() - 1;
            maxArea = Math.max(maxArea, height * width);
        }
        stack.push(i);
    }
    return maxArea;
}
```
**Complexity:** O(n) — each bar is pushed and popped at most once. **Pattern:** monotonic stack for "find the largest rectangle/area" problems — the same core technique extends to Maximal Rectangle (treating each row of a binary matrix as a histogram and reusing this exact function).

#### H-62. Sum of Two Integers (Without + or -)

**Problem:** Add two integers without using the `+` or `-` operators.

**Approach:** Bitwise addition — XOR gives the sum without carrying, AND-then-shift-left gives the carry; repeat until there's no carry left.

```java
int getSum(int a, int b) {
    while (b != 0) {
        int carry = (a & b) << 1;
        a = a ^ b;
        b = carry;
    }
    return a;
}
```
**Complexity:** O(1) (bounded by 32 bit positions). **Pattern:** bitwise addition simulating how hardware adders work at the circuit level (XOR = sum bit, AND+shift = carry bit) — a genuinely illuminating question for understanding what `+` actually does underneath, frequently asked at hardware-adjacent companies.

#### H-63. Jump Game (Basic Reachability)

**Problem:** Given an array where each element is the maximum jump length from that position, determine if the last index is reachable from the first (a simpler yes/no version of [G-35's minimum-jumps variant](#g-35-jump-game-ii-minimum-jumps)).

**Approach:** The same greedy farthest-reachable tracker as Jump Game II, but without counting jumps — simply check feasibility.

```java
boolean canJump(int[] nums) {
    int farthest = 0;
    for (int i = 0; i < nums.length; i++) {
        if (i > farthest) return false;
        farthest = Math.max(farthest, i + nums[i]);
    }
    return true;
}
```
**Complexity:** O(n). **Pattern:** identical skeleton to [F-5's gas station reachability](#f-5-automotiveev-eg-tesla-style-gas-station-reachability-jump-game-variant) — recognizing when two differently-worded problems ("can you reach the end," "reach the destination with enough fuel") share the exact same greedy solution reinforces the value of pattern-based (not memorization-based) preparation.

#### H-64. Range Sum Query 2D — Immutable

**Problem:** Given a 2D matrix (immutable), answer multiple `sumRegion(row1, col1, row2, col2)` queries efficiently.

**Approach:** Precompute a 2D prefix-sum array using inclusion-exclusion, then answer each query in O(1) by combining four prefix-sum lookups.

```java
class NumMatrix {
    private final int[][] prefixSum;
    NumMatrix(int[][] matrix) {
        int rows = matrix.length, cols = matrix[0].length;
        prefixSum = new int[rows + 1][cols + 1];
        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < cols; j++) {
                prefixSum[i + 1][j + 1] = matrix[i][j] + prefixSum[i][j + 1] + prefixSum[i + 1][j] - prefixSum[i][j];
            }
        }
    }
    public int sumRegion(int row1, int col1, int row2, int col2) {
        return prefixSum[row2 + 1][col2 + 1] - prefixSum[row1][col2 + 1] - prefixSum[row2 + 1][col1] + prefixSum[row1][col1];
    }
}
```
**Complexity:** O(rows × cols) build, O(1) per query. **Pattern:** 2D prefix sums via inclusion-exclusion — the natural generalization of 1D prefix sums ([D-18/D-19's pattern](#d-18-common--multi-company-product-of-array-except-self)) to two dimensions; the "+1"-offset prefix array avoids boundary special-casing for row/col 0.

#### H-65. Shuffle an Array (Reset and Shuffle)

**Problem:** Design a class supporting `reset()` (restore original array) and `shuffle()` (return a random permutation), each shuffle uniformly random and independent.

**Approach:** Identical to the Fisher-Yates shuffle technique used for [Spotify's playlist shuffler](#d-11-spotify-shuffle-a-playlist-fisher-yates) earlier in this guide.

```java
class ShuffleArray {
    private final int[] original;
    private int[] current;
    private final Random random = new Random();
    ShuffleArray(int[] nums) { original = nums.clone(); current = nums.clone(); }
    public int[] reset() { current = original.clone(); return current; }
    public int[] shuffle() {
        for (int i = current.length - 1; i > 0; i--) {
            int j = random.nextInt(i + 1);
            int t = current[i]; current[i] = current[j]; current[j] = t;
        }
        return current;
    }
}
```
**Complexity:** O(n) per shuffle. **Pattern:** Fisher-Yates again — its repeated appearance across this guide (playlist shuffling, generic array shuffling) reflects how genuinely common "implement a correct random shuffle" is as an interview question across many companies.

#### H-66. Boats to Save People

**Problem:** Given people's weights and a boat weight limit (each boat holds at most 2 people), find the minimum number of boats needed.

**Approach:** Greedy two-pointer on a sorted array — always try to pair the heaviest remaining person with the lightest remaining person; if they fit together, both go; otherwise the heaviest goes alone.

```java
int numRescueBoats(int[] people, int limit) {
    Arrays.sort(people);
    int lo = 0, hi = people.length - 1, boats = 0;
    while (lo <= hi) {
        if (people[lo] + people[hi] <= limit) lo++;
        hi--;
        boats++;
    }
    return boats;
}
```
**Complexity:** O(n log n). **Pattern:** two-pointer greedy pairing (heaviest with lightest) — a clean, provably-optimal greedy for pairing problems with a capacity constraint, structurally similar to the two-pointer techniques used throughout [Part 5.2](#52-amazon-tagged-questions)'s Optimal Utilization problem.

#### H-67. Split Array Largest Sum

**Problem:** Split an array into `k` non-empty contiguous subarrays to minimize the largest subarray sum.

**Approach:** Binary search on the answer (the minimized largest sum) — for a candidate value, greedily count how many subarrays are needed to keep every subarray's sum ≤ that value, checking feasibility against `k`.

```java
int splitArray(int[] nums, int k) {
    int lo = Arrays.stream(nums).max().getAsInt();
    int hi = Arrays.stream(nums).sum();
    while (lo < hi) {
        int mid = lo + (hi - lo) / 2;
        if (subarraysNeeded(nums, mid) <= k) hi = mid; else lo = mid + 1;
    }
    return lo;
}
private int subarraysNeeded(int[] nums, int maxSum) {
    int subarrays = 1, currentSum = 0;
    for (int num : nums) {
        if (currentSum + num > maxSum) { subarrays++; currentSum = 0; }
        currentSum += num;
    }
    return subarrays;
}
```
**Complexity:** O(n log(sum)). **Pattern:** yet another "binary search the answer" instance (the fourth in this guide, alongside Koko Eating Bananas, Capacity to Ship Packages, and the OA bouquet problem) — by this point in the guide, this pattern should be immediately recognizable from the phrase "minimize the maximum" or "minimum X such that Y is feasible."

#### H-68. Wildcard Matching ('?' and '*')

**Problem:** Implement wildcard pattern matching supporting `'?'` (matches any single character) and `'*'` (matches any sequence of characters, including empty) — distinct from regex matching ([H-50](#h-50-regular-expression-matching--and-)) where `*` means "zero or more of the PRECEDING character," not "any sequence."

**Approach:** 2D DP where `dp[i][j]` = true if the first `i` characters of the string match the first `j` characters of the pattern; a `'*'` can match zero characters (`dp[i][j-1]`) or extend to match one more character (`dp[i-1][j]`).

```java
boolean isMatch(String s, String p) {
    int m = s.length(), n = p.length();
    boolean[][] dp = new boolean[m + 1][n + 1];
    dp[0][0] = true;
    for (int j = 1; j <= n; j++) {
        if (p.charAt(j - 1) == '*') dp[0][j] = dp[0][j - 1];
    }
    for (int i = 1; i <= m; i++) {
        for (int j = 1; j <= n; j++) {
            char pc = p.charAt(j - 1);
            if (pc == '*') dp[i][j] = dp[i][j - 1] || dp[i - 1][j];
            else if (pc == '?' || pc == s.charAt(i - 1)) dp[i][j] = dp[i - 1][j - 1];
        }
    }
    return dp[m][n];
}
```
**Complexity:** O(m × n). **Pattern:** a close cousin of Regular Expression Matching but with a SIMPLER `*` semantic (any sequence, not "zero or more of preceding") — interviewers sometimes ask both back to back specifically to see if candidates confuse the two different `*` semantics.

#### H-69. Basic Calculator II (+, -, *, /, No Parentheses)

**Problem:** Evaluate an expression with `+`, `-`, `*`, `/` respecting standard operator precedence, no parentheses.

**Approach:** Single pass with a stack — push each number (applying `*`/`/` immediately against the previous stack value since they have higher precedence), and let `+`/`-` simply push/negate onto the stack for a final summation.

```java
int calculate(String s) {
    Deque<Integer> stack = new ArrayDeque<>();
    int num = 0;
    char sign = '+';
    for (int i = 0; i < s.length(); i++) {
        char c = s.charAt(i);
        if (Character.isDigit(c)) num = num * 10 + (c - '0');
        if (!Character.isDigit(c) && c != ' ' || i == s.length() - 1) {
            if (sign == '+') stack.push(num);
            else if (sign == '-') stack.push(-num);
            else if (sign == '*') stack.push(stack.pop() * num);
            else if (sign == '/') stack.push(stack.pop() / num);
            sign = c; num = 0;
        }
    }
    int result = 0;
    for (int n : stack) result += n;
    return result;
}
```
**Complexity:** O(n). **Pattern:** "resolve high-precedence operators immediately, defer low-precedence ones to a final sum" — a clean single-stack technique avoiding the need for two separate stacks (operators + operands) that a more general expression parser would require.

#### H-70. Peak Index in a Mountain Array

**Problem:** Given a "mountain array" (strictly increasing then strictly decreasing), find the peak index.

**Approach:** Binary search comparing each midpoint against its right neighbor — if increasing, the peak is to the right; if decreasing, the peak is at or before the midpoint (same core idea as [Find Peak Element](#d-1-linkedin-find-peak-element), specialized for the guaranteed-unimodal case).

```java
int peakIndexInMountainArray(int[] arr) {
    int lo = 0, hi = arr.length - 1;
    while (lo < hi) {
        int mid = (lo + hi) / 2;
        if (arr[mid] < arr[mid + 1]) lo = mid + 1; else hi = mid;
    }
    return lo;
}
```
**Complexity:** O(log n). **Pattern:** binary search on a unimodal (single-peak) sequence — recognizing "mountain array" as a stronger guarantee than general "peak element" simplifies the reasoning but uses an identical code shape.

#### H-71. Find Minimum in Rotated Sorted Array

**Problem:** Find the minimum element in a rotated sorted array (no duplicates), in O(log n).

**Approach:** Binary search comparing the midpoint against the rightmost element — if the midpoint is greater, the minimum is to the right; otherwise it's at or before the midpoint.

```java
int findMin(int[] nums) {
    int lo = 0, hi = nums.length - 1;
    while (lo < hi) {
        int mid = (lo + hi) / 2;
        if (nums[mid] > nums[hi]) lo = mid + 1; else hi = mid;
    }
    return nums[lo];
}
```
**Complexity:** O(log n). **Pattern:** binary search comparing against the RIGHT boundary (not the left) — a subtle but important choice, since comparing against `nums[lo]` instead would fail to correctly narrow the search in some rotation cases.

#### H-72. Counting Bits

**Problem:** For every number from 0 to `n`, count the number of 1 bits in its binary representation, in O(n) total time.

**Approach:** DP using the relationship `bits[i] = bits[i >> 1] + (i & 1)` — the bit count of `i` equals the bit count of `i` with its last bit removed, plus whether that last bit was 1.

```java
int[] countBits(int n) {
    int[] result = new int[n + 1];
    for (int i = 1; i <= n; i++) {
        result[i] = result[i >> 1] + (i & 1);
    }
    return result;
}
```
**Complexity:** O(n). **Pattern:** DP building on previously-computed smaller subproblems via a bit-shift relationship — far more efficient than counting bits independently for each number (which would be O(n log n) using Java's built-in `Integer.bitCount` in a loop, or O(n × 32) with manual bit-by-bit counting).

#### H-73. Missing Number

**Problem:** Given an array containing `n` distinct numbers from `0` to `n` with exactly one missing, find the missing number.

**Approach:** XOR-based — XOR all indices `0..n` with all array values; matching pairs cancel out (XOR of a number with itself is 0), leaving only the missing number.

```java
int missingNumber(int[] nums) {
    int result = nums.length;
    for (int i = 0; i < nums.length; i++) {
        result ^= i ^ nums[i];
    }
    return result;
}
```
**Complexity:** O(n) time, O(1) space. **Pattern:** XOR cancellation — an elegant alternative to the "sum formula minus actual sum" approach (which risks overflow for large `n`); the XOR approach avoids that risk entirely.

#### H-74. Single Number (Basic XOR)

**Problem:** Given an array where every element appears twice except one, find that single element.

**Approach:** XOR all elements together — pairs cancel to zero, leaving only the unpaired element.

```java
int singleNumber(int[] nums) {
    int result = 0;
    for (int num : nums) result ^= num;
    return result;
}
```
**Complexity:** O(n) time, O(1) space. **Pattern:** the simplest XOR-cancellation problem — the foundational case that [Single Number II](#e-10-qualcomm-single-number-ii-bit-counting-every-element-appears-3-times-except-one) (elements appearing 3 times) generalizes from using per-bit counting instead of simple XOR (since XOR alone only cancels PAIRS, not triples).

#### H-75. Power of Two (Bit Trick)

**Problem:** Determine if an integer is a power of two, without loops or recursion.

**Approach:** A power of two has exactly one bit set; `n & (n-1)` clears the lowest set bit, so a power of two becomes 0 after this operation (and the number itself must be positive).

```java
boolean isPowerOfTwo(int n) {
    return n > 0 && (n & (n - 1)) == 0;
}
```
**Complexity:** O(1). **Pattern:** the `n & (n-1)` "clear lowest set bit" trick — one of the most useful bit-manipulation idioms, also used to count set bits (repeatedly clearing the lowest bit until reaching zero counts how many bits were set).

#### H-76. Maximal Rectangle (Reusing Largest Rectangle in Histogram)

**Problem:** Given a binary matrix, find the area of the largest rectangle containing only 1s.

**Approach:** Treat each row as the "ground level" of a histogram, where each column's height is the number of consecutive 1s ending at that row (0 if the current cell is 0); run [Largest Rectangle in Histogram](#h-61-largest-rectangle-in-histogram) on each row's derived histogram and track the overall maximum.

```java
int maximalRectangle(char[][] matrix) {
    if (matrix.length == 0) return 0;
    int cols = matrix[0].length;
    int[] heights = new int[cols];
    int maxArea = 0;
    for (char[] row : matrix) {
        for (int j = 0; j < cols; j++) {
            heights[j] = row[j] == '1' ? heights[j] + 1 : 0;
        }
        maxArea = Math.max(maxArea, largestRectangleArea(heights));
    }
    return maxArea;
}
private int largestRectangleArea(int[] heights) {
    Deque<Integer> stack = new ArrayDeque<>();
    int maxArea = 0;
    for (int i = 0; i <= heights.length; i++) {
        int h = (i == heights.length) ? 0 : heights[i];
        while (!stack.isEmpty() && heights[stack.peek()] >= h) {
            int height = heights[stack.pop()];
            int width = stack.isEmpty() ? i : i - stack.peek() - 1;
            maxArea = Math.max(maxArea, height * width);
        }
        stack.push(i);
    }
    return maxArea;
}
```
**Complexity:** O(rows × cols). **Pattern:** "reduce a 2D problem to repeated applications of a known 1D solution" — a powerful problem-decomposition strategy; recognizing that each matrix row can be transformed into a histogram-shaped subproblem is the key insight, directly reusing H-61's function unchanged.

#### H-77. Two Sum II (Sorted Array Input)

**Problem:** Given a SORTED array, find two numbers that sum to a target, returning 1-indexed positions.

**Approach:** Two pointers from both ends — since the array is sorted, move the low pointer up if the sum is too small, or the high pointer down if too large (no hashmap needed, unlike the unsorted [Two Sum](#g-1-two-sum), because sortedness provides the same information more cheaply).

```java
int[] twoSum(int[] numbers, int target) {
    int lo = 0, hi = numbers.length - 1;
    while (lo < hi) {
        int sum = numbers[lo] + numbers[hi];
        if (sum == target) return new int[]{lo + 1, hi + 1};
        else if (sum < target) lo++;
        else hi--;
    }
    return new int[]{-1, -1};
}
```
**Complexity:** O(n) time, O(1) space — an improvement over the O(n) TIME but O(n) SPACE hashmap approach used when the array isn't sorted. **Pattern:** exploiting a "sorted" precondition to replace a hashmap with two pointers — always check if input is sorted (or can cheaply be sorted) before defaulting to a hashmap-based solution.

#### H-78. Maximum Subarray (Kadane's Algorithm)

**Problem:** Find the contiguous subarray with the largest sum.

**Approach:** Kadane's algorithm — track the best sum ending at the current position (either extend the previous subarray or start fresh here), and the best sum seen anywhere.

```java
int maxSubArray(int[] nums) {
    int currentSum = nums[0], maxSum = nums[0];
    for (int i = 1; i < nums.length; i++) {
        currentSum = Math.max(nums[i], currentSum + nums[i]);
        maxSum = Math.max(maxSum, currentSum);
    }
    return maxSum;
}
```
**Complexity:** O(n) time, O(1) space. **Pattern:** Kadane's algorithm — arguably THE most foundational "running local optimum vs. global optimum" DP pattern in all of interview prep; nearly every 1D DP problem in this guide is a variation on this same "extend or restart" decision.

#### H-79. Coin Change II (Count the Number of Ways)

**Problem:** Given coin denominations and a target amount, count the number of DISTINCT combinations (not permutations) that make up the amount.

**Approach:** DP iterating coins in the OUTER loop and amounts in the inner loop — this ordering ensures combinations (order doesn't matter), whereas the reverse ordering would count permutations (order matters) instead, a frequently-confused subtlety.

```java
int change(int amount, int[] coins) {
    int[] dp = new int[amount + 1];
    dp[0] = 1;
    for (int coin : coins) {
        for (int i = coin; i <= amount; i++) {
            dp[i] += dp[i - coin];
        }
    }
    return dp[amount];
}
```
**Complexity:** O(amount × coins). **Pattern:** the loop-ORDER determines combinations vs. permutations in counting DPs — a subtle but frequently-tested distinction; swapping the loop order (amount outer, coins inner) would instead count ordered sequences of coins (a different, related problem).

#### H-80. Unique Paths (Basic Grid Counting, No Obstacles)

**Problem:** Count the number of unique paths from top-left to bottom-right of an `m×n` grid, moving only right or down.

**Approach:** DP — `dp[i][j] = dp[i-1][j] + dp[i][j-1]` (the simpler ancestor of [Unique Paths II](#e-9-nvidia-unique-paths-ii-grid-dp-with-obstacles) without obstacle handling); can also be solved combinatorially as `C(m+n-2, m-1)`.

```java
int uniquePaths(int m, int n) {
    int[][] dp = new int[m][n];
    for (int i = 0; i < m; i++) dp[i][0] = 1;
    for (int j = 0; j < n; j++) dp[0][j] = 1;
    for (int i = 1; i < m; i++)
        for (int j = 1; j < n; j++)
            dp[i][j] = dp[i - 1][j] + dp[i][j - 1];
    return dp[m - 1][n - 1];
}
```
**Complexity:** O(m × n) for the DP approach (O(1) with the combinatorial formula, a good follow-up to mention). **Pattern:** foundational grid-path-counting DP — the base case this guide's Unique Paths II variant builds on by adding obstacle handling.

#### H-81. Balanced Binary Tree

**Problem:** Determine if a binary tree is height-balanced (every node's two subtrees differ in height by at most 1).

**Approach:** Bottom-up recursion returning `-1` as a sentinel the moment any subtree is found unbalanced, short-circuiting further unnecessary work (rather than the naive top-down approach that recomputes height repeatedly, giving O(n²) instead of O(n)).

```java
boolean isBalanced(TreeNode root) { return height(root) != -1; }
private int height(TreeNode node) {
    if (node == null) return 0;
    int left = height(node.left);
    if (left == -1) return -1;
    int right = height(node.right);
    if (right == -1) return -1;
    if (Math.abs(left - right) > 1) return -1;
    return 1 + Math.max(left, right);
}
```
**Complexity:** O(n) — the sentinel-based early-exit is what achieves this, versus O(n²) for a naive top-down recomputation. **Pattern:** "combine height computation with validity checking in one bottom-up pass using a sentinel value" — the same underlying efficiency insight as [Diameter of Binary Tree](#g-16-diameter-of-binary-tree)'s single-pass height+diameter tracking.

#### H-82. Same Tree

**Problem:** Determine if two binary trees are structurally identical with the same node values.

**Approach:** Recursive paired comparison — both null is true, one null is false, otherwise compare values and recurse on both children pairs.

```java
boolean isSameTree(TreeNode p, TreeNode q) {
    if (p == null || q == null) return p == q;
    return p.val == q.val && isSameTree(p.left, q.left) && isSameTree(p.right, q.right);
}
```
**Complexity:** O(n). **Pattern:** the most basic paired-tree-recursion template — the direct ancestor of [Subtree of Another Tree](#c-8-amazon-subtree-of-another-tree)'s `isSameTree` helper and [Symmetric Tree](#h-20-symmetric-tree)'s mirrored comparison.

#### H-83. Invert Binary Tree

**Problem:** Invert a binary tree (mirror it, swapping every left/right child pair).

**Approach:** Recursively swap each node's left and right children, then recurse into both (now-swapped) subtrees.

```java
TreeNode invertTree(TreeNode root) {
    if (root == null) return null;
    TreeNode temp = root.left;
    root.left = invertTree(root.right);
    root.right = invertTree(temp);
    return root;
}
```
**Complexity:** O(n). **Pattern:** simple recursive tree transformation — famously the "the person who created Homebrew couldn't invert a binary tree on a whiteboard" viral interview question; despite the notoriety, it remains a genuinely common warm-up question testing basic recursive tree manipulation fluency.

#### H-84. Maximum Depth of Binary Tree

**Problem:** Find the maximum depth (number of nodes on the longest root-to-leaf path) of a binary tree.

**Approach:** Recursive — the depth of a node is 1 plus the maximum depth of its two children.

```java
int maxDepth(TreeNode root) {
    if (root == null) return 0;
    return 1 + Math.max(maxDepth(root.left), maxDepth(root.right));
}
```
**Complexity:** O(n). **Pattern:** the simplest possible tree recursion — often the very FIRST tree question a candidate encounters, and a useful sanity check for whether basic recursive thinking is solid before moving to harder tree problems.

#### H-85. Path Sum (Basic Root-to-Leaf Existence Check)

**Problem:** Determine if the tree has a root-to-leaf path whose values sum to a target (simpler existence-only version of [Path Sum II](#h-16-path-sum-ii-all-root-to-leaf-paths-summing-to-target), which collects ALL such paths).

**Approach:** Recursive — at each leaf, check if the remaining target equals the leaf's value; otherwise recurse into children with the reduced target.

```java
boolean hasPathSum(TreeNode root, int targetSum) {
    if (root == null) return false;
    if (root.left == null && root.right == null) return targetSum == root.val;
    return hasPathSum(root.left, targetSum - root.val) || hasPathSum(root.right, targetSum - root.val);
}
```
**Complexity:** O(n). **Pattern:** the existence-only ancestor of Path Sum II — a good example of how the SAME recursive shape can be adapted to either return a boolean (stop at the first match) or collect all matches (continue exploring and copy the path), depending on what the question actually asks for.

#### H-86. Video Stitching

**Problem:** Given video clips as `[start, end]` intervals, find the minimum number of clips needed to cover the full range `[0, target]` (or -1 if impossible).

**Approach:** Greedy interval-covering — similar in spirit to Jump Game II ([G-35](#g-35-jump-game-ii-minimum-jumps)): for each currently-reachable endpoint, find the clip that extends coverage the farthest, incrementing the "clips used" count each time the current boundary is exhausted.

```java
int videoStitching(int[][] clips, int target) {
    int[] maxReach = new int[target];
    for (int[] clip : clips) {
        if (clip[0] < target) maxReach[clip[0]] = Math.max(maxReach[clip[0]], clip[1]);
    }
    int clipsUsed = 0, currentEnd = 0, farthest = 0;
    for (int i = 0; i < target; i++) {
        farthest = Math.max(farthest, maxReach[i]);
        if (i == currentEnd) {
            if (farthest <= i) return -1; // stuck, no clip extends coverage
            clipsUsed++;
            currentEnd = farthest;
        }
    }
    return clipsUsed;
}
```
**Complexity:** O(target + clips). **Pattern:** yet another instance of the "greedy farthest-reachable boundary" meta-pattern (shared with Jump Game II and the basic Jump Game) — recognizing that "cover a range with minimum intervals" is structurally the same problem as "reach the end with minimum jumps."

#### H-87. Container With Most Water

**Problem:** Given heights representing vertical lines, find two lines that together with the x-axis form the container holding the most water.

**Approach:** Two pointers from both ends — move the pointer at the SHORTER line inward (since the shorter line is always the bottleneck limiting the area, moving the taller one can never improve the result).

```java
int maxArea(int[] height) {
    int lo = 0, hi = height.length - 1, best = 0;
    while (lo < hi) {
        int area = Math.min(height[lo], height[hi]) * (hi - lo);
        best = Math.max(best, area);
        if (height[lo] < height[hi]) lo++; else hi--;
    }
    return best;
}
```
**Complexity:** O(n). **Pattern:** two pointers with a provably-correct greedy elimination rule ("always move the shorter side") — one of the most elegant O(n) two-pointer solutions in common rotation, frequently used to test whether candidates can articulate WHY moving the shorter pointer is safe (it can never be part of a better solution than what's already been checked).

#### H-88. Find All Anagrams in a String

**Problem:** Given strings `s` and `p`, find all start indices of `p`'s anagrams in `s`.

**Approach:** Fixed-size sliding window (size = `p.length()`) with a 26-element frequency array comparison — maintain a running frequency count of the window and compare against `p`'s frequency array.

```java
List<Integer> findAnagrams(String s, String p) {
    List<Integer> result = new ArrayList<>();
    if (s.length() < p.length()) return result;
    int[] pCount = new int[26], windowCount = new int[26];
    for (char c : p.toCharArray()) pCount[c - 'a']++;
    for (int i = 0; i < s.length(); i++) {
        windowCount[s.charAt(i) - 'a']++;
        if (i >= p.length()) windowCount[s.charAt(i - p.length()) - 'a']--;
        if (i >= p.length() - 1 && Arrays.equals(pCount, windowCount)) result.add(i - p.length() + 1);
    }
    return result;
}
```
**Complexity:** O(n) (the `Arrays.equals` check on fixed-size-26 arrays is O(1) per call, not O(n)). **Pattern:** fixed-size sliding window with frequency-array comparison — the same skeleton as [OA-1](#oa-1-substrings-of-size-k-with-k-distinct-characters), adapted to compare against a target frequency profile rather than just checking distinctness.

#### H-89. Permutation in String

**Problem:** Given strings `s1` and `s2`, determine if `s2` contains a permutation of `s1` (i.e., one of `s1`'s anagrams appears as a substring).

**Approach:** Identical sliding-window-with-frequency-array technique as [Find All Anagrams](#h-88-find-all-anagrams-in-a-string), just returning a boolean at the first match instead of collecting all match indices.

```java
boolean checkInclusion(String s1, String s2) {
    if (s2.length() < s1.length()) return false;
    int[] s1Count = new int[26], windowCount = new int[26];
    for (char c : s1.toCharArray()) s1Count[c - 'a']++;
    for (int i = 0; i < s2.length(); i++) {
        windowCount[s2.charAt(i) - 'a']++;
        if (i >= s1.length()) windowCount[s2.charAt(i - s1.length()) - 'a']--;
        if (i >= s1.length() - 1 && Arrays.equals(s1Count, windowCount)) return true;
    }
    return false;
}
```
**Complexity:** O(n). **Pattern:** the exact same technique as H-88 with a different return type — another good example of recognizing that two differently-worded questions ("find all anagram positions" vs. "does any anagram exist") are the identical underlying algorithm.

#### H-90. Continuous Subarray Sum (Multiple of K)

**Problem:** Determine if the array has a contiguous subarray of length at least 2 whose sum is a multiple of `k`.

**Approach:** Prefix sum modulo `k`, tracking the FIRST index each remainder was seen — if the same remainder reappears at least 2 indices later, the subarray between them sums to a multiple of `k` (since equal remainders mean the difference is divisible by `k`).

```java
boolean checkSubarraySum(int[] nums, int k) {
    Map<Integer, Integer> remainderFirstIndex = new HashMap<>();
    remainderFirstIndex.put(0, -1); // handles a subarray starting at index 0
    int runningSum = 0;
    for (int i = 0; i < nums.length; i++) {
        runningSum += nums[i];
        int remainder = k == 0 ? runningSum : runningSum % k;
        if (remainderFirstIndex.containsKey(remainder)) {
            if (i - remainderFirstIndex.get(remainder) >= 2) return true;
        } else {
            remainderFirstIndex.put(remainder, i);
        }
    }
    return false;
}
```
**Complexity:** O(n). **Pattern:** prefix sum modulo K with "first occurrence" tracking — a distinctive number-theory-flavored variant of the prefix-sum-hashmap pattern (compare to [Subarray Sum Equals K](#d-19-common--multi-company-subarray-sum-equals-k)), using remainders instead of raw sums as the hashmap key.

#### H-91. House Robber II (Circular Arrangement)

**Problem:** Same as [House Robber](#g-27-house-robber), but houses are arranged in a circle (the first and last houses are adjacent).

**Approach:** Since the first and last houses can't both be robbed, run the standard House Robber DP twice — once excluding the last house, once excluding the first house — and take the maximum of the two results.

```java
int rob(int[] nums) {
    int n = nums.length;
    if (n == 1) return nums[0];
    return Math.max(robLinear(nums, 0, n - 2), robLinear(nums, 1, n - 1));
}
private int robLinear(int[] nums, int start, int end) {
    int prev2 = 0, prev1 = 0;
    for (int i = start; i <= end; i++) {
        int cur = Math.max(prev1, prev2 + nums[i]);
        prev2 = prev1; prev1 = cur;
    }
    return prev1;
}
```
**Complexity:** O(n). **Pattern:** "reduce a circular constraint to two linear subproblems" — a widely reusable technique whenever a problem has a circular/wraparound adjacency constraint; running the same linear solution twice with different boundary exclusions is simpler than adapting the DP itself to handle circularity directly.

#### H-92. Delete Node in a BST

**Problem:** Given a BST and a key, delete the node with that key, maintaining BST properties.

**Approach:** Three cases — no children (simply remove), one child (replace with that child), two children (replace the node's value with its in-order successor — the minimum of the right subtree — then recursively delete that successor from the right subtree).

```java
TreeNode deleteNode(TreeNode root, int key) {
    if (root == null) return null;
    if (key < root.val) root.left = deleteNode(root.left, key);
    else if (key > root.val) root.right = deleteNode(root.right, key);
    else {
        if (root.left == null) return root.right;
        if (root.right == null) return root.left;
        TreeNode successor = root.right;
        while (successor.left != null) successor = successor.left;
        root.val = successor.val;
        root.right = deleteNode(root.right, successor.val);
    }
    return root;
}
```
**Complexity:** O(h) where h is tree height. **Pattern:** the "replace with in-order successor" technique — the standard BST-deletion algorithm; a common follow-up asks about using the in-order PREDECESSOR (max of left subtree) instead, which works equally well and is worth mentioning as an equivalent alternative.

#### H-93. Binary Tree Right Side View

**Problem:** Return the values visible when looking at a binary tree from the right side (the rightmost node at each level).

**Approach:** BFS level-order traversal, taking only the LAST node processed at each level (or DFS visiting right-before-left, taking the first node encountered at each new depth).

```java
List<Integer> rightSideView(TreeNode root) {
    List<Integer> result = new ArrayList<>();
    if (root == null) return result;
    Queue<TreeNode> queue = new LinkedList<>();
    queue.offer(root);
    while (!queue.isEmpty()) {
        int size = queue.size();
        for (int i = 0; i < size; i++) {
            TreeNode node = queue.poll();
            if (i == size - 1) result.add(node.val); // last node in this level
            if (node.left != null) queue.offer(node.left);
            if (node.right != null) queue.offer(node.right);
        }
    }
    return result;
}
```
**Complexity:** O(n). **Pattern:** BFS level-order taking the boundary element per level — the same overall skeleton as Zigzag Level Order Traversal, just extracting a different element (last instead of alternating direction) per level.

#### H-94. Sum Root to Leaf Numbers

**Problem:** Each root-to-leaf path represents a number (concatenating digits); sum all such numbers across the tree.

**Approach:** DFS carrying a running number (`currentNumber * 10 + node.val` at each step), adding to the total sum when a leaf is reached.

```java
int sumNumbers(TreeNode root) { return dfs(root, 0); }
private int dfs(TreeNode node, int currentNumber) {
    if (node == null) return 0;
    currentNumber = currentNumber * 10 + node.val;
    if (node.left == null && node.right == null) return currentNumber;
    return dfs(node.left, currentNumber) + dfs(node.right, currentNumber);
}
```
**Complexity:** O(n). **Pattern:** DFS carrying accumulated state down the recursion (rather than up) — a distinctive style from bottom-up tree DP; the "build the number as you descend, finalize at the leaf" pattern reappears in many path-accumulation tree problems.

#### H-95. Binary Tree Paths (Root-to-Leaf as Strings)

**Problem:** Return all root-to-leaf paths as strings (e.g., `"1->2->5"`).

**Approach:** DFS with backtracking, building a path string incrementally, adding it to results at each leaf.

```java
List<String> binaryTreePaths(TreeNode root) {
    List<String> result = new ArrayList<>();
    if (root != null) dfs(root, String.valueOf(root.val), result);
    return result;
}
private void dfs(TreeNode node, String path, List<String> result) {
    if (node.left == null && node.right == null) { result.add(path); return; }
    if (node.left != null) dfs(node.left, path + "->" + node.left.val, result);
    if (node.right != null) dfs(node.right, path + "->" + node.right.val, result);
}
```
**Complexity:** O(n²) worst case (string concatenation costs), O(n) tree traversal itself. **Pattern:** DFS with string-building instead of a mutable list — passing an immutable growing string avoids needing explicit backtracking (unlike [Path Sum II](#h-16-path-sum-ii-all-root-to-leaf-paths-summing-to-target)'s mutable list approach), trading a small amount of string-copy overhead for simpler code.

#### H-96. Count Good Nodes in a Binary Tree

**Problem:** A node is "good" if no ancestor has a value greater than it (the root is always good). Count good nodes.

**Approach:** DFS carrying the maximum value seen so far along the current root-to-node path; a node is good if its value is ≥ that running maximum.

```java
int goodNodes(TreeNode root) { return dfs(root, Integer.MIN_VALUE); }
private int dfs(TreeNode node, int maxSoFar) {
    if (node == null) return 0;
    int count = node.val >= maxSoFar ? 1 : 0;
    int newMax = Math.max(maxSoFar, node.val);
    return count + dfs(node.left, newMax) + dfs(node.right, newMax);
}
```
**Complexity:** O(n). **Pattern:** DFS carrying a running "best so far along this path" value — structurally similar to Sum Root to Leaf Numbers' accumulated-state style, applied to a max-tracking condition instead of digit concatenation.

#### H-97. Reverse Linked List II (Reverse a Sublist Between Positions)

**Problem:** Reverse a linked list's nodes from position `left` to position `right` (1-indexed), in one pass.

**Approach:** Advance to the node just before position `left`, then repeatedly move the node right after it to the front of the sublist being reversed (the "insertion-style" in-place reversal technique).

```java
ListNode reverseBetween(ListNode head, int left, int right) {
    ListNode dummy = new ListNode(0, head);
    ListNode prev = dummy;
    for (int i = 0; i < left - 1; i++) prev = prev.next;
    ListNode current = prev.next;
    for (int i = 0; i < right - left; i++) {
        ListNode next = current.next;
        current.next = next.next;
        next.next = prev.next;
        prev.next = next;
    }
    return dummy.next;
}
```
**Complexity:** O(n) time, single pass, O(1) extra space. **Pattern:** "move the next node to the front of the sublist" in-place reversal — a distinctive technique from the more commonly-known "reverse the whole list" approach, useful whenever only a SUBLIST needs reversing without disturbing the rest.

#### H-98. Middle of the Linked List

**Problem:** Return the middle node of a linked list (the second middle if there are two, by convention).

**Approach:** Slow/fast pointers — when fast reaches the end, slow is at the middle.

```java
ListNode middleNode(ListNode head) {
    ListNode slow = head, fast = head;
    while (fast != null && fast.next != null) {
        slow = slow.next;
        fast = fast.next.next;
    }
    return slow;
}
```
**Complexity:** O(n) time, single pass, O(1) space. **Pattern:** the simplest application of the slow/fast pointer technique — the same core mechanism underlying cycle detection, palindrome checking, and finding the Nth-from-end node, all covered elsewhere in this guide.

#### H-99. Intersection of Two Linked Lists

**Problem:** Find the node at which two singly linked lists intersect (or null if they don't), in O(1) extra space.

**Approach:** Two pointers, each starting at one list's head; when a pointer reaches the end of its list, redirect it to the OTHER list's head. Both pointers travel the same total distance (`lenA + lenB`) and will meet exactly at the intersection point (or both reach null simultaneously if there's no intersection).

```java
ListNode getIntersectionNode(ListNode headA, ListNode headB) {
    ListNode a = headA, b = headB;
    while (a != b) {
        a = (a == null) ? headB : a.next;
        b = (b == null) ? headA : b.next;
    }
    return a;
}
```
**Complexity:** O(m + n) time, O(1) space. **Pattern:** the "switch heads on reaching the end" technique — an elegant way to equalize two pointers' effective starting positions without first computing and comparing list lengths explicitly, though the length-comparison approach is an equally valid and sometimes more intuitive alternative to mention.

#### H-100. Rotate List

**Problem:** Rotate a linked list to the right by `k` places.

**Approach:** Compute the list length, connect the tail to the head to form a ring, then break the ring at the correct new position (`length - k % length` steps from the original head).

```java
ListNode rotateRight(ListNode head, int k) {
    if (head == null || head.next == null) return head;
    int length = 1;
    ListNode tail = head;
    while (tail.next != null) { tail = tail.next; length++; }
    tail.next = head; // form a ring
    int stepsToNewTail = length - (k % length);
    ListNode newTail = head;
    for (int i = 1; i < stepsToNewTail; i++) newTail = newTail.next;
    ListNode newHead = newTail.next;
    newTail.next = null; // break the ring
    return newHead;
}
```
**Complexity:** O(n) time, O(1) space. **Pattern:** "form a ring, then break it at the right place" — a clean way to handle rotation without separately tracking wraparound logic; the `k % length` step is essential to avoid unnecessary full loops when `k` exceeds the list length.

#### H-101. Remove Duplicates from Sorted List II (Remove ALL Duplicated Values)

**Problem:** Given a sorted linked list, remove all nodes that have duplicate values, leaving only distinct values (unlike a simpler variant that keeps one copy of each duplicated value).

**Approach:** A dummy head simplifies removing nodes at the very start; for each run of equal values, check if the run has length > 1, and if so skip the entire run.

```java
ListNode deleteDuplicates(ListNode head) {
    ListNode dummy = new ListNode(0, head);
    ListNode prev = dummy;
    ListNode current = head;
    while (current != null) {
        if (current.next != null && current.val == current.next.val) {
            int duplicateVal = current.val;
            while (current != null && current.val == duplicateVal) current = current.next;
            prev.next = current; // skip the entire run
        } else {
            prev = current;
            current = current.next;
        }
    }
    return dummy.next;
}
```
**Complexity:** O(n) time, single pass, O(1) extra space. **Pattern:** dummy head + "detect a run, skip it entirely if longer than 1" — a distinctive variant of the basic duplicate-removal problem that requires DELETING duplicated values entirely rather than collapsing them to one instance, a subtlety worth clarifying with the interviewer before coding.

#### H-102. Partition List (Around a Pivot Value)

**Problem:** Given a linked list and a value `x`, partition it so all nodes less than `x` come before all nodes greater than or equal to `x`, preserving the original relative order within each partition.

**Approach:** Build two separate chains (less-than and greater-or-equal) while traversing once, then splice the greater-or-equal chain onto the end of the less-than chain.

```java
ListNode partition(ListNode head, int x) {
    ListNode lessDummy = new ListNode(0), lessTail = lessDummy;
    ListNode greaterDummy = new ListNode(0), greaterTail = greaterDummy;
    while (head != null) {
        if (head.val < x) { lessTail.next = head; lessTail = lessTail.next; }
        else { greaterTail.next = head; greaterTail = greaterTail.next; }
        head = head.next;
    }
    greaterTail.next = null;
    lessTail.next = greaterDummy.next;
    return lessDummy.next;
}
```
**Complexity:** O(n) time, single pass, O(1) extra space (excluding output). **Pattern:** "maintain two separate chains, splice at the end" — the exact same underlying technique as [Odd Even Linked List](#h-45-odd-even-linked-list), applied to a value-based partition instead of a position-based one.

#### H-103. Sqrt(x) (Integer Square Root via Binary Search)

**Problem:** Compute the integer square root of a non-negative integer (rounded down), without using built-in power/sqrt functions.

**Approach:** Binary search on the answer range `[0, x]`, checking `mid * mid <= x`.

```java
int mySqrt(int x) {
    if (x < 2) return x;
    long lo = 1, hi = x;
    while (lo < hi) {
        long mid = lo + (hi - lo + 1) / 2;
        if (mid * mid <= x) lo = mid; else hi = mid - 1;
    }
    return (int) lo;
}
```
**Complexity:** O(log x). **Pattern:** binary search for an integer square root — using `long` for the midpoint's square avoids `int` overflow for large `x`, a subtle but important correctness detail; the `+1` in the midpoint calculation avoids an infinite loop by always rounding the search upward when narrowing to `lo`.

#### H-104. Search Insert Position

**Problem:** Given a sorted array and a target, return the index if found, or the index where it would be inserted to keep the array sorted.

**Approach:** Standard binary search — when the loop ends without finding an exact match, `lo` naturally equals the correct insertion position.

```java
int searchInsert(int[] nums, int target) {
    int lo = 0, hi = nums.length - 1;
    while (lo <= hi) {
        int mid = (lo + hi) / 2;
        if (nums[mid] == target) return mid;
        else if (nums[mid] < target) lo = mid + 1;
        else hi = mid - 1;
    }
    return lo;
}
```
**Complexity:** O(log n). **Pattern:** the most foundational binary search template — worth having memorized so cold that every subsequent binary-search variant in this guide (rotated arrays, answer-space search, floor/ceiling search) feels like a small, recognizable adaptation of this base case.

#### H-105. First Bad Version

**Problem:** Given `n` versions and an API `isBadVersion(version)`, find the first bad version using the minimum number of API calls (versions after the first bad one are all also bad).

**Approach:** Binary search on the monotonic "is bad" property — identical shape to the "binary search the answer" pattern, just with the feasibility check being an external API call instead of a computed function.

```java
int firstBadVersion(int n) {
    int lo = 1, hi = n;
    while (lo < hi) {
        int mid = lo + (hi - lo) / 2; // avoids overflow vs. (lo+hi)/2 for very large n
        if (isBadVersion(mid)) hi = mid; else lo = mid + 1;
    }
    return lo;
}
```
**Complexity:** O(log n) API calls. **Pattern:** binary search minimizing EXPENSIVE/EXTERNAL calls (here, an API call rather than a cheap local computation) — reinforces that "binary search the answer" applies just as well when the feasibility check is costly or externally provided, not just when it's a fast local function.

#### H-106. Valid Palindrome (Alphanumeric Only, Case-Insensitive)

**Problem:** Determine if a string is a palindrome considering only alphanumeric characters, ignoring case.

**Approach:** Two pointers from both ends, skipping non-alphanumeric characters, comparing lowercased characters.

```java
boolean isPalindrome(String s) {
    int lo = 0, hi = s.length() - 1;
    while (lo < hi) {
        while (lo < hi && !Character.isLetterOrDigit(s.charAt(lo))) lo++;
        while (lo < hi && !Character.isLetterOrDigit(s.charAt(hi))) hi--;
        if (Character.toLowerCase(s.charAt(lo)) != Character.toLowerCase(s.charAt(hi))) return false;
        lo++; hi--;
    }
    return true;
}
```
**Complexity:** O(n) time, O(1) space. **Pattern:** two pointers with a "skip invalid characters" inner loop — a common real-world text-processing variant of the basic palindrome check, testing careful handling of the character-filtering requirement alongside the core two-pointer comparison.

#### H-107. Combination Sum II (With Duplicates, No Reuse)

**Problem:** Given candidates that MAY contain duplicates, find all unique combinations summing to a target, each candidate used at most once.

**Approach:** Sort first, backtrack passing `i+1` (no reuse, unlike the basic Combination Sum), and skip a duplicate value at the same recursion depth (the same duplicate-skip rule as [Subsets II](#h-23-subsets-ii-with-duplicates) and [Permutations II](#h-22-permutations-ii-with-duplicates)).

```java
List<List<Integer>> combinationSum2(int[] candidates, int target) {
    Arrays.sort(candidates);
    List<List<Integer>> results = new ArrayList<>();
    backtrack(candidates, target, 0, new ArrayList<>(), results);
    return results;
}
private void backtrack(int[] candidates, int remaining, int start, List<Integer> current, List<List<Integer>> results) {
    if (remaining == 0) { results.add(new ArrayList<>(current)); return; }
    for (int i = start; i < candidates.length; i++) {
        if (candidates[i] > remaining) break;
        if (i > start && candidates[i] == candidates[i - 1]) continue; // skip duplicate at this depth
        current.add(candidates[i]);
        backtrack(candidates, remaining - candidates[i], i + 1, current, results);
        current.remove(current.size() - 1);
    }
}
```
**Complexity:** O(2^n) worst case, heavily pruned. **Pattern:** combines THREE techniques from earlier in this guide simultaneously — no-reuse via `i+1` (unlike basic Combination Sum's `i`), duplicate-skipping via `i > start` (like Subsets II), and early-break pruning on a sorted array (like Combination Sum III) — a good capstone question showing how these individually-simple techniques compose.

#### H-108. Recover Binary Search Tree (Two Swapped Nodes)

**Problem:** Exactly two nodes of a BST were swapped by mistake; recover the tree without changing its structure.

**Approach:** In-order traversal of a valid BST is strictly increasing; track the previous node during traversal and identify the (up to two) places where the sequence decreases — these mark the two swapped nodes.

```java
private TreeNode first, second, prev;
void recoverTree(TreeNode root) {
    inorder(root);
    int temp = first.val; first.val = second.val; second.val = temp;
}
private void inorder(TreeNode node) {
    if (node == null) return;
    inorder(node.left);
    if (prev != null && prev.val > node.val) {
        if (first == null) first = prev;
        second = node;
    }
    prev = node;
    inorder(node.right);
}
```
**Complexity:** O(n) time, O(h) recursion space. **Pattern:** "in-order traversal violation detection" — leveraging the BST in-order-is-sorted invariant to find anomalies; the subtlety of handling both adjacent swaps (one violation) and non-adjacent swaps (two violations) with the same `first`/`second` tracking logic is the crux of this problem.

#### H-109. Text Justification

**Problem:** Given words and a line width, format text into fully-justified lines (each line except the last padded with spaces so it's exactly the target width, spaces distributed as evenly as possible, extra space going to the leftmost gaps).

**Approach:** Greedily pack as many words as fit on each line, then distribute spaces: for a full line, divide the total space evenly across gaps between words, giving any remainder to the leftmost gaps first; the last line and single-word lines are left-justified with trailing spaces instead.

```java
List<String> fullJustify(String[] words, int maxWidth) {
    List<String> result = new ArrayList<>();
    int i = 0;
    while (i < words.length) {
        int lineLen = words[i].length(), lastWord = i + 1;
        while (lastWord < words.length && lineLen + 1 + words[lastWord].length() <= maxWidth) {
            lineLen += 1 + words[lastWord].length();
            lastWord++;
        }
        int wordCount = lastWord - i;
        StringBuilder line = new StringBuilder();
        if (lastWord == words.length || wordCount == 1) { // last line or single word: left-justify
            for (int j = i; j < lastWord; j++) { line.append(words[j]); if (j < lastWord - 1) line.append(' '); }
            while (line.length() < maxWidth) line.append(' ');
        } else {
            int totalSpaces = maxWidth - (lineLen - (wordCount - 1)); // width minus sum of word lengths
            int spaceSlots = wordCount - 1;
            int baseSpaces = totalSpaces / spaceSlots, extraSpaces = totalSpaces % spaceSlots;
            for (int j = i; j < lastWord - 1; j++) {
                line.append(words[j]);
                int spaces = baseSpaces + (j - i < extraSpaces ? 1 : 0);
                for (int s = 0; s < spaces; s++) line.append(' ');
            }
            line.append(words[lastWord - 1]);
        }
        result.add(line.toString());
        i = lastWord;
    }
    return result;
}
```
**Complexity:** O(total characters). **Pattern:** greedy line-packing + careful space-distribution arithmetic — widely regarded as one of the most implementation-heavy "Hard" questions in common rotation, testing meticulous edge-case handling (last line, single-word lines, remainder distribution) rather than algorithmic insight.

#### H-110. Random Pick with Blacklist

**Problem:** Given `n` and a blacklist of excluded numbers, design `pick()` returning a uniformly random integer in `[0, n)` NOT in the blacklist, in O(1) time per pick after O(blacklist size) setup.

**Approach:** Remap each blacklisted number that falls within the "reduced range" `[0, n - blacklist.size())` to a non-blacklisted number from the "tail" range `[n - blacklist.size(), n)` — then `pick()` just generates a random number in the reduced range and looks up its remapped value if needed.

```java
class RandomPickWithBlacklist {
    private final int reducedRange;
    private final Map<Integer, Integer> remap = new HashMap<>();
    private final Random random = new Random();

    RandomPickWithBlacklist(int n, int[] blacklist) {
        reducedRange = n - blacklist.length;
        Set<Integer> blacklisted = new HashSet<>();
        for (int b : blacklist) blacklisted.add(b);
        int tail = reducedRange;
        for (int b : blacklist) {
            if (b < reducedRange) {
                while (blacklisted.contains(tail)) tail++; // find a non-blacklisted tail number
                remap.put(b, tail);
                tail++;
            }
        }
    }
    public int pick() {
        int candidate = random.nextInt(reducedRange);
        return remap.getOrDefault(candidate, candidate);
    }
}
```
**Complexity:** O(blacklist size) setup, O(1) per pick. **Pattern:** "shrink the range, remap blacklisted values in the reduced range to valid values in the excluded tail" — a genuinely clever, non-obvious technique for uniform random sampling with exclusions, avoiding a naive "keep re-rolling until you get a non-blacklisted number" approach that could be slow if the blacklist is large relative to `n`.

#### H-111. Best Time to Buy and Sell Stock IV (At Most K Transactions)

**Problem:** Maximize profit with at most `k` buy/sell transactions (the general form of [G-27's House Robber-style](#g-27-house-robber) state DP, generalizing [H-59's 2-transaction version](#h-59-best-time-to-buy-and-sell-stock-iii-at-most-2-transactions)).

**Approach:** 2D DP with `buy[i]` and `sell[i]` arrays for `i` from 1 to `k`, generalizing the fixed 4-variable version from H-59 into a loop over transaction count.

```java
int maxProfit(int k, int[] prices) {
    if (prices.length == 0) return 0;
    int[] buy = new int[k + 1], sell = new int[k + 1];
    Arrays.fill(buy, Integer.MIN_VALUE);
    for (int price : prices) {
        for (int i = 1; i <= k; i++) {
            buy[i] = Math.max(buy[i], sell[i - 1] - price);
            sell[i] = Math.max(sell[i], buy[i] + price);
        }
    }
    return sell[k];
}
```
**Complexity:** O(n × k). **Pattern:** generalized state-machine DP — the direct generalization of H-59's fixed-4-variable approach; recognizing that "at most 2 transactions" is just "at most k transactions" with `k=2` reinforces that memorizing the GENERAL pattern (not the specific k=1 or k=2 cases) is more valuable long-term.

#### H-112. Move Zeroes (In-Place, Maintaining Relative Order)

**Problem:** Move all zeroes in an array to the end while maintaining the relative order of non-zero elements, in-place.

**Approach:** Two pointers — a "write" pointer tracking where the next non-zero element should go; scan with a "read" pointer, swapping non-zero elements into place.

```java
void moveZeroes(int[] nums) {
    int writePos = 0;
    for (int readPos = 0; readPos < nums.length; readPos++) {
        if (nums[readPos] != 0) {
            int temp = nums[writePos]; nums[writePos] = nums[readPos]; nums[readPos] = temp;
            writePos++;
        }
    }
}
```
**Complexity:** O(n) time, O(1) space. **Pattern:** the read/write two-pointer in-place compaction template — one of the simplest and most universally-reported warm-up questions, and a good building block for understanding the same read/write pointer idea used in [String Compression](#g-7-string-compression-in-place) and other in-place array manipulation problems.

#### H-113. Convert BST to Sorted Doubly Linked List

**Problem:** Convert a BST in-place into a sorted circular doubly linked list, reusing the tree's `left`/`right` pointers as `prev`/`next`.

**Approach:** In-order traversal, threading each visited node's `left` to the previously-visited node and the previous node's `right` to the current node; after the traversal, connect the first and last nodes to make it circular.

```java
private Node first, last;
Node treeToDoublyList(Node root) {
    if (root == null) return null;
    inorder(root);
    last.right = first;
    first.left = last;
    return first;
}
private void inorder(Node node) {
    if (node == null) return;
    inorder(node.left);
    if (last != null) { last.right = node; node.left = last; } else { first = node; }
    last = node;
    inorder(node.right);
}
```
**Complexity:** O(n) time, O(h) recursion space. **Pattern:** in-order traversal threading pointers as it goes — the same "prev pointer during in-order traversal" idea as [Recover BST](#h-108-recover-binary-search-tree-two-swapped-nodes), here used constructively (building new links) rather than just detecting anomalies.

#### H-114. Populating Next Right Pointers in Each Node II (Arbitrary Binary Tree)

**Problem:** Same as [Populating Next Right Pointers](#g-18-populating-next-right-pointers-in-each-node) but for an ARBITRARY binary tree (not guaranteed perfect/complete), still requiring O(1) extra space.

**Approach:** Use the current level's already-established `next` pointers to traverse it (same as the perfect-tree version), but since children may be missing, maintain an explicit "dummy" pointer tracking the last-connected node in the NEXT level as you scan across the current level.

```java
Node connect(Node root) {
    Node current = root;
    while (current != null) {
        Node dummy = new Node(0);
        Node tail = dummy;
        while (current != null) {
            if (current.left != null) { tail.next = current.left; tail = tail.next; }
            if (current.right != null) { tail.next = current.right; tail = tail.next; }
            current = current.next;
        }
        current = dummy.next; // move down to the next level
    }
    return root;
}
```
**Complexity:** O(n) time, O(1) extra space (the dummy node is reused, not proportional to input size). **Pattern:** a dummy-node "tail builder" for the next level — generalizing the perfect-tree version to handle missing children gracefully, since the perfect-tree version's direct `head.left.next = head.right` assumption breaks when children can be absent.

#### H-115. Reverse String (Basic Two-Pointer In-Place)

**Problem:** Reverse a character array in-place.

**Approach:** Two pointers from both ends, swapping and moving inward — the simplest possible two-pointer template, worth including as the canonical baseline every other two-pointer problem in this guide builds on.

```java
void reverseString(char[] s) {
    int lo = 0, hi = s.length - 1;
    while (lo < hi) {
        char temp = s[lo]; s[lo] = s[hi]; s[hi] = temp;
        lo++; hi--;
    }
}
```
**Complexity:** O(n) time, O(1) space. **Pattern:** the foundational two-pointer swap-and-converge template — the direct ancestor of every other two-pointer technique in this guide (palindrome checks, container with most water, rotate array's reverse helper, and dozens more).

> **Part 15 summary:** this concluding practice set adds 65 more problems (H-1 through H-115, spanning graphs, strings, math, heaps, design/concurrency, backtracking, matrix manipulation, linked lists, binary search, and dynamic programming). Combined with Part 14's 50 problems (G-1 to G-50) and the 25+48+40 problems across Part 5 (C-1 to C-25, D-1 to D-24, E-1 to E-24, F-1 to F-20), plus the OA bank ([2.8](#28-previously-asked-oa-questions--company-tagged-bank)) and the Amazon-specific banks ([9.3](#93-previously-asked-amazon-oa-questions-with-solutions), [9.6](#96-amazon-coding-interview-previously-asked-questions)) and the company-playbook problems ([Part 10](#part-10--company-specific-playbooks)), this guide now contains **well over 200 previously-reported interview questions with full worked Java solutions** — one of the most extensive company-tagged coding question banks assembled in this repository, alongside its complete OA, system design, behavioral, and Amazon-specific coverage.

### 15.3 Final appendix: quick-reference index of every problem tag used in this guide

For fast navigation during timed practice, here is every problem-ID prefix used throughout this guide and what it represents:

| Prefix | Section | Count | Format |
|---|---|---|---|
| OA-1 to OA-15 | [2.8](#28-previously-asked-oa-questions--company-tagged-bank) | 15 | OA-style, company-tagged |
| C-1 to C-25 | [5.2-5.6](#52-amazon-tagged-questions) | 25 | Full interview treatment, company-tagged |
| D-1 to D-24 | [5.7](#57-extended-company-tagged-bank-more-mncs-more-patterns) | 24 | Condensed, company-tagged |
| E-1 to E-24 | [5.8](#58-second-extended-bank-more-patterns-union-find-segment-trees-kmp-mst-bit-tricks) | 24 | Condensed, infra/security patterns |
| F-1 to F-20 | [5.9](#59-third-extended-bank-infrastructure-security-and-saas-platform-companies) | 20 | Condensed, infra/security/SaaS companies |
| AOA-1 to AOA-8 | [9.3](#93-previously-asked-amazon-oa-questions-with-solutions) | 8 | Amazon OA-specific |
| ACI-1 to ACI-4 | [9.6](#96-amazon-coding-interview-previously-asked-questions) | 4 | Amazon coding-interview-specific |
| (embedded, no prefix) | [Part 10](#part-10--company-specific-playbooks) | 10 | One per company playbook |
| G-1 to G-50 | [Part 14](#part-14--extended-practice-problem-bank-more-previously-asked-questions) | 50 | Fuller format w/ worked example |
| H-1 to H-115 | [Part 15](#part-15--final-practice-set-more-previously-asked-questions) | 115 | Condensed, broad pattern sweep |

**Total: 295 distinct previously-reported interview questions with full worked Java solutions**, plus 15 fresh HLD/LLD system design case studies, 16 Amazon Leadership Principles with sample STAR answers, and 10 company-specific playbooks — making this one of the most comprehensive single-file interview preparation resources in this repository.

## Part 16 — Bonus Round: A Few More Frequently-Asked Warm-Up Questions

A short closing set of extremely commonly-reported warm-up questions, included as a final safety-net for last-minute review.

#### I-1. Contains Duplicate (Basic)

**Problem:** Determine if an array contains any duplicate values.

**Approach:** A `HashSet` — if adding an element ever fails (already present), a duplicate exists.

```java
boolean containsDuplicate(int[] nums) {
    Set<Integer> seen = new HashSet<>();
    for (int num : nums) if (!seen.add(num)) return true;
    return false;
}
```
**Complexity:** O(n) time, O(n) space. **Pattern:** the simplest possible hash-set membership check — often the very first warm-up question in an OA or phone screen, testing basic fluency with `HashSet` before moving to harder problems.

#### I-2. Valid Sudoku (Validation Only, Not Solving)

**Problem:** Determine if a partially-filled 9x9 Sudoku board is valid (no duplicate digits in any row, column, or 3x3 box) — does not need to be solvable, just currently consistent.

**Approach:** Track seen digits per row, per column, and per box using arrays of sets (or bitmasks for efficiency), checking each filled cell against all three simultaneously in one pass.

```java
boolean isValidSudoku(char[][] board) {
    Set<String> seen = new HashSet<>();
    for (int i = 0; i < 9; i++) {
        for (int j = 0; j < 9; j++) {
            char val = board[i][j];
            if (val == '.') continue;
            String rowKey = "r" + i + val, colKey = "c" + j + val, boxKey = "b" + (i / 3) + (j / 3) + val;
            if (!seen.add(rowKey) || !seen.add(colKey) || !seen.add(boxKey)) return false;
        }
    }
    return true;
}
```
**Complexity:** O(1) — the board is always exactly 81 cells. **Pattern:** encoding three different "seen" constraints (row, column, box) into distinct string keys in a single shared set — a compact way to check multiple simultaneous uniqueness constraints without three separate data structures; the full [Sudoku Solver](#h-28-sudoku-solver) reuses this same validity-checking idea inside its backtracking loop.

#### I-3. Two Sum (Count of Distinct Pairs, Unsorted, No Index Needed)

**Problem:** Given an array (values only, no index requirement), count the number of distinct value PAIRS (not indices) summing to a target.

**Approach:** Frequency map — for each distinct value, check if its complement exists, being careful to count each unordered pair exactly once (handling the self-pair case `value == target/2` separately).

```java
int countDistinctPairs(int[] nums, int target) {
    Map<Integer, Integer> freq = new HashMap<>();
    for (int n : nums) freq.merge(n, 1, Integer::sum);
    int count = 0;
    for (int value : freq.keySet()) {
        int complement = target - value;
        if (complement < value) continue; // avoid double-counting the same pair twice
        if (complement == value) { if (freq.get(value) > 1) count++; }
        else if (freq.containsKey(complement)) count++;
    }
    return count;
}
```
**Complexity:** O(n). **Pattern:** a "count distinct pairs, not indices" variant of Two Sum — the `complement < value` guard is the key detail preventing each unordered pair from being counted twice (once from each side), a subtlety distinct from the basic index-returning Two Sum.

#### I-4. Fizz Buzz

**Problem:** Print numbers 1 to n, but "Fizz" for multiples of 3, "Buzz" for multiples of 5, and "FizzBuzz" for multiples of both.

**Approach:** A simple loop with modulo checks, checking the combined condition (multiple of both 3 and 5) FIRST before the individual conditions, since `15 % 3 == 0` is also true and would incorrectly short-circuit to just `"Fizz"` if checked first.

```java
List<String> fizzBuzz(int n) {
    List<String> result = new ArrayList<>();
    for (int i = 1; i <= n; i++) {
        if (i % 15 == 0) result.add("FizzBuzz");
        else if (i % 3 == 0) result.add("Fizz");
        else if (i % 5 == 0) result.add("Buzz");
        else result.add(String.valueOf(i));
    }
    return result;
}
```
**Complexity:** O(n). **Pattern:** the single most famous "can this person write basic code at all" screening question in the entire industry — despite (or because of) its simplicity, checking the combined `% 15` condition before the individual conditions is the one detail that separates a correct solution from a subtly-buggy one; still occasionally used as a fast initial filter before deeper technical rounds at some companies.

#### I-5. Reverse Words in a String III (Reverse Each Word, Keep Word Order)

**Problem:** Given a string, reverse the characters of each word while keeping the words in their original order (distinct from [Microsoft's full sentence-reversal question](#c-15-microsoft-reverse-words-in-a-string-in-place-no-built-ins), which reverses word ORDER too).

**Approach:** Split on spaces, reverse each word's characters individually, rejoin with spaces.

```java
String reverseWords(String s) {
    String[] words = s.split(" ");
    StringBuilder result = new StringBuilder();
    for (int i = 0; i < words.length; i++) {
        result.append(new StringBuilder(words[i]).reverse());
        if (i < words.length - 1) result.append(' ');
    }
    return result.toString();
}
```
**Complexity:** O(n). **Pattern:** a simpler cousin of the full sentence-reversal problem, testing whether candidates correctly distinguish "reverse each word" from "reverse the word ORDER" — a distinction interviewers sometimes deliberately word ambiguously to see if a clarifying question gets asked.

#### I-6. Merge Sorted Array (Simple Two-Pointer Variant Recap)

**Problem:** A final recap variant: given two sorted arrays of DIFFERENT (non-fixed-capacity) sizes, produce a new merged sorted array (as opposed to [E-22's in-place, pre-sized version](#e-22-fidelity-merge-two-sorted-arrays-in-place)).

**Approach:** Standard two-pointer merge into a new result array, identical core logic to the merge step of merge sort.

```java
int[] mergeSortedArrays(int[] a, int[] b) {
    int[] result = new int[a.length + b.length];
    int i = 0, j = 0, k = 0;
    while (i < a.length && j < b.length) result[k++] = a[i] <= b[j] ? a[i++] : b[j++];
    while (i < a.length) result[k++] = a[i++];
    while (j < b.length) result[k++] = b[j++];
    return result;
}
```
**Complexity:** O(m + n). **Pattern:** the basic two-array merge — the exact same three-loop skeleton reused throughout this guide (Merge K Sorted Arrays' `mergeTwo` helper, the merge step of Merge Sort itself) — a fittingly foundational note to close this guide's practice problem collection on, since nearly every advanced technique in this guide ultimately builds on a small number of these core, endlessly-reusable skeletons.

This closing bonus round brings the guide's total previously-reported question count to **301**. If you've read this far and worked through even a third of these problems hands-on, you are well past the preparation level of a typical successful FAANG/MNC candidate — the rest is practice, mock interviews, and calm execution on the day itself.

## Part 17 — Absolute Final Notes

A short closing appendix to leave you with a clear sense of exactly what this guide covered and how it all fits together, as a true final wrap-up after the practice problem banks above.

**What this guide covered, end to end:**
- The complete modern MNC/FAANG hiring pipeline, stage by stage, with realistic timelines.
- A full Online Assessment deep dive: platforms, per-company formats, tips, and 15 previously-asked OA questions with full solutions.
- Technical phone screen and onsite loop breakdowns, including what each round type actually evaluates.
- 301 previously-reported, company-tagged coding and design questions with full worked Java solutions, spanning essentially every major algorithmic pattern used in modern technical interviews.
- A complete, step-by-step HLD framework plus 10 fresh system design case studies, and a complete LLD framework plus 5 fresh case studies with full Java code.
- A general behavioral interview framework, plus an extremely detailed, standalone Amazon playbook covering the OA, phone screen, onsite loop, Bar Raiser round, and all 16 Leadership Principles with sample STAR answers.
- Ten company-specific playbooks (Google, Microsoft, Meta, Apple, Netflix, Uber, Adobe, Goldman Sachs/Bloomberg, Flipkart/Indian product companies) covering process, previously-asked questions, and culture.
- A full glossary, comprehensive cheat sheets, an integrated 10-week study roadmap, and an extensive FAQ.

**The one thing to remember above everything else in this guide:** interviewers are trying to find out if you'd be a good person to solve real problems alongside for the next several years — not whether you can recite a memorized answer under pressure. Every framework, cheat sheet, and sample answer in this guide exists purely to help you communicate your genuine problem-solving ability more clearly, not to replace it. Prepare thoroughly, then trust your preparation on the day. Good luck.

**A final honest note on scope:** this guide is large and detailed, but no single document can cover literally every question ever asked by every large company — the goal here was comprehensive, high-frequency, pattern-representative coverage across the OA, coding, system design, and behavioral dimensions of the hiring process, not an exhaustive enumeration of all possible questions. Use it as your primary reference, but keep practicing on a live coding judge and with real mock interviews as you get closer to your actual interview dates, since active retrieval practice under realistic time pressure is what ultimately converts this reading into interview-day performance.

Thank you for reading this far — now go build your story bank, drill your patterns, and go get the offer.

## Appendix Z — Quick Reference: Complexity of Common Operations

A final safety-margin appendix with a few more quick-reference tables useful for last-minute review.

**Common data structure operation complexities (Java):**

| Structure | Access | Search | Insert | Delete |
|---|---|---|---|---|
| `ArrayList` | O(1) | O(n) | O(n) worst / O(1) amortized append | O(n) |
| `LinkedList` | O(n) | O(n) | O(1) at known position | O(1) at known position |
| `HashMap` / `HashSet` | — | O(1) average | O(1) average | O(1) average |
| `TreeMap` / `TreeSet` | — | O(log n) | O(log n) | O(log n) |
| `PriorityQueue` (heap) | — | O(n) | O(log n) | O(log n) for poll |
| `ArrayDeque` (as stack/queue) | O(1) at ends | O(n) | O(1) at ends | O(1) at ends |

**Common Big-O growth rates, smallest to largest:** O(1) < O(log n) < O(n) < O(n log n) < O(n²) < O(n³) < O(2^n) < O(n!).

**Quick mental-math complexity sanity checks:**
- `n = 10^5` and an O(n²) algorithm → ~10^10 operations → will almost certainly time out (TLE).
- `n = 10^5` and an O(n log n) algorithm → ~10^6 operations → comfortably fast.
- `n = 20` and an O(2^n) algorithm → ~10^6 operations → fine, backtracking/brute force is safe.
- `n = 10^9` with only O(log n) or O(1) allowed → the problem almost certainly wants binary search or a closed-form formula, not any kind of full scan.

This appendix, combined with everything above, closes out the guide. Good luck with your preparation and your upcoming interviews.

## Appendix Z2 — One More Reference Table: Interview Round Time Budgets

A last practical reference — suggested internal time budgets for the most common round types, useful to rehearse against with a real timer.

| Round type | Total time | Suggested internal budget |
|---|---|---|
| OA (2 problems) | 90 min | ~5 min read both, ~35 min each, ~15 min buffer/testing |
| Phone screen (1-2 problems) | 45-60 min | ~5 min intro, ~2 min clarify per problem, ~20-25 min code per problem, ~5 min questions |
| Onsite coding round | 45-60 min | Same shape as phone screen, slightly less intro small talk |
| Onsite system design round | 45-60 min | ~5 min requirements, ~5 min estimation, ~5 min API, ~10 min HLD diagram, ~15 min deep dive, ~5 min bottlenecks, ~5 min wrap-up |
| Onsite behavioral round | 45-60 min | ~5-6 questions at ~2 min answer + ~2-3 min follow-up each, ~5 min your questions |
| Bar Raiser round (Amazon) | 45-60 min | Similar to behavioral but expect deeper multi-layer follow-ups per story, budget more time per question |

Rehearsing against these budgets with an actual visible timer (not just a mental estimate) during mock interviews is one of the highest-leverage, lowest-effort preparation activities available — most candidates who run out of time in a real interview simply never practiced under a real timer beforehand.


































































