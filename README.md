# Sawarajya Hackfest

A static website for the Sawarajya hackathon — problem statements, submissions,
and event information.

## Screenshots

No screenshots are stored in this repo, and no live site is linked in the repo.
To add screenshots, open `index.html` in a browser and capture the home page
and the problem-statement page.

## What it does

- Hackathon home page
- Problem statements (`problem-statement.html`)
- Submissions (`submission.html`) — collected via Google Sheets
  (see `GOOGLE_SHEETS_SETUP.md`)

## Tech Stack

- Plain HTML, CSS, and JavaScript — no build step, no framework
- Google Sheets for submissions

## How to Run

No installation needed. Open `index.html` directly in a browser, or serve it locally:

```bash
python -m http.server 8000
# then open http://localhost:8000
```

## Project Structure

```
├── index.html
├── problem-statement.html
├── submission.html
├── images/
├── templates/
├── project.md
├── GOOGLE_SHEETS_SETUP.md
└── *.pptx            # Sample presentation
```
