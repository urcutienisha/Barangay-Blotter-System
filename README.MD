# Barangay Blotter Management System — Resident Portal

A lightweight, front-end-only web app that lets barangay residents file and track blotter (incident) reports. It is plain HTML, CSS and JavaScript: no build step, no server, no dependencies.

## Features

- **Dashboard** — welcome banner, report counts (Total / Pending / Under Investigation / Resolved) and the five most recent reports.
- **File a Blotter Report** — incident type, location, date and time, person(s) complained against, witness(es) and a narrative. Reference numbers are generated automatically (e.g. `BLT-2026-0001`).
- **My Reports** — search by reference number, type or location; filter by status; view details with a status timeline; edit or withdraw while the report is still *Pending*; print a report.
- **My Profile** — name, contact number, age, gender and home address, attached to every report you file.
- **Responsive layout** with a collapsible sidebar on small screens.

## Getting Started

1. Clone or download this repository.
2. Open `index.html` in any modern browser.

Optionally, serve it locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Project Structure

```
brgy/
├── index.html   # Markup and application logic (inline script)
├── style.css    # Styles and responsive layout
├── README.MD    # Project documentation
├── PROMTLOG.MD  # Log of AI prompts used during development
└── .gitignore   # Files excluded from version control
```

## Data Storage

All data is saved in the browser's `localStorage` under these keys:

| Key             | Contents                       |
| --------------- | ------------------------------ |
| `bbms_reports`  | Filed blotter reports          |
| `bbms_profile`  | The resident's profile         |
| `bbms_counter`  | Running reference-number count |

Data stays on the device and browser used. It is not shared or synced, and clearing browser data removes it. **My Profile → Clear All My Data** deletes everything the app has stored.

## Report Status Flow

`Pending` → `Under Investigation` → `Resolved`, or `Pending` → `Withdrawn` (by the resident).

Residents can only edit or withdraw reports that are *Pending*. This portal has no officer-side interface, so moving a report to *Under Investigation* or *Resolved* is not yet possible from the UI.

## Limitations and Possible Next Steps

- No back end or authentication; data is per-browser only.
- No official/admin dashboard for updating report status.
- Ideas: server database, user accounts, SMS or email notifications, file/photo attachments, export to PDF.

## Disclaimer

This is a demonstration project. For emergencies, call **911** or your barangay hotline immediately. Filing false reports may have legal consequences.
