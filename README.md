# Academic English Writing

A reusable agent skill for polishing, diagnosing, drafting, and teaching academic English. It is designed for essays, research writing, literature reviews, abstracts, source integration, thesis statements, and ESL/EFL feedback.

The skill applies the paragraph-to-essay logic associated with Oshima and Hogue's *Writing Academic English*. It operationalizes that approach in original instructions and examples; it does not reproduce textbook passages or exercises.

## What It Does

Academic writing is treated as controlled meaning design, not decorative language. The skill checks a draft from global concerns to local ones:

1. **Controlling idea**: identify the topic sentence, thesis statement, or position claim.
2. **Unity and support**: ensure each paragraph develops one idea with relevant explanation, evidence, and analysis.
3. **Coherence and organization**: improve key-term repetition, pronoun reference, transitions, logical order, and the essay's governing pattern.
4. **Source discipline**: distinguish quotation, paraphrase, and summary; retain citation intent; never invent sources, data, quotations, or bibliographic details.
5. **Sentence control**: edit fragments, run-ons, comma splices, clause relationships, parallelism, punctuation, tone, and concision only after the argument works.

The framework supports logical-division, chronological/process, cause/effect, comparison/contrast, and argumentative essays. For substantial work, it separates developmental feedback from line editing so grammar corrections do not hide weaknesses in the thesis, evidence, or paragraph roles.

## Install In Codex

Install it as a personal skill by cloning this repository into Codex's skills directory. Restart Codex or begin a new session after installation.

```powershell
git clone https://github.com/Dagwbl/writing-academic-english.git "$HOME/.codex/skills/academic-english-writing"
```

To update an existing installation:

```powershell
git -C "$HOME/.codex/skills/academic-english-writing" pull
```

Codex discovers `SKILL.md` in that directory. The included `agents/openai.yaml` supplies its display name, description, and default prompt in Codex.

## Install In Claude Code

Claude Code can use the same `SKILL.md` skill directory. Choose one scope:

**Personal skill**, available across your projects:

```bash
git clone https://github.com/Dagwbl/writing-academic-english.git ~/.claude/skills/academic-english-writing
```

**Project skill**, available only in the current repository:

```bash
git clone https://github.com/Dagwbl/writing-academic-english.git .claude/skills/academic-english-writing
```

Restart Claude Code or start a new session once the directory is present. Claude Code uses the `SKILL.md` and `references/` files; the Codex-specific `agents/openai.yaml` is harmless and can remain in place.

## Use It

Invoke the skill explicitly when you want the full framework applied:

```text
Use $academic-english-writing to revise this draft. Preserve my meaning and citations, diagnose global issues before editing sentences, and give me a clean revised version followed by concise feedback.
```

Example requests:

```text
Use $academic-english-writing to evaluate whether this introduction has a defensible thesis and propose a revised paragraph plan.

Use $academic-english-writing to revise this literature-review paragraph. Keep its disciplinary terminology, flag unsupported claims, and use [citation needed] where source details are missing.

Use $academic-english-writing to turn these notes into a cause-and-effect essay outline with a focused thesis and body-paragraph topic sentences.

Use $academic-english-writing to explain the comma-splice errors in this paragraph, provide corrected examples, and give a reusable rule.
```

For Chinese-language requests, the skill provides feedback in Chinese and revised academic prose in English unless instructed otherwise.

## Expected Behavior

- Preserves the author's meaning, data, stance, disciplinary terminology, and citation intent.
- Uses light editing when the draft already works and developmental revision when the controlling idea, support, unity, or organization is weak.
- Leads with the changes that most affect the argument instead of burying them beneath grammar comments.
- Does not fabricate sources, findings, page numbers, statistics, quotations, methods, or references.
- Uses clear, precise academic English rather than inflated or unnecessarily complex prose.

## Repository Layout

- `SKILL.md`: trigger description, workflow, task routing, and output expectations.
- `references/academic-writing-framework.md`: detailed checklists for revision, teaching, drafting, organization patterns, source use, and sentence repair.
- `agents/openai.yaml`: Codex interface metadata.

## Limits

This skill improves writing quality and helps identify citation gaps, but it does not verify claims against external sources unless the agent is also asked to research them. Follow the assignment's required citation style and confirm any factual or source details that the draft does not provide.
