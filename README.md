# Count what counts: SSQL × IEFI

A Quarto website containing a Reveal.js slide deck and a companion handout for
a 30-minute session introducing the Social Science Quantitative Lab to
Swarthmore's Inclusive Excellence Fellows.

## What's in here

| File | What it does |
|---|---|
| `_quarto.yml` | Project settings: website navbar, Bootswatch theme for HTML pages |
| `slides.qmd` | The Reveal.js presentation |
| `index.qmd` | Landing page |
| `project-ideas.qmd` | Handout with ideas for each 2026–27 project |
| `styles/site.scss` | Overrides for the Bootswatch theme (website pages) |
| `styles/slides.scss` | Custom Reveal.js theme (slides), sharing the same palette |
| `.github/workflows/publish.yml` | Re-publishes the site on every push to `main` |

**One thing to know:** Bootswatch themes apply to Quarto's HTML pages (the
website), not to Reveal.js slides, which have their own theme system. This
project uses Bootswatch for the site and a custom Reveal.js SCSS theme for the
slides, with the same colors and fonts in both so they feel like one project.

## Work on it locally

1. Install [Quarto](https://quarto.org/docs/get-started/) and use Positron,
   RStudio, or VS Code with the Quarto extension.
2. From the project folder, run:

   ```bash
   quarto preview
   ```

   This opens a live preview that re-renders every time you save.

3. Search the slides for `todo` to find placeholders to fill in.

## Put it on GitHub

1. Create an empty repository on GitHub, for example `ssql-iefi`.
2. From the project folder:

   ```bash
   git init
   git add .
   git commit -m "First draft of IEFI presentation"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/ssql-iefi.git
   git push -u origin main
   ```

3. Update the GitHub link in `_quarto.yml` with your username.

## Publish with GitHub Pages

**First time only**, publish from your computer. This creates a `gh-pages`
branch and a `_publish.yml` file:

```bash
quarto publish gh-pages
```

Commit and push the new `_publish.yml`. Then in your repository on GitHub, go to
**Settings → Pages** and make sure the source is **Deploy from a branch**, with
branch `gh-pages` and folder `/ (root)`.

**After that**, the GitHub Action in `.github/workflows/publish.yml` re-renders
and publishes the site automatically every time you push to `main`. You can
watch it run under the **Actions** tab.

Your site will be at `https://YOUR-USERNAME.github.io/ssql-iefi/`, and the
slides at `.../slides.html`.

## Presenting

- **F**: full screen
- **S**: speaker notes (with timings) in a separate window
- **O** or **Esc**: slide overview
- Add `?print-pdf` to the slides URL and print from Chrome to save a PDF.

## Exercises to build your skills

1. **Swap the Bootswatch theme.** In `_quarto.yml`, change `flatly` to `litera`,
   `lux`, or `sandstone` and compare. Notice which of your overrides in
   `styles/site.scss` still apply.
2. **Add dark mode.** Replace the `theme:` line with `light:` and `dark:` entries
   (for example `flatly` and `darkly`). You'll need a lighter garnet for contrast
   on the dark background.
3. **Try `_brand.yml`.** Recent Quarto versions can read colors and fonts from a
   single `_brand.yml` file and apply them to both the website and the slides.
   Moving the shared palette there would remove the duplication between the two
   SCSS files.
4. **Add a real chart.** Add an R or Python code chunk to a slide, using data from
   the opening poll. You'll need `execute: freeze: auto` in `_quarto.yml` so the
   GitHub Action doesn't need R installed. See the Quarto docs on freezing
   computations.
5. **Add extensions.** Try `quarto add` with a QR-code extension for the poll
   slide, or a countdown-timer extension for the two-minute activity.
6. **Make a slide background image.** Add `background-image="images/your-photo.jpg"`
   to a slide heading. Use photos you have rights to.
