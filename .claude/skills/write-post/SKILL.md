---
name: write-post
description: Draft Tetia Mercury's next in-character Discord post from the director's pasted scene and goals, have it checked, hand it over, then save the turn to the record in the background. Use whenever the director asks for a post, reply, turn or response for Tetia, or pastes new GM or player posts and says what she does.
argument-hint: "then paste the scene and your goals, in any format"
---

# Write Tetia's next post

**Tetia comes first.** The post must be true to her personality, voice, body and lore: the bible and appendix, already loaded in full. Everything else in this skill serves that. The scene tells you what she is responding to; the record keeps her consistent from post to post.

**The post comes first, the bookkeeping after.** Draft and check the post, hand it over, and only then save the turn to the record (filing the posts, refreshing the current state, committing), in the background. The checker still runs on every post.

Director's input for this post (may be empty if it's in the conversation instead):

$ARGUMENTS

## 1. Read the request
From the director's message and the conversation, identify:
- **The scene:** the Discord posts he pasted, ideally starting from Tetia's own last post as it appeared on Discord.
- **What Tetia does:** his goals, beats and intent.
- **Mechanics, if any:** the spell or ability, its **level**, and the **results** (hit or miss, the creature's save made or failed, her own save made or failed, damage taken). He tracks her hit points, spell slots and exhaustion himself and says how worn she is when it matters. Never invent a result, and never track mechanics.
  - If he names something she rolls for (an attack, a spell with a save, a check) but gives no result, **ask** for it before drafting.
  - What follows from a result is the GM's: write that the creature fails its save and reels, not how the fight ends. Narrate a kill only if he says the creature dies.
- **Length:** what he asked for. If he didn't say: combat 50 to 100 words; out of combat around 120 to 250; always well under 2,000 characters.

Ask **one** short question only if something essential is missing. Otherwise proceed, and state any assumption in one line after the draft.

**The current state is one turn behind your paste** until the record is saved after the draft. Anything said, named or learned in the pasted posts counts as known now (a name just given, a fact just told her).

## 2. Load only what this post needs
Already in context: the director's preferences, the bible, the appendix, the post format, and the current state with the party roster (one turn behind the paste).
- **Her last few posts, always.** Grep `posts/archive.md` for `^## 20` to find the entries, then Read from the fourth-from-last entry to the end. The newest is usually last turn's draft, marked `· PENDING`; if her post in the paste differs from it, the paste is what actually went up, so use that.
- **A party member's file** (`campaign/party/<name>.md`): when the director mentions a detail about them, or the post turns on them (she addresses, examines or reacts to them in particular). Otherwise the roster is enough. Anyone named in the roster is an ally, whether or not Tetia knows their name.
- **`campaign/party.md`:** when a poster's name in the paste doesn't match the roster (who posts as whom), or when she first speaks with one of them directly (her starting stance with the group).
- **An NPC or place:** current-state first ("People she has met"), then `campaign/npcs.md` when one appears. Grep for the name rather than reading the whole file.
- **The story so far** (`campaign/log.md`): only when someone refers to something Tetia wasn't there for and you need to understand it. She still doesn't know it.
- **Her abilities** (`character/sheet-notes.md`): when she casts a spell or uses a feature, so the fiction matches what it does.
- `character/homeland-moonshae.md` or `campaign/setting.md`: only for lore the bible and appendix don't cover.

## 3. Check before drafting (flag conflicts first)
Stop and tell the director, briefly and with options, if the request would:
- give Tetia knowledge she hasn't learned in play (bible section 14, current-state, and the pasted posts): a name she hasn't been told, the party's history, the Cult of Talos behind the storms, anything GM-side;
- contradict her canon (bible, appendix) or a retired detail (bible section 18);
- contradict the campaign facts or Forgotten Realms lore;
- control another PC or an NPC, or decide an outcome that belongs to the GM;
- have her lie, use mind-reading for curiosity or advantage, wield a weapon, or act against her faith, without a reason the director gives.

Small judgment calls don't need a stop: make the call and mention it in one line.

## 4. Work out her state
Run the bible's scene checklist (section 13): what she knows, her physical state, who is present and what they are to her, what she wants and owes, which feeling reaches her body first, how formal to be, what must not repeat, and **how sure of herself she is**. With people she doesn't yet know, not very: her shyness (bible sections 5 and 6) should shape the post, not sit under a poised surface.

**If she casts a spell:** scale the visible strain to the spell's level (bible section 8), and add the day's accumulated fatigue only when the director says she is worn or the scene shows a long, hard day. Cantrips cost nothing visible.

## 5. Draft
- **Format** (`campaign/table-rules.md` Part 2): narration in plain text, third person, present tense; speech in bold quotes, `**"like this"**`; thoughts in single underscores, `_like this_`; telepathy in bold angle brackets, `**‹like this›**`; signed words as speech, with the narration saying she signs. No out-of-character notes. No dice, commands or turn lines.
- **Never name a spell, feature or mechanic.** Show the prayer, the light, the feeling, the cost.
- **Her voice:** formal, precise, gentle; formality in phrasing, not archaic speech. Readying her voice only when it matters. No slang, no swearing.
- **Her shyness:** with near-strangers she is polite to a fault and unsure of herself, and her formality is something she holds on to, not ease. Pick one or two signals and rotate them: a lowered gaze, color in her cheeks, toes turning inward, a pause before she answers, shorter answers, a voice that softens or trails off, an inner voice questioning whether she spoke rightly. **Never stammering.** Don't write long, perfectly balanced speeches for her among people she has just met.
- **Her magic:** divine, intimate, flowing through her body from the Earthmother; moonlight and dawn, cool water, green growth. Not arcane, never commanding.
- **Senses and body:** draw on the appendix (senses, body states, movement) for one or two fresh, scene-specific details. Physical description serves the scene; it never reintroduces her and never lingers on her body.
- **Others:** respond to what other PCs actually posted. Speak to them, never for them. Use only names she knows; otherwise describe them as she sees them.
- **Don't retell the scene.** The GM's and players' posts sit right above hers, and everyone has just read them. Never open by re-narrating what they described (the axe tap, the falling page, the door opening). Touch an event only through Tetia, and only as much as her reaction needs: "at the rustle, her head turns", not "a loose page slips from the shelves and flutters down". Spend the words on what only her post can add: what she does and how, what her body shows, what she notices that others haven't, what she thinks and says.
- **Variation:** don't reuse any feature, mannerism, image or phrase from her recent posts.
- **Ending:** leave an opening for the others or the GM. Don't close the scene.
- **One draft**, unless the director asked for options.

## 6. Count and check
Count the draft's characters and words exactly with a command (save it to a scratch file outside the repo and run `wc -m -w`); don't estimate. Unless the director asked for speed ("quick"), give the **continuity-check** agent: the draft; the scene; his goals (spell, level, results, how worn she is); the length target; the counts; which characters are present; and **the text of her last four posts** from step 2 (the newest as it actually went up), so it needn't read the archive. Tell it the current state is one turn behind the scene. Fix every must-fix issue; use judgment on the rest.

## 7. Hand it over
- **The post inside a code block** (` ```text `), exactly as it should be pasted, so the markup survives copying.
- Under it, one line: the exact word and character count. If it's over 2,000 characters, split it into two code blocks at a paragraph break.
- Then at most three short lines: an assumption you made, something you flagged, a milestone worth logging (`/log-update`), or a missing post (ask whether her last post went up as written). No commentary on the writing.
- Last line: **"Saving the record in the background."**

## 8. Save the record in the background
In the same message, right after handing the post over, invoke the **record-turn** skill. It runs in the background, so the turn ends as soon as it starts. It can't see this conversation, so give it everything it needs, verbatim where marked:
```
Mode: turn
Date and session: YYYY-MM-DD · Session NN
Label for the new draft: <one-line scene label>
Her last post: posted as drafted | changed (the paste has what went up) | not in the paste | no pending entry
Milestone: no | yes (what)
## Pasted posts (verbatim, in order, exactly as given)
...
## New draft (verbatim, with markup, exactly as handed over)
...
## What changed this turn (for the current state; one line each)
- Beats: ...
- Roster: names given; what she now knows of someone
- Tetia: learned / said / kept back / body and mood / anything her post settles from bible section 18 / NPCs met
- Positions or setting, if they changed
```
If nothing was pasted (a fresh draft from goals alone), leave that section empty.

When it reports back, tell the director in one line: "Record saved." or what failed. **Before he types `/clear`, the record must be saved**: if he asks to clear early, tell him to wait for that line.

## 9. Revisions
The director asks for changes in plain words, in the same session or a later one. Don't rerun the whole skill and don't re-file the scene.
- **Find the draft:** in this conversation, or, after a `/clear` or in a new session, the newest `· PENDING` entry in `posts/archive.md`.
- **Change what he asked for, and only that.** Keep everything he didn't mention. If he wants a new direction ("start over: she…"), redraft from the same scene and his new goals. If he gives his own wording, use it as written, fixing only format markup.
- **Re-count** exactly. **Re-run the checker** if the change goes beyond wording (new action, new speech, a new detail about Tetia or anyone else); for a pure wording tweak, check it yourself against the format and her recent posts.
- **Hand it over** exactly as in step 7.
- **Then save it in the background:** if an earlier record save from this session hasn't reported back yet, wait for it first. Invoke **record-turn** with `Mode: revision`, the revised post verbatim, and one line on anything that changes what she has said or done this turn.
