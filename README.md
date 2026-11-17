# chaoswrangler.github.io

Portfolio site for Raae Wolfram (pronounced "Ray"). Everything, including every photo, lives in one file, `index.html`. There's no build step, and it runs on GitHub Pages.

## Repo layout

```
index.html   the whole site, with all photos built in
README.md    this file
```

You don't need an `images/` folder. If one is left over from an earlier version, you can delete it.

## Publishing and updating

**First time:**
1. Create a repo named `chaoswrangler.github.io`, so the site lives at the root address.
2. Upload `index.html` and `README.md`.
3. Go to **Settings → Pages**, set **Source** to "Deploy from a branch", pick `main` and `/ (root)`, and save.
4. The site goes live at `https://chaoswrangler.github.io` within a minute or two.

**Every update after that:**
1. In the repo, go to **Add file → Upload files**, drop in the new `index.html`, and click **Commit changes**. It replaces the old file.
2. Wait a minute or two, then hard-refresh the site (Ctrl+Shift+R or Cmd+Shift+R; on a phone, pull down to reload).
3. Optional: open the **Actions** tab. A green check next to "pages build and deployment" means it's live.

## Page order

1. Hero: photo, intro, pronunciation, and the TL;DR link to Role match
2. How I operate (Playbook), with the "concept to customer" panel
3. Stat tiles and the Now/Before strip
4. Photo carousel 1
5. What I do
6. Outcomes
7. Photo carousel 2
8. S.T.A.R. webinar series, featuring episode 10
9. Projects, with links to live builds and repos
10. Photo carousel 3
11. Experience
12. Photo carousel 4
13. Role match, the AI fit-check prompt builder
14. FAQ (9 questions)
15. About me
16. Let's talk, with the wolf head and the binary moon

## Photos

The photos are built into `index.html`, so they show up anywhere the file is opened.

- **Main photo:** this is the profile picture in the hero console.
- **Carousels:** there are 4 carousels with 12 photos, all labeled FIELD LOG 01–12. Each one plays as a film-style frame:
  - The HUD shows "SCANNING FOR THREATS," then "PAYLOAD DETECTED · HIGH VALUE."
  - Target brackets lock onto each photo, the caption types itself out, and a glitch transition plays between photos.
  - There's a row of thumbnails, plus arrows and swipe.
  - Each carousel advances every 6 seconds and pauses on hover.
- **Changing captions:** search `index.html` for `FIELD LOG`. The captions are the `"txt"` values next to each tag.
- **Adding, removing or reordering photos:** this means re-encoding images into the file, so the easiest way is to send the new photos to Claude and ask for an updated `index.html`.
- **File size:** the page is about 2 MB because of the photos. Each extra photo adds roughly 100–200 KB.

## S.T.A.R. reel

- Episode 10 is the featured video and starts at 0:00. Its title and channel load live from YouTube.
- Episodes are listed in `STAR_EPISODES` in `index.html`. Remove `feature:true` to show every episode as a carousel.
- Episode 9's YouTube ID is still blank. Add it to `STAR_EPISODES` if you want it in the list.

## Role match (AI fit check)

Role match builds an AI prompt from Raae's résumé for a specific role.

- Every field is optional. Visitors can paste a job posting URL, enter a role and company, paste a job description, or any combination.
- **Job links:** the page tries to pull the posting text through r.jina.ai, a free page reader. Some job sites block it. When that happens, the prompt includes the link and asks the AI to open it.
- **Pre-filled links:** add `?job=`, `?role=` or `?company=` to the site address, and the page fills in the form and runs it. For example: `https://chaoswrangler.github.io/?role=Head%20of%20AI%20Strategy&company=Skynet`
- **Résumé source:** the prompt includes your full résumé text from May 2026 (with no phone number), plus an "Additional context" block for portfolio-only work. Both live in `index.html` under `const PROFILE`. Paste in new résumé text there when you update it.
- **Long prompts:** the Claude and ChatGPT buttons copy the prompt and open a new chat for pasting, because the prompt is too long to put in a link.

## FAQ and AI search

The FAQ appears on the page and also in hidden structured data (JSON-LD) that search engines and AI assistants read. If you edit an answer by hand, change it in both places: search `index.html` for the question text and you'll find two copies.

## Notes

- Animations follow the visitor's "reduce motion" setting. With it on, the intro, particles, glitches and the wolf's entrance are turned off.
- Everything is built to work on phones, down to the smallest screen width.
- There's no tracking or analytics.
