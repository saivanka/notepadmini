# NOTE_MINI

A simple online notepad application: type text in the browser and download it as a `.txt` file. No account, no backend storage — everything happens in the page.

## What it does

- **Write** — Click "Get Started!" to open the notepad modal and type in a large text area (the page brands itself NOTE_MINI / Notemini and suggests Chrome for the best experience).
- **Save as a file** — Enter a file name and click Save. The page builds a plain-text Blob from the text and downloads it in the browser, so the note lands on your device as a `.txt` file.
- **Load a file** — A `loadFileAsText` helper reads a chosen text file back into the editor with the FileReader API.
- **Navigation shell** — A top nav with HOME, CONVERT, CONTACT and ABOUT links; only HOME is wired to the app page, the others are placeholders.

## Tech stack

- Plain HTML, CSS and inline JavaScript — no build step and no framework
- Bootstrap 5.0.0-alpha1 + Popper.js via CDN for the modal layout, Roboto Mono from Google Fonts
- Local styles in `css/` (compiled from `scss/`), Bootstrap also vendored under `node_modules/bootstrap`
- `index.php` includes the app page for PHP hosting, and a `Procfile` is present for Heroku-style deployment

## How to run

There is no build step. Serve the folder and open the app page:

```bash
npx serve .
```

Then open `src/index.html` in a browser, click "Get Started!", type your note, enter a file name and click Save to download it as a text file.

## Project structure

```
src/
  index.html        # The notepad app page (modal editor + save/load scripts)
  images/           # Logo and decorative images used by the page
index.php           # Includes the app page for PHP hosting
css/                # Compiled styles (app.css)
scss/               # SCSS sources
package.json        # Bootstrap dependency (no start script)
Procfile            # Heroku-style process file
```

## Status

A small 2021 single-page utility. Notes are only saved when you download them — there is no autosave, account or cloud storage, and the CONVERT/CONTACT/ABOUT nav links are placeholders.
