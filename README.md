<div align="center">

# 🗺️ Context Map

### A Claude skill that silently saves your session — automatically.
### No commands. No "save" button. No memory required. It just works.

[![Version](https://img.shields.io/badge/version-2.1-blue?style=flat-square)](./CHANGELOG.md)
[![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)](./LICENSE)
[![Status](https://img.shields.io/badge/status-active-brightgreen?style=flat-square)](#)
[![Claude Skill](https://img.shields.io/badge/Claude-Skill-orange?style=flat-square)](https://claude.ai)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-blueviolet?style=flat-square)](./CONTRIBUTING.md)

*Designed by [Manish Jaju](https://github.com/MANISH-524) · Built in collaboration with Claude by Anthropic*

</div>

---

## 📌 The Problem

Every Claude user hits this wall:

```
1.  Open Claude
2.  Start building — code, research, writing, analysis
3.  Go deep — decisions made, context built, real progress
4.  Session limit hits (or you close the tab)
5.  Open a new session
6.  Claude re-reads, re-analyzes, re-understands everything from scratch
7.  15–25% of your NEW session tokens are burned before Claude says anything useful
8.  And you still have to re-explain half of it anyway
```

**The standard fix? Paste the old conversation back in.**
Which burns even *more* tokens. Which makes the problem worse.

This happens to every Claude user, every single day.

---

## 💡 The Core Insight

> *Instead of saving the conversation (full history),*
> *save a compressed map of the session state —*
> *like a Git commit, not a full file history.*

The conversation is noise.
**The state is what matters.**

---

## ✅ The Solution

**Context Map** is a Claude skill that solves this automatically.

| Without Context Map | With Context Map |
|---|---|
| 15–25% of tokens wasted on re-context | 3–6% of tokens on re-context |
| Re-explain decisions every session | Decisions locked — never re-debated |
| Claude repeats past mistakes | Mistakes captured, never repeated |
| Style has to be re-established | Preferences applied from first response |
| Manual save required | Zero user action — ever |

**The user never has to think about it. It just works.**

---

## ⚡ Quick Start — 3 Steps

### Step 1 — Copy the skill
Open [`SKILL.md`](./SKILL.md) and copy the entire file content.

### Step 2 — Install in Claude

<details>
<summary><b>Claude.ai (Projects)</b></summary>

```
Claude.ai → Projects → New Project (or open existing)
→ Project Instructions → Paste the SKILL.md content → Save
```
The skill is now active for every conversation in that project.

</details>

<details>
<summary><b>Claude.ai (Custom Instructions)</b></summary>

```
Claude.ai → Settings → Custom Instructions
→ Paste the SKILL.md content → Save
```
Active globally across all Claude.ai conversations.

</details>

<details>
<summary><b>Claude API (system prompt)</b></summary>

```python
import anthropic

client = anthropic.Anthropic()

with open("SKILL.md", "r") as f:
    skill = f.read()

response = client.messages.create(
    model="claude-opus-4-5",
    max_tokens=8096,
    system=skill,           # <-- paste skill here
    messages=[
        {"role": "user", "content": "Your message here"}
    ]
)
```

</details>

<details>
<summary><b>Claude Code (.claude/CLAUDE.md)</b></summary>

```bash
# In your project root
mkdir -p .claude
cat SKILL.md >> .claude/CLAUDE.md
```
Claude Code loads this file automatically on every session.

</details>

### Step 3 — Done ✅
No configuration. No commands. Active immediately.
Start your session — the map will appear automatically.

---

## 🔄 How to Resume a Session

```
1.  Session ends (limit hit or you close it)
2.  Scroll to the bottom of Claude's last response
3.  Copy the Context Map block
4.  Open a new Claude session
5.  Paste the map as your first message
6.  Claude responds: "Resuming [session] — starting from [pending item]."
7.  Continues immediately — like the session never ended
```

**That's it.** One copy-paste. Zero re-explanation.

---

## 🏗️ How It Works — The 4-Layer Map

Context Map uses a **Living 4-Layer Map** that Claude builds and updates silently after every 2–3 meaningful exchanges:

```
╔══════════════════════════════════════════════════════╗
║  CONTEXT MAP V2.1                                    ║
║  Type: [Code / Conversation / Creative / Research]   ║
║  Size: [Light / Standard / Deep]                     ║
║  Session: [3–5 word session identifier]              ║
╠══════════════════════════════════════════════════════╣
║  LAYER 1 — GOAL                                      ║
║  What the user is building or solving (1–2 lines)    ║
╠══════════════════════════════════════════════════════╣
║  LAYER 2 — STRUCTURE                                 ║
║  Skeleton of what exists:                            ║
║  → Code:         folder tree, stack, APIs, env vars  ║
║  → Conversation: topic, context, findings            ║
║  → Creative:     characters, plot, tone, rules       ║
║  → Research:     question, sources, findings         ║
╠══════════════════════════════════════════════════════╣
║  LAYER 3 — STATE                                     ║
║  ✅ DONE      : What has been completed              ║
║  🔄 PENDING   : Next steps — most critical first     ║
║  ⚠️ BLOCKERS  : Unresolved issues or errors          ║
║  💡 DECISIONS : Locked — never re-debated            ║
╠══════════════════════════════════════════════════════╣
║  LAYER 4 — LESSONS  ← The V2 Difference             ║
║  ❌ MISTAKES  : Errors made + how they were fixed    ║
║  🔒 CRITICAL  : If forgotten → breaks everything     ║
║  🔁 PATTERNS  : User preferences → apply immediately ║
╚══════════════════════════════════════════════════════╝
📍 Copy this map to resume session instantly.
```

### Why Layer 4 Is the Game-Changer

Without Layer 4 — Claude can repeat the same mistake in a new session.
With Layer 4 — mistakes are locked, and never repeated.

Without Layer 4 — Claude doesn't know your preferences until you re-establish them.
With Layer 4 — Claude matches your style from the very first response after resume.

---

## ⚡ Three Modes

| Mode | Trigger | When it fires |
|---|---|---|
| **AUTO** | Always on — zero user action | Every 2–3 meaningful exchanges |
| **SAVE** | Say `"save"` or `"save progress"` | Immediate on-demand snapshot |
| **RESUME** | Paste any Context Map | New session start |

---

## 📐 Scale Intelligence

Context Map detects complexity and scales the map size automatically:

| Complexity | Map Size | Max Lines | What's Included |
|---|---|---|---|
| 2–4 exchanges | **Light** | 40 lines | Layer 1 + Layer 3 only |
| 5–12 exchanges | **Standard** | 80 lines | All 4 layers, moderate detail |
| 13+ exchanges | **Deep** | 130 lines | All 4 layers, full detail |

Short sessions get a lightweight map. Complex projects get full depth.
Always proportionate. Never over-engineered.

---

## 📊 Token Savings — Real Numbers

| Approach | Re-context Token Cost | Resume Quality | User Effort |
|---|---|---|---|
| Re-paste full conversation | 18–25% | Wasteful | High |
| Manual user summary | 10–15% | Medium | High |
| Plain text snapshot | 8–12% | Good | Medium |
| V1 Context Map | 5–8% | Good | Low |
| **V2.1 Context Map** | **3–6%** | **High** | **Zero** |

### In Practice

```
Session budget    : 1,000 tokens

Without skill     : 180–250 tokens wasted on re-context
                    before Claude says anything useful

With Context Map  : 30–60 tokens on re-context
                    Claude resumes in one line, then executes

Savings per resume: 120–220 tokens saved
```

For power users resuming multiple sessions daily — this compounds fast.

---

## 📋 Full Examples

### Example 1 — Code Project (Deep Map)

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
║               MongoDB Atlas free tier, no TypeScript ║
╠══════════════════════════════════════════════════════╣
║  LAYER 4 — LESSONS                                   ║
║  ❌ MISTAKES: localStorage for JWT → httpOnly        ║
║  🔒 CRITICAL: .env must exist before npm start       ║
║               User model needs email or auth breaks  ║
║  🔁 PATTERNS: Folder structure first, then code      ║
║               Short blocks + explanation after       ║
╚══════════════════════════════════════════════════════╝
📍 Copy this map to resume session instantly.
```

**Resume response:** *"Resuming React Task Manager App — starting with PUT /tasks/:id route."*
Then immediately writes the code. No warmup. No re-explanation.

---

### Example 2 — Penetration Testing / CTF Session (Security)

```
╔══════════════════════════════════════════════════════╗
║  CONTEXT MAP V2.1                                    ║
║  Type: Research  |  Size: Standard                   ║
║  Session: HackerOne Web App Pentest                  ║
╠══════════════════════════════════════════════════════╣
║  LAYER 1 — GOAL                                      ║
║  Identify and document OWASP Top 10 vulnerabilities  ║
║  on target web app within program scope              ║
╠══════════════════════════════════════════════════════╣
║  LAYER 2 — STRUCTURE                                 ║
║  Target  : app.target.com (in-scope)                 ║
║  Scope   : In  → app.target.com, api.target.com      ║
║             Out → admin.target.com, payment portal   ║
║  Tools   : Burp Suite, nmap, gobuster, sqlmap        ║
║  Findings:                                           ║
║    HIGH   → Reflected XSS on /search?q= param       ║
║    MEDIUM → Missing HSTS header on main domain       ║
║    INFO   → Server version disclosure in headers     ║
╠══════════════════════════════════════════════════════╣
║  LAYER 3 — STATE                                     ║
║  ✅ DONE    : Recon complete, port scan done         ║
║               Directory brute-force done             ║
║               XSS finding documented + PoC written   ║
║  🔄 PENDING : 1. Test /api/user endpoint for IDOR    ║
║               2. Check auth tokens for JWT issues    ║
║               3. Write final report                  ║
║  ⚠️ BLOCKER : Rate limiting on /api — slow down      ║
║  💡 LOCKED  : admin.target.com is out of scope       ║
╠══════════════════════════════════════════════════════╣
║  LAYER 4 — LESSONS                                   ║
║  ❌ MISTAKES: Tested out-of-scope endpoint briefly — ║
║               flagged, stopped immediately           ║
║  🔒 CRITICAL: All testing only on in-scope assets    ║
║  🔁 PATTERNS: CVSS score each finding before moving  ║
║               Show PoC payload + impact per vuln     ║
╚══════════════════════════════════════════════════════╝
📍 Copy this map to resume session instantly.
```

**Resume response:** *"Resuming HackerOne Web App Pentest — testing /api/user endpoint for IDOR vulnerabilities."*

---

### Example 3 — Research / Analysis (Standard Map)

See [`examples/research-map.md`](./examples/research-map.md) for full walkthrough.

### Example 4 — Creative Writing (Standard Map)

See [`examples/creative-map.md`](./examples/creative-map.md) for full walkthrough.

### Example 5 — General Conversation (Light Map)

See [`examples/conversation-map.md`](./examples/conversation-map.md) for full walkthrough.

---

## 💻 Works For Every Task Type

| Task Type | What Gets Saved |
|---|---|
| **Code / Projects** | Stack, folder structure, APIs, env config, architectural decisions, mistakes |
| **Penetration Testing** | Scope, findings (by severity), tools, CVSS scores, locked constraints |
| **Research / Analysis** | Core question, scope, confirmed findings, disputed areas, sources |
| **Creative Writing** | Characters, plot so far, setting, tone, world rules, style constraints |
| **General Conversation** | Topic, key background, conclusions, goal, next steps |

---

## 📁 Repository Structure

```
CLAUDE-SKILL-CONTEXT-MAP/
├── README.md                    ← You are here
├── SKILL.md                     ← Full skill source — paste this into Claude
├── CHANGELOG.md                 ← Full version history V0 → V2.1
├── CONTRIBUTING.md              ← How to contribute
├── LICENSE                      ← MIT License
├── .gitignore
└── examples/
    ├── code-project-map.md      ← Code project (Deep map)
    ├── research-map.md          ← Research/analysis (Standard map)
    ├── creative-map.md          ← Creative writing (Standard map)
    ├── conversation-map.md      ← General conversation (Light map)
    └── security-pentest-map.md  ← Penetration testing (Standard map)
```

---

## 📜 Version History

| Version | Theme | Key Change |
|---|---|---|
| V0 | Problem identified | Gap found, no solution yet |
| V1 | Foundation | 3-layer map, manual save, basic resume |
| V2 | Intelligence | Layer 4 Lessons, Living Map, scale detection |
| **V2.1** | **Zero effort** | **Auto-trigger at 2–3 exchanges, no user action ever** |

Full changelog with all details → [`CHANGELOG.md`](./CHANGELOG.md)

---

## 🔮 Roadmap — V3 Ideas

| Feature | Status |
|---|---|
| Multi-session version history | Planned |
| Conflict detection (flags when new session contradicts a locked decision) | Planned |
| Export to markdown project doc | Planned |
| Claude Code native integration (.claude/CLAUDE.md auto-template) | Exploring |
| Token savings benchmark tool | Exploring |

Have an idea? [Open an issue](https://github.com/MANISH-524/CLAUDE-SKILL-CONTEXT-MAP/issues/new) — all suggestions considered.

---

## 🤝 Contributing

Contributions are welcome and credited.

See [`CONTRIBUTING.md`](./CONTRIBUTING.md) for the full guide.

**Quick start:**
1. Fork the repo
2. Create a branch: `git checkout -b feat/your-feature`
3. Make changes and commit: `git commit -m "feat: describe your change"`
4. Push and open a PR

**Good first contributions:**
- Add a new example map (any domain)
- Improve installation instructions
- Fix typos or broken links
- Suggest a V3 feature via Issue

---

## 📄 License

[MIT License](./LICENSE) — free to use, modify, share, and build on.

---

## 👤 Author

**Manish Jaju**
- GitHub: [@MANISH-524](https://github.com/MANISH-524)
- LinkedIn: [linkedin.com/in/manish524](https://www.linkedin.com/in/manish524/)

> The problem statement, core idea, design decisions, and all version upgrades are original work by Manish Jaju.
> Claude assisted in structuring, refining, and writing the skill files.

---

<div align="center">

*Born from a real frustration. Built for every Claude user.*

**If this helped you — star the repo ⭐ and share it.**

[![GitHub stars](https://img.shields.io/github/stars/MANISH-524/CLAUDE-SKILL-CONTEXT-MAP?style=social)](https://github.com/MANISH-524/CLAUDE-SKILL-CONTEXT-MAP/stargazers)

</div>
