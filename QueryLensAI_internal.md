# QueryLensAI — Interview Prep Guide

This is a companion to [`README.md`](README.md). It turns the project into interview material: a memorizable pitch, then Easy → Medium → Hard questions with grounded answers, a live "spot the bug" code-review round based on real issues found in the codebase, and a behavioral round. Everything here is tied back to actual files so your answers can cite specifics instead of speaking in generalities.

## Table of Contents

1. [The 60-Second Pitch](#the-60-second-pitch)
2. [How to Use This Guide](#how-to-use-this-guide)
3. [Easy Questions](#easy-questions)
4. [Medium Questions](#medium-questions)
5. [Hard / System-Design Questions](#hard--system-design-questions)
6. [Spot-the-Bug Code Review Round](#spot-the-bug-code-review-round)
7. [Behavioral / Project-Ownership Questions](#behavioral--project-ownership-questions)
8. [Quick-Reference Cheat Sheet](#quick-reference-cheat-sheet)

---

## The 60-Second Pitch

Use this as your answer to *"Tell me about a project you've worked on."*

> "QueryLensAI is a conversational data-querying platform — the idea is that instead of writing SQL or pandas code, you pick a dataset, ask a question in plain English, like 'what's the average income for states with a population over a million', and get back a natural-language answer that's actually been computed against the real data. The frontend is a React 18 and Vite single-page app with Clerk for authentication and Tailwind/DaisyUI for styling. It talks to a FastAPI backend over REST — that backend uses LangChain to orchestrate an agent that decides between retrieving context with FAISS and running actual pandas computations on the dataset, then a fine-tuned LLM composes the final answer. What I think is the most interesting part is that every generated answer is checked against a manually curated ground-truth reference before it's shown to the user, so the UI can display a 'Valid' or 'Invalid' badge with a plain-English reason — it's a self-auditing system, not just a chatbot. I worked on [your specific layer — frontend/backend/mobile], and one of the trickiest problems was [pick one real challenge, e.g. getting the agent to reliably choose between retrieval and computation, or getting the chat UI's state management right without a global store]."

Swap in your actual role/contribution using the [Behavioral](#behavioral--project-ownership-questions) section below.

## How to Use This Guide

- **Easy** = fundamentals any contributor should be able to answer about their own project (React basics, what a library does, why a tool was chosen).
- **Medium** = requires connecting two or more parts of the system together (frontend ↔ backend contract, why an architectural choice was made).
- **Hard** = system design / trade-off discussions with no single correct answer — these are where you demonstrate seniority.
- **Spot-the-Bug** = real issues discovered while reviewing this exact codebase, formatted as live code-review prompts.

---

## Easy Questions

**Q1. What does QueryLensAI do, in one sentence?**
A conversational AI platform that lets a user ask natural-language questions about a dataset and get back a validated, explainable answer instead of writing SQL/pandas by hand.

**Q2. What does this specific repository contain?**
Only the frontend — a React 18 single-page app built with Vite. The AI/data backend (FastAPI, LangChain, FAISS, pandas) is a separate service this app calls over REST (see `config.js`).

**Q3. Why Vite instead of Create React App?**
Native ES-module dev server (near-instant start, fast HMR), Rollup-based production bundling, and a lightweight plugin model — `@vitejs/plugin-react` gives React Fast Refresh without CRA's heavier webpack setup.

**Q4. How is routing implemented?**
`react-router-dom` v7. `main.jsx` defines a `RoutesObj` array of `{ path, element }` pairs and maps it into `<Route>` elements inside one `<Routes>` — a small data-driven routing pattern instead of manually writing every route tag.

**Q5. What is Clerk, and where is it wired in?**
A hosted authentication-as-a-service provider. `ClerkProvider` wraps the whole app in `main.jsx`; `SignedIn`/`SignedOut`/`SignInButton`/`UserButton` (in `NavBar.jsx`) render conditionally based on auth state; `useUser()` (in `DashNav.jsx`, `DashScreen.jsx`) reads the current user's name/avatar.

**Q6. Is hardcoding the Clerk key in `main.jsx` a security risk?**
No — it's a *publishable* key (`pk_...`), explicitly designed to ship to the client. The actual secret key (`sk_...`) lives only server-side/in the Clerk dashboard and is never in frontend code. It's still not great practice for environment management, but it's not a secret-leak vulnerability.

**Q7. What icon library is used, and where?**
`lucide-react` — tree-shakeable SVG icon components. Used in `NavBar` (`AlignJustify`), `DashNav` (`ArrowRightFromLine`), `DashMenu` (`ChevronRight`, `CircleHelp`, `SlidersHorizontal`), multiple CTAs (`MoveRight`), and the whole chat UI (`Plus`, `ChevronDown`, `Check`, `Ellipsis`, `Info`, `Bot`, `Brain`, `DatabaseZap`).

**Q8. What's the styling stack?**
Tailwind CSS (utility classes) + DaisyUI (a Tailwind plugin adding component classes like `rounded-badge`, `hero`, `carousel`, `mockup-code`, plus a theme system) + `@tailwindcss/typography` for the `.prose` long-form text on the About/Docs pages.

**Q9. How does the app fetch the list of available datasets?**
A `useEffect` with an empty dependency array in `DashSession.jsx` runs once on mount, calls `fetch(API_ENDPOINTS.GET_DATASET)`, and stores the returned `names[]` array in state, defaulting the selection to the first entry.

**Q10. What are `useState` and `useEffect` doing, conceptually?**
`useState` gives a component local, re-render-triggering memory (e.g. the `messages` array). `useEffect` runs side effects — like a network call — in response to a component mounting or a dependency changing, outside of the render itself.

**Q11. Difference between props and state, with an example from this codebase?**
Props are read-only data passed down from a parent — `FeatureCard` receives `imgsrc`, `headline`, `details` from `Cards.jsx`. State is data a component owns and updates itself — `DashSession`'s `messages` array, updated via `setMessages`.

**Q12. What does `afterSignOutUrl="/"` do on `ClerkProvider`?**
Tells Clerk where to redirect the browser after a user signs out — back to the landing page in this app.

**Q13. Why two different layout components (`MainLayout`, `DashboardLayout`)?**
A layout-composition pattern: `MainLayout` (NavBar + footer) wraps public marketing pages; `DashboardLayout` (sticky DashNav, no footer) wraps the authenticated dashboard. Both take a `children` prop so any page can be dropped inside.

**Q14. What is `lottie-react` used for?**
Rendering `database-animation.json` — an exported JSON animation — on the dashboard's intro screen via `<Lottie animationData={...} loop />`.

**Q15. What request does sending a chat message trigger?**
A `POST` to `/get_answer` with JSON body `{ "query": "<user text>" }` and header `Content-Type: application/json`.

---

## Medium Questions

**Q1. Walk me through what happens end-to-end when a user asks a question.**
On mount, `DashSession` fetches the dataset list. The user selects a dataset, types a question, and submits — the UI immediately shows the message and a loading indicator, then `POST /get_answer` fires. On the backend (per the project's own design/docs): a custom fine-tuned model interprets intent, a LangChain agent retrieves relevant context via FAISS and/or executes pandas operations against the dataset, an LLM composes the natural-language answer, and a validation step compares that answer to a manually curated ground truth. The response — `{ answer, valid_answer, reason }` — comes back as JSON; the UI appends the bot's answer as a chat bubble and renders a Valid/Invalid badge with a "why" modal.

**Q2. What is RAG (Retrieval-Augmented Generation), and where does it fit here?**
RAG grounds an LLM's output in retrieved, relevant external context instead of relying purely on the model's internal/parametric knowledge. Here, FAISS stores embeddings of dataset schema/metadata/documentation; the LangChain agent retrieves the top-k most similar chunks for a given query and feeds them to the LLM alongside the computed pandas result, so the answer is grounded in the actual dataset's structure rather than guessed.

**Q3. Why FAISS specifically, instead of a plain SQL `LIKE` search or a managed vector DB?**
FAISS gives fast approximate nearest-neighbor search over dense embeddings — semantic similarity, not keyword matching — and runs in-process with no extra infrastructure to stand up, which fits a project at this scale. The trade-off against a managed vector database (Pinecone, Weaviate, pgvector) is durability, horizontal scale, and built-in multi-tenant metadata filtering, none of which FAISS gives you for free.

**Q4. What is LangChain actually orchestrating here, concretely?**
The decision logic for "what does this question need?" — does it need schema/context retrieval (FAISS), a computed value from the dataset (a pandas dataframe agent), or a direct LLM completion — and then assembling all of that into one final prompt/response.

**Q5. Why pandas specifically for the computation layer?**
The underlying datasets are tabular; pandas is the standard, mature API for filter/group/aggregate operations, and LangChain has an established "pandas dataframe agent" pattern that lets an LLM translate natural language into pandas operations and execute them against a loaded dataframe.

**Q6. Explain the `valid_answer` / `reason` contract and why it exists.**
Every backend answer is checked against a manually curated "ground truth" reference for that question, producing a boolean pass/fail plus a plain-English `reason`. This turns the product into a self-auditing system — a trust signal for end users, and an accuracy-tracking/regression-testing mechanism for the team.

**Q7. Why does the frontend never actually send which dataset the user selected?**
This is a real bug in `DashSession.jsx`: `handleSendMessage` guards the whole function on `selectedVersion` being truthy, but only serializes `{ query }` into the POST body — the selected dataset name is tracked in state and checked, but never transmitted. It's a good example of a "looks complete but isn't" bug: the state exists and gates the logic, which makes it easy to assume it's also being sent.

**Q8. How would CORS need to be configured, and why?**
The frontend (a Vercel domain) and backend (a different host/port — `localhost:8000` in dev, a VM IP in the commented fallback) are different origins, so the FastAPI app needs `CORSMiddleware` allowlisting the frontend's origin(s), the methods used (`GET`, `POST`), and the `Content-Type` header — otherwise the browser blocks the response before JS ever sees it.

**Q9. What would you change about how `config.js` handles environments?**
Replace the commented-out URL swap with Vite's built-in env support — `import.meta.env.VITE_API_BASE_URL` sourced from `.env.development` / `.env.production` files — so switching environments doesn't require editing tracked source code.

**Q10. How does the chat UI show loading state, and what's the limitation?**
A `loadingMessage` boolean toggles an animated `Ellipsis` bubble while `await fetch(...)` is pending. It's a single blocking request/response with no streaming, so for a slow LLM call the user just watches the dots with no partial progress — a production version would likely stream tokens via SSE or WebSockets.

**Q11. What's the intended purpose of the "final report" PDF export, and how would it technically work?**
`html2canvas` would walk the target DOM subtree (e.g. the chat/validation panel) and rasterize it to a canvas/PNG entirely client-side — no server-side rendering needed. `jsPDF` would then create a PDF document and place that image as a page, which the browser can save/download. It's a "screenshot-to-PDF" pattern, not structured/selectable-text PDF generation. Note: this isn't implemented in the current codebase (no dependency, no call site) — it's a designed feature, described here as intended.

**Q12. Why might the product need a "custom model" step before the LLM agent, rather than sending the raw question straight to a general-purpose LLM?**
Per the team's own description, this is an in-house fine-tuned model — likely tuned to the vocabulary/shape of the supported datasets, deciding how to route or decompose a question before the heavier/general agent step runs. That can improve both accuracy and cost/latency versus always invoking a full agentic chain for every query.

**Q13. How would you add tests to this frontend today?**
There currently are none configured (no test runner in `package.json`). Vitest pairs naturally with Vite; start with pure/presentational components (`FeatureCard`, `AboutCard`), then mock `fetch` to test `DashSession`'s dataset-load effect and send-message handler.

---

## Hard / System-Design Questions

**Q1. How would you scale the backend to handle many concurrent users querying large datasets with an LLM agent?**
Talking points: async FastAPI endpoints with a task queue (Celery/RQ, or async workers) so long LLM calls don't block request threads; cache embeddings/FAISS indices per dataset instead of rebuilding per request; stream responses (SSE/WebSocket) instead of one blocking round trip; rate-limit per user/session; scale stateless API instances horizontally behind a load balancer while keeping the vector store and dataframes in shared/persisted storage rather than per-process memory.

**Q2. LangChain's pandas dataframe agent can generate and execute code against a live Python process. What's the security concern, and how do you mitigate it?**
This is a code-execution / prompt-injection risk — an adversarial query could try to make the agent execute something outside the intended dataframe operations. Mitigations: run the agent in a sandboxed, least-privilege process; allow-list permitted pandas operations instead of arbitrary `exec`; enforce timeouts and resource limits; block filesystem/network access from within the sandbox; validate and constrain user input before it reaches the prompt.

**Q3. How would you evolve "manual ground truth" validation so it doesn't require a human to hand-write a reference answer for every possible question?**
Options to discuss: LLM-as-judge (a second model scores the primary answer against a rubric instead of requiring an exact reference); embedding-based semantic-similarity thresholds between generated and reference answers; tolerant numeric comparison for quantitative answers; a growing "golden dataset" of Q&A pairs for regression testing whenever the model/prompt changes; a human-review queue for low-confidence verdicts that feeds back into that golden set.

**Q4. How would you design multi-tenant data isolation if different organizations used this platform with their own private datasets?**
Per-tenant namespacing (or fully separate indices) for FAISS and dataframe storage; never share embeddings/context across tenants during retrieval; scope every backend request by an authenticated tenant/session identity — Clerk already gives a verifiable user identity on the frontend, so you'd propagate that as a verified token to the backend and check it there (not currently happening based on this repo's code); encrypt sensitive data at rest.

**Q5. How would you introduce API versioning safely, given `config.js` already anticipates `/v1/get_answer` and `/v2/get_answer`?**
Keep `v0`'s contract frozen for existing clients; add `v1`/`v2` as additive, parallel routes rather than mutating `v0`; document a deprecation window; let the frontend opt into a newer version deliberately rather than a hard cutover; add contract tests so a backend change can't silently break the `{ answer, valid_answer, reason }` shape the frontend depends on.

**Q6. The current request is a single blocking `await fetch()`. How would you redesign this for a streaming LLM experience?**
Replace the single JSON response with Server-Sent Events or a WebSocket channel; stream partial tokens as they're generated and append them to the last "bot" message incrementally; keep the ground-truth validation step as a distinct final event once the full answer is assembled (validation needs the complete answer, not partial tokens); handle reconnects/backpressure on the client.

**Q7. What are the trade-offs of FAISS versus a managed vector database as this product grows?**
FAISS: fast, free, in-process, zero extra ops — but no built-in persistence, replication, horizontal scale, or native multi-tenant metadata filtering. Managed options (Pinecone, Weaviate, pgvector): built-in persistence/scale/filtering/access control, at the cost of money and an external network dependency. FAISS is pragmatic for a handful of curated datasets; a managed store becomes more attractive with many tenants or huge corpora.

**Q8. How would you monitor and debug a wrong/invalid answer in production?**
Log the full pipeline trace per request (retrieved chunks, generated pandas operations, raw LLM output, validation result) tied to a request ID; surface `valid_answer: false` cases into a review dashboard; track the invalid-rate over time as a core product health metric; replay historically-failing queries against newer model/prompt versions before shipping changes.

---

## Spot-the-Bug Code Review Round

Real findings from this exact codebase, framed as "here's a snippet — what's wrong, and how would you fix it?"

**1. Dataset selection never reaches the backend**

```jsx
// DashSession.jsx
const handleSendMessage = async () => {
    if (inputText.trim() !== "" && selectedVersion) {
        // ...
        const response = await fetch(API_ENDPOINTS.GET_ANS_V0, {
            method: "POST",
            headers: { "Content-Type": "application/json" },
            body: JSON.stringify({ query: inputText }), // selectedVersion is missing here
        });
```

*What's wrong:* `selectedVersion` gates the function but is never included in the request body.
*Fix:* `body: JSON.stringify({ query: inputText, dataset: selectedVersion })` (and update the backend contract to accept it).

**2. The chat workspace can't actually be reached**

```jsx
// DashScreen.jsx
const [open, setOpen] = useState(false);
// ...
<a href="https://http://localhost:3000/">
  <button>Get Started</button>
</a>
// setOpen is never called anywhere in this file
```

*What's wrong:* Two issues stacked — a malformed URL (`https://http://...` has two protocols) on the CTA, and `setOpen(true)` is never called, so `{!open ? <intro/> : <DashSession/>}` always renders the intro.
*Fix:* Replace the anchor with a button `onClick={() => setOpen(true)}`.

**3. Inconsistent router import**

```jsx
// Landing.jsx
import { Link } from 'react-router';       // <- everywhere else it's 'react-router-dom'
```

*What's wrong:* Works today only because `react-router-dom@7` depends on `react-router` internally — fragile, and inconsistent with the rest of the codebase.
*Fix:* Standardize on `react-router-dom` everywhere.

**4. Orphaned page**

```jsx
// main.jsx — RoutesObj array
{ path: '/', element: <App /> },
{ path: '/login', element: <Login /> },
{ path: '/Docs', element: <Docs /> },
{ path: '/About', element: <About /> },
{ path: '/Dashboard', element: <Dashboard /> },
// no route for Registration.jsx
```

*What's wrong:* `Registration.jsx` exists in `src/Pages/Auth/` but is never imported or routed.
*Fix:* Either add a `/register` route or delete the dead file.

---

## Behavioral / Project-Ownership Questions

**Q: What was your specific role/contribution?**
Tailor this to whichever real layer you owned — this project's own team split was: UI/UX + full-stack (frontend architecture and product design), backend/API + LLM integration (server-side design and metadata-driven query processing), and cross-platform/web (extending reach across devices). Speak concretely about the layer you touched — specific files, specific decisions — rather than generic project-management language.

**Q: What was the hardest technical problem you ran into?**
Strong, grounded answers to adapt: getting an agent to reliably choose between "retrieve context" and "compute a value" for ambiguous natural-language questions; keeping FAISS-retrieved context relevant enough that the LLM doesn't answer from stale/irrelevant chunks; designing ground-truth validation so it doesn't degrade into brittle exact-string matching; managing chat UI state cleanly with only local `useState` as the number of flags grew (this file alone tracks eleven pieces of state).

**Q: What would you do differently if you rebuilt this today?**
Use the [Known Gaps &amp; Tech Debt](README.md#known-gaps--tech-debt) list as authentic material: send the selected dataset with every query, wire up the dashboard's entry point, move secrets/URLs into `.env` files, add response streaming, add a test suite, consolidate the duplicated scrollbar CSS.

**Q: How did a small team divide the work without stepping on each other?**
Discuss splitting by layer (frontend/UI vs. backend/API vs. cross-platform) with a shared contract at the boundary — in this project, that boundary is the `{ query } → { answer, valid_answer, reason }` REST contract, which let frontend and backend work independently as long as both sides honored that shape.

**Q: How do you decide what's in scope vs. a "nice to have" under a deadline?**
Use the PDF export feature as a live example: it's part of the designed pipeline and shows up in the product's own description of itself, but it's explicitly not implemented yet — a good example of consciously sequencing "core loop first" (ask → validate → answer) before "delight" features (export/share).

---

## Quick-Reference Cheat Sheet

| Term                             | One-line definition                                                                                                                |
| -------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| **Clerk**                  | Hosted authentication-as-a-service; handles sign-in/out, sessions, and user profile UI components                                  |
| **FAISS**                  | Facebook AI Similarity Search — a library for fast approximate nearest-neighbor search over vector embeddings                     |
| **LangChain**              | A framework for orchestrating LLM calls, tools, and agents into multi-step pipelines                                               |
| **RAG**                    | Retrieval-Augmented Generation — grounding an LLM's answer in retrieved external context instead of relying on its own memory     |
| **Agent (LLM context)**    | An LLM-driven controller that decides which tool(s) to call (retrieval, computation, etc.) to answer a request                     |
| **Vector embedding**       | A numeric representation of text/data such that semantically similar items are close together in vector space                      |
| **Ground truth**           | A known-correct reference answer used to check a generated answer's accuracy                                                       |
| **pandas dataframe agent** | A LangChain pattern where an LLM translates natural language into pandas operations executed against a real dataframe              |
| **Vite**                   | A fast frontend build tool using native ES modules in dev and Rollup for production bundling                                       |
| **HMR**                    | Hot Module Replacement — updates modules in the browser without a full page reload                                                |
| **DaisyUI**                | A Tailwind CSS plugin adding pre-built component classes and theming on top of utility classes                                     |
| **CORS**                   | Cross-Origin Resource Sharing — browser security policy that a backend must explicitly allow for cross-origin requests to succeed |
| **SSE**                    | Server-Sent Events — a one-way streaming protocol from server to client over HTTP, well suited to streaming LLM tokens            |
| **ESLint flat config**     | The newer, array-based configuration format for ESLint (replacing`.eslintrc`), used in `eslint.config.js` here                 |
| **html2canvas**            | Client-side library that rasterizes a DOM subtree into a canvas/image                                                              |
| **jsPDF**                  | Client-side library for generating PDF documents in the browser, often combined with`html2canvas` for "export as PDF"            |

---

## Explain It Like I'm 8 🍕

Use this version when someone (or a very tired interviewer) wants the *simplest possible* version of the story — no jargon, just a picture in your head. It's the same project, just told like a bedtime story. Once you've got this, all the harder Q&A above is just "the grown-up words for the same story."

### The Pizza Shop Story

Imagine QueryLensAI is a **pizza shop**. 🍕

- **You** are a hungry customer with a question, like *"How many pepperoni pizzas did we sell last month?"*
- You don't ask in a weird secret code (like SQL) — you just ask like a normal person.
- There's a **front counter** (that's the part of the shop you can see and touch — the **frontend**, the website).
- Behind a door there's a **kitchen** you never see (that's the **backend** — all the real work happens back there, hidden from you).

Here's what happens to your question, step by step:

1. 🗣️ **You talk to the counter person.** You type your question into the chat box. The counter person writes your order on a little ticket and slides it through the kitchen window. *(The frontend sends your question to the backend.)*
2. 👂 **A super-listener reads your ticket.** This is a helper who's really good at understanding orders even if you say them a bit weirdly — they figure out exactly what you *really* meant. *(The "custom model" interprets your question.)*
3. 🕵️ **The head chef decides what to do.** Does the chef need to peek in the fridge for an ingredient, or actually cook/count something? The chef is like a smart detective who picks the right tools for the job. *(This is the "LLM agent" deciding what to do.)*
4. 📇 **A magic recipe box finds the right card instantly.** Instead of flipping through a thousand recipe cards one by one, there's a magic box that jumps straight to the 2-3 cards that actually matter. *(That's **FAISS** — it finds the right information fast instead of searching everything.)*
5. 🧮 **The chef actually counts the real ingredients.** No guessing — the chef opens the real fridge (the real data) and actually counts/weighs/adds things up for real. *(That's **pandas** doing the real math on the real data.)*
6. 📖 **A taste-tester checks the pizza against a secret answer key.** Before your pizza goes out, someone compares it to a "perfect pizza" photo that a teacher already made earlier. *(That's comparing the answer to the **manual ground truth**.)*
7. ✅❌ **You get a sticker.** If it matches the perfect photo, it gets a green sticker (**Valid**). If it doesn't quite match, it gets a red sticker (**Invalid**) *and* a little note explaining why. *(That's the **validation & comparison** step.)*
8. 🧾 **You get your pizza AND a receipt.** The receipt is something you can keep and show your friends later. *(That's the **final report** you could export/save.)*

### The simplest picture

```
You ask a question
        │
        ▼
  Front counter (the website you see)
        │
        ▼
  Kitchen window (question travels to the backend)
        │
        ▼
  Super-listener figures out what you meant
        │
        ▼
  Chef decides: look something up? do math? both?
        │
   ┌────┴─────┐
   ▼          ▼
Magic recipe   Real counting
box (FAISS)    (pandas math)
   └────┬─────┘
        ▼
  Chef writes the answer in plain words
        │
        ▼
  Taste-tester checks it against the answer key
        │
        ▼
  You get: the answer + a ✅/❌ sticker + why + a keepsake receipt
```

### Grown-up word decoder

| Kid-story word          | What it really is                                                                       |
| ----------------------- | --------------------------------------------------------------------------------------- |
| Front counter           | The**frontend** — the website (React) you actually see and click on              |
| Kitchen (hidden)        | The**backend** — the FastAPI server doing the real work                          |
| The ticket              | The API request (`POST /get_answer`)                                                  |
| Super-listener          | The **custom fine-tuned model** that figures out what you're really asking       |
| Head chef               | The**LLM agent** (built with LangChain) deciding what steps are needed            |
| Magic recipe box        | **FAISS** — finds the most relevant info fast instead of checking everything     |
| Real counting/measuring | **pandas** — does the actual math on the actual dataset                          |
| Perfect-pizza photo     | The**manual ground truth** — an answer a person already confirmed is correct     |
| Sticker + note          | The**validation result** (`valid_answer`) and **reason** shown in the app |
| Receipt to keep         | The**final report** (planned PDF export)                                          |

### The one-breath summary

*"You ask a question like you're talking to a person. A website sends it to a hidden kitchen. Someone figures out what you meant, a smart helper decides whether to look something up or do real math, then checks the answer against one a teacher already approved — and you get your answer back with a sticker saying if it's correct, plus a receipt to keep."*
