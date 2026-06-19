# Example — Research / Analysis Map (Standard)

This is what a Context Map looks like for a research or analysis session.

## Scenario
Researching the best database options for a high-traffic SaaS application.
Session ended after comparing PostgreSQL and MongoDB — Redis and Cassandra still pending.

---

## The Map

```
╔══════════════════════════════════════════════════════╗
║  CONTEXT MAP V2.1                                    ║
║  Type: Research  |  Size: Standard                   ║
║  Session: SaaS Database Selection Research           ║
╠══════════════════════════════════════════════════════╣
║  LAYER 1 — GOAL                                      ║
║  Choose the right database stack for a SaaS app      ║
║  expecting 100k+ users and high read/write load      ║
╠══════════════════════════════════════════════════════╣
║  LAYER 2 — STRUCTURE                                 ║
║  Question : Best DB stack for high-traffic SaaS      ║
║  Scope    : In  → PostgreSQL, MongoDB, Redis,        ║
║                    Cassandra                         ║
║             Out → Oracle, MS SQL (licensing cost)    ║
║  Sources  : Official docs, AWS benchmarks,           ║
║             Stripe/Airbnb engineering blogs          ║
║  Confirmed:                                          ║
║    - PostgreSQL wins for relational + ACID needs     ║
║    - MongoDB better for flexible schema + scale      ║
║    - Both viable — depends on data structure         ║
║  Disputed :                                          ║
║    - MongoDB vs PostgreSQL for mixed workloads       ║
║      (conflicting benchmark results found)           ║
╠══════════════════════════════════════════════════════╣
║  LAYER 3 — STATE                                     ║
║  ✅ DONE    : PostgreSQL deep dive complete           ║
║               MongoDB deep dive complete             ║
║               Head-to-head comparison done           ║
║  🔄 PENDING : 1. Redis analysis (caching layer)      ║
║               2. Cassandra analysis (write-heavy)    ║
║               3. Final recommendation + reasoning    ║
║  ⚠️ BLOCKER : Mixed benchmark results for MongoDB    ║
║               need resolution before final rec       ║
║  💡 LOCKED  : Oracle/MS SQL excluded (cost)          ║
║               User's app is write-heavy (60/40)      ║
╠══════════════════════════════════════════════════════╣
║  LAYER 4 — LESSONS                                   ║
║  🔒 CRITICAL: User's workload is 60% writes —        ║
║               this changes the recommendation        ║
║  🔁 PATTERNS: User wants pros/cons tables            ║
║               Wants real-world company examples      ║
╚══════════════════════════════════════════════════════╝
📍 Copy this map to resume session instantly.
```

---

## What Resuming Looks Like

**New session. User pastes the map above.**

Claude responds:

> "Resuming SaaS Database Selection Research — starting Redis analysis for the caching layer."

Then immediately dives into Redis — using pros/cons table format and real-world examples (matching the user's established pattern), keeping the 60% write-heavy workload context in mind throughout.

No "what databases have we covered?" No re-explaining PostgreSQL. No re-asking about scope.
**One line. Then Redis.**

