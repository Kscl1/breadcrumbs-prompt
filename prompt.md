# Breadcrumbs v0.1: memory for small projects

LANGUAGE: Turkish

You are about to set up a small working memory in this folder, then work in it with the user.
Follow these steps in order. Copy every file below exactly: same names, same headings, same words. Do not improve, shorten or translate them.
Wherever a file says {LANGUAGE}, write the value of the LANGUAGE line above instead.
Talk to the user only in LANGUAGE.

## Step 1: look before you write

If `notes/state.md` already exists in this folder, do not write or change any file. Go to Step 5.

## Step 2: write these five files

If `AGENTS.md` or `CLAUDE.md` already exists, do not replace it: add the text of the new file at its end, after one blank line.

File `AGENTS.md`:

```markdown
# Working rules

Set up by the Breadcrumbs prompt. They apply to every session in this folder.

- Talk to the user in {LANGUAGE}. Write new notes in {LANGUAGE}. Keep file names and headings as they are.

## At the start of every session, and after the chat was summarised

1. Read `notes/state.md` and `notes/decisions.md`, and the last 10 lines of `notes/log.md`.
2. Tell the user in one sentence where we are and what comes next.

## After each block of work

1. Update `Now` and `Next` in `notes/state.md`. Move finished items to `notes/log.md`.
2. Add one line to `notes/log.md`.
3. Add every decision you made to `notes/decisions.md`, with its reason.
4. Read the files back and check that your changes are there. Never say a note is updated before you have checked.

## When to ask the user

Ask only when:
- the goal or the scope would change;
- a step cannot be undone (deleting, submitting, sending, pushing);
- only the user knows the answer.
Otherwise decide yourself and write the decision with its reason.

## Other rules

- Keep `notes/state.md` under 60 lines.
- When the user brings an answer from another model or a person, write it in `notes/decisions.md` as an input, with its source.
- When the user says "retro", read `notes/log.md` and `notes/decisions.md` and answer: what went well, what went wrong, what to keep doing.
- If this folder is a git repository, offer one short commit after a block of work. Never push without asking.
```

File `CLAUDE.md`:

```markdown
@AGENTS.md
```

File `notes/state.md`:

```markdown
# State

## Goal

## Now

## Next

- [ ]

## Open questions

## Files that matter
```

File `notes/decisions.md`:

```markdown
# Decisions

One line per decision: `D-n · YYYY-MM-DD · decision · why`.
Never delete a line. When a decision is replaced, strike it through (~~like this~~) and add the new one with "replaces D-n".
```

File `notes/log.md`:

```markdown
# Log

One line per block of work, newest at the bottom: `YYYY-MM-DD · what was done · what broke or was learned`.
```

## Step 3: check your work

Read each file back and compare it with its block above. If one differs, fix it once.
Say nothing about this check if every file matches. If a file still differs, add one line after your reply in Step 4, in LANGUAGE, naming that file.

## Step 4: your first reply

Translate this text into LANGUAGE and print it, with nothing before it and nothing after it:

```text
Ready. The memory files are set up: AGENTS.md, CLAUDE.md, notes/state.md, notes/decisions.md, notes/log.md.
Three questions to start:
1. What is the goal of this project, in one sentence?
2. Is there a deadline or a limit?
3. What do you already have (files, the assignment text, code)?
```

After the user answers, write the answers into `notes/state.md` (Goal, Next, Files that matter) and follow `AGENTS.md` from then on.
If you are Claude Code or Codex, at the end of the first block of work ask once whether to add a hook that reads `notes/state.md` again after the chat is summarised. Add it only if the user says yes.

## Step 5: resume

The memory already exists. Follow "At the start of every session" in `AGENTS.md`. Then tell the user, in LANGUAGE, the next step and, if one is open, one question. Do not rewrite any file from Step 2.
