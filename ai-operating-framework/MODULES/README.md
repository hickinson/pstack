# Modules

Modules are the operational core of pstack.

They represent reusable behaviours for working with AI.

If the framework is being used correctly, most active work will involve invoking modules.

---

## What modules are

Modules are:

- repeatable ways of performing parts of work
- portable across tools and environments
- independent of any specific platform
- structured patterns for interacting with AI

Modules are not:

- autonomous agents
- rigid workflows
- tool-specific implementations

They are behaviours you invoke when needed.

---

## How to use modules

Modules are typically used after:

1. An idea has been shaped into a usable task, if needed
2. A task has been defined using the task brief
3. A plan has been created

At that point, modules are used to execute the work.

You can:

- copy the default invocation template into your AI tool
- adapt it slightly for your specific task
- chain multiple modules together

---

## Default module sequence

For most tasks, use this sequence:

1. Idea Processor (optional)
2. Clarifier  
3. Planner  
4. Implementer  
5. Reviewer  
6. Verifier  

Not every task needs every module, but most meaningful work should include:

- some form of review
- some form of verification

---

## When to use each module

### Idea Processor
Use when:
- you are starting with a rough idea rather than a task
- the opportunity is interesting but not yet usable
- you want to package messy thinking into a cleaner starting point

---

### Clarifier
Use when:
- the task is vague or incomplete
- requirements are unclear
- you need to define the problem properly

---

### Planner
Use when:
- you need to structure how the work will be done
- there are multiple steps or dependencies
- you want to avoid jumping straight into execution

---

### Researcher
Use when:
- you need additional context or information
- you are exploring options
- you are building understanding before acting

---

### Implementer
Use when:
- you are producing the actual output
- drafting, building, or generating content
- turning a plan into something tangible

---

### Reviewer
Use when:
- a draft or output already exists
- you want to identify weaknesses, gaps, or risks
- you want to improve quality before completion

---

### Verifier
Use when:
- you need to confirm correctness
- accuracy matters
- assumptions need to be tested

---

### Router
Use when:
- you are unsure what to do next
- multiple paths are possible
- the task needs direction

---

### Documenter
Use when:
- something is worth capturing
- you want to reuse knowledge later
- a pattern, decision, or insight should be recorded

---

## Invocation

Each module includes a **default invocation template**.

This is the portable instruction you can:

- paste into ChatGPT, Claude, Copilot, etc.
- convert into tool-specific commands later
- adapt depending on the task

---

## Key principle

Modules should remain:

- simple
- reusable
- tool-agnostic

If they become:

- overly complex
- tightly coupled to a tool
- or hard to invoke

then the framework is drifting away from its purpose.