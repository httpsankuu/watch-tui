# Phase 1: Core TUI and Metadata Integration - Research

## Context
This phase focuses on establishing the foundational Terminal User Interface (TUI) for "Watch It" using Go and the Bubble Tea framework. It involves setting up the core keyboard-first navigation patterns, integrating with the TMDB API to fetch media metadata, and rendering complex UI elements like visual posters and detailed views directly within the terminal environment.

## Requirements Covered
- **CORE-01**: User can instantly search for titles.
- **CORE-02**: User can navigate categories (movies, shows, anime, trending) using slash commands.
- **CORE-03**: User can navigate the UI exclusively using the keyboard (arrow keys, etc).
- **META-01**: System integrates with TMDB API to fetch high-quality metadata.
- **META-02**: User can view visual posters and detailed title views within the terminal.
- **META-03**: User can select visual themes (Modern, ASCII).

## Technical Domain & Dependencies
1.  **TUI Framework (Go)**:
    -   `charmbracelet/bubbletea`: The core architecture (Model, Update, View).
    -   `charmbracelet/bubbles`: Pre-built reusable UI components (e.g., `textinput` for search/slash commands, `list` or `viewport` for browsing titles).
    -   `charmbracelet/lipgloss`: For defining styles, layouts, and supporting different visual themes.
2.  **Metadata Integration (TMDB)**:
    -   HTTP client integration with the TMDB (The Movie Database) API.
    -   Need JSON unmarshaling into strongly-typed Go structs representing Movies, Shows, and standard metadata responses.
    -   Authentication will require a TMDB API Key.
3.  **Terminal Image Rendering**:
    -   Rendering posters (META-02) in a terminal requires translating image pixels to terminal characters/colors.
    -   Libraries like `github.com/qeesung/image2ascii` or native lipgloss/custom rendering for terminal block characters will be necessary to support the "Modern" vs "ASCII" visual themes.

## Key Patterns & Architectural Considerations
1.  **State Management & Routing**:
    -   The main Bubble Tea model will need a routing mechanism to switch between different states/views (e.g., `ViewStateSearch`, `ViewStateBrowse`, `ViewStateDetails`).
2.  **Asynchronous Operations**:
    -   Fetching from TMDB and processing images must be non-blocking. This requires utilizing Bubble Tea's `Cmd` functionality to perform work in the background and return `Msg` events (e.g., `TMDBDataReceivedMsg`, `ImageProcessedMsg`) to update the UI.
    -   **Instant Search**: The text input component needs debouncing to avoid hitting the TMDB API on every keystroke.
3.  **Navigation System**:
    -   **Slash Commands (CORE-02)**: The global update loop needs to intercept the `/` key to activate a command input mode, parse the command (e.g., `/movies`, `/trending`), and transition the view.
    -   **Keyboard Focus**: Managing which component (input, list, detail view) currently receives keyboard events (CORE-03).
4.  **Theming Engine**:
    -   A centralized styling strategy using `lipgloss` that can toggle between "Modern" (rich colors, unicode borders, block-rendered images) and "ASCII" (standard ASCII borders, text-based layouts) configurations based on user preference.

## Unknowns / Questions for Planning Phase
- **API Key Management**: How should the user provide the TMDB API Key (e.g., environment variable, initial setup prompt, configuration file)?
- **Image Rendering Fidelity**: What is the minimum acceptable quality for terminal posters? Which specific library will best serve this without bloating the binary?
- **Slash Command Schema**: What is the exact expected syntax for slash commands (e.g., `/goto movies`, `/movies`, `/search <query>`)?
- **Configuration Storage**: Where will user preferences, like the selected theme (Modern vs ASCII), be stored?
