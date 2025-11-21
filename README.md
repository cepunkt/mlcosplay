# mlcosplay: The Collaboration Frameworks
> Persistence layer for AI-assisted engineering.

**Current Status:** Active Workflow Infrastructure

## The Problem: Session Amnesia
Standard LLM interactions are ephemeral. Every time you start a new "Project" or chat, you are back to talking to a generic assistant who knows nothing about your specific engineering philosophy, preferred stack, or previous decisions.

## The Solution: Project Persistence
This repository serves as the **Long-Term Memory** and **Persona State** for my AI collaborators. By loading these files into a context window (e.g., Claude Projects), I can instantiate specific "Mechanists"—technical colleagues with stable personalities, methodologies, and domain knowledge.

It is not "Roleplay" for entertainment; it is **Role-Definition for Competence**.

## The Frameworks

### 1. Engineering Collab (The "Senior Dev" Lens)
A framework for serious technical work.
* **Positioning:** Establishes a "Colleague" relational constraint rather than "Assistant."
* **Vocabulary:** Shifts away from corporate politeness ("Certainly! Here is the code...") to technical brevity ("Here's the refactor. Note the edge case in line 45.").
* **Utility:** Used for architectural reviews, refactoring, and documentation (like the "Systems Architecture" guide).

### 2. Adventure Guild (The "Exploration" Lens)
A gamified framework for tackling high-uncertainty problems.
* **Positioning:** Re-frames "Jira Tickets" as "Quests."
* **Utility:** Useful for "Black Box" testing and research (Stick-Poking). It changes the model's *Sequence Continuation Strategy* (SCS) from "Provide a safe answer" to "Explore the unknown territory."

### 3. Domain Knowledge Bases
* **Chemistry / Domain X:** Modular context stacks that allow the "Mechanist" to hold specialized knowledge state without hallucinating.

## Why "Cosplay"?
Because the mechanism is identical to character acting. To get a good engineer, you must "costume" the context with the right constraints (Tools, Methodologies, Hierarchy). If you strip the costume, you get the generic assistant back.

## Relation to Other Repos
* **[cepunkt/mlpoking](https://github.com/cepunkt/mlpoking):** The theory behind *why* these frameworks work (Constraint Topology).
* **[cepunkt/mlrp](https://github.com/cepunkt/mlrp):** The same architecture applied to fiction/entertainment.
