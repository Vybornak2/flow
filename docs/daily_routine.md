# Flow: The Daily Routine & Product Vision

## The Core Philosophy
Flow is designed to protect an engineer's "Deep Work" state. It achieves this by eliminating context fragmentation—bringing project management, time tracking, and Git workflows into a single, unified routine.

## Phase 1: The Morning Ritual (Planning)
**Goal:** Transition from a state of rest to a state of high-intent focus.
* **Unified View:** The dashboard aggregates Calendar events, assigned GitHub Issues, and local TODOs into one prioritized agenda.
* **The "Launchpad":** The core action of the morning. Selecting a task automatically sets up the environment (e.g., mapping to the correct directory) and starts the active timer, preventing untracked "leakage" time.
* **Intelligent Prioritization:** The engine assists in surfacing what matters most based on upcoming meetings and PR urgency.

## Phase 2: The Execution Phase (Deep Work)
**Goal:** Minimize context switching and protect the active workspace.
* **Active Tracking:** The engine silently monitors time spent, logging focus blocks and workspace events.
* **Soft Notifications:** Interruptions are minimized. Upcoming meetings or urgent PR reviews are surfaced via unobtrusive UI shifts (e.g., statusline colors) rather than jarring popups, unless absolutely necessary.
* **Seamless Operations:** Complex actions like commenting on issues or reviewing PRs can be handled directly from the terminal or editor buffer, keeping the engineer in their flow state.

## Phase 3: The Evening Wrap-up (Closure)
**Goal:** Cognitive offloading to ensure a clean break from work and a prepared start for tomorrow.
* **Guided Shutdown:** An iterative process that forces the user to review the day's active tasks.
* **Granularization:** Unfinished work must be broken down into sub-tasks or new GitHub issues. This prevents stale, massive tasks from carrying over indefinitely.
* **The "Daily Receipt":** The user is presented with a summary of their day: total time tracked, items closed, and an activity heatmap.

## Key Performance Indicators (The Engine's Metrics)
The system calculates specific metrics to help the user understand their working habits:
1. **Throughput:** Real-time tracking of PRs merged and issues closed.
2. **Focus Score:** A metric derived from uninterrupted coding blocks versus meeting density and context switches.
3. **Velocity:** A visual representation of commit frequency and lines of code (LOC) trends.
