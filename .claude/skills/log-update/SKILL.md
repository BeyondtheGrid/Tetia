---
name: log-update
description: Record a milestone in the campaign record, or file a GM recap, GM lore post, a batch of Discord chat, or news about Tetia (a new item, a lasting injury, a level-up). Use when a scene ends or something lasting happens, when the director pastes a recap, lore or chat to file, or asks to update the record. Routine posts are filed by /write-post.
argument-hint: "then say or paste what's new, in any format"
---

# Update the campaign record

Routine turns are handled by `/write-post`, which files each scene's posts and refreshes `campaign/current-state.md`. This skill does the bigger, rarer work: **milestones**, and anything that doesn't come with a post. Keep **one home per fact** (see `CLAUDE.md`, Keeping the record): move facts to their home, don't copy them.

**Tetia comes first.** The most important thing this skill touches is her canon. Change the bible and appendix carefully, only for lasting changes, and never let them drift from what happened in play.

New information for this update (may be empty if it's in the conversation instead):

$ARGUMENTS

## 1. Work out what's new
From the director's message and the conversation:
- **A milestone:** a scene ends; a fight is decided; a bond, promise or falling-out; a discovery that changes Tetia's picture of the world; a lasting injury; a new item; a level-up.
- **A GM recap**, a **GM lore post**, or a **batch of chat** to file.
- **Posts `/write-post` didn't file:** check the end of the scene file and the newest archive entry.

Never record her hit points, spell slots, exhaustion or other mechanics; the director tracks those.

## 2. File the exact text first
Never paraphrase into these files.
- **Her posts:** `/write-post` adds each draft to `posts/archive.md` marked `· PENDING` and confirms it the next turn. Confirm any pending entry the director's paste or word settles (if he changed the post, match its words, keep the post format's markup, and remove the mark), and add any of her posts that are missing.
- **Chat:** into the right file in `campaign/chat/`, one file per scene named `YYYY-MM-<short-scene-name>.md`, in posting order. A new scene file starts when the GM moves the party to a new place or a new day, or the director says so; update the pointer in `current-state.md`. Check only the end of a file for duplicates.
- **GM recap:** append to `campaign/gm-recaps.md` in the same format as the others.
- **GM lore post:** append to `campaign/gm-lore.md`.

## 3. At a milestone
- **`campaign/log.md`:** one entry under "Since Tetia arrived", written like the GM's recaps from the scene file since the last milestone: a short paragraph on what happened and what changed for Tetia, not post by post. If the party learned something, update "What the party knows" there; update "Open threads".
- **Her canon** (`character/bible.md`, `character/bible-appendix.md`), lasting changes only:
  - What she has learned of the world moves from "Learned since" in `current-state.md` into bible section 14, and what her posts have settled moves from "Settled in play" into sections 15 and 18. Then those lines come off current-state.
  - Bonds, promises, changed beliefs, lasting injuries, new gear or abilities go in the relevant bible sections, with a dated line in section 15.
  - Follow the bible's change control (section 19): **one version bump per milestone**, bundling everything from it, with one changelog line. Never let old and new canon coexist silently.
  - Brainstorming, possibilities and your own guesses never go into canon. If something is unclear, ask the director.
- **People:** a dated line under "With Tetia (milestones)" in the party member's file (`campaign/party/<name>.md`) for anything lasting between them; new details a player reveals (appearance, abilities, history) in that file. For an NPC, move what she knows from "People she has met" in `current-state.md` to a line under their entry in `campaign/npcs.md` (add the entry if they're new). The roster in `current-state.md` keeps what she knows of each party member *now*.
- **Trim `current-state.md`:** drop recent beats the log entry now covers; keep the setting until the scene changes, then start the new scene's setting and file pointer. Update the "Last updated" line.
- **Level-up or new item:** from what the director gives you, update `character/sheet-notes.md`; the class and level in bible sections 1 and 12; and the "highest spell level" row of the strain table in bible section 8.

## 4. Commit and push
- Check with `git status` that only the intended files changed.
- Commit with a short, plain message, for example "Log session 64: the party takes Tetia in".
- Push to `main` exactly as `CLAUDE.md` (Git) describes, including when the session is on another branch. Never force-push. If something still fails, tell the director plainly.

## 5. Report
Two or three lines to the director: what was recorded, any change to her canon (with the new bible version), and anything that needs his decision.
