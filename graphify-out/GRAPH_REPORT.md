# Graph Report - Assignment-Tracker  (2026-11-10)

## Corpus Check
- Corpus is ~21,016 words - fits in a single context window. You may not need a graph.

## Summary
- 53 nodes · 54 edges · 9 communities (6 shown, 3 thin omitted)
- Extraction: 85% EXTRACTED · 15% INFERRED · 0% AMBIGUOUS · INFERRED: 8 edges (avg confidence: 0.78)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- AI Scanners & Puter
- Views & Planning
- App Shell & Styling
- Interaction & Drawer
- Quick Add & Import
- Data Model & Storage
- Logo Artwork
- App Icon
- UI State

## God Nodes (most connected - your core abstractions)
1. `renderMain (view router)` - 7 edges
2. `Event delegation (click/change/input/keydown)` - 6 edges
3. `openQuick / saveQuick (quick add)` - 5 edges
4. `aiRows (calls puter.ai.chat)` - 5 edges
5. `index.html (Ledger app)` - 4 edges
6. `scanTimetable` - 4 edges
7. `scanAssignment` - 4 edges
8. `localStorage store (ledger.v1) state S` - 3 edges
9. `renderRail (sidebar + tab bar)` - 3 edges
10. `viewToday (Today page)` - 3 edges

## Surprising Connections (you probably didn't know these)
- `Assignment Tracker logo` --conceptually_related_to--> `Assignment-Tracker`  [INFERRED]
  logo.svg → README.md

## Import Cycles
- None detected.

## Hyperedges (group relationships)
- **AI scanner pipeline (PDF/image to rows via Puter)** — index_filetobatches, index_pdfjs, index_airows, index_puter_js, index_claude_haiku_model, index_scantimetable, index_scanassignment [EXTRACTED 1.00]
- **Smart prioritisation and workload logic** — index_priority_ranking, index_reminders, index_weeksuggestion, index_crunchweeks, index_gradestats [INFERRED 0.85]
- **Ways to add assignments** — index_openquick_savequick, index_parsetext, index_import_syllabus_ics, index_scanassignment, index_export_import_json [INFERRED 0.75]

## Communities (9 total, 3 thin omitted)

### Community 0 - "AI Scanners & Puter"
Cohesion: 0.24
Nodes (11): AI scanners (timetable and assignment), aiRows (calls puter.ai.chat), claude-haiku-5-5 vision model, fileToBatches (image/PDF to base64 batches), pdf.js (cdnjs, lazy loaded), Puter account popup (openPuter, puterLogin, puterLogout), Puter.js (js.puter.com/v2) auth and AI, runScan / SCAN_ERR (limits: 15 MB, 100 pages, 20 images, 5 PDFs) (+3 more)

### Community 1 - "Views & Planning"
Cohesion: 0.20
Nodes (10): calendarHTML / renderCal (month calendar), crunchWeeks, gradeStats, Priority ranking: urgency x mark (Work on now), renderMain (view router), viewCourse / updateCourseCalc (grade calculator), viewSearch, viewSemester (term timeline, crunch weeks) (+2 more)

### Community 2 - "App Shell & Styling"
Cohesion: 0.22
Nodes (9): index.html (Ledger app), CSS design tokens and themes (light/dark), Google Fonts (Instrument Sans, JetBrains Mono, Newsreader), Ledger single-file assignment tracker, Liquid glass styling, reminders / leadDays, renderRail (sidebar + tab bar), setRoute (hash routing) (+1 more)

### Community 3 - "Interaction & Drawer"
Cohesion: 0.29
Nodes (7): Event delegation (click/change/input/keydown), Drag and drop to reschedule assignments, Export / Import JSON backup, Keyboard shortcuts (openKeys), renderDrawer (assignment details drawer), toast, toggleSubmitted (with undo toast)

### Community 4 - "Quick Add & Import"
Cohesion: 0.33
Nodes (6): chime (WebAudio save sound), Apple-style date/time picker (openPicker), Import syllabus text / .ics (rowsFromText, parseICS), openQuick / saveQuick (quick add), parseText / resolveDue (natural-language parser), viewProfile / openProfile / saveProfile

### Community 6 - "Logo Artwork"
Cohesion: 0.50
Nodes (4): Assignment Tracker logo, Gold gradient fountain pen, Open notebook with handwriting, Assignment-Tracker

## Knowledge Gaps
- **22 isolated node(s):** `Ledger single-file assignment tracker`, `ui state object`, `Apple-style date/time picker (openPicker)`, `calendarHTML / renderCal (month calendar)`, `viewSearch` (+17 more)
  These have ≤1 connection - possible missing edges or undocumented components. (Counts symbols only; 24 node(s) total have ≤1 connection when file, concept and rationale nodes are included.)
- **3 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `renderMain (view router)` connect `Views & Planning` to `AI Scanners & Puter`, `App Shell & Styling`, `Quick Add & Import`?**
  _High betweenness centrality (0.309) - this node is a cross-community bridge._
- **What connects `Ledger single-file assignment tracker`, `ui state object`, `Apple-style date/time picker (openPicker)` to the rest of the system?**
  _22 weakly-connected nodes found - possible documentation gaps or missing edges._
- **Why does `Event delegation (click/change/input/keydown)` connect `Interaction & Drawer` to `AI Scanners & Puter`, `Quick Add & Import`?**
  _High betweenness centrality (0.184) - this node is a cross-community bridge._