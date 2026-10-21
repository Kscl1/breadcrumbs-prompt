# Breadcrumbs

One prompt that gives a coding agent a small working memory for a small project.

You paste it once at the start. The agent writes five short files into the folder and from then on keeps them up to date: where the work stands, what comes next, which decisions were made and why, and a dated log. When a session is compacted or a new one starts, the agent reads the notes and carries on from there. One agent is enough; no tools to install.

Status: v0.1, experimental.

## Use

1. Open an empty folder (or an existing one) in a coding agent that can write files: Claude Code, Codex, Pi, OpenCode, Cursor and similar.
2. Edit the `LANGUAGE:` line at the top of [`prompt.md`](prompt.md) if you do not want Turkish.
3. Paste the whole prompt as your first message.

The agent answers with a short ready line and three questions about the project. If `notes/state.md` already exists, it changes nothing and resumes instead.

## What it creates

| File | Holds |
|---|---|
| `AGENTS.md` | the working rules: read the notes at every start, update and re-check them after each block of work, when to ask you |
| `CLAUDE.md` | `@AGENTS.md`, so Claude Code reads the same rules |
| `notes/state.md` | goal, now, next steps, open questions, files that matter (kept under 60 lines) |
| `notes/decisions.md` | one line per decision with its reason; replaced decisions are struck through, never deleted |
| `notes/log.md` | one dated line per block of work, for a retrospective (say "retro") |

If `AGENTS.md` or `CLAUDE.md` already exists, the new text is added at its end.

## Why files

A pasted prompt does not survive compaction word for word: harnesses summarise the conversation. The instruction file of the harness (`AGENTS.md`, `CLAUDE.md`) and files on disk are read again. So the prompt's real job is to write those files.

## What is promised

Any model that can write files creates the same five files, with the same names, headings and rules. The wording of its replies differs from model to model. See [`tests/`](tests/) for the measurements.

## License

MIT, see [LICENSE](LICENSE).
