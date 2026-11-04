# Bramble Wall

Felix and Alex's shared-canon story world: the **Bramble Wall** series (grounded forest adventures, five books, complete), the restarted **Trio Force** case files, and standalone stories from the wider shared-canon universe.

This repo holds the stories and everything behind them: series bibles, ledgers, canon references, the writing and review process, and narration scripts. The site that publishes them is the [Stories](https://github.com/RobertBeverton/Stories) repo, which pulls `stories/` in at build time and serves it at **https://robertbeverton.github.io/Stories/**.

It was split out of the Stories repo (history kept) when Stories became the app for every story world.

| Path | What it is |
|---|---|
| `stories/` | Finished, locked stories as Markdown with front matter. Audio is not stored here: it is hosted on Cloudflare R2 and each story points at it with `audioUrl`. |
| `reference/` | Canon: series bibles and ledgers for Bramble Wall and Trio Force, plus the shared-canon directory, villain roster, magic system and story archive. |
| `docs/process/` | The writing workflow: read-order by task, craft rules, review personas and protocols, narration notes. Start at `docs/process/README.md`. |
| `narration/` | Narration scripts for stories that have been voiced, and this world's narration settings (`pronunciations.json`, `narrator.json`) when it has any. |
| `.claude/commands/write-story.md` | The `/write-story` command: title to locked, narration-ready story. |

## How this fits

This repo is content only. The app, the narrator and audio hosting live in the [Stories](https://github.com/RobertBeverton/Stories) repo. To narrate a story, run `npm run narrate -- ../bramble-wall/stories/<story>.md` from a Stories checkout, then `npm run upload-audio -- --apply --world bramble-wall`, and commit the story's changed front matter here. CI here only checks the stories against the app's rules (`.github/workflows/validate.yml`). Rebuilding the site after a push is the Stories repo's nightly build, or its "Build and Deploy" workflow run by hand.

Canon here is kept separate from [isles-of-yum](https://github.com/RobertBeverton/isles-of-yum) on purpose, so neither world leaks into the other.
