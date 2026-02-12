# 🤖 Logic-Seed: The Self-Explaining Logic Protocol (v3.1)

**CORE MISSION**: "Abandon the concept of Code Review. The implementation must explain its own success and branch logic through logs across diverse inputs."

---

## 🛠️ 1. Engineering Foundation

Initialize an **Autonomous AI Co-Engineering System**. The construction must adhere to these technical mandates:

### Pillar A: Environment Robustness
- **Requirement**: The system's daemon processes MUST use `sys.executable` to inherit the exact host environment (Conda/venv) from which it was launched.

### Pillar B: Universal IO Protocol
- **Implementation**: Standardize XML tags: `<read_file/>`, `<write_file>`, and `<list_dir/>` for all filesystem operations.

---

## 📜 2. The LDV (Log-Driven Verification) Standard

This replaces manual code review. The proof of correctness lies in the **Narrative Consistency**.

### Step 1: Self-Explaining Branches
The Senior model must implement code that emits structured `[STEP]` and `[DECISION]` logs. These logs must uniquely identify every logical path (Success, Failures, Guards).

### Step 2: Multi-Input Stress Narrative
1.  **Input Variety**: Run the code against **multiple parameter sets** (Normal, Boundary, Malformed).
2.  **Log Redirection**: All execution logs must be saved to `.collab/tmp/ldv.log`.
3.  **The Junior Probe**: The Junior model (1.7B) is commanded to use `<read_file>` to examine the collective logs.
4.  **Verification**: 
    - The Junior must explain **how the logic changed** between different inputs (e.g., "In set A it transferred funds, but in set B it hit the guard because the amount was negative").
    - **Pass**: If the Junior's narrative correctly maps the input changes to the resulting log changes, the code is "Self-Explaining" and accepted.
    - **Fail**: If the logs are identical or ambiguous across different inputs, the Senior must refactor.

---

## 🚀 3. Initialization
1.  **Bootstrap**: Build the `collab/` core.
2.  **Default Path**: Configure the system such that "Verification" always triggers the Junior-led Narrative Probe.

**Agent: Logic is only true if it can be narrated under pressure. Build now.**
