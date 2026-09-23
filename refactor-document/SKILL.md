---
name: refactor-document
description: Reorganize existing documentation to make its content more logical, simple, and concise while preserving meaning, useful examples, and technical qualifications. Use for substantive content refactoring rather than isolated proofreading or conversation-to-document conversion.
---

# Refactor Document

* -> Make the document easier to understand with less repetition, while preserving the knowledge it needs to convey.

## Review the structure

* -> Read the requested document and relevant neighboring notes before choosing what to move, combine, or remove.
- Identify concepts introduced too late, disconnected explanations, duplicate points, and detail that belongs in an existing central note.
- Respect the requested scope and the user's unfinished edits. When learning from a diff, use only the portion the user identifies as reviewed.

## Organize across notes

* -> Refactor across files when a section explains an independently reusable concept: use its existing owning note, or create a focused note in the appropriate topic folder when none exists.
- Keep the overview or applied discussion in the original note; replace the extracted explanation with a compact reference under its topic heading when that heading still helps readers.
- Move the concept's definitions, qualifications, subtopics, and useful examples together. Preserve relationships needed to understand it in the destination.
- Avoid splitting every subsection into a file or leaving duplicate explanations behind. Follow `personal-markdown` for reference formatting.

```yml
# Example: extract reusable concepts from an authentication overview
Before -> overview contains managed identity types + delegated/application permissions
After -> each concept lives in its own topic note with its examples and qualifications
Overview -> retains the corresponding headings with references + its applied discussion
```

## Refactor the content

* -> Put prerequisites and definitions before dependent explanations; keep qualifications near the claim they constrain and examples beside the concept they illustrate.
* -> Give each heading a clear topic and each point one coherent idea. Combine close dependencies; separate independently useful facts.
* -> Remove repeated introductions, conversational filler, and examples that add no new understanding.
- Shorten wording without deleting conditions, changing certainty, or broadening a technical claim.
- Preserve useful diagrams, code, and the existing language mix.
- Add only the connective explanation needed to make the structure understandable; avoid turning an editorial task into a larger tutorial.

* -> For Markdown, apply the available `personal-markdown` skill; keep reusable formatting rules there.

## Review the result

* -> Compare against the original for lost meaning, changed claims, broken references, and examples separated from their prerequisites.
* -> Check headings, code fences, and local paths, including references left after extraction. Verify technical corrections as needed and distinguish them from structural edits.

## Evolve

* -> Add focused refinements based on actual edits and user feedback. Keep project-specific conventions in project instructions and shared presentation rules in `personal-markdown`.
