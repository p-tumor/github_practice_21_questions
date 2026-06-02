# 21 Questions — A Git Practice Repo

## Synopsis

Welcome! This repository is a playground for practicing the everyday **Git**
workflow. Instead of dry exercises, you'll learn the commands by playing a game
of **21 Questions**.

The plan is simple:

1. **Fork** this repository to your own GitHub account.
2. **Clone** your fork to your computer.
3. Play the game by **editing [`21_questions.txt`](21_questions.txt) directly** —
   the two players take turns writing into the same file.
4. Here's the key part: you **add, commit, and push** after *every single
   question and every single answer*, and you **pull** before each of your turns
   so you can see what the other player just wrote.

In other words, Git is how the two players talk to each other:

- The **Guesser** writes a question → `add` → `commit` → `push`.
- The **Host** does `pull` to see the question, checks yes or no →
  `add` → `commit` → `push`.
- The **Guesser** does `pull` to see the answer, then writes the next question.
- Repeat for all 21 questions, then the final guess and the reveal.

By the time you've finished a game, you'll have run the core Git loop —
**pull, edit, add, commit, push** — dozens of times, which is exactly the rhythm
of day-to-day software development.

---

## How to Play 21 Questions

21 Questions is a classic guessing game for two or more people.

**The rules:**

1. One player is the **Host**. The Host secretly thinks of a *person, place,
   thing, or animal* and writes it down (don't show anyone yet!).
2. The other player is the **Guesser**. The Guesser asks up to **21 questions**
   to figure out what the Host is thinking of.
3. Every question must be answerable with **"Yes" or "No"** (e.g. *"Is it
   alive?"*, *"Is it bigger than a car?"*). The Host answers honestly.
4. The Guesser can make a final guess at any time. If they guess correctly
   within 21 questions, **the Guesser wins**. If they run out of questions or
   guess wrong, **the Host wins**.
5. Swap roles and play again!

**Tip:** Start with broad questions to narrow things down quickly
(*"Is it a living thing?"*) before asking specific ones (*"Does it bark?"*).

Use the [`21_questions.txt`](21_questions.txt) template to record your game.

---

## Common Git Commands

These are the commands you'll use in this exercise. Run them from a terminal
inside your cloned repository.

### Fork (on GitHub)

Forking happens **on the GitHub website**, not in the terminal. Click the
**"Fork"** button in the top-right of this repo's GitHub page. This creates your
own personal copy of the repository under your account that you can freely edit.

For a game, **only one player needs to fork** — that fork becomes the shared
board both players push to.

> 📖 GitHub's guide: [Fork a repository](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo)

### Add the Other Player as a Collaborator

Because both players push to the *same* repository, the fork's owner must invite
the other player and give them **write access**.

1. On your fork's GitHub page, go to **Settings → Collaborators**
   (you may be asked to confirm your password).
2. Click **"Add people"**, search for the other player's GitHub username, and
   select them.
3. Choose the **Write** permission level — this lets them push commits but not
   change repository settings — and send the invitation.
4. The other player accepts the emailed invite (or the link under their GitHub
   notifications). Now both of you can clone, push, and pull from this one repo.

> 📖 GitHub's guides:
> [Inviting collaborators to a personal repository](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-access-to-your-personal-repositories/inviting-collaborators-to-a-personal-repository)
> · [Repository permission levels](https://docs.github.com/en/organizations/managing-user-access-to-your-organizations-repositories/managing-repository-roles/repository-roles-for-an-organization)

### Clone

Download your fork from GitHub to your local machine:

```bash
git clone https://github.com/<your-username>/github_practice_21_questions.git
cd github_practice_21_questions
```

### Pull

Before each turn, download whatever the other player just wrote so your local
copy is up to date:

```bash
git pull
```

### Add

After editing `21_questions.txt`, stage your change so Git knows you want to
save it:

```bash
git add 21_questions.txt
```

### Commit

Save your staged change to your local history with a message describing what you
just did:

```bash
git commit -m "asked q3"
```

### Push

Upload your commit to GitHub so the other player can pull it:

```bash
git push
```

---

## Putting It Together: One Turn at a Time

Every question and every answer is its own pull → edit → add → commit → push
cycle. Here's a full exchange for question 3.

**Guesser's turn — ask a question:**

```bash
git pull                                          # get the latest file
# ...edit 21_questions.txt: write your question on line 3...
git add 21_questions.txt
git commit -m "asked q3"
git push
```

**Host's turn — answer it:**

```bash
git pull                                          # see the new question
# ...edit 21_questions.txt: check [x] Yes or [x] No on line 3...
git add 21_questions.txt
git commit -m "A3: Yes"
git push
```

Then the Guesser pulls again and asks question 4. Repeat all the way to 21.

---

## The Final Guess and the Reveal

When the Guesser is ready (any time up to question 21), the game ends with two
last commits.

**Guesser's turn — make the final guess:**

```bash
git pull
# ...edit 21_questions.txt: fill in the "My guess is:" line...
git add 21_questions.txt
git commit -m "Final guess: a toaster"
git push
```

**Host's turn — score it and reveal the secret:**

```bash
git pull
# ...edit 21_questions.txt: check Correct/Incorrect and fill in
#    "THE SECRET WAS:" to reveal the answer...
git add 21_questions.txt
git commit -m "Reveal: it was a toaster — correct!"
git push
```

The Guesser does one last `git pull` to see the reveal. Game over — swap roles
and play again!

---

## Have Fun and git Good!

---

## Disclaimer

This README and the accompanying template were **written by Claude** (an AI
assistant by Anthropic). The exercise concept is **Jon Chin's** own idea, and
Jon critically reviews all generated content.
