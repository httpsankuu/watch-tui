# Roadmap

## Phase 1: Core TUI and Metadata Integration
**Goal:** Establish the BubbleTea terminal UI foundation, navigation, and TMDB metadata integration.
**Requirements:** CORE-01, CORE-02, CORE-03, META-01, META-02, META-03
**Success Criteria:**
1. User can run the app and navigate categories using arrow keys and slash commands.
2. User can search for a title and view its poster (Modern/ASCII themes) and detail info from TMDB.

## Phase 2: Stream Extraction and Local Playback
**Goal:** Implement stream scraping, episode selection, subtitle fetching, and local player integration.
**Requirements:** PLAY-01, PLAY-02, PLAY-03, PLAY-04
**Success Criteria:**
1. User can select a title/episode, and the system extracts valid stream URLs.
2. User can choose a subtitle and successfully launch the video in mpv, VLC, or IINA.

## Phase 3: Downloads and Live TV
**Goal:** Add download management with resume capabilities, and Live TV via M3U playlists.
**Requirements:** DOWN-01, DOWN-02, DOWN-03, LIVE-01, LIVE-02
**Success Criteria:**
1. User can initiate a download for an episode/season and resume it if interrupted.
2. User can configure an M3U playlist, browse channels, and launch a Live TV stream.
