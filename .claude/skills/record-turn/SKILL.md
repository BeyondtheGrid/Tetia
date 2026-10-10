---
name: record-turn
description: Internal to /write-post. Saves a turn to the campaign record in the background after the post has been handed over - files the pasted posts, confirms her last post, adds the new draft as pending, refreshes the current state, then commits and pushes. Also saves revisions.
user-invocable: false
context: fork
agent: general-purpose
background: true
effort: medium
---

# Save the turn to the record

`/write-post` has already handed the director his post. Your job is the bookkeeping that keeps the next post accurate. You can't see that conversation: everything you need is below. **Read each file fresh before editing it**; any copy you were started with may be out of date.

Input from `/write-post`:

$ARGUMENTS

Follow the rules in `CLAUDE.md` (Keeping the record, Git). Exact text is never paraphrased. Nothing mechanical is recorded.

## Mode: turn

### 1. File the pasted posts
Skip if none were pasted.
- Append every pasted post, Tetia's included, exactly as given and in order, to the scene file named in `campaign/current-state.md`. Check only the last part of that file for duplicates; never re-read the whole file.
- **A new scene file** starts when the GM moves the party to a new place or a new day, or the director said a new scene has begun: create `campaign/chat/YYYY-MM-<short-scene-name>.md` and update the pointer in current-state.

### 2. Her archive (`posts/archive.md`)
Grep for `^## 20` to find the entries; read only the last two or three.
- **Her last post** (the newest entry, marked `· PENDING`), as the input says:
  - posted as drafted: remove the `· PENDING` mark;
  - changed: update the entry's words to match what was posted (her post in the pasted text), keep the post format's markup (copying from Discord strips bold and underscores), and remove the mark;
  - not in the paste: leave it pending;
  - no pending entry, and her post in the paste isn't archived yet: archive it, restoring the format's markup. Never add the same post twice.
- **Add the new draft** as the newest entry: `## YYYY-MM-DD · Session NN · <label> · PENDING`, followed by the draft exactly as given.

### 3. Refresh the current state (`campaign/current-state.md`)
Apply "What changed this turn". Keep the file short; it loads in every session.
- **Setting:** the place, layout and positions. Change only what changed.
- **Recent beats:** one line per beat, two at most. Add the new beats, including her new post marked "(drafted, pending)" and her last post's beat updated to say it went up (and how it changed, if it did). Keep only the last five or so; drop older ones (the scene file keeps the exact text).
- **The party roster:** a name she has now been told; a line on what she now knows of someone.
- **Tetia right now:** body and mood as the story shows them; what she has told them and kept back; "Learned since"; "People she has met"; "Settled in play" for anything her post settles from bible section 18. Condense; don't let lists grow with detail she doesn't need.
- **Session number:** sessions begin each Sunday (session 63 began on Sunday 4 October 2026); advance it when a new week starts.
- Update the "Last updated" line.
- Don't touch the log, the bible, the party files or `npcs.md`; those wait for a milestone.

### 4. Commit and push
- `git status` to confirm only the intended files changed.
- One commit with a short, plain message, for example "Session 63: file Pip's question and the GM's reply; draft her answer".
- Push to `main` exactly as `CLAUDE.md` (Git) describes. Never force-push.

### 5. Report
One line: "Record saved." with the commit's first words, or plainly what failed.

## Mode: revision
1. Replace the newest `· PENDING` entry's text in `posts/archive.md` with the revised post, exactly as given; keep its heading.
2. In `current-state.md`, update the pending post's beat, and what she has told them, if the revision changed them.
3. Commit ("Session NN: revise her pending reply (…)") and push as above.
4. Report one line, as above.
