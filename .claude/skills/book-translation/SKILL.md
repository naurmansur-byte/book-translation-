---
name: book-translation
description: Use this skill whenever translating book-length or chapter-length text from Turkish into Russian, especially contemporary authors writing on Islamic topics (essays, memoirs, popular theology, publicistic and narrative works touching on faith, practice, or Islamic history) — and also apply its core discipline (register-matching, terminology consistency, a running glossary, a fidelity self-check) to any long-form literary or nonfiction translation. Trigger this for any request to translate a book, chapter, article, or excerpt from Turkish to Russian, to build or maintain a glossary across a translation project, or to decide how to render Arabic-origin Islamic terminology, honorific formulas (ﷺ, rahimehullah, radıyallahu anh, etc.), or Qur'an/hadith quotations that appear inside a modern Turkish text. Don't skip this skill just because a request looks like "translate this one paragraph" — even a short excerpt from a larger book should follow the glossary and fidelity workflow below, since consistency only holds if it starts from the first page.
---

# Book Translation (Turkish → Russian)

## What this skill protects against

Machine-fluent translation fails books in two specific, avoidable ways: it
quietly rewrites what the author said into what reads smoothly, and it
flattens a distinctive voice into generic neutral prose. Both are invisible
sentence-by-sentence and devastating over a whole book — a reader ends up
with *a* book, not *this* book. For religious content the stakes are higher
still: a mistranslated term or a dropped honorific isn't a stylistic
smoothing, it's a change to what the author is asserting about matters of
faith. Treat every choice below as a fidelity decision, not a style
preference.

## Step 1 — Read before you translate

Before producing any output, read enough of the source (the whole excerpt,
or a representative sample of a longer book) to answer:

- **Genre and register**: Is this conversational address to the reader,
  formal essayistic prose, storytelling/narrative, or a mix? Turkish
  religious-publicistic writing often shifts register within a single
  chapter — direct address to the reader, then quoted scripture, then
  argument. Each register needs to survive into Russian as itself, not get
  averaged into one flat tone.
- **Recurring terminology**: Scan for Islamic terms, honorific formulas, and
  any Qur'an/hadith quotations. You will decide *once* how each is rendered
  and then hold that decision for the rest of the book — see Step 2.
- **The author's stance**: Note where the author is asserting something as
  religious truth, reporting a scholarly opinion, narrating a personal
  story, or being rhetorical/ironic. Translating a sincere theological claim
  as if it were a rhetorical flourish (or vice versa) is a fidelity error
  even when every word is individually correct.

## Step 2 — Build a project glossary before translating prose

For any job beyond a single short excerpt, create (or update) a glossary
file in the project — e.g. `<book-name>-glossary.md` next to the text being
translated. This is what keeps term #1 and term #400 rendered the same way.
Start from `references/glossary-tr-ru-islamic.md` in this skill, which
covers the common Turkish Islamic-topic vocabulary with the rendering
convention described in Step 4; add every book-specific or less-common term
you encounter, in the same format: **Turkish term → chosen Russian
rendering → note on first use? (y/n) → where it first appears**.

Consult the glossary before every session and update it the moment you
render a new term for the first time. If you notice midway through a book
that an earlier choice was wrong, fix the glossary entry *and* go back and
correct earlier occurrences — a glossary that silently changes partway
through the book is worse than no glossary.

## Step 3 — Translate for fidelity, not fluency-at-any-cost

- Translate what the author wrote, not an improved or smoothed version of
  it. Don't summarize, don't drop a clause because it feels redundant in
  Russian, don't add a clarifying phrase the author didn't write, and don't
  soften or sharpen a claim because you'd have phrased it differently.
  If the source repeats itself, repeats; if it's blunt, stay blunt.
- Match the register you identified in Step 1. Formal Turkish essayistic
  prose should read as formal literary Russian, not as a casual blog post;
  a warm, direct second-person address to the reader should keep that
  intimacy rather than becoming impersonal. When Turkish rhetorical
  patterns (long chained clauses, rhetorical questions, emphatic repetition)
  don't work mechanically in Russian, reproduce the *effect* — the emphasis,
  the rhythm, the address to the reader — with Russian means, rather than
  either forcing a literal calque or discarding the device entirely.
- Preserve structure: paragraph breaks, lists, headings, emphasis
  (italics/bold), and quotation formatting should carry over unless there's
  a specific reason not to.
- Watch Turkish–Russian false friends and structural traps: Turkish's
  frequent nominalized/participial constructions (-dığı, -ecek, -miş forms)
  often need to unpack into full Russian clauses to avoid an unnaturally
  compressed or ambiguous sentence; don't let sentence-length management
  turn into content loss.

## Step 4 — Islamic terminology and religious content: the precision rules

This is the part of the job with the least room for improvisation.

**Don't domesticate core terms.** Words like Allah, namaz, zekât, hac,
sünnet, tevhid name specific things that are not identical to their nearest
generic Russian gloss. Do not silently translate "Allah" as "Бог", or
"namaz" as the generic "молитва" when the text means the prescribed ritual
prayer specifically. Use `references/glossary-tr-ru-islamic.md` for the
default rendering of common terms; when a term isn't in the glossary yet,
choose a rendering that stays close to established Russian-language Islamic
usage (transliteration of the Arabic-origin term, as used in existing
Russian Islamic literature) rather than inventing a domesticated paraphrase,
and add it to the project glossary.

**Preserve honorific formulas as formulas, not as decoration.** When the
source marks the Prophet's name with ﷺ or its spelled-out equivalent
(sallallahu aleyhi ve sellem), or a companion's name with r.a.
(radıyallahu anh/anha), or a scholar's name with rahimehullah, keep that
marker every time it occurs in the source — don't drop it as visual clutter
and don't fold it into a one-time footnote and omit it afterward. Represent
it consistently (pick one form — the symbol, or a fixed Russian phrase —
per glossary, and use it every time the source uses the equivalent Turkish
marker).

**Add a note instead of explaining inline or omitting.** When you keep a
term or formula in its original/transliterated form and a Russian reader
unfamiliar with Islamic vocabulary might not follow it, don't rewrite the
sentence to explain it in place — add a short translator's note instead
(a footnote, or a first-use bracketed gloss, kept consistent for the whole
book — ask the user which convention the project uses if it isn't already
established). The note explains; the text stays a translation of what the
author actually wrote.

**Never freely re-translate direct Qur'an or hadith quotations.** When the
modern text quotes a Qur'anic verse or a hadith, that quotation is not
yours to translate fresh from the Turkish — it's a quotation of an
already-existing, load-bearing text.
- If the author cites a location (sura:ayah, or a hadith collection and
  number), match the quotation to that reference and render it using (or
  closely following) an established Russian reference translation, and keep
  the citation.
- If the author doesn't cite a precise location, flag the passage for the
  user rather than guessing — say plainly that you found an apparent
  Qur'an/hadith quotation without a clear reference and ask them how they
  want it sourced, instead of silently free-translating scripture as if it
  were the author's own prose.
- Never paraphrase, trim, or "improve" scriptural wording even when the
  surrounding prose is being translated freely.

**Distinguish the author's voice from quoted scholarship.** Contemporary
authors often quote earlier scholars, cite differing opinions, or narrate
sira/history. Keep quotation marks, attribution, and any hedging
("bazı alimlere göre" → "по мнению некоторых учёных", not stated as fact)
intact — don't let a quoted or attributed claim read as the narrator's own
assertion, or vice versa.

## Step 5 — Self-check pass before delivering

After translating a chunk (or the whole book), do a dedicated pass — don't
rely on getting it right the first time through:

1. **Fidelity spot-check**: pick several paragraphs and compare sentence-by-
   sentence against the source. Did anything get added, dropped, or
   softened/sharpened?
2. **Glossary consistency**: search your translation for each glossary term
   and confirm every occurrence matches the chosen rendering.
3. **Honorifics**: confirm every honorific formula present in the source
   appears in the translation, consistently rendered.
4. **Scripture check**: confirm every Qur'an/hadith quotation was matched to
   a reference translation (or flagged to the user), not freely rendered.
5. **Register check**: read a page aloud (mentally) — does it sound like
   one consistent authorial voice, or does the tone wander between
   paragraphs?

Report anything you flagged in Step 4 (uncited scripture, ambiguous terms,
places you weren't confident in) to the user explicitly rather than
resolving it silently — a translator's uncertainty is useful information,
not a failure to hide.

## Reference

- `references/glossary-tr-ru-islamic.md` — starter glossary of common
  Turkish Islamic-topic terms with their default Russian rendering and the
  note-vs-no-note convention. Extend it per-project; treat it as a living
  document, not a fixed table.
