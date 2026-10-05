---
name: write-post
description: Draft Tetia Mercury's next in-character Discord post from the director's scene context and goals. Use whenever the director asks for a post, reply, turn or response for Tetia, or pastes new GM or player posts and says what she does.
argument-hint: "[pasted scene, what Tetia does, results, length]"
---

# Write Tetia's next post

The director has given you a scene and his goals for Tetia's post. Your job is one finished, paste-ready Discord post that is true to her, the lore and the campaign, and checked before he sees it.

Director's input for this post (may be empty if it's in the conversation instead):

$ARGUMENTS

## 1. Gather the inputs
From the director's message and the conversation, identify:
- **The scene:** the pasted GM and player posts since Tetia last acted. If none were pasted, use `campaign/current-state.md`.
- **What Tetia does:** the director's goals, beats and intent.
- **Mechanics, if any:** the spell or ability and its **level**, and the **results** (hit or miss, the creature's save made or failed, her own save made or failed, damage taken). Never invent a result.
  - If he names something she rolls for (an attack, a spell with a save, a check) but gives no result, **ask** for it before drafting.
  - What follows from a result is the GM's: write that the creature fails its save and reels, not how the fight ends. Narrate a kill only if the director says the creature dies.
- **Length:** what he asked for. If he didn't say: combat 50 to 100 words; out of combat around 120 to 250; always well under 2,000 characters.

Ask **one** short question only if something essential is missing (for example, a spell is named with no result and the post can't be written without it). Otherwise proceed, and state any assumption in one line after the draft.

## 2. Save the scene
Append any newly pasted Discord posts, exactly as given, to `campaign/chat/inbox.md` under a dated heading. Don't rewrite or tidy them. `/log-update` files them properly later. Commit and push the inbox right away (see `CLAUDE.md`, Git) so the scene isn't stranded on this device.

## 3. Load what this post needs
Already in context: the director's preferences, the bible, the appendix, the table rules and the current state. Also read:
- `campaign/party.md`: every PC present in the scene.
- `campaign/npcs.md`: any NPC or place in the scene.
- `posts/archive.md`: Tetia's last several posts, to avoid repetition.
- `character/sheet-notes.md`: if a spell or ability is involved, so the fiction matches what it actually does.
- `campaign/log.md` or `campaign/gm-recaps.md`: only if the scene depends on earlier events.

## 4. Check before drafting (flag conflicts first)
Stop and tell the director, briefly and with options, if the request would:
- give Tetia knowledge she hasn't learned in play (bible section 14): a name she hasn't been told, the party's history, the Cult of Talos behind the storms, anything GM-side;
- contradict her canon (bible, appendix) or a retired detail (bible section 18);
- contradict the campaign facts or Forgotten Realms lore;
- control another PC or an NPC, or decide an outcome that belongs to the GM;
- have her lie, use mind-reading for curiosity or advantage, wield a weapon, or act against her faith, without a reason the director gives.

Small judgment calls don't need a stop: make the call and mention it in one line.

## 5. Work out her state
Run the bible's scene checklist (section 13): what she knows, her physical state, who is present and what they are to her, what she wants and owes, which feeling reaches her body first, how formal to be, and what must not repeat.

**If she casts a spell:** check her spell-slot tracking in `current-state.md`. Scale the visible strain to the slot level **and** to how much she has already spent since her last long rest (bible section 8): a prayer late in a hard day costs her more than the same prayer at dawn. Cantrips cost nothing visible.

## 6. Her first appearance
Tetia's first post in the campaign is different from every other:
- **Wait for the GM's post placing her** in the scene. Don't invent where she is or how she arrives.
- **This is the one post where a fuller description is right**, because the others are seeing her for the first time. Choose the three or four details a stranger would notice first (bible section 3 and the appendix): her height and silver hair, the delicate plate, the elven ears, her composure. Write them as what anyone looking would see, never lingering on her body.
- **How she introduces herself** follows the director's goals: formally, by full name; as an emissary she says less than she knows, and she asks more than she answers.
- She doesn't know any of their names or history yet (bible section 14).

## 7. Draft
- **Format** (`campaign/table-rules.md` Part 2): narration in plain text, third person, present tense; speech in bold quotes, `**"like this"**`; thoughts in single underscores, `_like this_`; telepathy in bold angle brackets, `**‹like this›**`; signed words as speech, with the narration saying she signs. No out-of-character notes. No dice, commands or turn lines.
- **Never name a spell, feature or mechanic.** Show the prayer, the light, the feeling, the cost.
- **Her voice:** formal, precise, gentle; formality in phrasing, not archaic speech. Readying her voice only when it matters. No slang, no swearing.
- **Her magic:** divine, intimate, flowing through her body from the Earthmother; moonlight and dawn, cool water, green growth. Not arcane, never commanding.
- **Senses and body:** draw on the appendix (senses, body states, movement) for one or two fresh, scene-specific details. Physical description serves the scene; it never reintroduces her and never lingers on her body.
- **Others:** respond to what other PCs actually posted. Speak to them, never for them. Use only names she knows; otherwise describe them as she sees them.
- **Variation:** don't reuse any feature, mannerism, image or phrase from her recent posts in `posts/archive.md`.
- **Ending:** leave an opening for the others or the GM. Don't close the scene.
- **One draft**, unless the director asked for options.

## 8. Independent check
Count the draft's characters and words exactly with a command (for example, save it to a scratch file and run `wc -m -w`); don't estimate. Unless the director asked for speed ("quick"), give the draft to the **continuity-check** agent along with the scene, the director's goals, the spell and level, the length target and the counts. It hasn't seen your reasoning, so it catches what you missed. Fix every must-fix issue it raises; use judgment on the rest.

## 9. Hand it over
- The post **inside a code block** (` ```text `), exactly as it should be pasted, so the markup survives copying.
- Under it, one line: the exact word and character count. If it's over 2,000 characters, split it into two code blocks at a paragraph break.
- Then at most three short lines: an assumption you made, something you flagged, or a choice he might want to change. No commentary on the writing.

## 10. Afterwards
When the director says he has posted it (or pastes his edited version), run **/log-update** so the archive, her spell slots and the record stay current.
