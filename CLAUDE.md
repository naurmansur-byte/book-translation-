# CLAUDE.md

Guidance for Claude Code (and any AI assistant) working in this repository.

## What this repository is

A workspace for translating books from **Turkish into Russian**, with a
current focus on contemporary authors writing on **Islamic topics**
(essays, memoirs, popular theology, publicistic and narrative works). The
repository is otherwise minimal at this stage — the main asset so far is
the translation skill described below.

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

## Conventions

- Keep translator's notes (footnotes or first-use glosses) in whatever
  format the current project has already established; don't switch
  conventions mid-book.
- Never resolve a flagged uncertainty (an uncited Qur'an/hadith quotation,
  an ambiguous term) silently — surface it to the user explicitly, per the
  skill's self-check step.
