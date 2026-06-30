# Machal Portal

A web-based paperwork process portal for managing student onboarding documentation. Hosted on GitHub Pages at ezshap-rgb.github.io/machal-portal.

## Project Structure
- Supervisor portal — supervisor-facing HTML interface
- Student portal — student-facing HTML interface
- Shared config — config used by both portals

## Backend
- Google Drive (file storage)
- Google Forms (data collection)
- Google Apps Script (handles save/load between the portals and Drive)

## Architecture Notes
- The student portal uses a hybrid config delivery model:
  1. Config is baked into the file at export time
  2. On load, it attempts to auto-fetch updated config from a Google Drive share link
  3. If that fetch fails, it falls back to localStorage
- Google Apps Script handles Drive-based save/load — CORS issues have come up here before and may resurface with future changes

## Conventions
- The exported student-facing file should be named "Machal Paperwork Portal.html"

## Outstanding / In-Progress Items
- Add a favicon to both the supervisor and student portals
- (Add new items here as they come up)

## Notes for Claude
- This is a solo project — Ezra is the primary developer and has a precise eye for detail; prefer minimal, targeted changes over broad rewrites unless asked otherwise
- Confirm understanding of the hybrid config/localStorage fallback logic before modifying save/load behavior, since it's a deliberate design choice, not a bug
