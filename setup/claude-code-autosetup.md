# Tetia: Automated Local Setup (for Claude Code)

**For Claude Code.** Jeff will give you this document in a Claude Code session on his Mac. Your job: get the Tetia play-by-post repo working locally, so that a Claude Code session opened in the repo folder loads its instructions, commands, agent and sync hook, and can commit and push to GitHub. Run it once on each of his computers; it is safe to run again.

## Ground rules
- **Work through the steps in order.** Report each step's result in one short line as you go.
- **Never delete, overwrite or reset anything** that already exists. Never force-push. Do not edit any file in the repo during setup.
- **Ask Jeff before installing any software**, and hand him any step that needs him (a browser sign-in, his Mac password). Give him the exact command to paste into Terminal, then wait for him to say it's done and re-check.
- If a step fails twice, stop and explain plainly what failed and what Jeff can do.

## Settings
| Name | Value |
|---|---|
| Repo | `BeyondtheGrid/Tetia` |
| Clone URL | `https://github.com/BeyondtheGrid/Tetia.git` |
| Branch | `main` |
| Target folder | `$HOME/Tetia` (if Jeff names another location, use that everywhere below) |

---

## Step 1: Confirm the machine
Run `uname -s` and `sw_vers -productVersion`. This document assumes macOS (`Darwin`). If it isn't macOS, tell Jeff and adapt the install commands for his system before continuing.

## Step 2: Git
Run `git --version`.
- If git is missing, or macOS asks to install the Command Line Tools: run `xcode-select --install`, tell Jeff a system installer has opened and ask him to finish it, then re-check.

## Step 3: GitHub CLI
Run `command -v gh`.
- **Present:** continue.
- **Missing, Homebrew present** (`command -v brew` succeeds): ask Jeff's permission, then run `brew install gh`.
- **Missing, no Homebrew:** offer Jeff two options and wait for his choice:
  1. Install Homebrew. He runs this in Terminal himself, since it asks for his password: `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`. Afterward, run `brew install gh`.
  2. Install the GitHub CLI from its own installer at https://cli.github.com.
- Re-check with `gh --version`.

## Step 4: Sign in to GitHub
Run `gh auth status`.
- **Not signed in:** ask Jeff to run this in Terminal and complete the sign-in in his browser:
  `gh auth login --hostname github.com --git-protocol https --web`
  Wait for him, then run `gh auth status` again.
- Once signed in, run `gh auth setup-git` so git uses that sign-in for pushes.
- Confirm access: `gh repo view BeyondtheGrid/Tetia --json name,visibility,viewerPermission`. `viewerPermission` must be `ADMIN`, `MAINTAIN` or `WRITE`. If it isn't, stop: Jeff is signed in to the wrong GitHub account.

## Step 5: Commit identity
Run `git config --global user.name` and `git config --global user.email`.
- If either is empty, ask Jeff for the value (name: suggest "Jeff"; email: the one on his GitHub account) and set it with `git config --global user.name "…"` / `git config --global user.email "…"`.

## Step 6: Clone or update the repo
Check the target folder:
- **Doesn't exist:** `gh repo clone BeyondtheGrid/Tetia "$HOME/Tetia"`.
- **Exists and is this repo** (`git -C "$HOME/Tetia" remote get-url origin` contains `BeyondtheGrid/Tetia`, ignoring case):
  - Run `git -C "$HOME/Tetia" status --porcelain`.
  - If that prints nothing: `git -C "$HOME/Tetia" checkout main` and `git -C "$HOME/Tetia" pull --ff-only origin main`.
  - If it prints anything, there are local changes: **stop and tell Jeff.** Don't touch them.
- **Exists but is something else:** don't touch it. Ask Jeff for a different location (for example `$HOME/Projects/Tetia`) and use that from here on.

Then make sure the remote uses the exact name: `git -C "<target>" remote set-url origin https://github.com/BeyondtheGrid/Tetia.git`.

## Step 7: Verify the contents
Confirm that each of these exists in the target folder:
- `CLAUDE.md`, `README.md`, `SETUP.md`, `director-preferences.md`
- `character/bible.md`, `character/bible-appendix.md`, `character/sheet-notes.md`
- `campaign/current-state.md`, `campaign/table-rules.md`, `campaign/party.md`, `posts/archive.md`
- `.claude/settings.json`, `.claude/skills/write-post/SKILL.md`, `.claude/skills/log-update/SKILL.md`, `.claude/agents/continuity-check.md`

Then:
- Check the settings file is valid JSON: `python3 -m json.tool "<target>/.claude/settings.json" > /dev/null && echo valid`.
- Show the latest commits: `git -C "<target>" log --oneline -3`.

If anything is missing, stop and tell Jeff which files.

## Step 8: Test sync without changing anything
Run `git -C "<target>" fetch origin`, then `git -C "<target>" push --dry-run origin main`. The push dry run should report "Everything up-to-date". An authentication error means going back to Step 4.

Then run the same command the session-start hook uses:
`cd "<target>" && git pull --ff-only --quiet origin main && echo "sync OK"`

## Step 9: Report, and hand over to Jeff
Give Jeff a short summary: each step with ✓ or ✗, the folder path, the latest commit, and anything he still needs to do.

Then tell him plainly: **this session can't load the project, because it wasn't opened in the project folder.** To finish:
1. **Open the project.** Start a new Claude Code session and choose the folder `<target>` itself, not a folder above it.
2. **Trust the folder** when asked, so the sync hook can run.
3. **Check it in the new session:**
   - Typing `/` lists **write-post** and **log-update**.
   - *"Where does the campaign stand, and what is Tetia's spell-slot status?"* gets where the party is in Thalivar's Tower, whether Tetia is in play, and how many spell slots she has used.
   - *"Which agents do you have for this project?"* names **continuity-check**.
   - No "SYNC WARNING" appears at the start.
4. **Test the round trip.**
   - **First computer:** make one small real change in that session (for example, once the backstory has gone to Ronnie: *"Mark the GM backstory as sent"*), then check the new commit appears on GitHub.
   - **Second computer:** ask *"What's the most recent commit?"* It should match the change made on the first computer.

From then on, all of Tetia's work happens in sessions opened on that folder. `README.md` covers day-to-day use.
