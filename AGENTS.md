# AGENTS.md

Instructions for any AI coding/writing assistant working in this
repository (Claude, ChatGPT, or another agent). This file is a
tool-agnostic mirror of `CLAUDE.md` — read that file too if your tool
supports it, but everything you need is also summarized here.

## What this repository is

A workspace for translating books from **Turkish into Russian**, currently
focused on contemporary authors writing on **Islamic topics** (essays,
memoirs, popular theology, publicistic and narrative works). Translation
quality here means narrative fidelity and voice-matching, not just
grammatical correctness — see the rules below before translating anything.

## Read before translating

- `.claude/skills/book-translation/SKILL.md` — the full translation
  workflow and the precision rules for religious content. Treat it as
  required reading, not optional background.
- `.claude/skills/book-translation/references/glossary-tr-ru-islamic.md` —
  starter glossary of common Turkish Islamic-topic terms and their default
  Russian rendering.
- Any per-book `glossary.md` under `books/<book-slug>/` — the
  project-specific term list; check it before translating and update it the
  moment you render a new recurring term for the first time.

## Core rules, condensed

1. **Fidelity over fluency.** Translate what the author wrote — don't
   summarize, soften, sharpen, add, or drop content because a smoother
   version occurred to you.
2. **Match the register.** Identify whether the source is formal essayistic
   prose, warm direct address, narrative, etc., and reproduce that voice in
   Russian instead of flattening everything into generic neutral prose.
3. **Don't domesticate Islamic terminology.** Allah stays Аллах (not
   "Бог"), namaz stays намаз (not generic "молитва"), and so on — use the
   glossary's established Russian-Islamic-literature renderings rather than
   inventing paraphrases.
4. **Preserve honorific formulas every time they occur** (ﷺ, radıyallâhu
   anh, rahimehullah, etc.) — don't drop them as clutter or note them once
   and omit them afterward.
5. **Add a translator's note instead of explaining inline.** When a kept
   term needs a gloss for a Russian reader, use a footnote or a first-use
   bracketed note — don't rewrite the sentence around it, and don't keep
   re-explaining a term after its first noted occurrence.
6. **Never freely re-translate a Qur'an or hadith quotation.** Match it to
   an established reference translation when the source cites one, and flag
   it for the user when it doesn't — quotations of scripture are not the
   translator's prose to improvise.
7. **Keep one glossary per book, and hold to it.** The same term must not
   be rendered three different ways across one project.
8. **Do a fidelity self-check before delivering**: spot-check against the
   source, verify glossary consistency, confirm honorifics and scripture
   citations, and read back for register drift.

## Scope of use — read this before translating a whole book

Any book text in this repository is being translated for the repository
owner's **personal, non-commercial study/reference use** — not for
publication or wider distribution — unless the owner has explicitly said
otherwise for a specific project. Full commercially published books are
copyrighted, and translation rights normally belong to the rights holder;
don't treat a request to "translate the whole book, page by page" as
license to assemble and hand over a complete, publication-quality
translation of an entire copyrighted work. Short excerpts, glossary work,
and personal-study-oriented translation help are fine; producing what
amounts to a full unauthorized translated copy of a commercially published
book is not, regardless of how the request is chunked.

## Suggested project layout

```
books/
  <book-slug>/
    source/          # original Turkish text, chapter by chapter
    translation/      # Russian translation, mirroring the source structure
    glossary.md        # per-book glossary (seeded from the skill's starter glossary)
    notes.md           # flagged items: uncited quotations, uncertain terms, open questions for the user
```
