# Daniel Frankl — portfolio site

Everything sits in one flat folder — no subfolders, so nothing can get
separated when you download or move files around:

```
index.html
robots.txt
LICENSE
prosthetic-interface-video.mp4
Modular_Prosthetic_Interface_Report.pdf
datafest-award.jpg
buggy-run-video.mp4
buggy-final-build.jpg
buggy-payload-target.jpg
buggy-poster.jpg
drone-flight-video.mp4
turbine-poster.jpg
```

**Important:** all files must stay in the same folder as `index.html`.
If you download them one at a time, make sure they all land in the same
folder before opening `index.html` — if the video or PDF end up
somewhere else (like a different Downloads subfolder), the video will
show blank and the report link will 404.

## View it

Double-click `index.html`. It opens in your browser.

## Add a new project

Open `index.html` in a text editor (Notepad, TextEdit, or something nicer
like VS Code / Sublime Text if you have it). Search for `const PROJECTS`
— you'll find a block that looks like this for each project:

```js
{
  "id": "prosthetic-interface",
  "title": "Modular quick-connect prosthetic foot interface",
  "subtitle": "eNABLe Lab, Technion — Summer 2026 research placement",
  "category": "medical",
  "categoryLabel": "Medical device",
  "featured": true,
  "stat": "3-DOF mechanism",
  "statLabel": "FEA-validated",
  "summary": "...",
  "role": "...",
  "approach": "...",
  "outcome": "...",
  "tools": ["SolidWorks", "FEA", "GD&T"],
  "image": null,
  "video": "prosthetic-interface-video.mp4",
  "report": "Modular_Prosthetic_Interface_Report.pdf",
  "links": []
},
```

Copy one whole block (from `{` to the `},` after it), paste it in as a new
entry, and edit the fields:

- `id` — unique, no spaces
- `category` — `medical`, `mechanical`, or `mechatronics` (controls the tag
  colour)
- `featured` — `true` shows it in the top "Featured work" row (keep this to
  2 projects at a time)
- `stat` / `statLabel` — optional headline number, e.g. `"1st / 33 teams"`,
  or leave both as `null`
- `tools` — list of skills/tools shown as tags
- `video` — just the filename, if you add one to the folder — or leave the
  line out entirely if there isn't one
- `report` — just the filename, if you add one to the folder — or leave
  the line out entirely if there isn't one

Save the file, refresh it in your browser (Cmd/Ctrl + R). That's it.

**Careful with commas and quotes** — each field needs a comma after it
except the last one in a block, and text needs to stay inside `" "`. If the
page breaks after an edit, check you haven't left a stray comma or missing
quote mark near what you changed.

## Add a video, report, or image to a project

1. Drop the file (video, PDF, or image) into the same folder as
   `index.html` — no subfolder.
2. In that project's block in `index.html`, reference it by filename only:
   ```js
   "video": "your-video-file.mp4",
   "report": "your-report.pdf",
   "image": "your-image.png",
   ```
3. Save and refresh. Video autoplays muted as the card thumbnail and plays
   in full with controls in the expanded view; the report shows as a
   "view full report" button.

## Add your CV

The "Download CV" button points at a file called `Daniel_Frankl_CV.pdf`
that doesn't exist yet. Put your CV PDF in the same folder as
`index.html`, or tell me and I'll add it and update the link for you.

## Update contact links

Search `index.html` for `mailto:` and the GitHub/LinkedIn `href="https://..."`
placeholders (there are two sets — one in the header, one in the footer)
and swap in your real email, GitHub, and LinkedIn URLs.

## Deploy to GitHub Pages (free hosting)

1. Create a GitHub account at github.com if you don't have one.
2. Create a new repository (e.g. `portfolio`) — public.
3. On the repo page, click "Add file" → "Upload files", and drag in every
   file from this folder (they can all go straight into the repo root —
   no subfolders needed there either).
4. Commit the upload.
5. Go to the repo's **Settings** tab → **Pages** (left sidebar).
6. Under "Build and deployment", set **Source** to "Deploy from a branch",
   branch = `main`, folder = `/ (root)`. Save.
7. Wait about a minute, then refresh — GitHub shows your live URL, something
   like `https://yourusername.github.io/portfolio/`.

Any time you edit files and re-upload them, the live site updates within
a minute or two.

## Search engine privacy

The site is set to tell Google and other search engines not to index it
(`robots.txt` plus a `noindex` tag in `index.html`) — so it won't come up
if someone searches your name, but anyone you send the direct link to can
still open it instantly, no password needed. Keep `robots.txt` in the same
folder as `index.html` when you upload to GitHub — it needs to sit at the
root of the site to work.

Note this only stops well-behaved crawlers (Google, Bing, etc.) from
listing it in search results — the URL itself is still publicly
reachable by anyone who has it, which is the trade-off for a link that
opens with zero friction for recruiters.
