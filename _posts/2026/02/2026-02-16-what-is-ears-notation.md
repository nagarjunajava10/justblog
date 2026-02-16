---
title: "What is EARS notation (Easy Approach to Requirements Syntax)"
date: 2026-02-16
---

# 📘 **EARS Notation Explained for Beginners: A Simple Guide to Writing Clear Software Requirements**

Modern software development is full of ambiguity.  
Developers interpret requirements differently, product managers write them inconsistently, and AI agents often struggle when instructions are vague.

This is where **EARS notation** comes in.

**EARS** stands for **Easy Approach to Requirements Syntax** — a lightweight, structured way to write requirements that are:

- clear  
- testable  
- unambiguous  
- easy for humans and AI to understand  

It’s used in industries like aerospace, automotive, and now increasingly in AI‑assisted development tools such as **AWS Kiro**.  
If you’re building AI‑driven workflows with **Continue.dev**, **Aider**, or **DeepSeek**, EARS can dramatically improve the quality of your specs.

This article explains EARS in the simplest possible way, with examples you can use immediately.

---

# 🟦 **Why EARS Matters in AI‑Driven Development**

AI coding agents — whether in Kiro, Continue.dev, Aider, or OpenCode — perform best when instructions are:

- structured  
- explicit  
- free of ambiguity  

EARS gives you exactly that.

When you write requirements in EARS:

- AI agents can break tasks down more accurately  
- multi‑file edits become safer  
- architecture decisions become clearer  
- tests can be generated automatically  
- bugs caused by misinterpretation are reduced  

This is why Kiro uses EARS automatically — and why you can replicate the same clarity in Continue.dev using custom agents.

---

# 🟩 **The 5 Core EARS Patterns (With Simple Examples)**

EARS defines a small set of templates for different types of system behavior.  
Each template is easy to learn and easy to apply.

Let’s walk through them.

---

## **1. Ubiquitous Requirements**  
Used when the system must *always* behave a certain way.

**Pattern:**  
```
The system shall <response>.
```

**Example:**  
```
The system shall encrypt all stored user data.
```

This is the simplest EARS pattern.

---

## **2. Event‑Driven Requirements**  
Used when something happens and the system must respond.

**Pattern:**  
```
When <trigger>, the system shall <response>.
```

**Example:**  
```
When the user clicks “Export Notes”, the system shall generate a PDF.
```

This is the most common pattern in interactive applications.

---

## **3. State‑Driven Requirements**  
Used when the system is in a particular state.

**Pattern:**  
```
While <state>, the system shall <response>.
```

**Example:**  
```
While the user is offline, the system shall queue sync operations.
```

This is useful for background processes or conditional behavior.

---

## **4. Optional Feature Requirements**  
Used when a feature is enabled or configured.

**Pattern:**  
```
Where <feature is enabled>, the system shall <response>.
```

**Example:**  
```
Where dark mode is enabled, the system shall use the dark color palette.
```

This pattern is perfect for feature flags.

---

## **5. Unwanted Behavior Requirements**  
Used to describe how the system should handle errors or invalid conditions.

**Pattern:**  
```
If <undesired condition>, the system shall <response>.
```

**Example:**  
```
If the login credentials are invalid, the system shall show an error message.
```

This pattern is ideal for error handling and validation.

---

# 🟧 **Putting It All Together: A Full EARS Example**

Let’s take a simple feature request:

> “Add user login with email and password.”

A complete EARS‑style requirement might look like this:

```
Requirement: User Authentication

When the user submits valid email and password,
The system shall authenticate the user
And redirect them to the dashboard.

If the credentials are invalid,
The system shall show an error message.

The system shall log all authentication attempts.

Where multi-factor authentication is enabled,
The system shall prompt the user for a verification code.
```

This is exactly the kind of structured spec that AI agents — and human developers — can work with confidently.

---

# 🟪 **How EARS Helps in Continue.dev + Aider Workflows**

If you’re using **Continue.dev** and **Aider CLI** with **DeepSeek**, EARS becomes a superpower.

### ✔ Continue.dev  
Use EARS to generate:

- specs  
- architecture  
- task plans  
- file impact analysis  

### ✔ Aider CLI  
Use EARS to implement:

- multi‑file changes  
- refactors  
- error handling  
- tests  

### ✔ DeepSeek  
DeepSeek models excel at:

- structured reasoning  
- spec interpretation  
- task planning  
- code generation  

EARS gives DeepSeek the clarity it needs to perform at its best.

---

# 🟫 **How to Ask Continue.dev to Generate EARS Specs**

Use this prompt:

```
Convert the following feature request into a formal EARS-style requirement. 
Include triggers, system responses, alternate flows, constraints, and acceptance criteria.

Feature request:
[YOUR FEATURE]
```

This replicates Kiro’s automatic spec generation.

---

# 🟦 **Why EARS Is Perfect for Beginners**

EARS is:

- simple  
- intuitive  
- easy to learn  
- easy to apply  
- powerful enough for complex systems  

You don’t need to be a requirements engineer.  
You don’t need UML diagrams.  
You don’t need heavy documentation tools.

Just follow the templates.

---

# 🟩 **Conclusion**

EARS notation is one of the simplest and most effective ways to write clear, testable, AI‑friendly software requirements.  
Whether you’re using AWS Kiro or building your own open‑source workflow with Continue.dev + Aider + DeepSeek, EARS helps you:

- reduce ambiguity  
- improve planning  
- generate better code  
- create better tests  
- collaborate more effectively  

It’s a small investment that pays off massively in clarity and productivity.
