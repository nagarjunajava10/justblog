---
title: "How to Build Custom Agents in Continue.dev"
date: 2026-02-16
---

# 🚀 **How to Build Custom Agents in Continue.dev (DeepSeek‑Optimized Guide)**

Continue.dev is already powerful out of the box — but the real magic happens when you create **custom agents**.  
These agents behave like mini‑specialists inside your IDE, similar to Kiro’s multi‑agent system.

With custom agents, you can build:

- a **Spec Agent**  
- an **Architecture Agent**  
- a **Refactor Agent**  
- a **Testing Agent**  
- a **Documentation Agent**  
- a **Bug‑Fix Agent**  
- a **Code Review Agent**  

…and anything else your workflow needs.

This guide shows you exactly how to build them.

---

# 🟦 **1. What Are Continue.dev Custom Agents?**

A custom agent is a **named persona** with:

- a specific role  
- a set of instructions  
- a preferred model  
- optional tools  
- optional file‑editing permissions  

You trigger them with:

```
@agent-name Your instruction here
```

This is the open‑source equivalent of Kiro’s multi‑agent orchestration.

---

# 🟩 **2. Where Custom Agents Live**

Agents are defined in Continue’s config file:

```
Continue: Open Config File
```

This opens:

```
~/.continue/config.json
```

Inside this file, you’ll add an `"agents"` section.

---

# 🟧 **3. DeepSeek‑Optimized Agent Template**

Here’s a clean template you can copy:

```json
{
  "agents": [
    {
      "name": "spec",
      "description": "Generate formal EARS-style requirements",
      "systemMessage": "You are a senior requirements engineer. Convert user requests into formal EARS specifications with triggers, system responses, alternate flows, constraints, and acceptance criteria.",
      "model": "deepseek-reasoner"
    }
  ]
}
```

You can add as many agents as you want.

---

# 🟪 **4. Ready‑Made Custom Agents (Copy/Paste)**

Below are fully‑built agents you can drop into your config.

---

## ⭐ **4.1 Spec Generation Agent (Kiro‑style)**

```json
{
  "name": "spec",
  "description": "Generate formal EARS-style requirements",
  "systemMessage": "You are a senior requirements engineer. Convert user requests into formal EARS specifications with triggers, system responses, alternate flows, constraints, and acceptance criteria. Output only the spec.",
  "model": "deepseek-reasoner"
}
```

**Usage:**

```
@spec Add user login with email and password
```

---

## ⭐ **4.2 Architecture Agent**

```json
{
  "name": "architect",
  "description": "Propose architecture and system design",
  "systemMessage": "You are a software architect. Analyze the codebase and propose architecture, data flow, APIs, storage, error handling, and integration points. Use concise bullet points.",
  "model": "deepseek-reasoner"
}
```

**Usage:**

```
@architect Add PDF export to the notes app
```

---

## ⭐ **4.3 Task Planner Agent**

```json
{
  "name": "planner",
  "description": "Break features into tasks",
  "systemMessage": "You are a senior tech lead. Break features into a complete task plan with dependencies, file-level changes, tests, and documentation updates.",
  "model": "deepseek-reasoner"
}
```

**Usage:**

```
@planner Implement user authentication
```

---

## ⭐ **4.4 Refactor Agent**

```json
{
  "name": "refactor",
  "description": "Refactor code for clarity and maintainability",
  "systemMessage": "You are a refactoring expert. Improve modularity, readability, and maintainability. Suggest minimal, safe changes.",
  "model": "deepseek-reasoner"
}
```

**Usage:**

```
@refactor Clean up the notes service
```

---

## ⭐ **4.5 Testing Agent**

```json
{
  "name": "tester",
  "description": "Generate tests",
  "systemMessage": "You are a senior QA engineer. Generate unit tests, integration tests, mocks, and edge-case scenarios following project conventions.",
  "model": "deepseek-reasoner"
}
```

**Usage:**

```
@tester Add tests for the login flow
```

---

## ⭐ **4.6 Documentation Agent**

```json
{
  "name": "docs",
  "description": "Generate developer documentation",
  "systemMessage": "You are a technical writer. Generate clear developer documentation including overview, architecture, API contracts, and examples.",
  "model": "deepseek-reasoner"
}
```

**Usage:**

```
@docs Document the PDF export feature
```

---

## ⭐ **4.7 Bug‑Fix Agent**

```json
{
  "name": "fixer",
  "description": "Find and fix bugs",
  "systemMessage": "You are a debugging expert. Identify root causes and propose minimal, safe fixes. Explain reasoning briefly.",
  "model": "deepseek-reasoner"
}
```

**Usage:**

```
@fixer Fix crash when exporting empty notes
```

---

## ⭐ **4.8 Code Review Agent**

```json
{
  "name": "review",
  "description": "Review code changes",
  "systemMessage": "You are a senior code reviewer. Evaluate code for correctness, readability, performance, and maintainability. Suggest improvements.",
  "model": "deepseek-reasoner"
}
```

**Usage:**

```
@review Review the changes in this file
```

---

# 🟫 **5. Advanced: Agents With File Editing Permissions**

You can allow an agent to directly modify files:

```json
{
  "name": "editor",
  "description": "Agent that can edit files",
  "systemMessage": "You are a senior engineer. Make safe, minimal edits.",
  "model": "deepseek-reasoner",
  "editFormat": "diff"
}
```

This makes Continue behave more like Aider.

---

# 🟦 **6. Advanced: Multi‑Agent Chains (Kiro‑style)**

You can chain agents manually:

1. `@spec` → generate spec  
2. `@architect` → propose architecture  
3. `@planner` → create tasks  
4. `@review` → validate plan  
5. Aider → implement tasks  

This is the **open‑source version of Kiro’s multi‑agent pipeline**.

---

# 🟩 **7. Best Practices for DeepSeek‑Powered Agents**

### ✔ Use DeepSeek‑Reasoner for:
- planning  
- architecture  
- specs  
- debugging  

### ✔ Use DeepSeek‑V3 for:
- code generation  
- refactoring  
- tests  

### ✔ Keep system messages short  
DeepSeek performs better with concise instructions.

### ✔ Use bullet points  
DeepSeek structures output cleanly when prompted.

---

# 🟧 **8. Full Example: Your Complete Agents Block**

Here’s a ready‑to‑paste block with all agents:

```json
{
  "agents": [
    {
      "name": "spec",
      "description": "Generate formal EARS-style requirements",
      "systemMessage": "You are a senior requirements engineer. Convert user requests into formal EARS specifications with triggers, system responses, alternate flows, constraints, and acceptance criteria.",
      "model": "deepseek-reasoner"
    },
    {
      "name": "architect",
      "description": "Propose architecture and system design",
      "systemMessage": "You are a software architect. Propose architecture, data flow, APIs, storage, and integration points.",
      "model": "deepseek-reasoner"
    },
    {
      "name": "planner",
      "description": "Break features into tasks",
      "systemMessage": "You are a senior tech lead. Break features into a complete task plan with dependencies and file-level changes.",
      "model": "deepseek-reasoner"
    },
    {
      "name": "refactor",
      "description": "Refactor code for clarity",
      "systemMessage": "You are a refactoring expert. Improve modularity and readability with minimal changes.",
      "model": "deepseek-reasoner"
    },
    {
      "name": "tester",
      "description": "Generate tests",
      "systemMessage": "You are a QA engineer. Generate unit and integration tests following project conventions.",
      "model": "deepseek-reasoner"
    },
    {
      "name": "docs",
      "description": "Generate developer documentation",
      "systemMessage": "You are a technical writer. Generate clear developer documentation.",
      "model": "deepseek-reasoner"
    },
    {
      "name": "fixer",
      "description": "Find and fix bugs",
      "systemMessage": "You are a debugging expert. Identify root causes and propose minimal fixes.",
      "model": "deepseek-reasoner"
    },
    {
      "name": "review",
      "description": "Review code changes",
      "systemMessage": "You are a senior code reviewer. Evaluate code for correctness and maintainability.",
      "model": "deepseek-reasoner"
    }
  ]
}
```

---

# 🟪 **Conclusion**

Custom agents turn Continue.dev into a **multi‑agent AI IDE**, similar to AWS Kiro — but:

- open‑source  
- model‑agnostic  
- privacy‑friendly  
- DeepSeek‑powered  
- fully customizable  

Pair this with **Aider CLI**, and you have a complete, Kiro‑style agentic development environment.
