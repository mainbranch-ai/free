# Skills Guide: When to Use What

Skills are specialized workflows. Each one does something specific. This guide helps you pick the right one.

---

## Free Skills

### /start - Entry Point
**Use when:** Beginning a session, unsure what to do next, want Claude to figure out your state.

**What it does:**
- Pulls latest mb-free updates
- Loads your business repo automatically
- Checks your setup completeness
- Routes you to the right skill

**Daily habit:** Always start sessions with `/start`.

---

### /setup - First-Time Setup
**Use when:** New to Main Branch, need to create your business repo.

**What it does:**
- Creates your business folder structure
- Asks about your business type
- Gathers your context (offer, audience, voice)
- Saves everything to reference files

**One-time:** You only run this once per business.

---

### /think - Research, Decisions, and Context
**Use when:** Exploring a question, making a strategic decision, need to document rationale, or adding new context to reference files.

**What it does:**
- Researches topics (web, your files, your input)
- Synthesizes findings
- Helps you make decisions
- Records everything to files
- Updates reference when you codify
- Adds new context (via codify mode)

**Heavy use:** This is the core skill. Use it for any "should we...?" question.

See [the-think-cycle.md](the-think-cycle.md) for deep dive.

---

### /help - Get Answers
**Use when:** Confused, stuck, have questions about Main Branch.

**What it does:**
- Answers questions from documented curriculum
- Troubleshoots errors
- Explains concepts
- Suggests next skills

**You're using it now.**

---

### /pull - Update Engine
**Use when:** Want to pull the latest mb-free updates.

**What it does:**
- Runs `git pull origin main` on mb-free
- Reports what changed

**Note:** `/start` pulls automatically, so you rarely need `/pull` separately.

---

## Premium Skills (Main Branch Premium)

The following skills are available with Main Branch Premium at skool.com/main-branch:

| Skill | What It Does |
|-------|--------------|
| `/ads` | Generate image ads, video ad scripts, compliance review |
| `/vsl` | Write video sales letters (Skool or B2B frameworks) |
| `/organic` | Mine competitors, create Reels/TikTok/carousels |
| `/wiki` | Personal wiki with atomic notes |
| `/site` | Generate and deploy landing pages from reference files |
| `/newsletter` | Generate weekly newsletter from thinking work (coming soon) |

---

## Decision Tree

```
What do you need?
|
+-- Starting a session?
|   +-- /start
|
+-- First time setup?
|   +-- /setup
|
+-- Research, decide, or add context?
|   +-- /think
|
+-- Confused or stuck?
|   +-- /help
|
+-- Update the engine?
|   +-- /pull
|
+-- Create ads, content, videos, landing pages?
    +-- Main Branch Premium (skool.com/main-branch)
```

---

## Skill Combinations

Common workflows:

**Building your reference:**
1. `/think` - Research your angle
2. `/think codify` - Add findings to reference files
3. Next session starts with richer context

**Learning from results:**
1. `/think research` - Document what worked
2. `/think codify` - Add winning angles to reference
3. Future outputs use updated reference

**Business evolution:**
1. `/think` - Decide on offer change
2. `/think codify` - Update reference with decision
3. Future outputs reflect new offer

---

## When You're Not Sure

If you don't know which skill to use:

1. Run `/start` - It'll detect your state and suggest
2. Ask `/help` - Describe what you want to accomplish
3. Run `/think` - If it's a question worth exploring

Most of the time, `/start` will point you in the right direction.

---

## Creating Your Own Skills

You can create custom skills in **two locations**:

### Option 1: Business Repo Skills (Project-Specific)

Skills that only make sense for one business/project:

```
your-business-repo/
+-- .claude/skills/my-skill/SKILL.md
```

**Use for:** Business-specific workflows like `/notion-export`, `/publish`, `/batch-week`

### Option 2: Global Skills (Work Everywhere)

Skills you want available in **every** Claude Code session:

```
~/.claude/skills/my-skill/SKILL.md
```

This is your **user-level skills directory** -- Claude Code's official location for personal skills that persist across all projects.

**Use for:**
- Personal productivity workflows (`/daily-standup`)
- Cross-project utilities (`/git-cleanup`)
- Admin tools you use everywhere

### Skill Priority

When the same skill name exists in multiple locations, Claude uses this priority:

1. **Project `.claude/skills/`** (highest priority)
2. **User `~/.claude/skills/`** (global)
3. **mb-free `.claude/skills/`** (shared engine)

This means you can override mb-free skills with your own version if needed.
