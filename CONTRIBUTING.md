# Contributing to Context Map

Thank you for taking the time to contribute. Every improvement — big or small — makes this skill better for every Claude user.

---

## What You Can Contribute

### 1. New Example Maps
The most valuable contributions are real-world examples showing Context Map in different domains.

**Good example domains:**
- Security / penetration testing / CTF sessions
- Data science / machine learning projects
- Academic research / literature reviews
- Game development
- DevOps / infrastructure work
- Legal / contract drafting

**Format:** Follow the structure in `examples/code-project-map.md`.
Each example file should include:
- Scenario description (what was being worked on)
- The actual map (in the `╔═╗` format)
- A "What Resuming Looks Like" section showing the one-line resume response

### 2. Skill Improvements
Improvements to `SKILL.md` that make Claude follow the map structure more reliably or produce better output.

Open an Issue first describing the change and the problem it solves — this avoids wasted work.

### 3. README / Documentation
- Fix typos, grammar, or unclear explanations
- Improve installation instructions for a specific platform
- Add platform-specific examples (Claude Code, API, etc.)

### 4. Bug Reports
If the skill produces incorrect maps, resumes badly, or ignores a principle — open an Issue with:
- What you expected Claude to do
- What Claude actually did
- The conversation context (paste the relevant part)

---

## How to Contribute

### Step 1 — Fork and Clone

```bash
git clone https://github.com/YOUR-USERNAME/CLAUDE-SKILL-CONTEXT-MAP.git
cd CLAUDE-SKILL-CONTEXT-MAP
```

### Step 2 — Create a Branch

```bash
git checkout -b feat/your-feature-name
# or
git checkout -b fix/what-you-are-fixing
# or
git checkout -b docs/what-you-are-improving
```

**Branch naming convention:**
- `feat/` — new feature or example
- `fix/` — bug fix or correction
- `docs/` — documentation only

### Step 3 — Make Your Changes

For a new example:
```bash
# Create your file in examples/
touch examples/your-domain-map.md
```

For a skill change:
```bash
# Edit SKILL.md
# Test it thoroughly in Claude before submitting
```

### Step 4 — Commit

Use clear, conventional commit messages:

```bash
git commit -m "feat: add data science / ML session example map"
git commit -m "fix: correct Layer 4 compression rules in SKILL.md"
git commit -m "docs: improve Claude Code installation instructions"
```

### Step 5 — Push and Open a PR

```bash
git push origin feat/your-feature-name
```

Then open a Pull Request on GitHub with:
- A clear title describing the change
- A short description of what you changed and why
- If it's a skill change: describe how you tested it

---

## Guidelines

- **Keep examples realistic.** Made-up scenarios are fine, but they should feel like something a real user would actually work on.
- **Test skill changes in Claude.** If you change SKILL.md, run a real session and verify the map structure and resume behavior work correctly before submitting.
- **One thing per PR.** Keep PRs focused — a new example is one PR, a skill fix is a separate PR. This makes review faster.
- **Credit is given.** All contributors are credited in the CHANGELOG under the version they contributed to.

---

## Questions?

Open a [GitHub Issue](https://github.com/MANISH-524/CLAUDE-SKILL-CONTEXT-MAP/issues) — all questions welcome.
