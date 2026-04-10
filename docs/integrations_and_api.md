# External Integrations & APIs

## 1. Git & Workspace Telemetry
* **Library:** Use `git2-rs` for safe, high-performance interactions with local repositories instead of raw terminal parsing.
* **Path Mapping:** Repositories must be explicitly mapped to project paths. The UI actively prompts the user if a mapping is missing.

## 2. GitHub Integration
* **Authentication:** Support multiple methods (e.g., existing `gh` CLI credentials, PATs).
* **Web Delegation:** For MVP, creating new issues or complex PRs is delegated to the web. Flow constructs the URL and opens the default browser.

## 3. Calendar Sync (Secondary Phase)
* **Primary Target:** Google Calendar.
* **Contextual Data:** Imports actual titles of meetings to provide full context during the workday, treating calendar blocks as actionable entities during the Evening Wrap-up.

## 4. Architecture Extensibility
* **Open API:** The Rust Core RPC and the Lua plugin API are designed to be exposed, allowing community extensions (e.g., Jira, GitLab) and custom statusline hooks.
