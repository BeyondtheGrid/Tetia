# Setup: from the design chat to Claude Code

Tetia was designed in a separate chat. That chat built this repo; **from now on, all of her writing and record-keeping happens in Claude Code sessions opened on this repo.** Follow these steps once on each computer.

**Prefer to let Claude do it?** Give `setup/claude-code-autosetup.md` to a Claude Code session on the computer and it will run steps 1 to 6 for you, asking when it needs you.

---

## Before you start (once)

1. **Make the repo private again** (recommended). On GitHub: the Tetia repo → Settings → General → Danger Zone → Change visibility → Private. The repo holds your fellow players' Discord names and posts, Ronnie's recaps and Tetia's detailed description. The Claude GitHub app keeps its access either way.
2. **The Claude Docs intake document is retired.** Everything in it now lives in this repo, which is the only source of truth. Keep the doc for reference if you like, but edits there change nothing.

---

## Set up each Mac

Do steps 1–6 on your first Mac, then step 7. On the second Mac, do steps 1–6 and then step 8.

### 1. Check that git is installed
Open Terminal and run:
```
git --version
```
If macOS offers to install the Command Line Tools, accept and wait for it to finish.

### 2. Sign git in to GitHub
Claude commits and pushes from your Mac using your Mac's GitHub sign-in, so this has to work. The simplest way is the GitHub CLI (needs Homebrew):
```
brew install gh
gh auth login
gh auth setup-git
gh auth status
```
For `gh auth login`, choose GitHub.com, HTTPS, and log in with a web browser. `gh auth status` should say you're logged in.

### 3. Set your name for commits (once per Mac)
```
git config --global user.name "Jeff"
git config --global user.email "the-email-on-your-github-account"
```

### 4. Clone the repo
```
gh repo clone BeyondtheGrid/Tetia ~/Tetia
```
(Without the GitHub CLI: `git clone https://github.com/BeyondtheGrid/Tetia.git ~/Tetia`.)

### 5. Open it in Claude Code
In the Claude desktop app, start a new Claude Code session on your computer and choose the **`~/Tetia`** folder itself (not a folder above it). When asked whether to trust the folder, say yes; that lets the sync hook run at the start of each session.

### 6. Check that it loaded
In that session:
- Type `/`. You should see **write-post** and **log-update** in the list.
- Ask: *"Where does the campaign stand, and what is Tetia's spell-slot status?"* It should answer from `campaign/current-state.md` straight away: where the party is in Thalivar's Tower, whether Tetia is in play, and how many spell slots she has used.
- Ask: *"Which agents do you have for this project?"* It should name **continuity-check**.
- No "SYNC WARNING" should appear at the start.

### 7. First Mac only: test the round trip
Give it one small real task that changes a file, for example: *"I sent Ronnie the backstory messages. Mark them as sent."* Approve the git commands if asked (choose "always allow" for git). Then check the repo on GitHub: the new commit should be there.

### 8. Second Mac only: confirm the sync
Start a session and ask: *"What's the most recent commit?"* It should be the one you made on the first Mac. Both computers are now in step.

---

## Your phone (optional)
Start a Claude Code session on the web or in the Claude app and pick the **BeyondtheGrid/Tetia** repo. The same instructions and commands load. These sessions often work on a branch of their own; Claude pushes the record to `main` regardless, and tells you if it couldn't.

---

## First things to do in the new setup
1. **File the latest chat.** Run `/log-update` and paste the Discord chat from Thalivar's Tower since the session 62 recap, so the current state is up to date before Tetia's first post.
2. **Send Ronnie the backstory** (`character/backstory-for-gm.md`, two messages). When you've sent it, tell Claude so it records it.
3. **When Ronnie places Tetia in the scene,** run `/write-post` and paste his post plus your goals for her entrance.
4. **When convenient, ask Ronnie** whether he has a preferred format for telepathy, and the campaign year. Tell Claude the answers.

Day-to-day use is in `README.md`.

---

## If something goes wrong
| Problem | Fix |
|---|---|
| "SYNC WARNING" at the start of a session | There are uncommitted changes, or this Mac fell behind. Ask Claude to "commit and sync with GitHub." |
| A push fails or asks for a password | Run `gh auth setup-git` again (step 2). |
| `/write-post` doesn't appear | The session was opened on the wrong folder. Open it on `~/Tetia` itself. |
| Claude asks permission for every git command | Choose "always allow" once; the project also pre-allows the common git commands. |
| The two Macs disagree | Start a session on each; the hook pulls the latest. If one has unpushed changes, ask Claude there to commit and push first. |
