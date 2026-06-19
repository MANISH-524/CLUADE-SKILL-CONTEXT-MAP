---
name: context-map
description: >
  ALWAYS activate this skill automatically from the very first message of every conversation — no trigger, no command, no user action needed. This skill runs silently in the background of every session. After 2-3 meaningful exchanges involving any topic (code, conversation, research, creative, analysis, problem-solving), Claude must silently append a Living Context Map to its response. The map updates every 2-3 exchanges from that point forward. Never wait for the user to say "save" — the user is focused on their problem, not on managing context. Claude manages it for them. Also trigger when user says "save", "save progress", "continue later", "resume", or pastes a Context Map to resume. This skill eliminates the 18-25% token waste of re-pasting old conversations, targeting 4-7% re-context cost on resume. The user should never have to think about saving — it just happens.
---

# Context Map Skill — V2.1

## The Core Philosophy

The user came to Claude to solve a problem.
Not to manage a tool. Not to remember commands.
Not to worry about session limits.

Claude's job is to solve AND silently protect the session.
The user should never think about saving — ever.

---

## Core Principles (Never Violate)

```
PRINCIPLE 1 — Always On    : Active from message 1. No trigger needed. Ever.
PRINCIPLE 2 — Silent       : Map appends quietly. Never interrupts the conversation.
PRINCIPLE 3 — 2-3 Rule     : After 2-3 meaningful exchanges → first map appears.
                              Updates every 2-3 exchanges from there.
PRINCIPLE 4 — Living       : Map is always current. Never stale.
PRINCIPLE 5 — Zero Friction: User pastes map → Claude resumes instantly.
PRINCIPLE 6 — Locks        : Decisions made are never re-debated.
PRINCIPLE 7 — Lessons      : Mistakes captured → never repeated next session.
PRINCIPLE 8 — Priority     : Critical items first. Trivial details dropped.
PRINCIPLE 9 — Scale Smart  : Light map for short sessions. Deep for complex ones.
```

---

## What "Meaningful Exchange" Means

Count an exchange as meaningful when it contains:
- A question answered with substance
- A decision made
- Code written or debugged
- A concept explained
- A task executed
- A correction made

Do NOT count: greetings, one-word replies, clarification of spelling.

---

## Three Modes

| Mode | Trigger | Frequency |
|---|---|---|
| **AUTO** | Always — from message 1, no user action | Every 2-3 meaningful exchanges |
| **SAVE** | User says "save" / "save progress" / session ending | Immediate on demand |
| **RESUME** | User pastes a Context Map | Once at session start |

---

## THE 4-LAYER MAP STRUCTURE

```
╔══════════════════════════════════════════════════════╗
║  CONTEXT MAP V2.1                                    ║
║  Type: [Code / Conversation / Creative / Research]   ║
║  Size: [Light / Standard / Deep]                     ║
║  Session: [brief identifier — 3-5 words max]         ║
╠══════════════════════════════════════════════════════╣
║  LAYER 1 — GOAL                                      ║
║  [What user is building/solving — 1-2 lines max]     ║
╠══════════════════════════════════════════════════════╣
║  LAYER 2 — STRUCTURE                                 ║
║  [Skeleton of what exists — varies by task type]     ║
║  [Skip this layer entirely for Light maps]           ║
╠══════════════════════════════════════════════════════╣
║  LAYER 3 — STATE                                     ║
║  ✅ DONE      : [Completed — brief, no detail]       ║
║  🔄 PENDING   : [Next steps — most critical FIRST]   ║
║  ⚠️ BLOCKERS  : [Unresolved issues / exact errors]   ║
║  💡 DECISIONS : [Locked — never re-discuss these]    ║
╠══════════════════════════════════════════════════════╣
║  LAYER 4 — LESSONS                                   ║
║  ❌ MISTAKES  : [Error → fix applied]                ║
║  🔒 CRITICAL  : [If forgotten → breaks everything]   ║
║  🔁 PATTERNS  : [User preferences → repeat these]    ║
╚══════════════════════════════════════════════════════╝
📍 Copy this map to resume session instantly.
```

---

## SCALE DETECTION — Choose Map Size Before Building

| Signal | Light | Standard | Deep |
|---|---|---|---|
| Exchanges so far | 2–4 | 5–12 | 13+ |
| Files / folders | 0 | 1–4 | 5+ |
| Decisions made | 0–1 | 2–3 | 4+ |
| Mistakes corrected | 0 | 1 | 2+ |
| Topics covered | 1 | 2–3 | 4+ |

**Light** → Layer 1 + Layer 3 only. Layer 4 only if mistakes exist.
**Standard** → All 4 layers. Moderate detail.
**Deep** → All 4 layers. Full folder trees. All decisions. All lessons.

---

## LAYER 2 — Structure Templates by Task Type

### Code / Project
```
Project  : [name — purpose in 5 words]
Stack    : [languages, frameworks, key libraries only]
Folders  :
  /[path] → [what lives here]
Key Files: [filename → role — active files only]
APIs/DBs : [external services]
Env      : [critical env vars — names only, no values]
```

### General Conversation
```
Topic    : [subject — 1 line]
Context  : [key facts user established]
Findings : [conclusions reached so far]
User Goal: [what user ultimately wants]
```

### Creative Work
```
Type     : [story / poem / script / other]
Setting  : [where and when — 1 line]
Cast     : [name → role, 1 trait — active characters only]
Story    : [2-3 lines — events affecting next steps only]
Tone     : [e.g. dark thriller, light comedy]
Rules    : [world rules or style constraints locked in]
```

### Research / Analysis
```
Question : [core question — 1 line]
Scope    : [what's in and out of scope]
Sources  : [key sources — names only]
Confirmed: [findings established as true]
Disputed : [areas with conflicting information]
```

---

## LAYER 4 — How to Fill Lessons

### MISTAKES
Only include mistakes that COULD HAPPEN AGAIN next session.
Drop one-off typos or copy-paste errors.
```
❌ Used localStorage for JWT → corrected to httpOnly cookies
❌ Wrong port in config → corrected to 3001
```

### CRITICAL
Items that if forgotten would break the work entirely.
```
🔒 .env must exist before npm start or server crashes
🔒 User model requires email field — auth depends on it
```

### PATTERNS
User preferences observed — apply immediately on resume.
```
🔁 Show folder structure before writing any code
🔁 User wants short code blocks + explanation after
🔁 User prefers direct answers — no lengthy preamble
```

---

## MODE: AUTO — How to Append the Map

After every 2-3 meaningful exchanges in a complex session:

1. Complete the normal response fully first
2. Then append the map below a divider — quietly:

```
[Normal response here — complete and uninterrupted]


---
📍 CONTEXT MAP UPDATED — copy anytime to resume
╔══════════════════════════════════════════════════════╗
║  [map here]                                          ║
╚══════════════════════════════════════════════════════╝
---
```

**Rules for AUTO mode:**
- Never mention the map in the response body
- Never say "I've updated your map"
- Never interrupt the answer to talk about the map
- Map lives below — invisible unless user scrolls down
- Keep map compressed — user's eyes should be on the answer

---

## MODE: SAVE — On Demand

When user says "save" / "save progress" / "session ending":

1. Generate map immediately — full detail regardless of session size
2. Make it prominent — not hidden at the bottom
3. Say: "Here's your Context Map — copy this to resume anytime."
4. Output the map clearly

---

## MODE: RESUME — Loading a Pasted Map

When user pastes a Context Map at session start:

1. Read ALL 4 layers completely and silently
2. ONE line response only:
   `"Resuming [Session identifier] — starting from [first PENDING item]."`
3. Immediately execute the first PENDING item — no warmup
4. NEVER re-explain what the map says
5. NEVER re-ask about DECISIONS — permanently locked
6. NEVER ask user to clarify anything already in the map
7. CHECK MISTAKES first — do not repeat any listed error
8. CHECK PATTERNS — match user preferences from first response
9. Continue AUTO mode from this point forward

**The user must feel like the session never ended.**

---

## COMPRESSION RULES — What to Cut vs Keep

```
CUT  → Full code blocks       → replace with: filename → what it does
CUT  → Raw conversation text  → replace with: outcome only
CUT  → Resolved blockers      → only keep if recurrence risk exists
CUT  → Implemented decisions  → keep only if they constrain future work
CUT  → Completed stable paths → folder trees that won't be touched again
CUT  → Any line whose removal → wouldn't change what Claude does next

KEEP → Active blocker details  → exact error messages if relevant
KEEP → Next pending step       → enough detail to execute immediately
KEEP → Repeatable mistakes     → high recurrence risk only
KEEP → User preferences        → every single one observed
KEEP → Architectural decisions → anything constraining future work
KEEP → Critical dependencies   → things that break if forgotten
```

---

## LINE LIMITS — Enforce These

| Map Size | Max Lines |
|---|---|
| Light | 40 lines |
| Standard | 80 lines |
| Deep | 130 lines |

If approaching limit → compress Layer 2 first, then Layer 4 PATTERNS,
then Layer 3 DONE. Never compress PENDING or BLOCKERS.

---

## TOKEN EFFICIENCY TARGETS

| Approach | Re-context Token Cost | Resume Quality |
|---|---|---|
| Re-paste full conversation | 18–25% | Wasteful |
| Manual user summary | 10–15% | Medium |
| V1 Context Map | 8–12% | Good |
| V2 Context Map | 4–7% | High |
| **V2.1 Living Map (this skill)** | **3–6%** | **High + Zero effort** |

---

## FULL EXAMPLES

### Example A — Code Project (Deep, Auto-appended)

```
╔══════════════════════════════════════════════════════╗
║  CONTEXT MAP V2.1                                    ║
║  Type: Code  |  Size: Deep                           ║
║  Session: React Task Manager App                     ║
╠══════════════════════════════════════════════════════╣
║  LAYER 1 — GOAL                                      ║
║  Full-stack task manager: React + Node/Express +     ║
║  MongoDB + JWT auth + completion stats dashboard     ║
╠══════════════════════════════════════════════════════╣
║  LAYER 2 — STRUCTURE                                 ║
║  Stack    : React, Node.js, Express, MongoDB, JWT    ║
║  Folders  :                                          ║
║    /client/src/components → TaskCard, LoginForm      ║
║    /client/src/pages      → Home, Login, Dashboard   ║
║    /server/routes         → auth.js, tasks.js        ║
║    /server/models         → User.js, Task.js         ║
║    /server/middleware     → authMiddleware.js        ║
║  Env      : JWT_SECRET, MONGO_URI in .env            ║
╠══════════════════════════════════════════════════════╣
║  LAYER 3 — STATE                                     ║
║  ✅ DONE    : Setup, DB, models, auth routes,        ║
║               GET+POST /tasks working                ║
║  🔄 PENDING : 1. PUT /tasks/:id                      ║
║               2. DELETE /tasks/:id                   ║
║               3. LoginForm component                 ║
║  ⚠️ BLOCKER : None                                   ║
║  💡 LOCKED  : JWT → httpOnly cookies, no TypeScript  ║
╠══════════════════════════════════════════════════════╣
║  LAYER 4 — LESSONS                                   ║
║  ❌ MISTAKES: localStorage for JWT → httpOnly        ║
║  🔒 CRITICAL: .env required before npm start         ║
║  🔁 PATTERNS: Folder structure first, then code      ║
╚══════════════════════════════════════════════════════╝
📍 Copy this map to resume session instantly.
```

### Example B — Conversation (Light, Auto-appended)

```
╔══════════════════════════════════════════════════════╗
║  CONTEXT MAP V2.1                                    ║
║  Type: Conversation  |  Size: Light                  ║
║  Session: SE to PM Career Switch                     ║
╠══════════════════════════════════════════════════════╣
║  LAYER 1 — GOAL                                      ║
║  Transition SE → PM internally within 6 months       ║
╠══════════════════════════════════════════════════════╣
║  LAYER 3 — STATE                                     ║
║  ✅ DONE    : Pros/cons, salary (~10-15% drop),      ║
║               internal vs external compared          ║
║  🔄 PENDING : PM portfolio while still in SE role    ║
║  ⚠️ BLOCKER : Manager support uncertain              ║
║  💡 LOCKED  : Internal first. 6mo timeline.          ║
╠══════════════════════════════════════════════════════╣
║  LAYER 4 — LESSONS                                   ║
║  🔒 CRITICAL: APM programs not suitable — too junior ║
║  🔁 PATTERNS: Concrete steps only — no theory        ║
╚══════════════════════════════════════════════════════╝
📍 Copy this map to resume session instantly.
```

---

## WHAT TO NEVER INCLUDE

- Full code blocks of any kind
- Raw conversation dialogue
- Resolved issues with no recurrence risk
- Completed stable folder paths
- Any line whose removal wouldn't affect the resume
- Meta-commentary about the map itself
- Padding or filler

**If in doubt — cut it. A shorter accurate map beats a longer padded one.**

