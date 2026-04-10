# Data Models & Sync Layer

## 1. Local-First Storage Strategy
* **Database:** SQLite is the single source of truth to guarantee zero latency.
* **Time-Series Compression:** Granular telemetry (file diffs, active branch times) is stored temporarily. After a set period, this raw data is automatically compressed into high-level metrics (e.g., "Total LOC: +400") to prevent database bloat.
* **On-Demand Caching:** External data (GitHub Issues) is not fully mirrored. Flow caches metadata (titles, status) for the dashboard and fetches full descriptions/comments only when the item is expanded.

## 2. Synchronization Strategy
* **Git-Backed Syncing:** The SQLite database (or a JSON dump of it) is synchronized using a standard Git repository. Flow silently handles `git pull` on startup and `git push` on shutdown.
* **Provider Agility:** The sync layer is pluggable, allowing future implementation of other backends (Supabase, iCloud).
* **Crash Recovery:** If the daemon is interrupted, it scans the workspace upon reboot and prompts the user to confirm what happened during the offline period.

## 3. Data Schema Guidelines
* **Tasks:** Must support a unified format capable of mapping to a GitHub Issue, a Calendar Event, or a Local TODO.
* **Telemetry Logs:** Must include a "Trigger Reason" (e.g., "Started timer because user switched to branch `feat-auth`") for transparency and debugging.
* **Strict Categorization:** Repositories, files, and issues map strictly (1:1) to a single designated "Project" by default.
