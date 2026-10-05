# Tetia Mercury: Play-by-Post Companion

Everything Claude needs to play **Tetia Mercury**, Jeff's Llewyrr cleric in Ronnie's *Beyond the Dragon of Icespire Peak* play-by-post on Discord, and to keep the campaign record. Jeff directs; Claude acts.

## Setting up a computer (once per machine)
1. Clone this repo somewhere convenient, for example `~/Tetia`.
2. In the Claude Code desktop app, start a new session and choose this folder as the working folder.
3. The first time, Claude Code asks whether to trust the folder. Say yes, so the sync hook can run.

From then on, every session pulls the latest from GitHub when it starts, and Claude pushes after every change, so both computers (and the phone) stay in step.

**From your phone:** start a Claude Code session on the web or in the Claude app with this repo. The same instructions and commands load there. Those sessions often work on a branch of their own; Claude still pushes the record to `main`, and tells you if it couldn't.

## Writing a post
Type `/write-post`, then paste:
1. **The scene:** the GM and player posts since Tetia last acted.
2. **Your goals:** what Tetia does and any beats you want.
3. **Mechanics and results:** the spell or ability and its level, and how it went ("hit," "it failed the save," "she failed her save," "took 12 damage").
4. **Length**, if it matters ("short, combat").

Claude checks for conflicts first, drafts one post, has an independent checker review it, and hands it to you in a code block ready to paste. Copy from the code block so the bold and underscores come through.

Add "quick" to skip the independent check when you're in a hurry.

## After posting
Type `/log-update`, plus anything that changed: "posted as written," your edited version, "long rest," "she used a level 3 slot," new chat or a GM recap. Claude files everything, updates her spell slots and the record, and pushes to GitHub.

You can also just tell Claude in plain words; it knows to run these.

## What's where
| Path | What it is |
|---|---|
| `CLAUDE.md` | Claude's standing instructions (loads automatically) |
| `director-preferences.md` | How you want posts written. Edit it anytime |
| `character/bible.md` | Tetia's master canon |
| `character/bible-appendix.md` | Head-to-toe physical, behavioral and world detail |
| `character/sheet-notes.md` | Her mechanics, from D&D Beyond |
| `character/homeland-moonshae.md` | Moonshae, Llewyrr and Sarifal lore |
| `campaign/current-state.md` | Where things stand now, including her spell slots |
| `campaign/table-rules.md` | The GM's rules and the post format |
| `campaign/party.md` | The other PCs |
| `campaign/npcs.md` | NPCs, enemies, former companions and places |
| `campaign/log.md` | The story so far, and the running log |
| `campaign/gm-recaps.md`, `gm-lore.md`, `chat/` | The GM's recaps and lore, and Discord chat, verbatim |
| `campaign/setting.md` | Player-facing Leilon and Sword Coast lore |
| `posts/archive.md` | Every post Tetia has made |
| `.claude/` | The `/write-post` and `/log-update` commands, the continuity checker, and the sync hook |

## Good habits
- **Paste the full scene** each time, even if it feels repetitive. It's also how the chat record stays complete.
- **Tell Claude about rests.** Her spell slots, and so how drained she looks, depend on it.
- **Changing who Tetia is** (a new fact about her past, a retcon) goes through you. Claude proposes; you decide; the bible records it with a version note.
- **If you edit files by hand**, commit and push them, or ask Claude to.
