# CLAUDE.md

Guidance for Claude Code (and any AI assistant) working in this repository.

## What this repository is

A workspace for translating books from **Turkish into Russian**, with a
current focus on contemporary authors writing on **Islamic topics**
(essays, memoirs, popular theology, publicistic and narrative works). The
repository is otherwise minimal at this stage — the main asset so far is
the translation skill described below.

`AGENTS.md` mirrors the essentials of this file in a tool-agnostic form,
for any AI assistant other than Claude Code that works in this repo — keep
the two in sync when the rules below change.

## Book translation skill

`.claude/skills/book-translation/SKILL.md` encodes the house rules for this
kind of work and should be treated as required reading before translating
anything here, not just an optional reference. It covers:

- Reading a source for genre/register before translating, so the Russian
  keeps the author's actual voice instead of flattening into generic prose.
- Building and maintaining a per-project glossary so recurring terms,
  honorific formulas, and names are rendered the same way from page 1 to
  the last page.
- Precision rules for Islamic terminology and religious content: don't
  domesticate core terms (Allah stays Аллах, namaz stays намаз, etc.),
  preserve honorific formulas (ﷺ, r.a., rahimehullah) every time they
  occur, add a translator's note instead of silently explaining or
  omitting, and never freely re-translate a Qur'an/hadith quotation — match
  it to an established reference translation or flag it for the user.
- A fidelity self-check pass before delivering any translated text.

`.claude/skills/book-translation/references/glossary-tr-ru-islamic.md` is a
starter glossary of common Turkish Islamic-topic terms and their default
Russian rendering. Extend it — and the per-project glossary it points
to — as new books introduce new terminology; treat both as living
documents, not fixed references.

When asked to translate a book, chapter, or excerpt in this repo (or to
help with terminology/glossary decisions for one), use this skill rather
than translating ad hoc.

## Suggested project layout (not yet enforced)

No book projects exist in the repo yet. When one is added, a layout like
this keeps the source, translation, and glossary easy to find and keep in
sync — adjust as actual needs surface rather than forcing it prematurely:

```
books/
  <book-slug>/
    source/           # original Turkish text, chapter by chapter
    translation/       # Russian translation, mirroring the source structure
    glossary.md         # per-book glossary (seeded from the skill's starter glossary)
    notes.md            # flagged items: uncited quotations, uncertain terms, open questions for the user
```

## Workflow: working a book from source to delivered translation

Follow this sequence for every book project — it turns the skill's
principles into concrete repo operations. Don't skip steps to save time;
each one exists because skipping it is exactly how a book-length
translation drifts inconsistent.

1. **Set up the project.** If `books/<book-slug>/` doesn't exist yet,
   create it with `source/`, `translation/`, `glossary.md`, `notes.md`
   (see layout above). Derive the slug from the book's title, kebab-case
   (e.g. *Kur'ân'dan İdrake Yansıyanlar* → `kurandan-idrake`).
2. **Load the source into `source/`, split by chapter/section**
   (`01-takdim.md`, `02-....md`, …), matching however the book itself is
   divided. Don't merge chapters into one file, even for a short book —
   per-chapter files are what keep translation and glossary work scoped
   and reviewable.
3. **Read before translating anything**: this file, the skill's
   `SKILL.md`, and the starter glossary — every session, not just the
   first one. Then read the *whole* chapter before starting to translate
   it, not just the first paragraph, to catch its register and recurring
   terms up front.
4. **Seed `glossary.md`** from
   `.claude/skills/book-translation/references/glossary-tr-ru-islamic.md`
   before the first chapter is translated, then add every book-specific
   term as you hit it — one row per term: chosen rendering, first-use
   location. Update it *before* moving to the next chapter, not as an
   afterthought.
5. **Translate chapter by chapter into `translation/`**, one output file
   per source file, same filename. Preserve paragraph breaks, headings,
   and emphasis matching the source.
6. **Log every flagged item in `notes.md`** as you hit it — an uncited
   Qur'an/hadith quotation, an uncertain term, an ambiguous passage. Don't
   resolve these silently; write them down (see Conventions below).
7. **Self-check each chapter before moving to the next one** (skill Step
   5): fidelity spot-check, glossary consistency, honorifics, scripture
   quotations, register — per chapter, not just once at the end of the
   whole book.
8. **Commit per chapter, not per book.** One commit per translated
   chapter (source + translation + that chapter's glossary/notes
   updates), message naming book and chapter, e.g.
   `Translate <book-slug>: chapter 3`. This keeps commits reviewable and
   means one bad chapter doesn't force re-checking the whole book.
9. **Ask, don't guess**, when a flagged item needs a decision the user
   hasn't already made. Keep translating what you're confident about
   rather than blocking the whole chapter on one open question — flag it,
   move on, and report open questions when you deliver the chapter.

## Scope of use

Book text in this repository is being translated for the owner's
**personal, non-commercial study/reference use** — not for publication or
wider distribution — unless they've explicitly said otherwise for a
specific project. Commercially published books are copyrighted, and
translation rights normally belong to the rights holder; treat "translate
the whole book, chapter by chapter" as personal-use translation help, not
as license to assemble a complete, publication-quality translated copy of
someone else's copyrighted book for redistribution.

## Conventions

- Keep translator's notes (footnotes or first-use glosses) in whatever
  format the current project has already established; don't switch
  conventions mid-book.
- Never resolve a flagged uncertainty (an uncited Qur'an/hadith quotation,
  an ambiguous term) silently — surface it to the user explicitly, per the
  skill's self-check step.
