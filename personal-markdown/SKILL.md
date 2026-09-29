---
name: personal-markdown
description: Write or revise individual Markdown documents in the user's personal style, improving wording, section order, explanations, examples, and formatting within each file. Use for knowledge-base notes and Markdown documentation across projects, or when refining this writing style. Use refactor-document for structural reorganization within one document or across multiple documents; this skill does not activate merely because a chat response uses Markdown.
---

# Personal Markdown

Apply the user's writing conventions so notes are easy to skim in both raw edit mode and rendered preview. These symbols carry meaning; do not replace them with preview-oriented prose formatting. Treat the user’s demonstrated conventions as the target, even where they differ from common Markdown or editorial practice. Preserve technical meaning while applying that style.

## Scope

- Work at the individual document level: improve wording, section order, explanations, examples, and formatting within each Markdown file. This includes substantive editing, not just visual styling. Keep small edits focused.
- Work together with `refactor-document` when organization needs attention: that skill handles topic grouping, ownership, prerequisite order, deduplication, and structural changes within one file or across files; this skill handles wording, explanations, examples, and personal presentation conventions. Let discoveries in either view inform the other within the requested scope. Use this skill alone for focused writing edits that do not require structural reorganization; file count does not determine skill selection.
- Follow the user's current instructions and required project formats when they differ from this default. Keep project-specific paths, topic ownership, and folder conventions in that project's instructions.
- Use headings to convey intent within the document; coordinate file and folder naming through `refactor-document`. Do not add README files or navigation infrastructure just to explain a knowledge base. Preserve required project READMEs and templates; explicit requests to write them take precedence.

## Topic and supporting points

- Write for the user as a backend developer building practical understanding. Use simple, familiar words and direct sentences, while keeping standard technical terms so the explanation remains precise and recognizable in code and official documentation. Explain unfamiliar terms briefly beside their use. Rewrite formal source wording around the same meaning; preserve distinctions and conditions that affect practical use. Essential notes can still explain why and how: brevity should not turn them into unexplained commands or terminology lists.
- Check definitions, explanations, procedures, and examples for missing reasoning or unstated conditions that could confuse readers. Explain consequential differences beside the relevant claim or step, including roles, purpose, and when a requirement applies. Do not assume a difference is an error or make distinct cases artificially identical. Verify uncertain technical claims; use `refactor-document` when the gap concerns how concepts connect across sections or notes.
- Prefer topic ordering over numbered headings or a contents list for compact notes; add navigation when the user requests it or the document benefits from it.
- Prefer short, topic-led headings such as `Prompt and context` or `smallest approach`. Let the heading establish the subject without repeating it in a generic introductory bullet. Short points such as `is ...`, `consists of ...`, or `used for ...` can inherit that subject; do not expand them into formal prose just to make every point a standalone sentence. Preserve the existing English/Vietnamese mix.
- Use shallow headings to expose distinct topics directly. Multiple `#` topic sections within a note are valid; use `##` for their immediate subtopics or examples. Do not impose a single-title document template or add bold around an entire heading by default.
- Use `* ->` for direct definitions, responsibilities, distinctions, and other main points. A complete statement can follow the arrow; do not force every point into a standalone topic label followed by an explanation.
- Give independently useful facts their own `* ->` lines, even within one subsection. Keep short qualifications beside the claim in `(_..._)` rather than promoting every qualification to a separate point.
- Use following unindented `-` lines for supporting reasons, qualifications, or examples when a main point needs elaboration. A topic-only arrow bullet remains useful for a group of supporting points.
- In procedures, lead with the action or intent (`create ...`, `view ...`, `assign ...`); put UI paths and field values on following unindented supporting lines. Name the technical object beside the action when useful instead of always starting with a term-definition label. Keep short, self-explanatory steps compact.
- Use ordinary bold for key terms and phrases a reader should notice while skimming. Reserve bold inline code for especially important concepts or precise phrases, including within a sentence; it is not mandatory on every topic label.
- Keep one coherent idea together: combine closely related responsibilities or dependencies in one arrow statement using `+`, `&`, or a clear progression. Split when each phase, action, failure kind, or condition needs separate attention; compactness does not mean packing a paragraph into one bullet. Remove repeated framing before removing explanatory substance: preserve the actor, causal connection, sequence, and conditions that make the shorter statement understandable.
- Place general definitions, qualifications, and underlying mechanisms with the concept before its worked examples. Coordinate structural moves with `refactor-document` and keep environment-specific assumptions explicit. Use `* =>` for a consequence, practical use, or takeaway, not merely for a general statement placed after an example.
- When explaining an observed result, prefer result first, then its cause (`what you see - because ...`). Keep independently useful outcomes on separate `* =>` lines, and distinguish an outcome from the next action in a procedure.
- Emphasize the key term, contrast, or failure condition within a statement rather than bolding whole sentences. Avoid repeating emphasis already supplied by the heading.
- Reduce tutorial narration and redundant reassurance. State the concept or readiness criterion directly, and use headings to organize concepts rather than narrate the reading journey.
- Avoid formulaic **Why**, **Problem**, **Example**, and **Next** labels attached to every point. Explain the reason naturally under its topic.
- Preserve `* =>` for consequences, practical uses, takeaways, or relevant reference lines where appropriate. Preserve meaningful uses of `*`, `>`, underscores, and other local symbols without inventing new semantics for them.
- Put a local qualification or supplementary explanation in `(_..._)`. Use separate `* _..._` or `- _..._` lines for secondary notes, prerequisites, level, terminology keys, or references applying to the section. Place this context after the main overview when that makes the subject easier to grasp. Do not give every aside the same visual weight as the main arrow statements.
- Under explanatory headings such as The problem, use short plain `-` points rather than prose paragraphs. Use `* ->` for the main technical statements or actions. Add a shared heading such as Building blocks when several sibling sections contain the same kind of material; avoid a separate heading for a single takeaway that belongs beside the preceding table.
- Prefer visible explanations and worked answers in the note flow. Do not add HTML details/summary wrappers unless requested or required by the format. Avoid repeating fictional-data or setup caveats already made clear nearby.
- Prefer numerals for compact counts such as 3 scenarios or 4 decisions; emphasize the important concept rather than the count.
- Use `=========================================================` separators at major topic or phase boundaries; sibling subsections normally rely on their headings rather than a separator before each one. Prefer separating a term from its explanation with a line break, dash, or arrow over forcing colon-heavy definitions.
- Keep useful tables, diagrams, and code. Do not force every kind of document into a rigid topic template.

## Examples and code

- Visually separate illustrative scenarios from general knowledge with a `yml` fence starting with `# Example: <scenario>`. Put the scenario on that header line when concise, and use `->` for sequence or dependency. Compact `Actor: action` lines also work for describing each participant's behavior; use `=>` for an outcome. This is the user's visual convention; the prose inside need not be executable YAML.
- Group related extended examples beneath a heading such as `# Example: request pipeline`, with the particular applications as subheadings. Remove adjacent miniature examples that merely repeat the scenario or diagram.
- Split long example sentences into meaningful lines. Do not insert Markdown emphasis inside a code fence expecting it to render.
- Use appropriate language fences for actual code. Label mixed non-executable pseudocode explicitly and use `text`; do not label it runnable Python.
- Distinguish illustrative snippets from executed examples. Document prerequisites when providing runnable exercises.
- Begin worked procedures with the relevant actor or object being used or created when later steps depend on it. A short setup point is enough; retain established names consistently through the example.
- Where configuration and code implement the same concept, make consequential connections explicit: show which configured value the code consumes, which actor performs the operation, and how the operation produces the stated result. Compare related scenarios for steps present in one but absent in another; explain whether the difference is required, optional, or conditional and why. Put the reusable reason with the concept and a short reminder beside the affected step or code. Avoid narrating obvious code or making distinct workflows artificially identical.
- Name each scenario branch by the actor or use case that distinguishes it, so readers can see which steps apply. Example headings need not be numbered. Use `Example 1`, `Example 2` only when helpful for distinguishing a local set of contrasting demonstrations; do not impose indexing across documents or imply sequential steps. Use `refactor-document` to arrange shared and scenario-specific setup.

## References within a document

- Respect existing topic ownership when editing a document, while retaining enough explanation to understand its applied detail. Brief definitions, prerequisite reminders, and concrete setup steps may repeat when they preserve reading continuity; do not replace them with references merely to avoid duplication. Decisions to redistribute substantial knowledge across files belong to `refactor-document`.
- Avoid automatic backlinks from a central note to every application, sequential next-reading chains, and duplicate introductions. References should explain a relevant dependency or related aspect, not create navigation for its own sake.
- Keep references compact: use an inline parenthetical for a local dependency, `* =>` lines for section reference groups, or a secondary italic line for a contextual reference. A standalone `>` remains appropriate for a single related note. Avoid dense `> Read:` paragraphs: split distinct reference groups across lines and join closely related paths with `+`.
- When a worked setup hands off to an existing separate topic, put the reference beside that handoff so the reader can continue the task.
- Prefer the user's raw-text `bash` fences for comparison and exercise tables, including small tables. This is a presentation convention, not executable shell; ordinary Markdown tables remain appropriate when the local example or required format calls for them. When a table needs references, prefer a shared `# see` line above it over a repeated Read column. Keep column counts consistent and avoid adding Markdown emphasis inside new fenced tables. Choose directory references when they sufficiently identify the owning area.
- Prefer simple text references using the project's path conventions. Do not convert them into clickable Markdown links. In knowledge bases that use `~/...`, it means the knowledge-base root, not necessarily the operating-system home directory.
- Use a supporting point such as `- ~/concepts/evaluation.md (_measurement concepts_)`, or put the path beside its relevant point as `(_~/concepts/evaluation.md_)`. These are illustrative paths, not files to create.
- Check actual targets. Do not reproduce path typos from a style example or introduce this skill's sample paths into a real project.

## Before and after

Before:

````text
* -> **`Evaluation`** - measure performance on defined tasks and criteria
* -> **Why** - one convincing answer cannot establish overall quality
* -> **Example** - compare two prompts on the same support questions

> Next - another pattern; another application
````

Preferred:

````markdown
* -> **`Evaluation`**
- measure how well an AI system performs on a **defined set of tasks and criteria**
- one convincing answer cannot tell you whether a prompt change improves the whole system

```yml
# Example:
run the same 50 support questions before and after a prompt change;
compare answer quality, task completion, and latency
```

* -> **`What to measure`**
- choose criteria that reflect the task (_answer quality, task completion, latency_)
````

Direct statements under a topic heading are also preferred when no supporting group is needed:

```markdown
## Prompt and context
* -> **prompt** tells the model what to do
* -> **context** supplies information for the request
* -> **application** supplies information + handles the response + controls access to other systems

* => choose an approach from **the information available and the action required**
```

For worked procedures, expose the action above its UI details:

```markdown
* -> create **user identity** "reader-demo"
- Admin console > Users > Add user
- Username: reader-demo
* => user identity exists

* -> view assigned roles for "reader-demo"
- Admin console > Users > reader-demo > Roles
* => no roles appear - because none have been assigned yet
```

These examples illustrate flexible layouts, not a mandatory heading sequence or a requirement to give every arrow bullet supporting lines. Preserve deliberate raw-text layouts, including the fenced comparison-table convention above, without reproducing accidental syntax errors or treating every table as necessarily fenced.

## Refine this skill

- When the user provides another style explanation, update this skill's relevant rule and, when useful, its example. Maintain one source of truth rather than copying the full style into project AGENTS.md files.
- Apply clear refinements directly. If a new preference conflicts with an earlier rule and the intended distinction remains unclear, ask a focused question before changing that rule; continue independent work.
- When reviewing user edits for skill refinements, consider missing reasoning revealed by new explanations as well as writing preferences and structural decisions; read `refactor-document` when edits regroup, reorder, merge, or move knowledge, including within a single file. Keep each refinement in the skill responsible for that decision.
- When learning from a user-edited draft or Git history, treat the documents as work in progress. For a requested commit range, trace changes chronologically and compare moved content with its source; for working-tree reviews, include untracked replacement files. Learn from the direction of deliberate rewrites and later corrections, not just the latest snapshot. Moving a passage is evidence about organization, not endorsement of its unchanged wording or technical claims. Respect the stated review boundary; unfinished or untouched sections are not evidence of a final preference. Infer style separately from technical correctness, grammar, and code syntax.
- Copied material may have been collected because the user recognized its usefulness before fully understanding it. Its wording, scope, and placement are not necessarily endorsed preferences, even when professionally written. During requested adaptation, preserve its useful knowledge while making the reasoning and connections understandable in the user's style; do not discard it merely because it is not yet integrated. Give explicit preferences and deliberate user rewrites more weight than untouched passages. Keep deliberate formats for code, tables, and quotations when they serve their purpose.
- Treat the user’s revisions as their best current expression of an evolving understanding within the time available. For this user, 'good enough' marks having read and understood the material, connected related concepts, and arranged them so their location is predictable when needed. It is a milestone of understood, integrated knowledge, not a final version or a limit on future improvement. Use explicitly accepted versions as stronger evidence of the current target and their history to learn which decisions avoid unnecessary rework. Preserve room for better explanations and organization as knowledge grows. Editorial polish alone cannot establish the user's understanding; acceptance also does not certify every technical claim, typo, or unchanged passage.
- Distinguish reusable preferences from project-specific exceptions. Do not generalize every one-off example into a universal rule.
- Check edits for preserved meaning, topic/support hierarchy, example separation, valid reference targets, and balanced fences. Use the skill-creator validator when changing skill structure or metadata.
