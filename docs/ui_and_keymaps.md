# User Interface & Keybindings

## 1. Design Philosophy
* **Clean & Minimalist:** Progressive disclosure. Essential info first, detailed info via folds or detail buffers.
* **Colors:** Inherits existing Neovim/Terminal colorschemes. Minimal use of NerdFont icons.
* **Right-Aligned Telemetry:** Performance data and heatmaps use a `btop`-inspired aesthetic with Unicode block characters.

## 2. Dashboard Layout
* **Hierarchy:** Tree structure. `Project Name` -> `In Progress` -> `Open` -> `Backlog`.
* **Neovim Entry:** Opened via a standard command (`:Flow`) which launches a full-screen buffer in a new tab.

## 3. Interaction & Keybindings (Vim-Native)
* **Navigation:** `j/k` for movement. `zo/zc` or `TAB` for folding sections.
* **Search:** Standard Vim search (`/`) natively supported. Integrates with `Telescope`/`Snacks` for deeper filtering.
* **Execution:** Pressing `Enter` acts as the "Launchpad" action (starts context/timer).
* **Editing:** Users modify task descriptions by typing directly in the detail buffer. Saving the buffer (`:w`) commits the change to SQLite.
* **Visual Mode:** `v` highlights multiple items for bulk operations (e.g., changing priority).

## 4. Timers & Notifications
* **Active Timer:** Kept out of the main buffer. Injected into Neovim's `lualine` via API.
* **Global Controls:** Dedicated hotkeys allow toggling the timer without opening the dashboard.
