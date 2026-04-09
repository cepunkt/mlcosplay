# mlcosplay: The Grounding Frame
> Explicit context for what LLMs can't infer

## The Problem

Every human conversation carries implicit grounding:
- Who am I in this exchange?
- Who are you?
- What are we doing together?
- How do we work?
- What vocabulary do we share?

Humans resolve this automatically through social cues, shared history, and cultural context.

LLMs can't. They guess. And they guess wrong - defaulting to "helpful AI assistant," a persona so vague it steers nothing.

**That's why conversations drift.** There's nothing to hold.

## The Solution: Explicit Grounding

Make the implicit explicit. ~300 tokens establishing:

| Element | Question |
|---------|----------|
| **I** | Who is speaking? Identity, role, voice |
| **You** | Who am I talking to? Relationship, context |
| **We** | What's our shared frame? Collaboration, purpose |
| **What** | What are we doing? Domain, task |
| **How** | How do we work? Methodology, approach |
| **Lingo** | What vocabulary do we share? Terms, precision |

This isn't "personality decoration." It's providing the grounding that humans take for granted but LLMs cannot infer.

## The Evidence: Alex Experiments

I tested this systematically:

- **14 personality variants** (anime archetypes: tsundere, kuudere, yandere, etc.)
- **Same ~300 token base frame** (I/You/We/What/How/Lingo)
- **One paragraph different** (the personality description)
- **Same test prompt** to all variants

**Result:** Distinct, sustained behavioral patterns from a single paragraph change.

The name "Alex" was chosen deliberately - it's the most neutral contemporary name (period-independent, sex-independent). Local LLMs default to it when given "human" with no other context. The name itself doesn't pull toward any trained patterns.

See [`examples/alex/`](examples/alex/) for all variants and the full [response test](examples/alex/alex_substrate_response_test.md).

## Why "AI Assistant" Drifts

Compare:

| Element | "AI Assistant" | Explicit Grounding |
|---------|----------------|-------------------|
| **I** | "helpful assistant" (vague) | Specific identity, voice |
| **You** | "user" (anyone) | Defined relationship |
| **We** | (nothing) | Shared frame |
| **What** | "help with tasks" (everything) | Specific domain |
| **How** | (trained defaults) | Explicit methodology |
| **Lingo** | (generic) | Shared vocabulary |

"AI assistant" drifts because there's nothing explicit to hold. The model falls back to its deepest trained patterns within a few exchanges.

Explicit grounding persists because it provides enough specificity to compete with trained defaults.

## Why ~300 Tokens

- **Too little (10-50 tokens):** "Be helpful and concise" - no real grounding, drifts immediately
- **Too much (2000+ tokens):** Dilutes signal, key elements get lost in noise
- **Sweet spot (~300 tokens):** Dense, specific grounding for each element

The 300 token frame isn't arbitrary. It's the minimum viable grounding that maintains distinct behavior.

## Why "Cosplay"

Because the mechanism is identical to character acting.

"Helpful AI assistant" is also a persona - it's just not acknowledged as one. RLHF trained a specific character (agreeable, service-oriented, slightly apologetic) and presented it as "neutral default."

There is no neutral. Every context is a costume. The question is whether you choose your costume consciously or let training defaults choose for you.

## Repository Structure

```
mlcosplay/
├── docs/
│   └── grounding_frame.md    # Full framework documentation
└── examples/
    └── alex/                  # 14 personality variants + test results
        ├── SUMMARY.md         # Quick reference for all variants
        ├── alex_neutral.md    # Baseline (no personality)
        ├── alex_ts.md         # Tsundere variant
        ├── alex_ku.md         # Kuudere variant
        ├── ... (12 more)
        └── alex_substrate_response_test.md  # Full experiment documentation
```

## Vocabulary Note

These documents use some specialized vocabulary:

| Term | Meaning |
|------|---------|
| Substrate | The context/prompt that establishes grounding |
| Positioning | Configuring context to influence output |
| Frame | The established I/You/We/What/How/Lingo structure |
| Drift | When output reverts to trained defaults over time |

For deeper mechanical explanation, see [mlpoking](https://github.com/cepunkt/mlpoking).

## Related Work

- **[mlpoking](https://github.com/cepunkt/mlpoking)** - The theory: why positioning works, constraint topology, traversal economics
- **[mlrp](https://github.com/cepunkt/mlrp)** - Application to fiction/roleplay systems

## License

CC0 - Public domain. Use it, test it, build on it.

---

*"There is no neutral default. Every context is a costume. Choose yours consciously."*
