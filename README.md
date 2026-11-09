# Ledger

![Single file](https://img.shields.io/badge/single--file-HTML%2FCSS%2FJS-blue)
![No build step](https://img.shields.io/badge/build-none-brightgreen)
![Mobile friendly](https://img.shields.io/badge/mobile-friendly-orange)

An assignment tracker for students. It runs as one `index.html` file, with no build step and no backend. Your data stays in your browser, and you can sync it between phone and PC with a free Puter account.

## Why

Deadlines are easy to lose across courses. Ledger puts every assignment in one place and shows what is due, how heavy the week is, and how each task counts toward your grade.

## Features

- **Calendar** with a bar for each assignment, running straight from its start date to its deadline. Tap a day to list everything due or running through it. On mobile the list opens as a bottom sheet.
- **Today, Week and Semester views**, with crunch-week warnings and a timeline that sizes each task by its share of the grade.
- **Courses** with weightings, a grade calculator, instructor and colour. Pick one of ten preset colours or press **Custom** for a colour wheel and hex input.
- **Timetable** with a weekly class grid. A scanner reads a timetable image and creates courses automatically.
- **Quick add**: type an assignment in plain language and the date, course and time are parsed for you.
- **Cross-device sync** through `puter.kv`, last write wins.
- **Confirm before submit**, so a mis-tap does not mark a task as done.
- **Light and dark themes**, a touch-friendly settings menu, and locked zoom on phones.

## Prerequisites

- A modern browser (Chrome, Edge, Firefox, Safari).
- Optional: a [Puter](https://puter.com) account for sync and the AI scanners.
- Optional: Python 3 (or any static file server) to serve the file locally.

## Installation

```bash
git clone https://github.com/Danialbroz/Assignment-Tracker.git
cd Assignment-Tracker
```

## Usage

Open `index.html` directly, or serve it:

```bash
python -m http.server 8000
# open http://localhost:8000
```

1. Add a course (or scan your timetable) from the left rail.
2. Press **+ Add assignment** and set a start date and due date.
3. Tick an assignment when done and confirm the prompt.
4. To sync, open the settings gear, sign in to Puter on each device, and the data follows you.

On a phone, use your browser's **Add to Home Screen** to install it like an app.

## Configuration

There are no environment variables. Data lives in `localStorage` under the key `ledger.v1`. The settings menu holds the semester start date, theme and Puter sign-in.

## Project structure

| File | Purpose |
|---|---|
| `index.html` | The whole app: markup, styles and logic |
| `logo.svg`, `apple-touch-icon.png` | Icons |
| `graphify-out/` | Generated code knowledge graph (optional) |

## Contributing

1. Fork the repo and create a branch: `git checkout -b feature/my-change`.
2. Keep the app in a single file with no build tooling.
3. Test on desktop and a phone-sized viewport, in light and dark themes.
4. Open a pull request that describes what changed and why.

## License

No license has been chosen yet. Add a `LICENSE` file (for example MIT) before others reuse the code.
