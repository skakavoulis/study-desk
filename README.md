# Study Desk

A study website: flashcards, quizzes, a focus timer and notes, with ready-made decks for every Greek school subject and grade, in 5 languages (EL, EN, ES, FR, DE).

It's a single static page (`index.html`), with no build step and no dependencies besides Google Fonts.

## Run locally

```bash
npx serve .
# or
python3 -m http.server 8080
```

## Deploy to Cloudflare Pages

**Option A: connect the Git repo (auto-deploys on every push)**

1. Push this repo to GitHub or GitLab.
2. In the Cloudflare dashboard go to **Workers & Pages → Create → Pages → Connect to Git** and pick the repo.
3. Build settings:
   - Framework preset: **None**
   - Build command: *(leave empty)*
   - Build output directory: `/`
4. Click **Save and Deploy**. The site goes live at `https://<project>.pages.dev`.

**Option B: direct upload with Wrangler**

```bash
npx wrangler login
npx wrangler pages deploy . --project-name study-desk
```

## Notes

- Outside Claude, decks, notes and progress are saved in each visitor's browser (localStorage).
- The "Make cards with Claude" features only work when the page is opened inside Claude; on Cloudflare Pages they stay hidden or show a note.
- Textbook links point to the official books at ebooks.edu.gr.
