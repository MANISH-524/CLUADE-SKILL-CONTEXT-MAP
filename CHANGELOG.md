# Changelog

All versions of Context Map documented here.

---

## V2.1 — Current Release

**Theme: Zero User Effort**

### What Changed
- Auto-trigger reduced from 5+ exchanges to **2–3 meaningful exchanges**
- Removed all user-facing commands — skill is now fully automatic
- Claude owns session continuity responsibility — user focuses on their work
- Added precise definition of "meaningful exchange" to prevent false triggers
- Enforced line limits per map size (Light: 40 / Standard: 80 / Deep: 130)
- AUTO mode map appended silently below response — never interrupts the answer
- Resume mode: single-line acknowledgment then immediate execution
- Token target improved: **3–6%** re-context cost (down from 4–7%)

### Core Philosophy Added
> "The user came to Claude to solve a problem. Not to manage a tool."

---

## V2 — Living Map Release

**Theme: Intelligence + Lessons**

### What Changed from V1
- Added **Layer 4 — Lessons** (Mistakes / Critical / Patterns)
  - Captures mistakes made mid-session so they don't repeat on resume
  - Captures critical dependencies that break work if forgotten
  - Captures user preferences for immediate style-matching on resume
- Map changed from one-time snapshot to **Living Map** (updates continuously)
- Added **Scale Detection**: Light / Standard / Deep map sizes
- Added **Priority Intelligence**: critical items listed first in every layer
- Task-type templates refined for Code / Conversation / Creative / Research
- Compression rules made explicit — what to cut vs what to keep
- Resume rules hardened: decisions permanently locked, zero re-explanation

### Gap That V2 Still Had
- Auto-trigger was 5+ exchanges — too late for short sessions
- Still had optional /context-map command — put burden on user memory
- User could still forget to activate it

---

## V1 — Foundation Release

**Theme: Map Over Transcript**

### What Was Built
- Core insight: save **state** not **history**
- 3-Layer map structure: Goal → Structure → State
- Task-type detection: Code / Conversation / Creative / Research
- Layer 2 templates for each task type
- Basic resume rules: no re-explanation, decisions locked
- Proactive save reminder when session gets long
- Token efficiency target: 5–8% re-context cost

### Gaps Identified After V1
- Map generated once — went stale if session continued after save
- No memory of mistakes — Claude could repeat errors next session
- No user preference capture — style had to be re-established each resume
- Scale not considered — same map depth for 3-message chat and 50-message project
- Still manual — user had to remember to say "save"
- No priority ordering — all items treated equally

---

## V0 — Problem Statement

**Theme: Gap Identified**

### The Observation
Claude uses 18–25% of a new session's tokens just to re-understand what was already done in the previous session. This happens because:
- Claude has no persistent memory between sessions
- Users re-paste old conversations as their only option
- Re-pasting triggers full re-analysis before any useful output

### The Insight
Instead of saving the conversation (full history), save a **compressed map of the session state** — like a commit message, not a diff.

### What V0 Lacked
Everything. Problem was clear. Solution was not yet designed.

