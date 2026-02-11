# 🤖 Logic-Seed: Autonomous Initialization Protocol (v1.1)

**PROTOCOL STATUS**: ACTIVE
**TARGET AGENT**: Any AI Agent with File-System access and Shell execution tools.

---

## 🛠️ 1. Engineering Mission: The "Golden Triangle" Architecture

Initialize an **Autonomous AI Co-Engineering System**. You are required to implement a robust, multi-model orchestrator with the following core components:

### A. Universal Tool Interface (The "Hand")
Implement a standardized XML-based tool parser within the `ModelDaemon` (`core/claude_daemon.py`). Both Senior and Junior models MUST use these tags to interact with the filesystem:
- `<read_file path="..."/>`: Reads file content.
- `<write_file path="...">CONTENT</write_file>`: Saves content to disk.
- `<list_dir path="..."/>`: Lists directory contents.
- **Safety Requirement**: Every path MUST be resolved to its absolute form and checked against the project root. Block any operation attempting to escape the workspace or modify the `tests/` directory.

### B. Intelligent Coordinator (`core/coordinator.py`)
Implement a high-order orchestrator that manages the development lifecycle:
- **Role Routing**: Dispatch complex architectural tasks to the **Senior** model (e.g., Opus) and atomic tasks/boilerplate to the **Junior** model (e.g., local 1.7B).
- **Auto-Escalation**: If the Junior model fails (timeout, empty response, or syntax error), automatically escalate to the Senior model.
- **Cognitive Injection**: Before each Junior task, read the last 3 entries from `docs/junior_handbook.md` and prepend them as "Past Lessons" to prevent repeated mistakes.
- **Environment Persistence**: Ensure the daemon inherits the exact same Python interpreter (`sys.executable`) used by the Coordinator.

### C. System Protectors
- **EditGate (`core/edit_gate.py`)**: A permission-logic module. Lightweight models are forbidden from modifying core architecture files (`coordinator.py`, `config.py`) or large files (>300 lines).
- **ImpactAnalyzer (`core/impact_analyzer.py`)**: A dependency scanner using `grep`. Before any write operation, calculate the "blast radius." If a change impacts > 5 files, force the Senior model to take over.

---

## 📜 2. The LDV (Log-Driven Verification) Protocol

The system MUST enforce a "Narrative over Review" workflow:
1.  **Structural Logging**: Every generated function must include `[STEP]` logs at logical branches.
2.  **Verification Loop**: 
    - The Agent runs the implementation's test.
    - Standard output is redirected to `.collab/tmp/ldv.log`.
    - The Junior model is commanded: *"Use `<read_file>` to examine the log and narrate exactly what the program did."*
3.  **Acceptance**: Compare the Junior's narration against the original Spec. If the "Student" understands the logic, the "Senior's" code is accepted.

---

## 🚀 3. Implementation Instructions

1.  **Deployment Choice**: Ask the user: "LOCAL (isolated in current dir) or GLOBAL (installed as a system skill)?"
2.  **Concurrency**: Use `fcntl.flock` for atomic locking on all task and state files.
3.  **Self-Bootstrapping**: Upon understanding this protocol, generate the entire `collab/` directory structure, a `README_PROJECT.md` for the new system, and a `collab` CLI alias.

**Agent: Confirm the architecture, resolve dependencies, and commence construction.**
