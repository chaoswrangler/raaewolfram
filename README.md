# raaewolfram.github.io

Portfolio site for Raae Wolfram (pronounced "Ray"). It's a single page with no build step and runs on GitHub Pages.

## Repo layout

```
index.html          the whole site
README.md           this file
images/           (empty for now; photos go here later)
```

## Publishing on GitHub Pages

1. Create a repo named `<your-github-username>.github.io` (or any repo name).
2. Upload `index.html`, `README.md`, and the `images/` folder.
3. Go to **Settings → Pages**, set **Source** to "Deploy from a branch", pick `main` and `/ (root)`, and save.
4. The site goes live at `https://<username>.github.io/` (or `/<repo-name>/`) within a minute or two.

## Photos (not on the site yet)

The page has no photos right now. When you have them, send them over to be added, or add them yourself with the snippets below.

### Headshot: `images/portrait.jpg`
- **Where it goes:** the profile console in the hero, in place of the wolf reticle.
- **Shape:** square or 4:5. Example: 1200 × 1500 px. It's cropped to a circle.
- **Framing:** head and shoulders, centered, with a little space above your head.
- **Look:** a dark or neutral background (navy, charcoal, slate) and cool, soft light. Avoid bright white walls and busy backgrounds.
- **File size:** under 400 KB, exported as JPG at about 80% quality.
- **To add it:** in `index.html`, find `<div class="reticle"` and put this line just above it:
  `<img class="ship-photo" src="images/portrait.jpg" alt="Portrait of Raae Wolfram">`

### Speaking photo: `images/speaking.jpg`
- **Where it goes:** the Experience section, above Education.
- **Shape:** landscape, 16:10. Example: 1600 × 1000 px.
- **Content:** you presenting, at BSides, Experts Live, a webinar set, or a briefing, with a stage, screen, or audience visible.
- **File size:** under 500 KB.
- **To add it:** in `index.html`, find `<div class="side">` and put this line just below it:
  `<img class="stage-photo" src="images/speaking.jpg" alt="Raae speaking at a conference">`

### Tips
- Shrink images before uploading (squoosh.app is free and works in the browser).
- File names are case-sensitive: `portrait.jpg` works, `Portrait.JPG` doesn't.

## Editing text

All copy lives in `index.html`. Search for the sentence you want to change and edit it in place. Contact links (email and LinkedIn) are in the Contact section and in the hero buttons.

## Role match (AI fit check)

The Role match section builds an AI prompt from Raae's résumé for a specific role.

- Visitors can paste a job posting URL, enter a role and company, or both. A pasted job description works too.
- **Auto-loading a job link:** the page tries to pull the posting text through r.jina.ai, a free public page-reader. Some job sites block it. When that happens, the prompt includes the link and tells the AI to open it.
- **Shareable pre-filled link:** add `?job=`, `?role=`, and `?company=` to the site URL, and the page fills in the form and runs it automatically. Example:
  `https://chaoswrangler.github.io/?role=Head%20of%20AI%20Strategy&company=Skynet`
- **Résumé source:** the prompt embeds your full résumé text (May 2026), with the phone number removed, plus a short "Additional context" block for portfolio-only work like AI builds and independent projects. Both live in `index.html` under `const PROFILE`. Paste in new résumé text there when you update it.
- **Prompt length:** the full prompt is about 9,000 characters, too long to pre-fill in a link. So the Claude and ChatGPT buttons copy the prompt and open a new chat for the visitor to paste into.

## Notes
- Animations respect the visitor's "reduce motion" setting. With it on, the intro, particles, and flares are turned off.
- No tracking or analytics are included.
