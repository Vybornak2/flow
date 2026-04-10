# Flow: The Engineer’s Command Center

!!! Warning "Early Development"
    This project is in active development. With no planned public release date.

[![Built with Rust](https://img.shields.io/badge/Built%20with-Rust-orange.svg)](https://www.rust-lang.org/)
[![Neovim Integration](https://img.shields.io/badge/Neovim-Native-green.svg)](https://neovim.io/)
[![Status: MVP Development](https://img.shields.io/badge/Status-Active_Development-blue.svg)]()

**Flow** is a unified workflow engine designed to protect a software engineer's "Deep Work" state. It eliminates context fragmentation by merging project management, Git workflows, calendar integration, and time tracking into a single, keyboard-centric routine.

---

## 🧠 The Philosophy: Protect Your Deep Work
Modern engineering is plagued by context switching. Checking a calendar, updating a Jira ticket, reviewing a PR, and tracking time usually requires 4 different web apps. Flow brings it all into your terminal and your editor, operating across three distinct phases of your day:

1. **The Morning Ritual (Planning):** A unified, intelligent dashboard that merges your calendar, GitHub Issues, and local TODOs so you can plan your day without opening a browser.
2. **The Execution Phase (Deep Work):** A seamless `gh` and Git wrapper. Start a task, and Flow automatically tracks your time, branch checkouts, and file activity while keeping notifications minimal.
3. **The Evening Wrap-up (Closure):** A guided shutdown routine that forces you to granularize unfinished work into actionable sub-tasks for tomorrow, giving you a daily receipt of your throughput and focus score.

---

## 🏗️ Architecture Overview
Flow is not just a Neovim plugin; it is a **Single Core, Dual Frontend** architecture built for speed and resilience.

* **Flow Core (Rust Daemon):** A background engine that manages a local-first SQLite database, API polling, and Git workspace telemetry.
* **Neovim Frontend:** A native editor experience using MessagePack-RPC to show active timers in your statusline and manage tasks directly inside code buffers.
* **Standalone TUI (Ratatui):** A dedicated, `btop`-inspired terminal dashboard for high-level planning and visual data tracking.

*Flow synchronizes state silently in the background using a Git-backed repository, ensuring seamless transition between your work and home machines.*

---

## 📚 Documentation
If you are looking to contribute or understand how Flow works under the hood, check out our comprehensive engineering specifications in the `docs/` folder:

* [**Core Architecture**](docs/architecture_core.md): The Rust daemon, state management, and telemetry.
* [**Data Models & Sync**](docs/data_schema_sync.md): SQLite schema, Git-backed syncing, and data retention.
* [**UI & Keybindings**](docs/ui_and_keybindings.md): Ratatui dashboard layouts, Neovim buffers, and Vim motions.
* [**External Integrations**](docs/integrations_and_api.md): `git2-rs`, GitHub API delegation, and Calendar sync.
* [**The Daily Routine**](docs/daily_routine.md): The product vision and Key Performance Indicators (KPIs).

---

## 🚀 Getting Started
*(Coming soon: Installation instructions for the Flow Core Daemon, Neovim Plugin, and Ratatui TUI).*

---

## 🤝 Contributing
Flow is built by developers, for developers. We welcome PRs for new sync providers, Neovim extensions, and TUI enhancements. Please read the documentation before submitting major architectural changes.

## 📄 License
MIT
