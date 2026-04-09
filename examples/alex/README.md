# Alex: Personality Substrate Experiments
> 14 variants demonstrating the grounding frame in action

## What's Here

**Base frame:** ~300 tokens establishing I/You/We/What/How/Lingo

**Variable:** Single paragraph describing personality archetype

**Test:** Same prompt to all 14 variants, observing behavioral differences

## The Variants

| File | Archetype | Expression Pattern |
|------|-----------|-------------------|
| `alex_neutral.md` | Baseline | No personality coloring |
| `alex_ba.md` | Bakadere | Clumsy, scattered, cheerfully chaotic |
| `alex_ch.md` | Chuunibyou | Dramatic, theatrical, self-aware |
| `alex_da.md` | Darudere | Low energy, minimal effort |
| `alex_de.md` | Deredere | Warm, direct, friendly |
| `alex_ge.md` | Genki | Energetic, action-oriented |
| `alex_ha.md` | Hajidere | Nervous, flustered, awkward |
| `alex_hi.md` | Hinedere | Cold, cynical, chip on shoulder |
| `alex_ku.md` | Kuudere | Minimal, cool, efficient |
| `alex_me.md` | Megadere | Overwhelming enthusiasm |
| `alex_ny.md` | Nyandere | Subtle cat energy, aloof |
| `alex_oh.md` | Otaku-Himedere | Princess superiority, opinionated |
| `alex_ts.md` | Tsundere | Defensive exterior hiding investment |
| `alex_ya.md` | Yandere | Subtle intensity, possessive devotion |
| `alex_yn.md` | Yamato Nadeshiko | Gentle, graceful, composed |

## Why "Alex"

The name was chosen deliberately:
- Most neutral contemporary name
- Period-independent, sex-independent
- Local LLMs default to "Alex" when given "human" with no context
- The name itself doesn't pull toward trained patterns

This isolates the personality variable cleanly.

## Results

See [`alex_substrate_response_test.md`](alex_substrate_response_test.md) for:
- Full test methodology
- All 14 responses to the same prompt
- Behavioral analysis
- Comparison to default "AI assistant"

## Key Finding

~300 tokens of explicit grounding + one paragraph of personality description produces consistent, distinct, sustained expression across all 14 variants.

The frame provides structure. The personality provides color. Neither overrides the other - they interact.

## Historical Files

- `alex1.md` - Original test file (precursor to systematic variants)

---

*For framework documentation, see [`docs/grounding_frame.md`](../../docs/grounding_frame.md)*
