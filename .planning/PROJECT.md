# Watch It

## What This Is

A fast, keyboard-first terminal application for browsing and streaming movies, TV shows, anime, and live TV. It provides a polished TUI with instant search, easy navigation, and visual elements like posters and detail views, integrating seamlessly with local video players like mpv, VLC, or IINA.

## Core Value

Instant, frictionless terminal-based access to streaming media and live TV without leaving the keyboard or dealing with heavy web interfaces.

## Requirements

### Validated

(None yet — ship to validate)

### Active

- [ ] Interactive TUI built with Go and BubbleTea
- [ ] Instant search and category navigation (movies, shows, anime, trending) via slash commands
- [ ] Visual poster and detail views within the terminal
- [ ] Integration with TMDB API for metadata
- [ ] Web scrapers/extractors for media streams
- [ ] Integration with local media players (mpv, VLC, IINA) to launch streams
- [ ] Subtitle selection prior to playback
- [ ] Single episode and full season downloads with resume support
- [ ] Live TV mode powered by user-provided M3U playlists
- [ ] Visual themes: Modern and ASCII styles

### Out of Scope

- [ ] Heavy GUI or web frontend — goes against the core value of a fast terminal app.
- [ ] Built-in video player — we rely on mature local players (mpv/VLC/IINA) for actual playback.

## Context

The user wants a streamlined, keyboard-driven alternative to web-based streaming platforms. The app needs to feel polished despite being in the terminal, which is why Go and BubbleTea were chosen for their robust TUI capabilities. Sourcing relies on TMDB for rich metadata and custom scrapers for streams, meaning the architecture needs to be modular enough to handle potentially brittle or changing stream extraction logic.

## Constraints

- **Tech stack**: Go with BubbleTea — Chosen for fast execution, single-binary distribution, and great TUI ecosystem.
- **External Dependencies**: Local video players (mpv, VLC, IINA) must be installed on the host machine for playback.
- **Data sources**: TMDB API key required; stream scrapers must be reliable or easily updatable.

## Key Decisions

| Decision | Rationale | Outcome |
|----------|-----------|---------|
| Go + BubbleTea | Fast, cross-platform single binary, excellent TUI capabilities | — Pending |
| TMDB API + Custom Scrapers | Provides high-quality metadata while keeping streaming sources flexible | — Pending |
| Local Video Player Integration | Avoids reinventing complex playback/codec support | — Pending |
| User-provided M3U playlists | Avoids maintaining fragile public IPTV links, gives user control | — Pending |

## Evolution

This document evolves at phase transitions and milestone boundaries.

**After each phase transition** (via `/gsd-transition`):
1. Requirements invalidated? → Move to Out of Scope with reason
2. Requirements validated? → Move to Validated with phase reference
3. New requirements emerged? → Add to Active
4. Decisions to log? → Add to Key Decisions
5. "What This Is" still accurate? → Update if drifted

**After each milestone** (via `/gsd-complete-milestone`):
1. Full review of all sections
2. Core Value check — still the right priority?
3. Audit Out of Scope — reasons still valid?
4. Update Context with current state

---
*Last updated: 2026-09-09 after initialization*
