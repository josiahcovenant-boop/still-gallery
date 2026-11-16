# Still: gallery website

3D museum for artists. A walkable 3D gallery built in one page (`index.html`) with Three.js. Visitors walk through an arched entrance, look at framed works, open each work's details and play an artist's audio clip. A looping playlist plays in the background and pauses while a clip plays.

## What is in this repo

| Path | What it is |
|---|---|
| `index.html` | The whole site: 3D room, artwork data, details screen, music and clip player. Edit this file. |
| `README.md` | This file. |

The page loads Three.js from a CDN, so there is nothing to install or build.

## Where things go

- **Public site: Hostinger.** Upload `index.html` to the site's public folder (for example `public_html`). The music is kept on Hostinger, not in this repo: create a `music/` folder beside `index.html` and upload the three tracks there. The site then lives at your domain.
- **Artist submissions: Replit.** Artists submit info, pictures and one audio clip per painting (2 minutes max). Submissions are saved to a table that you review. Keep the submission app in a separate Replit project, not in this repo, unless you decide otherwise.
- **Codex:** Clone this repo and work on `index.html`. Each change should be committed and pushed so Hostinger and Replit can pick it up.

## Setup: Hostinger (public site)

1. In hPanel, open the website's file manager (or connect Git if your plan supports it).
2. Upload `index.html` to the public folder. Create `music/` next to it and upload the three tracks (`late-lounge.mp3`, `late-blues-loop-a.mp3`, `late-blues-loop-b.mp3`) so the paths match.
3. Open the domain. The page should show a "Still" gallery with an "Enter the gallery" button.

The music paths in `index.html` are `music/late-lounge.mp3` and so on. If you rename a track, update the `MUSIC` list near the top of the `<script>` in `index.html`.

## Setup: Replit (artist submissions)

Replit runs the artist form and stores what artists send. It is separate from the public site.

1. Create a new Repl (Node.js template).
2. Build or paste the submission app there, with these parts:
   - A public form for artist name, contact email, painting title, year, medium, size, description, a picture and an audio clip of 2 minutes or less per painting.
   - A table for submissions with a status column: new, approved, needs changes.
   - A review page protected by a password.
3. Put the review password and any database settings in **Replit Secrets**, never in the code.
4. Share the form link with artists, and link to it from the gallery site.

## Setup: Codex

1. Clone the repo: `git clone` the Git address of this repo.
2. Open `index.html`. The sections you are most likely to change are:
   - `WORKS` and `ARTISTS` near the top of the script: titles, artists, prices and descriptions.
   - `WORK_IMAGES`: real artwork images, keyed by work number.
   - `MUSIC`: the playlist file paths (the tracks themselves live on Hostinger).
   - Each work's `clip` field: the audio clip path for that painting.
3. Test in a browser. The page works from a plain file, but audio and image loading are most reliable from a local web server (`python3 -m http.server`).
4. Commit with a clear message and push. Do not commit passwords, API keys or database details.

## Rules for this repo

- Never put secrets in the code. Use Replit Secrets and Hostinger's own settings.
- Keep real artist recordings and images out of the repo until the artist has agreed to their use.
- The `#admin` link (add `#admin` to the URL) shows editing tools. It is for you, not for visitors.

## Status

- Done: 3D gallery room, arched entrance with opening animation, 17 works, details screen, playlist, artist clip player.
- To do: artist submission app on Replit, review page, real artwork and artist details, final checks on phones.
