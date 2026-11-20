# CSIT248 – My Student Portal

- **Name:** Daniil Pinegin
- **Enrolment number:** A85204925012
- **Last four digits:** 5 0 1 2 → D1 = 5, D2 = 0, D3 = 1, D4 = 2
- **Started:** 2026-11-13

## My values

| Value | Meaning | Formula | Result |
|-------|---------|---------|--------|
| P | password min length | 6 + (D4 mod 4) = 6 + 2 | **8** |
| M | name max characters | 20 + D1 = 20 + 5 | **25** |
| S | students in JSON | 5 + (D3 mod 3) = 5 + 1 | **6** |
| K | my own marks | (5 + 0 + 1 + 2) × 4 = 32 (max 100) | **32** |
| T | pass mark | 40 + D4 = 40 + 2 | **42** |
| C | accent colour | named CSS colour starting with "P" (Pinegin) | **purple** |

## Repository

- **Repo name:** csit248-portal-5012

## How to run

`fetch()` does not work from a `file://` page, so open the site over HTTP:

- VS Code: right-click `index.html` → **Open with Live Server**, or
- terminal: `python -m http.server` in this folder, then open http://localhost:8000

## Reflection

The bug that cost me the most time was the Register button reloading the page instead of showing my errors, because my submit handler in app.js never ran. I found it with the browser console open: no message from my handler appeared, and once I attached the listener to the `<form id="registerForm">` (not the button), kept `defer` on the script tag and called `event.preventDefault()` first, validation worked. With another hour I would show each error next to its own field and remove the red `.invalid` border while the user types, not only on blur.
