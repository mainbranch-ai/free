# Troubleshooting

Common issues and fixes for Claude Code + Main Branch.

---

## "command not found: claude"

Terminal doesn't know where Claude is installed. Add it to your PATH.

**Mac (zsh - default on modern Macs):**
```bash
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.zshrc && source ~/.zshrc
```

**Linux or older Mac (bash):**
```bash
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc && source ~/.bashrc
```

**Verify it worked:**
```bash
claude --version
```

---

## Xcode Command Line Tools Popup (Mac)

If you see a popup about downloading "developer tools" or "Xcode Command Line Tools":

1. **Click Install** - You need these for Git operations
2. **Ignore the time estimate** - It says hours but usually takes minutes
3. **Wait for completion** - Don't cancel

**If you accidentally canceled:**
```bash
xcode-select --install
```

---

## Skills Not Working

If slash commands like `/start` or `/think` aren't recognized:

**Check 1: Are you in mb-free?**
```bash
pwd
ls .claude/skills
```

If not in mb-free, skills won't be available.

**Check 2: Did you add mb-free?**

If you started in your business repo, add mb-free:
```
/add-dir ~/Documents/GitHub/mb-free
```

**Best practice:** Always start in mb-free, run `/start`. It handles everything.

---

## Context Feels "Off" or Claude Forgot Things

Claude's context decays as conversations get longer. The CLAUDE.md instructions fade.

**Fix:** Run a slash command to reload fresh instructions.

Good commands for refreshing context:
- `/start` - Reloads and routes
- `/think` - For research/decisions
- `/help` - For questions

---

## MCP Not Working (Apify, etc.)

### "apify not found" in /mcp

MCP wasn't installed correctly. Re-run the setup:

```bash
claude mcp add apify -e APIFY_TOKEN=your_token_here --scope user -- npx -y @apify/actors-mcp-server
```

**Important:** Use `--scope user` so it's saved globally.

### "Invalid token" errors

Check your token at apify.com -> Settings -> API & Integrations. Copy the default token (don't create a new one).

### MCP installed but not showing

MCPs only load at startup. Restart Claude:

```bash
/exit
claude --continue
```

Then type `/mcp` to verify it appears.

### Permission prompts every time

When Claude first uses an MCP, hit `2` to "always allow" instead of `1` for one-time.

---

## Resuming a Session

If you closed Terminal or need to pick up where you left off:

```bash
claude --continue
```

This resumes your previous conversation with full context.

---

## Business Repo Not Loading Automatically

If `/start` doesn't find your business repo:

**Check machine-local config:**
```bash
cat ~/.config/mb-free/local.yaml
```

Should show:
```yaml
default_repo: /Users/yourname/Documents/GitHub/your-business
recent_repos:
  - /Users/yourname/Documents/GitHub/your-business
user:
  name: "Your Name"
  experience: intermediate  # beginner | intermediate | advanced
```

**Common fixes:**

| Problem | Solution |
|---------|----------|
| No config file | Run `/start` -- it will discover your repo and offer to save the path |
| Path is wrong | Run `/start` and select your repo when prompted, say "yes" to save |
| Folder was moved | Delete `~/.config/mb-free/local.yaml` and run `/start` again |

---

## Git Conflicts in mb-free

You shouldn't have any uncommitted changes in mb-free.

If you do:
```bash
cd ~/Documents/GitHub/mb-free
git status
git checkout .  # Discards local changes
git pull origin main
```

**Note:** mb-free is read-only. Any changes you made there should move to your business repo.
