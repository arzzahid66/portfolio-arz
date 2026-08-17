# Abdul Rehman Zahid — portfolio

Static site. No framework, no build step: one `index.html`, one `assets/` folder.

## Files
```
index.html      # whole site (HTML + CSS + a little vanilla JS)
assets/         # headshot + company logos
```

## Edit content
- **Text, timeline, bio, links** — edit the HTML directly in `index.html`.
- **Projects and demo videos** — edit the `PROJECTS` array in the `<script>` at the bottom.
  Paste an unlisted YouTube link into `video:` and the tile becomes a play thumbnail that
  expands an inline 16:9 player. Leave `video: ""` for the hatched placeholder.
- **Skills** — edit the `SKILLS` array in the same script.

## Run locally
Open `index.html` in a browser. That's it. (Or `python -m http.server` in this folder.)

## Deploy to Vercel
```bash
git init
git add .
git commit -m "portfolio"
git branch -M main
git remote add origin https://github.com/arzzahid66/portfolio.git
git push -u origin main
```
Then on vercel.com: **Add New → Project → import the repo**.
Framework Preset: **Other**. Build command: *empty*. Output directory: `./`
Deploy. Add your custom domain under Settings → Domains if you have one.

## Why plain HTML and not React/Next.js
Nothing on this page needs a server or a build step, so a framework would add tooling
and slow the first paint for zero benefit. Move to Next.js only when you add something
that genuinely needs a backend — a real admin login, a database, a contact form that
sends email, or an API route.

---

## Prompt for Claude Code

Paste this alongside the folder:

> This is my personal portfolio site: a single static `index.html` with inline CSS and
> vanilla JS, plus an `assets/` folder. It is deployed on Vercel as a static site with no
> build step. Keep it that way — do not introduce React, Next.js, a bundler, Tailwind, or
> any dependency unless I explicitly ask.
>
> House rules:
> - Preserve the existing visual design exactly: white background, 860px max-width centered
>   column, system sans-serif, 17px body text, `#0b5fbd` links, gray `.band` section labels,
>   168px logo/thumbnail column on the left of each row.
> - Content lives in two places: the HTML for profile/timeline/bio/elsewhere, and the
>   `PROJECTS` / `SKILLS` arrays at the bottom of `index.html`. Add projects there.
> - Demo videos are unlisted YouTube links in `PROJECTS[].video`; `youtubeId()` accepts full
>   URLs, youtu.be links, or bare 11-character IDs.
> - Keep it accessible: real focus states, keyboard-operable thumbnails, alt text on images.
> - Keep it fast: no web fonts, no analytics scripts, no CDN dependencies.
>
> Tasks I'll ask for: adding projects, updating the timeline, swapping logos, adding a blog
> section, improving SEO/meta tags, and eventually a real admin panel — for that last one,
> tell me honestly what backend it needs before writing code.
