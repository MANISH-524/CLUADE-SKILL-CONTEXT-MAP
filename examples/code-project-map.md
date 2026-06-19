# Example — Code / Project Map (Deep)

This is what a Context Map looks like for a complex coding project.

## Scenario
Building a full-stack React + Node.js task manager app.
Session ended mid-build after completing backend auth routes.

---

## The Map

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
║  🔄 PENDING : 1. PUT /tasks/:id (update task)        ║
║               2. DELETE /tasks/:id (delete task)     ║
║               3. LoginForm React component           ║
║  ⚠️ BLOCKER : None currently                         ║
║  💡 LOCKED  : JWT in httpOnly cookies (not storage)  ║
║               MongoDB Atlas free tier                ║
║               No TypeScript in this project          ║
╠══════════════════════════════════════════════════════╣
║  LAYER 4 — LESSONS                                   ║
║  ❌ MISTAKES: Used localStorage for JWT initially →  ║
║               corrected to httpOnly cookies          ║
║  🔒 CRITICAL: .env file must exist before npm start  ║
║               User model needs email field or auth   ║
║               breaks entirely                        ║
║  🔁 PATTERNS: Show folder structure before any code  ║
║               Short code blocks + explanation after  ║
╚══════════════════════════════════════════════════════╝
📍 Copy this map to resume session instantly.
```

---

## What Resuming Looks Like

**New session. User pastes the map above.**

Claude responds:

> "Resuming React Task Manager App — starting with PUT /tasks/:id route."

Then immediately writes the update route code.

No re-explanation. No "let me understand your project." No questions about decisions already made.
**One line. Then execution.**

