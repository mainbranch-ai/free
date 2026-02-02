# Beginner Setup Guide

Quick setup for Claude Code + Main Branch.

---

## Prerequisites

1. **GitHub account** - [github.com/signup](https://github.com/signup)
2. **Claude subscription** - Pro ($20/mo) or Max ($100-200/mo) at [claude.ai](https://claude.ai)

---

## Quick Setup (4 Steps)

### 1. Install GitHub Desktop

Download from [desktop.github.com](https://desktop.github.com). Sign in with your GitHub account.

### 2. Install Claude Code

**Mac:**
```bash
curl -fsSL https://claude.ai/install.sh | bash
```

**Windows (PowerShell):**
```powershell
irm https://claude.ai/install.ps1 | iex
```

### 3. Clone mb-free

In GitHub Desktop: **File -> Clone Repository -> URL tab -> paste `https://github.com/mainbranch-ai/mb-free.git`**

Or from the terminal:
```bash
git clone https://github.com/mainbranch-ai/mb-free.git
```

### 4. Start Claude

Open a terminal in the mb-free folder, then:

```bash
claude
```

Type `/start` and follow the prompts.

---

## Daily Workflow (After Setup)

Every time you use Main Branch:

```bash
cd ~/Documents/GitHub/mb-free
claude
/start
```

That's it. `/start` loads your business repo and routes you to the right skill.

---

## Common Issues

### "command not found: claude"

Your terminal doesn't know where Claude is installed. Run:

**Mac:**
```bash
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.zshrc && source ~/.zshrc
```

**Linux/older Mac:**
```bash
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc && source ~/.bashrc
```

### Xcode Command Line Tools (Mac)

If you see a popup about developer tools, click Install. You'll need it for Git operations. The time estimate is usually wrong (says hours, takes minutes).

To reinstall if you canceled: `xcode-select --install`

### Can't push to mb-free

Expected. mb-free is the engine -- it's shared. Your business data goes in your own repo (created via `/setup`).

---

## The Two Repos

```
mb-free/                your-business/
├── Skills              ├── Your offer
├── Templates           ├── Your audience
└── (engine, shared)    ├── Your voice
                        └── (your data)
```

Same engine + different data = outputs tailored to each business.

**Important:** Your business repo is a precision instrument, not a dumping ground. Every file should earn its place by improving what AI can do for you. PDFs, images, and media stay outside the repo -- only markdown reference files go in.

---

## What You Can Do

Once set up, type these commands:

- `/start` - Entry point, detects your state, routes you
- `/think` - Research, make decisions, build reference
- `/setup` - Create your business repo with the right structure
- `/help` - Get answers to any question

---

## Getting Help

- **Stuck?** Open a GitHub issue on mb-free.
- **Want more?** See [skool.com/main-branch](https://www.skool.com/main-branch) for the full skill library and community.
