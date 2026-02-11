# 🤖 Project Logic-Seed: The AI-to-AI Self-Bootstrapping Blueprint

> **Concept**: Don't ship code. Ship the *logic* to let an AI build the code locally.

This blueprint allows any user with a **Gemini-class Agent** to bootstrap a world-class AI engineering team (Architect + Senior + Junior) on their local machine.

---

## 🧠 1. The Core Philosophy

### The Golden Triangle (3-AI Team)
1.  **Architect & QA (Gemini Agent)**: Manages requirements, writes tests, and enforces the "Security Gates."
2.  **Senior Developer (Claude Opus)**: Handles complex logic, architecture debates, and high-risk refactoring.
3.  **Junior Intern (Local Lightweight Model)**: Handles boilerplate, simple utilities, and documentation.

### LDV (Log-Driven Verification)
Instead of manual reviews, we use **Narrative Testing**.
- **Rule**: Code must be "Self-Explaining."
- **Proof**: If the Junior Intern can read the execution logs and correctly narrate what the program did, the code is "Clean." If the Intern is confused, the Senior must refactor.

---

## 🛠️ 2. The Bootstrap Instructions

### ⚖️ Deployment Choice (System vs. User)
Before proceeding, decide how you want to deploy your AI team:
- **User-level (Recommended)**: Keeps the system isolated within your current project directory (`./collab`). Safer, portable, and requires no administrative privileges.
- **System-level**: Installs the tools globally (e.g., in `~/.local/bin`), making the `collab` command available in every terminal.

To build this system, paste the following prompt into your **AI Agent**:

### [BOOTSTRAP PROMPT]
> "I want to build an **Autonomous AI Co-Engineering System**. 
> **DEPLOYMENT MODE**: [User: Please specify 'LOCAL' or 'GLOBAL' here]
> 
> Please implement the following 3 core components in a `collab/` directory:
>
> 1. **ModelDaemon**: A Python class that manages a persistent `claude` session in `tmux` (via Unix Sockets) and a local `ollama` instance. It must support `Native Write` (parsing `<write_file>` tags) and `Native Read` (for LDV).
> 2. **Coordinator**: An orchestrator that routes tasks between 'Senior' and 'Junior' models. It must implement **Auto-Escalation** (if Junior fails, Senior takes over) and **Lesson Recording** (saving errors to a `junior_handbook.md`).
> 3. **The Guards**: Implement an `EditGate` to restrict Junior from core files, and an `ImpactAnalyzer` using `grep` to calculate the blast radius of changes before execution.
>
> **Requirements**:
> - Use strict OOP and include a `__version__ = "1.0"` attribute in `coordinator.py`.
> - Inherit the current Conda/venv environment using `sys.executable`.
> - Use user-specific sockets in `/tmp/` to prevent collisions.
> - Implement an atomic file lock using `fcntl.flock` for the task management system.
> - **Configuration**: If GLOBAL mode is chosen, generate a setup script to add the `collab` alias to my shell config."

---

## 🚦 3. The LDV Workflow (How to work)

Once your system is built, follow this protocol for every feature:

1.  **Red Phase**: You (Gemini) write a test `tests/test_xxx.py`.
2.  **Execution**: Run the test and redirect logs to `.collab/tmp/ldv.log`.
3.  **Narrative Check**: Ask the Intern: `"Read .collab/tmp/ldv.log and tell me exactly what happened."`
4.  **DoD**: If the Intern's story matches your Spec, the task is **DONE**.

---

## 🆙 4. How to Upgrade
Logic-Seed is a living blueprint. When a new version is released:
1.  **Logical Patching**: Instead of re-bootstrapping, feed the new blueprint instructions to your Agent and say: *"Based on my current `collab/` code (v1.0), apply these logic updates to reach vX.X."*
2.  **Surgical Update**: Your Agent will surgically update your local implementation while preserving your custom configurations and environment.

---

## 📂 Project Management
- **Security Gate**: Always check `Impact Analysis` before modifying files.
- **Continuous Evolution**: After every task, ask your Senior model: `"What is one generic engineering principle we learned here?"` and save it to your core memory.

---
**Core Mandate: Code? Ask Claude. Logic? Ask the Logs. Architecture? Debate.**
