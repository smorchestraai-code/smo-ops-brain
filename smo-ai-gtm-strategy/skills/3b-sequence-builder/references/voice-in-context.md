# Voice-in-Context Generation (shared across 3b/3c/3d/3e)

## Principle
Voice conformance is built IN at generation time, not corrected after.

## Required Primary Context

### Brain files
- brand-voice.md, communication-style.md, language-preferences.md

### Voice samples (the truth)
- `references/voice-samples/*.md` - the founder's REAL content. Ground truth, not aspirational.

## Generation Prompt Pattern
```
VOICE TRUTH (primary): <voice samples>
VOICE RULES: tone, signature phrases (use these), forbidden phrases (NEVER), channel rules, language
BRAIN CONTEXT: offer, icp, positioning, testimonials (verified), faq-objections
SOURCE MAP: <per-element brain field citations>

Generate <asset>. Cite brain source per element in YAML frontmatter. INPUT-GAP for unsourced. NEVER invent.
```

## Channel-Specific Voice Rules

- Email: subject brand-voice tone, body founder voice, P.S. signature style
- WhatsApp: dialect, shorter, conversational, no email-formal tone, Khaleeji default for MENA
- LinkedIn: Track A (AR) vs Track B (EN), hook = first 7 words
- Landing: hero = positioning, sub-headlines = signature phrases, CTA = founder's actual phrasing

## Voice-fit Scoring (3f verifies)
Semantic similarity 0-10, signature phrase count, forbidden phrase violations (target=0), tone profile match. Floor 8.5.

## Anti-Patterns BANNED
1. Generating without voice samples primary
2. Voice rules as post-hoc filter only
3. Generic professional tone defaults
4. AI-isms (delve into, tapestry, etc.) - list in forbidden
5. English default without language-preferences check
6. Skipping channel-specific tone
