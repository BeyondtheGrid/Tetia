---
name: log-update
description: Update the campaign record after Tetia's post goes up, or when new Discord chat, a GM recap, GM lore or news about Tetia arrives. Archives her post, files chat, updates current state, the log, party, NPCs, her spell slots and her canon, then commits and pushes. Use when the director says he posted, pastes new chat or a recap, or says something happened to her (a rest, an injury, a new item).
argument-hint: "then say or paste what's new, in any format"
---

# Update the campaign record

Keep the repo an accurate, current record so any future session, on any device, can pick up where this one left off.

New information for this update (may be empty if it's in the conversation instead):

$ARGUMENTS

## 1. Work out what's new
From the director's message and the conversation:
- **Tetia's post as actually posted.** If he edited your draft, his version is the record.
- **New Discord chat**, including anything waiting in `campaign/chat/inbox.md`.
- **A GM recap** or **GM lore post**.
- **Mechanical news from the director:** spells she cast (and their levels), Channel Divinity or other limited features used, damage or healing, conditions, a short or long rest, items gained or lost, a level-up.
- **Story developments:** where the party is, what happened, who she met, what she learned, promises, bonds, discoveries.

## 2. File the exact text first
Never paraphrase into these files; paste exactly.
- **Her post:** append to `posts/archive.md` with the date, the session number and a one-line scene label.
- **Chat:** move the contents of `campaign/chat/inbox.md`, and any newly pasted chat, into the right file in `campaign/chat/`, one file per scene or week named `YYYY-MM-<short-scene-name>.md`, in posting order. Then empty the inbox. Don't duplicate posts that are already filed.
- **GM recap:** append to `campaign/gm-recaps.md` in the same format as the others.
- **GM lore post:** append to `campaign/gm-lore.md`.

## 3. Update the working files
- **`campaign/current-state.md`:** where and when; the party; the scene; what the party knows; open threads; and **Tetia's section**: spell slots used by level, limited features used, HP if the director gives it, conditions, injuries, and what she now knows. Update the "last updated" line.
  - **Short rest:** restores one use of Channel Divinity.
  - **Long rest:** resets all spell slots and all limited features. Note when it happened.
  - Use only what the director tells you about mechanics. Never infer a slot, a result or a rest from the fiction.
- **`campaign/log.md`:** add a running-log entry: date, session, what happened in a few lines, and anything that changes Tetia. Events before she enters play go in the running log too, marked as before her arrival.
- **`campaign/party.md`:** under each PC, what Tetia has now learned about them and any change in their relationship with her. Add new details players reveal (appearance, abilities, history) to their entries.
- **`campaign/npcs.md`:** new NPCs and places; status changes; and under each, what Tetia knows of them.

**Where knowledge goes:** what Tetia knows about a *person* goes in `party.md` or `npcs.md`; what she knows about the *world* (the cult, the storms, Leilon, the tower's nature) goes in bible section 14; what is happening *right now* goes in `current-state.md`.

## 4. Update her canon, carefully
Change `character/bible.md` or `character/bible-appendix.md` only for **lasting** changes: an injury or scar, a bond, a promise, a changed belief, something she learns that alters her worldview, new gear or abilities, a level-up.
- Follow the bible's change control (section 19): bump the version, add a changelog line, and never let old and new canon coexist silently.
- Moving knowledge from "does not know" to "knows" in section 14 when she learns it in play (for example, the Cult of Talos behind the storms) is a normal update. Do it.
- A temporary state (tired, wet, a scratch) goes in `current-state.md`, not the bible.
- **Level-up or new item:** from what the director gives you, update `character/sheet-notes.md`; the class and level in bible sections 1 and 12; the "highest spell level" row of the strain table in bible section 8; and the maximums in the resource table in `current-state.md`.
- Brainstorming, possibilities and your own guesses never go into canon. If something is unclear, ask the director.

## 5. Commit and push
- Check with `git status` that only the intended files changed.
- Commit with a short, plain message, for example "Log session 63: Tetia meets the party at the tower".
- Push to `main` exactly as `CLAUDE.md` (Git) describes, including when the session is on another branch. Never force-push. If something still fails, tell the director plainly.

## 6. Report
Two or three lines to the director: what was recorded, where her spell slots stand, and anything that needs his decision.
