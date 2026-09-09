# Requirements

## v1 Requirements

### Search & Browse
- [ ] **CORE-01**: User can instantly search for titles.
- [ ] **CORE-02**: User can navigate categories (movies, shows, anime, trending) using slash commands.
- [ ] **CORE-03**: User can navigate the UI exclusively using the keyboard (arrow keys, etc).

### Metadata Display
- [ ] **META-01**: System integrates with TMDB API to fetch high-quality metadata.
- [ ] **META-02**: User can view visual posters and detailed title views within the terminal.
- [ ] **META-03**: User can select visual themes (Modern, ASCII).

### Playback & Subtitles
- [ ] **PLAY-01**: System scrapes/extracts streams from sources for selected titles.
- [ ] **PLAY-02**: User can pick an episode for TV shows/anime.
- [ ] **PLAY-03**: User can select subtitles before playback.
- [ ] **PLAY-04**: User can launch streams in local video players (mpv, VLC, IINA).

### Downloads
- [ ] **DOWN-01**: User can download single episodes.
- [ ] **DOWN-02**: User can download full seasons.
- [ ] **DOWN-03**: System supports resuming interrupted downloads.

### Live TV
- [ ] **LIVE-01**: User can provide M3U playlists via a config file.
- [ ] **LIVE-02**: User can browse and play live TV channels from the playlist.

## v2 Requirements (Deferred)
(None)

## Out of Scope
- Built-in video playback engine: Complex and goes against the goal of a fast TUI. Local mature players handle this best.
- Heavy GUI or Web Frontend: Goal is a terminal-first application.

## Traceability
(Updated by roadmap)
