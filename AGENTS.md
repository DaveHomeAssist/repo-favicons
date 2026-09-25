# AGENTS.md

Inherits root rules from `/Users/daverobertson/Desktop/Code/AGENTS.md`.

## Project Overview

Central repository of SVG favicon source files for all projects in the ecosystem. Contains one SVG per project. The index.html page serves as a visual gallery preview of the full set. A favicon-preview.html provides an alternate preview entry.

## Stack

- SVG source files (one per ecosystem project)
- Static HTML gallery (index.html)
- No build step, no bundler

## Key Decisions

- One canonical SVG per project, named to match the project repo
- Gallery page provides a visual overview of the full favicon set
- SVGs are the source of truth; PNG favicon sets in each project repo are derived from these

## Issue Tracker

| ID | Severity | Status | Title | Notes |
|----|----------|--------|-------|-------|

## Session Log

[2026-03-18] [Favicons] [docs] Add AGENTS baseline

## Status naming

Name work with one string everywhere (chat status title, session title, Notion
Status Check Runs "Human Name"):

`Project | 🚦 | Phase | Title → state, reason | MM-DD`

- 🚦: 🟢 complete and verified · 🟡 partial · 🔴 not started, blocked or failed · ⚪ unverifiable.
  Add ⏳ scheduled, 🙋 awaiting Dave or 🚧 blocked to 🟡/🔴/⚪, never to 🟢.
- Phase: Research, Design, Build, Audit or Scheduled. MM-DD: date of the latest light change.
- Every light change gets a new name: a `RENAME:` line in chat and the Notion row updated.
- Canonical source: https://github.com/DaveHomeAssist/skills/blob/master/status-naming.md
