# Karaoke Underground: content working copy

The site content for the karaokeunderground.com revamp, for editing and improving. It's Karaoke Underground's content, so it lives in this private repo. It never goes in the public one, [Johnesco/karaokeunderground](https://github.com/Johnesco/karaokeunderground).

## Where it came from

It started as the clean content from the 2026-09-23 snapshot ([#6](https://github.com/Johnesco/karaokeunderground/issues/6), [#7](https://github.com/Johnesco/karaokeunderground/issues/7)). The first commit holds that content unchanged, so the history shows every edit since.

The snapshot itself stays frozen and read-only in the public repo's gitignored `snapshot/` folder, on John's machine. That includes its reference copy of the old site.

## What's here

| Path | What it is |
|---|---|
| `songlist.csv` | The master songlist: artist, title, album |
| `themed-songlists.csv` | The 8 themed songlists from blog posts, in one format |
| `shows.json` | Upcoming shows from the homepage and the Calendar page |
| `pages/`, `posts/` | One HTML file per page and per post |
| `media/` | The uploaded images, plus the theme's logo and icons in `media/theme/` |
| `index.json` | The snapshot's map of all of it (old URLs, dates, files and checks) as of 2026-09-23. It doesn't update as the content changes |

Open the CSVs as UTF-8. In Excel, use Data → From Text/CSV.

## Working here

- Tickets live in the public repo. Reference them in commit messages as `Johnesco/karaokeunderground#N: description`.
- Keep it private. Don't paste this content into the public repo, its issues or its commit messages.
- Building the site from this content waits on ADR-001 ([#2](https://github.com/Johnesco/karaokeunderground/issues/2)), which picks the stack.
