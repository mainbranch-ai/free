# Main Branch

**Build a business brain that AI remembers.**

---

Every conversation with AI starts from zero. You explain your business, your audience, your voice -- again. Main Branch fixes this. You build reference files once, refine them over time, and every AI interaction starts from *your* context.

This is not passive memory. It is active reference management -- files you own, edit, and version control. The act of building them IS the thinking. The better your reference, the better every output.

---

## Install (3 Steps)

```bash
# 1. Clone the engine
git clone https://github.com/mainbranch-ai/mb-free.git

# 2. Open it
cd mb-free

# 3. Start Claude and type /start
claude
```

> Requires [Claude Code](https://claude.ai) (Pro or Max subscription).

---

## What You Get

| Skill | What It Does |
|-------|--------------|
| `/start` | Detects your state, loads context, routes you |
| `/setup` | Creates your business repo with the right structure |
| `/think` | Research -> decide -> codify into reference files |
| `/help` | Answers questions, troubleshoots, explains concepts |
| `/pull` | Updates the engine to the latest version |

---

## How It Works

**Engine + Data = Output**

Main Branch separates the engine (skills, templates) from your data (reference files, research, decisions). Same engine, different data, different outputs.

```
mb-free/ (engine)           your-repo/ (data)
├── Skills                  ├── reference/
├── Templates               │   ├── soul.md      (WHY you exist)
└── Docs                    │   ├── offer.md     (WHAT you sell)
                            │   ├── audience.md  (WHO buys)
                            │   └── voice.md     (HOW you sound)
                            ├── research/
                            ├── decisions/
                            └── outputs/
```

---

## The Compound Context Cycle

```
Research -> Decide -> Codify -> Generate -> Learn -> Research...
```

1. **Research** -- Explore questions, gather information
2. **Decide** -- Make choices with rationale
3. **Codify** -- Update reference files with what you learned
4. **Generate** -- Create outputs informed by your reference
5. **Learn** -- What worked? Loop back to research

Each cycle makes the next one better. Context compounds.

---

## Philosophy

Main Branch is a reconnection mechanism.

Most business owners become *dissociated* from their work. They execute brilliantly but feel nothing. Reference files are the solution -- the act of writing `soul.md`, updating `offer.md`, refining `voice.md` keeps you associated with WHY you do this.

Your repo is a precision instrument, not a dumping ground. Quantity of context hurts. Quality of context compounds.

Read the full philosophy: [docs/philosophy.md](docs/philosophy.md)

---

## Reference File Templates

Templates are included for the four core reference files:

| File | Purpose |
|------|---------|
| [`soul.md`](templates/reference/soul.md) | Why you exist -- reconnection fuel |
| [`offer.md`](templates/reference/offer.md) | What you sell -- price, mechanism, benefits |
| [`audience.md`](templates/reference/audience.md) | Who buys -- real people, not avatars |
| [`voice.md`](templates/reference/voice.md) | How you sound -- tone, phrases, personality |

`/setup` copies these into your business repo automatically.

---

## The Path

| Phase | What | You Learn |
|-------|------|-----------|
| **1. Terminal** | Claude Code + skills | How to think with AI |
| **2. Personal Cloud** | Railway + Postiz | How to run infrastructure |
| **3. Local** | Your own box | How to depend on no one |

---

## Premium

The free engine gives you the thinking foundation -- research, decisions, and reference files.

The full skill library adds output generation: ad creation, video scripts, organic content, landing pages, compliance review, and community. Available at [skool.com/main-branch](https://www.skool.com/main-branch).

---

## License

MIT
