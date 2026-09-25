# Karaoke Underground: content working copy

The site content for the karaokeunderground.com revamp, for editing and improving. It's Karaoke Underground's content, so it lives in this repo, apart from the code in [Johnesco/karaokeunderground](https://github.com/Johnesco/karaokeunderground), and never goes in that one.

This repo became public on 2026-09-24, so that the revamp's public preview at https://johnesco.github.io/karaokeunderground/ can build from it ([ADR-010](https://github.com/Johnesco/karaokeunderground/blob/main/docs/adr/010-preview-on-github-pages.md)). A scan of its whole history first found no phone numbers, email addresses, logins or plugin versions. The content itself was already public on karaokeunderground.com.

## Where it came from

It started as the clean content from the 2026-09-23 snapshot ([#6](https://github.com/Johnesco/karaokeunderground/issues/6), [#7](https://github.com/Johnesco/karaokeunderground/issues/7)). The first commit holds that content unchanged, so the history shows every edit since.

The same day it was converted into the core files in `content/` ([#10](https://github.com/Johnesco/karaokeunderground/issues/10)), in the formats that [ADR-002](https://github.com/Johnesco/karaokeunderground/blob/main/docs/adr/002-core-file-formats.md) sets. That commit changed the format, not the content. Fixes to the content come in the commits after it.

The snapshot itself stays frozen and read-only in the public repo's gitignored `snapshot/` folder, on John's machine. That includes its reference copy of the old site.

## What's here

| Path | What it is |
|---|---|
| `content/` | The core files the site reads: everything that changes lives here |
| `content/songlist.csv` | The master songlist: Artist, Title, Album, Themes, Tags |
| `content/pages/`, `content/posts/` | One Markdown file per page and per post |
| `content/images/` | The images, in year/month folders, with the logo and icons in `site/` |
| `shows.json` | The upcoming shows from the old homepage and Calendar page, as the snapshot found them. They become a core file once we decide how events get updated |

The snapshot's `index.json` (old URLs, dates and image IDs) and `themed-songlists.csv` (the 8 themed lists, parsed from their posts) aren't needed now. Both are in this repo's first commit and in the frozen snapshot.

## Editing the core files

The formats are in ADR-002 and the public repo's CLAUDE.md, under Data Formats. In short:

- **songlist.csv:** keep the first row as it is. Themes and Tags can be blank, or hold several values separated by semicolons, like `sad; scary`. The theme `unlisted` takes a song off every list without deleting it. Save it as UTF-8 (in Excel, "CSV UTF-8"), and open it the same way (in Excel, Data → From Text/CSV).
- **Pages and posts:** plain Markdown, with no HTML. A line break inside a paragraph ends with a backslash. Each file starts with its front matter: a title, a date, and, on the converted files, `updated` and `old_url`.
- **Images:** put a new one in the folder for its year and month, and show it with a path from the post, like `![What the image shows](../images/2026/12/flyer.jpg)`.

Check the files before committing: run `npm test` in the public repo, or `npm run check` for the content alone. It needs no network.

## Working here

- Tickets live in the public repo. Reference them in commit messages as `Johnesco/karaokeunderground#N: description`.
- Keep it apart from the code. Don't paste this content into the code repo, its issues or its commit messages, and keep personal and admin details out of both repos.
