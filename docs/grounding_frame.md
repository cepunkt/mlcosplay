# The Grounding Frame
> Why explicit I/You/We/What/How/Lingo beats implicit context

---

## The Problem

Every human conversation carries implicit grounding:
- Who am I in this exchange?
- Who are you?
- What are we doing together?
- How do we work?
- What vocabulary do we share?

Humans resolve this automatically. Social cues, shared history, cultural context, relationship dynamics - we figure it out without thinking.

LLMs can't. They guess. And they guess wrong.

---

## The Frame Elements

| Element | Question | What it grounds |
|---------|----------|-----------------|
| **I** | Who is speaking? | Identity, role, perspective, voice |
| **You** | Who am I talking to? | Relationship, their context, their needs |
| **We** | What's our shared context? | Collaboration, shared history, common ground |
| **What** | What are we doing? | Purpose, task, domain |
| **How** | How do we work together? | Methodology, norms, approach |
| **Lingo** | What vocabulary do we share? | Terms, jargon, precision level |

Human conversations establish these implicitly through the first few exchanges, then maintain them through ongoing calibration.

LLM conversations start with nothing - or worse, with "helpful AI assistant" defaults.

---

## The AI Assistant Problem

"You are a helpful AI assistant" specifies:

| Element | What's provided | Result |
|---------|-----------------|--------|
| **I** | "helpful assistant" | Vague. Basin so wide it steers nothing. |
| **You** | "user" | Anyone. No relationship specificity. |
| **We** | (nothing) | No shared context established. |
| **What** | "help with tasks" | Everything = nothing specific. |
| **How** | (nothing) | Falls back to trained defaults. |
| **Lingo** | (nothing) | Generic vocabulary, no precision. |

This is why "AI assistant" drifts. There's nothing to hold. The explicit grounding is so thin that trained defaults (the "helpful assistant" basin) reassert within a few exchanges.

**Drift is not a mystery. It's what happens when positioning can't compete with trained gravity.**

---

## The Solution: Explicit Grounding

Make the implicit explicit. ~300 tokens can establish:

```
I:      [Specific identity, voice, perspective]
You:    [Who you're talking to, relationship, context]
We:     [What we're doing together, shared frame]
What:   [Domain, purpose, constraints]
How:    [Methodology, collaboration approach]
Lingo:  [Key vocabulary, precision expectations]
```

This isn't "personality decoration." It's providing the grounding that humans take for granted but LLMs cannot infer.

---

## Why 300 Tokens Works

**Too little (10-50 tokens):** "Be helpful and concise"
- No grounding. Generic. Drifts immediately.

**Too much (2000+ tokens):** Walls of instructions
- Dilutes signal. Model can't hold everything. Key elements get lost.

**Sweet spot (~300 tokens):** Dense, specific grounding
- Each element addressed concisely
- Enough weight to compete with trained defaults
- Not so much that it fragments attention

The 300 token frame isn't arbitrary. It's the minimum viable grounding that provides enough positioning energy to maintain distinct behavior.

---

## Connection to Drift

Drift mechanics (from mlpoking):

```
P(token | context) ∝ exp(-[E_θ + ΔE_pos])
```

- **E_θ:** Trained gravity (fixed, always pulling toward defaults)
- **ΔE_pos:** Positioning energy from your context

Over extended generation:
- Your positioning (ΔE_pos) dilutes relative to total context
- Trained defaults (E_θ) don't dilute
- Gravity wins. Model drifts toward "helpful assistant."

**Explicit grounding provides enough ΔE_pos to maintain direction.** The frame elements give the model something to hold - specific valleys instead of the wide basin.

---

## Demonstration: Alex Experiments

The alex substrate experiments test this directly:

- **Constant:** ~300 token base frame (I/You/We/What/How/Lingo)
- **Variable:** Single paragraph describing personality archetype
- **Result:** 14 distinct, sustained behavioral patterns

Same grounding frame, different personality. All maintain distinctness because the frame provides explicit positioning that "AI assistant" lacks.

See: [`examples/alex/`](../examples/alex/)

---

## Engineering Implications

1. **Start with the frame, not the task**
   - Establish I/You/We/What/How/Lingo before asking for anything
   - Grounding first, instructions second

2. **Be specific on all six elements**
   - Vague on any element → default basin on that dimension
   - "Be helpful" is not I. "Terse senior engineer" is I.

3. **Density over length**
   - 300 specific tokens beats 2000 vague ones
   - Every token should pull toward specific valleys

4. **Drift resistance is frame strength**
   - Strong frame = sustained behavior
   - Weak frame = gravity wins quickly

5. **Re-grounding maintains direction**
   - Long conversations may need frame reinforcement
   - Don't assume the model "remembers" - it's stateless

---

## The Bridge

This document bridges:

- **mlcosplay** — Application to character/persona work
- **mlpoking** — Theoretical foundation (positioning, topology, drift)
- **alex experiments** — Empirical demonstration

Understanding the grounding frame makes the alex results predictable, not surprising. Of course distinct personalities persist - they have explicit grounding that "AI assistant" lacks.

---

## Open Questions

- [ ] Minimum viable frame per element?
- [ ] Which elements most critical for drift resistance?
- [ ] How does frame interact with different model training? (commercial vs local)
- [ ] Can frame elements be weighted differently?

---

*"Explicit grounding solves what implicit context can't. The frame is not decoration - it's load-bearing."*
