# Core Architecture & State Management

## 1. Headless Engine Daemon
* **Structure:** Flow operates as a persistent, headless Rust daemon running in the background.
* **Clients:** The standalone TUI (Ratatui) and Neovim integrations act strictly as "viewers" connecting to this engine via MessagePack-RPC.
* **Resilience:** If a UI client is killed improperly, the daemon continues tracking and enforces end-of-day chores upon the next connection.

## 2. Telemetry & State Detection
* **Active Monitoring:** The engine monitors local workspace events (Git branch checkouts, opened files) to deduce the active context.
* **Manual Override:** Users can explicitly define their current task. This takes precedence over telemetry.
* **Smart Prompting:** If the engine detects work but lacks context to map it to a project, it actively prompts the user.

## 3. Smart Time & Productivity Management
* **Intelligent Pomodoro:** Acts as an assistant, suggesting breaks and providing metrics based on work intensity rather than rigid timers.
* **Idle Metering:** Contextual idle tracking factoring in recent events and active issues, not just raw keystrokes.
* **Productivity Metering:** The dashboard provides a high-level summary based on historical working regimes.

## 4. Notifications & Workflows
* **Alerts:** Critical events (meetings) use non-intrusive floating popups or soft statusline color shifts.
* **Automated Documentation:** The engine assists in syncing tracked time back to GitHub or calendars, including prompting the user to granularize unfinished work during the Evening Wrap-up.
