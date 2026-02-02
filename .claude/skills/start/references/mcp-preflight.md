# MCP Pre-Flight Check

Verify required MCPs are installed before routing to skills that need them.

---

## Why This Matters

MCPs install to USER'S machine (`~/.claude.json`), not the repo. When someone clones their business repo on a new machine, MCPs won't be there.

---

## Check Flow

### 1. Read expected MCPs from config

```yaml
# From .main-branch/config.yaml
mcps:
  apify:
    required_for: [think]  # Handles web scraping AND YouTube transcripts
    setup_guide: ".claude/skills/think/references/apify-setup.md"
```

### 2. Check if MCP tools are available

Look for tool presence:
- `mcp__apify__*` tools -> Apify loaded (handles web scraping + YouTube transcripts)

### 3. Prompt if missing

If routing to skill that needs missing MCP:

> "The think skill works best with Apify. Not set up on this machine.
>
> 1. Set up now (5 min, one-time)
> 2. Skip for now (some features limited)"

If user picks 1 -> Show setup guide path, walk through it.

---

## When to Check

- **Always** when routing to skill that needs MCPs
- **Don't block** on optional MCPs — mention limitations
- **Remember** result for session (don't re-check)

---

## Research Tools Check

These tools enhance `/think` but are optional (except Apify which is important):

| Tool | Check Method | If Missing |
|------|--------------|------------|
| **Apify** | `mcp__apify__search-actors` tool exists | Offer setup (important - enables YouTube + Instagram mining) |
| **Gemini** | `$GOOGLE_API_KEY` set | Note, don't block (fallback: multi-source WebSearch) |

### Detection Order

Run on first `/think` invocation:

```bash
# 1. Apify - check for MCP tools (most important)
# If mcp__apify__* tools exist -> Apify loaded

# 2. Gemini - env var
[ -n "$GOOGLE_API_KEY" ] && echo "Gemini available"
```

### Reporting

**Good (all tools):**
> "Research tools ready: Apify, Gemini"

**Partial (common case):**
> "Research tools: Apify ready. Gemini not configured (web search fallback available)."

**Missing Apify (important):**
> "Apify MCP not detected. YouTube and Instagram mining won't work.
> Set up now? (5 min one-time) Or skip for this session."

### Progressive Disclosure

- Report availability once at session start
- Don't nag about missing optional tools
- Only offer setup when user tries to use missing capability
- Always provide fallback path

---

## Config vs Installation

| What | Where | Portable? |
|------|-------|-----------|
| "What this business needs" | `.main-branch/config.yaml` | Yes (git) |
| "What this machine has" | `~/.claude.json` | No (local) |

Config documents requirements. Installation state is Claude Code's domain. See [config-system.md](config-system.md) for the full config file layout.
