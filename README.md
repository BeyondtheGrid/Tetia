# Tetia Mercury: Play-by-Post Companion

Everything Claude needs to play **Tetia Mercury**, Jeff's Llewyrr cleric in Ronnie's *Beyond the Dragon of Icespire Peak* play-by-post on Discord, and to keep a light campaign record. Jeff directs; Claude acts. Tetia herself comes first: her bible and appendix load in full every session.

## Setting up a computer (once per machine)
Full step-by-step instructions, including signing git in to GitHub and testing the sync, are in **`SETUP.md`**. In short: clone this repo to `~/Tetia`, open that folder in a Claude Code session, and trust it when asked.

From then on, every session pulls the latest from GitHub when it starts, and Claude pushes after every change, so both computers (and the phone) stay in step.

**From your phone:** start a Claude Code session on the web or in the Claude app with this repo. The same instructions and commands load there. Those sessions often work on a branch of their own; Claude still pushes the record to `main`, and tells you if it couldn't.

## Each turn: one command
Type `/write-post`, then paste:
1. **The scene:** everything posted since Tetia last acted, **starting with her own last post** as it appeared on Discord. That's how her post gets filed, edits and all.
2. **Your goals:** what Tetia does and any beats you want. If a party member matters, mention a detail about them; that's Claude's cue to read their full file.
3. **Mechanics and results,** if any: the spell or ability and its level, how it went ("hit," "it failed the save," "she failed her save," "took 12 damage"), and how worn she is if it matters. You track her hit points, spell slots and exhaustion; Claude doesn't.
4. **Length**, if it matters ("short, combat").

Claude checks for conflicts, drafts one post, has an independent checker review it, and hands you the post in a code block ready to paste. Copy from the code block so the bold and underscores come through. **Then it saves the turn in the background** (filing the posts, updating the current state, pushing to GitHub) while you post. "Record saved." tells you it's done.

Each draft is saved to her archive marked pending, and confirmed against your next paste. If you change a post before posting it, your paste shows the change; if you don't paste it, say whether it went up as written.

Add "quick" to skip the independent check when you're in a hurry.

**Don't like a draft?** Just say what to change, in plain words, in the same session ("warmer toward Pip", "cut the last line", "she shouldn't swallow, she's used that"). No command needed, and no need to paste the scene again. After a `/clear` or in a new session, say "revise the pending draft" and what to change.

**When you're done,** wait for "Record saved.", then type `/clear` to start the next turn fresh: everything Claude needs is in the files.

## At milestones
Type `/log-update` when a scene ends or something lasting happens (a fight is decided, a bond, promise or discovery, a lasting injury, a new item, a level-up), or to file a GM recap, a lore post or a batch of chat. Claude writes a milestone entry, like the GM's recaps, updates her canon if something lasting changed, and pushes to GitHub. `/write-post` will tell you when a scene looks like a milestone.

You can also just tell Claude in plain words; it knows to run these.

## What's where
| Path | What it is |
|---|---|
| `SETUP.md` | One-time setup for each computer |
| `setup/claude-code-autosetup.md` | The same setup, as instructions for Claude Code to run |
| `CLAUDE.md` | Claude's standing instructions (loads automatically) |
| `director-preferences.md` | How you want posts written. Edit it anytime |
| `character/bible.md` | Tetia's master canon |
| `character/bible-appendix.md` | Head-to-toe physical, behavioral and world detail |
| `character/sheet-notes.md` | Her mechanics, from D&D Beyond |
| `character/homeland-moonshae.md` | Moonshae, Llewyrr and Sarifal lore |
| `campaign/current-state.md` | The here and now, with the party roster (loads every session) |
| `campaign/table-rules.md` | The post format (loads every session) |
| `campaign/gm-rules.md` | The GM's own rules: fees, sign-ups, house rules |
| `campaign/party.md`, `campaign/party/` | Who posts as whom; one file per party member |
| `campaign/npcs.md` | NPCs, enemies, former companions and places |
| `campaign/log.md` | The story so far as milestones; what the party knows; open threads |
| `campaign/gm-recaps.md`, `gm-lore.md`, `chat/` | The GM's recaps and lore, and Discord chat, verbatim |
| `campaign/setting.md` | Player-facing Leilon and Sword Coast lore |
| `posts/archive.md` | Every post Tetia has made |
| `.claude/` | The `/write-post` and `/log-update` commands, the continuity checker, and the sync hook |

## Good habits
- **Paste the full scene** each time, starting from her last post. It's how the chat record and her archive stay complete.
- **Say how worn she is** when it matters (a hard fight, a lot of magic spent). Her visible strain follows what you tell it.
- **One turn per session.** `/clear` after each post keeps sessions small and quick.
- **Changing who Tetia is** (a new fact about her past, a retcon) goes through you. Claude proposes; you decide; the bible records it with a version note.
- **If you edit files by hand**, commit and push them, or ask Claude to.
