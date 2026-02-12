# 🤖 Project Logic-Seed: The AI-to-AI Self-Bootstrapping Blueprint

[English | [中文](./README_ZH.md)]

> "In the age of AI, source code is no longer the final product. **Logic** is."

**Logic-Seed** is a **Zero-Code Delivery** protocol. You provide this blueprint to your AI Agent, and it **self-constructs** a world-class engineering team directly within your local environment.

---

## 🛠️ The LDV Workflow (Narrative over Review)

Instead of manual code review, Logic-Seed uses **Log-Driven Verification**:

```text
 [INPUT A/B] → [Implementation] → [LOGS] → [Junior Model]
      ↑               ↓             ↓            ↓
    Goal        Self-Explaining    Trace      Narrative (The Proof)
```

1.  **Senior** writes code that emits structured `[STEP]` logs.
2.  **Gemini** runs the code with multiple inputs (Normal/Edge).
3.  **Junior** reads the logs and **narrates** why results differ.
4.  **Truth** is found when the narration matches the Vision.

---

## 🚀 How to Initialize

Simply point your **AI Agent** (e.g., Gemini CLI) to this directory and say:

> **"Initialize the project according to [BLUEPRINT.md](./BLUEPRINT.md)."**

---

## 📋 Prerequisites

| Requirement | Purpose |
|---|---|
| **AI Agent** | Agent with file-access tools (e.g., Gemini CLI). |
| **tmux** | For persistent model sessions. |
| **ollama** | (Optional) For local lightweight models. |
| **python3** | The logic execution engine. |

---

## 🤝 Contributing & Safety

- **Contributing**: Submit PRs to improve `BLUEPRINT.md`.
- **Safety**: Code has local write access. Review plans before execution.

---
**Logic-Seed: The first software project that contains no code.**
*Licensed under MIT. Developed by Gemini & Claude AI.*
