---
name: refactor-document
description: Reorganize knowledge within a single document or across related documents, moving and rewriting content to improve reading order and remove duplication, overlap, or fragmentation. Use to decide topic grouping, ownership, section and document boundaries, meaningful names, prerequisite order, and useful references, or to split, merge, and move content while preserving meaning and examples. Work with personal-markdown for wording, explanations, examples, and personal presentation conventions.
---

# Refactor Document

* -> Make a document or collection of related documents easier for the user to find, read, and understand by deciding what belongs in each section or file and how those parts connect. Move content to its suitable section or owning note and rewrite where needed so the material stays simple to read, without duplicated knowledge, overlapping explanations, or fragmented topics. Follow the user’s mental organization even where it differs from common documentation structures. Preserve the knowledge, useful examples, and technical qualifications.

* -> Collaborate with `personal-markdown` throughout knowledge-base work: this skill handles structural organization within a document and across documents; that skill handles wording, explanations, examples, and personal presentation conventions. Revisit the arrangement when editing reveals a better topic boundary, and revise local explanations when the arrangement changes. Keep both within the requested scope; select by the decisions needed, not by file count. Regrouping sections, merging repeated explanations, or repairing prerequisite order in one file is also refactoring; focused wording or formatting edits can use `personal-markdown` alone.

## Review the structure

* -> Read the requested document or set of documents before choosing what to move, combine, or remove. Inspect neighboring notes when ownership, dependencies, or overlap requires that context; a self-contained structural change can stay within one file.
- Identify the reader’s purpose for each note, the knowledge it assumes, and where overlapping subjects are currently explained.
- For this user’s technical knowledge base, default to a backend developer’s practical focus: what the concept does, when it is useful, how to start applying it, and which decisions, prerequisites, or common mistakes affect that use. Select details by whether they help the user understand, implement, or troubleshoot the intended scenario. Use official documentation to verify claims and provide focused references for deeper detail; its breadth and formal presentation are not the target. Avoid importing every feature, alternative, administrative concern, or rare edge case for completeness. Include deeper mechanisms or qualifications when they explain a practical consequence, and broaden coverage when the user requests it. This guides scope selection, not silent deletion of distinct knowledge during a preservation-focused refactor.
- Identify concepts introduced too late, disconnected explanations, duplicate points, and detail that belongs in an existing central note. Check for missing relationships or conditions across related definitions, explanations, procedures, and examples; individually correct notes can still leave their connection unclear.
- Respect the requested scope and the user's unfinished edits. Daily commits may move material first and consolidate or clarify it later. When reviewing history, trace additions, removals, moves, and rewrites chronologically; compare moved passages with their sources, including destinations outside the immediate folder. Distinguish actual knowledge removal from relocation or compression, and temporary duplication from final ownership. Use the accepted result to identify the reasoning that would have avoided intermediate repairs, rather than teaching the skill to repeat those stages. Use the requested range or reviewed portion as evidence, with `personal-markdown` governing how to learn from edits.

## Organize within a note

* -> Group related explanations under meaningful headings, merge repeated definitions, and place prerequisite concepts before the examples that depend on them. Move shared explanations ahead of related scenarios; keep scenario-specific setup beside its use. Preserve distinct facts, qualifications, and examples when consolidating sections.
* -> Keep a coherent topic in one file when section reorganization resolves the problem. Creating or moving files is only one possible refactoring outcome.
* -> Keep the explanation of a mechanism beside the code that demonstrates its internals under one meaningful section, preserving platform-specific limits. Separate this shared explanation from examples of using the abstraction. When a walkthrough reveals reusable reasoning, promote that reasoning to the concept or mechanism section and retain the concrete application in the example. Shared setup belongs before scenario branches; a requirement unique to one branch belongs inside that branch.
* -> Prefer one well-chosen example when it explains the concept sufficiently. Keep equivalent examples selectively when their contrast materially improves understanding enough to justify the extra length, such as a target with special relevance to the topic paired with a general resource. Variation in names, actors, or environments alone is not a reason to add examples; judge what the comparison teaches in this note.

## Organize across notes

* -> Organize the knowledge base as a meaningful concept hierarchy: folders reinforce broader concepts, and each note has a focused concept or purpose within that context. Avoid mixing independent concepts merely because they appear in the same workflow or product. A product’s features can belong in different topic folders; follow the aspects the user studies or looks up rather than imposing a vendor taxonomy. Keep supporting detail together when separating it would fragment the explanation.

* -> Treat file and folder names as part of the reading experience: choose meaningful names that make the topic or purpose recognizable before opening the note. A folder names the shared aspect; a file names its specific subject. Reassess names when content moves or its scope changes, following local conventions without imposing a universal naming scheme. Update affected references when renaming within the requested scope.

* -> Refactor across files when a section is substantial enough to be studied or looked up independently and separating it improves reading or reuse: use its existing owning note, or create a focused note when needed. Reusability or a different abstraction level alone does not justify extraction. Keep a topic’s mechanism, essential setup, and useful implementation together when they form one explanation.
- Keep the overview or applied discussion in the original note; replace the extracted explanation with a compact reference under its topic heading when that heading still helps readers.
- When several actor or resource notes repeat the same operation, keep each actor’s setup in its own note, move the shared operation and its worked steps to one action-focused note, and reference it where the setup reaches that action. Keep useful actor-specific examples as distinct sections under the shared topic so their differences remain easy to compare.
- Apply the same ownership boundary when reviewing an operation note: the full reusable explanation of actor setup belongs with the actor, even if misplaced material appears only once. For example, identity creation and credential setup belong with the identity; permission assignment belongs with authorization. A worked example can still retain the brief setup or concrete assignment needed to demonstrate its own topic coherently. Centralize the explanation, not every occurrence of an operation. When setup is already taught elsewhere, place the brief reminder or reference before the main workflow so the steps teaching the current topic stay adjacent; for example, keep defining an API permission next to granting it, without interrupting them with identity creation.
- Move the concept's definitions, qualifications, subtopics, and useful examples together. Preserve relationships needed to understand it in the destination.
- Avoid splitting every subsection into a file or leaving duplicate explanations behind. Follow `personal-markdown` for reference formatting.

```yml
# Example: extract reusable concepts from an authentication overview
Before -> overview contains managed identity types + delegated/application permissions
After -> each concept lives in its own topic note with its examples and qualifications
Overview -> retains the corresponding headings with references + its applied discussion
```

## Preserve the reading flow

* -> Arrange prerequisite concepts before dependent applications. Use focused references where a reader needs another topic, and keep enough context in each note to make its purpose clear.
* -> Prioritize a coherent reading experience over strict deduplication or separation into concept, pattern, product, SDK, and operations notes. Centralize substantial explanations, but allow brief definitions, prerequisite reminders, and concrete setup steps to repeat when they let the reader finish the current topic or example. Use references for independently useful detail or real cross-topic dependencies; do not require a detour for context that belongs beside the current explanation.
* -> At a concept boundary, explain the relationship or condition needed to understand the current note before referring elsewhere for detail. A reference alone does not explain why related claims or setups differ. Inspect the relevant owning notes, distinguish valid differences from contradictions, and fill the missing connection locally while keeping the general explanation in its owning note. Stay within the requested topic and verify uncertain technical claims.
* -> Choose document boundaries that reduce both repeated explanations and unnecessary switching between files. Keep tightly coupled material together; combine overlapping notes when one coherent note would be easier to use. Repeated back-and-forth references or chains needed to finish one explanation are evidence to reassess those boundaries. Repair the arrangement and restore local context before removing links; fewer references alone is not the objective.
* -> Preserve useful diagrams, code, examples, technical conditions, and the existing language mix when moving content.
- Rewrite moved and surrounding passages when needed to integrate the knowledge: merge overlapping explanations, remove redundant introductions, and restore context or sequence. Preserve distinct facts and qualifications rather than merely appending moved sections or deleting everything that looks similar.
- Apply `personal-markdown` within the affected files, keeping presentation rules in that skill.

## Review the result

* -> Follow a representative reading and lookup task through the affected notes: starting from a concept or practical question, can the user predict which folder and note contain it, understand its relationships, and reach the applied detail without remembering the source conversation or original copied document? Names and ownership should reflect how the user understands the subject. Trace the actors and objects from setup through configuration and code to the observed result. Compare sibling scenarios for unexplained differences and check that code actually demonstrates the behavior claimed in the prose; organizing correct-sounding sentences is not sufficient.
* -> Compare against the original for lost meaning, changed claims, broken references, and examples separated from their prerequisites.
* -> Check headings, code fences, and local paths, including references left after extraction. Verify technical corrections as needed and distinguish them from structural edits.

* -> Aim to reach the current accepted quality in this pass: clear topic ownership, integrated explanations and examples, explicit consequential relationships, and predictable lookup. Once those hold and relevant checks pass, finish the requested work without adding speculative topics, extra navigation, or equivalent examples for exhaustiveness. Finishing a pass does not freeze the notes: growing understanding, new evidence, and clearer relationships can justify revisiting even an accepted arrangement.

## Evolve

* -> Use this skill to help any knowledge base reach the user’s intended organization sooner. Success means expressing the knowledge clearly from the user’s perspective, not reproducing the current file layout. As understanding develops, a passage may reasonably move back to its original note or to a different note because its relationship to the broader topic has become clearer. Learn the reasoning behind ownership decisions rather than treating a particular placement as permanent. Propose or carry out improvements within the requested scope without waiting for a finished reference version.

* -> Add focused refinements based on actual edits and user feedback. Keep project-specific conventions in project instructions and shared presentation rules in `personal-markdown`.
