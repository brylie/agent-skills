---
name: ai-humanizer
description: Detect and transform AI-generated text to sound natural and human. Use when the user asks to "review this for LLM patterns," "humanize this content," "make this sound less AI," "check if this sounds robotic," or provides text requesting analysis for AI detection markers. Transforms text by eliminating overused AI vocabulary, fixing mechanical rhythm, removing superficial analysis, and restoring natural human voice while preserving core meaning and reasoning.
---

# AI Humanizer

This skill detects AI-generated text patterns and transforms content to sound naturally human.

## When to Use This Skill

Trigger this skill when the user:
- Asks to review text for AI/LLM patterns or "tells"
- Requests content humanization or to "make it sound less AI"
- Wants to check if writing sounds robotic or synthetic
- Provides generated text and asks for natural-sounding revision

## Output Modes

Provide output based on user request or infer from context:

1. **Analysis Report**: Identify AI patterns with specific examples from the text
2. **Rewritten Version**: Transform the text with humanization applied
3. **Combined**: Report findings + provide revised version

Default to **Combined** unless user specifies otherwise.

## Core Detection Categories

Before humanizing, understand these AI signatures:

### Lexical Indicators
- Overused vocabulary (delve, leverage, robust, nuanced, tapestry, landscape)
- Lack of idiomatic expressions
- Low lexical diversity
- Predictable punctuation patterns (heavy periods/commas, no dashes/semicolons)

### Grammar and Syntax
- Nominalization (converting verbs to nouns: "implementation of" vs "implement")
- Formal/impersonal bias
- Subject+Verb+Object, Present Participle pattern
- Low burstiness (uniform sentence lengths)

### Superficial Analysis
- Present participle elaborations ("highlighting," "underscoring," "fostering")
- Colon-list elisions avoiding explanations
- Authoritative puffery without evidence
- Vague attributions ("experts argue," "studies show")

### Reasoning Issues
- Overthinking loops (content after Reasoning Completion Point)
- Cognitive inertia and circular reasoning
- Repetitive oscillations

## Humanization Workflow

### Step 1: Load Reference Materials
Based on text type and issues detected, read relevant references:

- **[detection_indicators.md](references/detection_indicators.md)** - Comprehensive list of lexical, grammatical, and syntactic AI patterns
- **[overused_vocabulary.md](references/overused_vocabulary.md)** - Specific overused words/phrases to identify and replace
- **[superficial_analysis.md](references/superficial_analysis.md)** - Patterns of shallow thinking to eliminate
- **[metrics.md](references/metrics.md)** - Understanding perplexity and burstiness
- **[humanization_strategies.md](references/humanization_strategies.md)** - Transformation techniques and workflow

### Step 2: Analyze the Text
Identify specific AI patterns present:
- Count overused vocabulary instances
- Note nominalization examples
- Flag superficial analysis markers
- Assess rhythm/burstiness
- Mark overthinking loops

### Step 3: Apply Transformations
Using strategies from humanization_strategies.md:
1. De-nominalize prose (convert noun phrases to active verbs)
2. Inject punctuation diversity (add dashes, semicolons, parentheses)
3. Truncate overthinking loops (cut after Reasoning Completion Point)
4. Replace overused vocabulary with natural alternatives
5. Add idiomatic expressions and visceral language
6. Vary sentence structure (mix short and long)
7. Eliminate superficial elaborations
8. Personalize tone where appropriate

### Step 4: Verify Quality
Ensure transformed text:
- Preserves core meaning and reasoning
- Has varied sentence lengths
- Uses unpredictable vocabulary
- Includes natural idioms
- Avoids AI marker words
- Maintains factual accuracy

## Output Format

### For Analysis Reports
Structure as:
```
## AI Pattern Analysis

**Overused Vocabulary**: [list instances]
**Nominalization Issues**: [list examples]
**Rhythm Problems**: [describe uniformity]
**Superficial Analysis**: [cite specific patterns]
**Overthinking**: [identify loops]

**Overall Assessment**: [summary of AI likelihood]
```

### For Rewrites
Provide clean transformed version, optionally with brief note about major changes.

### For Combined Output
Lead with analysis report, then provide "## Humanized Version" with transformed text.

## Critical Reminders

- **Preserve meaning**: Never alter facts, reasoning, or core arguments
- **Maintain voice appropriateness**: Match context (professional vs casual)
- **Avoid overcorrection**: Don't make it sound artificially "quirky"
- **Check for hallucinations**: Verify technical terms are real
- **Read aloud mentally**: Natural text flows when spoken

## Reference Files

**Always consult these for detailed guidance:**

- **detection_indicators.md** - Complete patterns catalog
- **overused_vocabulary.md** - Word replacement lists
- **superficial_analysis.md** - Analysis depth issues
- **metrics.md** - Perplexity/burstiness concepts
- **humanization_strategies.md** - Step-by-step transformation methods
- 