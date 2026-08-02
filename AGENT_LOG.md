# Agent Log

Append-only record of automated and agent-assisted changes to this deck.

Purpose: this work happens from more than one machine, so local notes are not a
reliable history. Anything an agent should know about a past change belongs
here, not in a local file.

## Conventions

- Newest entry first. Never rewrite or delete an existing entry; correct it with
  a new one that says what it supersedes.
- Record what was verified and how, not just what was edited. "Fixed" without a
  check is not a result.
- Record open items and known-failing things explicitly, so the next agent does
  not rediscover them or assume they are already handled.
- No participant data, transcripts, consent records, credentials, or tokens.

---

## 2026-08-01 - Restored proposal-controlled language on slide 9

Agent: Codex, at the author's request after checking the controlling Chapters
1-3 proposal.

- Removed the COREQ and SRQR comparison from slide 9. Those standards entered
  the deck through the Jones/TROUT-AI reading and do not appear in the proposal
  or the author's qualifying paper.
- Replaced the coda with the proposal's actual methodological logic: AI output
  is not context-free, its production conditions must be preserved, and the
  protocol's choices must remain open to committee scrutiny.

Verification: confirmed zero occurrences of either acronym in the controlling
Google Doc; verified the proposal's RQ1-RQ3 labels and the source language in
the `AI-Generated Text and Agentic Artifact Comparison` section; checked the
HTML diff and whitespace. The dissertation document was not modified.

## 2026-08-01 - Revised for the 30-minute doctoral guest session

Agent: Codex, at the author's request after a full content and delivery review.

The revision keeps the four-relationship argument and the final submitted
proposal terminology, while making the session more concrete and easier to
deliver in thirty minutes:

- Replaced the repository-governance slide with one completed, public-safe
  decision trace from the July 24 methodology revision. It shows the task,
  material supplied, AI contribution, verification, researcher decision, and
  effect on the study without exposing private proposal identifiers or
  participant material.
- Moved that example directly after the AI-use memo so the sequence now moves
  from disclosure principle to documented practice before treating AI output
  as comparison material.
- Reduced the infrastructure section from three live stops to one card-sort
  interaction. The overview and browser-local instrument remain follow-up
  links, not additional live demonstrations.
- Replaced claims about shared training data and the absence of any current
  reporting standard with narrower, defensible language about non-independent
  sources and the AI-specific gaps in COREQ and SRQR.
- Reframed AI output as traceable comparison material, changed "admissible" to
  "auditable," corrected the COPE authorship wording, added the Holmes and
  Zhgenti DOI, and changed the first discussion question from co-authorship to
  the defensibility of human authorship.
- Condensed the memo fields, limits, and resource descriptions and increased
  body copy size in the densest components.
- Fixed the footer and slide announcement title so line breaks in the title
  slide become spaces rather than concatenated words.

Verified: JavaScript syntax; 14 sequential slides; no duplicate IDs or missing
`aria-labelledby` targets; `git diff --check`; all 14 slides rendered and
reviewed individually at 1440x900; no overflow at 1440x900, 1280x720,
1024x768, 900x700, 620x800, or 390x844; no page or console errors; Arrow,
Home, End, overview, help, and Escape controls; and every staged reveal on
slides 3, 5, 7, 12, and 14. The three public dissertation links and the added
Holmes and Zhgenti DOI returned HTTP 200.

Not verified this pass: the Jones DOI and COPE page rejected scripted requests
with HTTP 403, so their unchanged public links were not re-read from their
landing pages. The private presenter-notes source was not present in this
workspace and was not updated. These changes remain local, uncommitted, and
unpushed.

## 2026-08-01 - Published to GitHub

Agent: Claude Code. Repository created by the author; everything else automated.

Remote: `minerclass/NLU-AI-Ethics-4-Relationships`, public, default branch
`main`. The local working folder is still named `ai-ethics-course-session`; the
mismatch is harmless but worth knowing when navigating between machines.

A pre-publish scan run before anything was staged caught two things that would
otherwise have gone public, both fixed in the same commit:

- **`AGENT_LOG.md` recorded the controlling proposal's Google Doc ID.** Replaced
  with a non-identifying reference. This file is public; treat it accordingly.
- **`README.md` spelled out both private presenting cautions**, including the
  observation that the course audience overlaps the study population and the
  defense date. Since the entire purpose of publishing is that the class will
  find this repository, that text would have been read by exactly the people it
  discussed. Replaced with a neutral "Study stage" section stating the study is
  pre-IRB and collects nothing. Both cautions remain in the private presenter
  notes, which are the right place for them.

Added for publication: `LICENSE` (MIT for code, with CC BY 4.0 for prose noted
in the README, matching `dissertation-overview`), `.nojekyll`, and a
`.gitignore` blocking presenter-notes filenames and PDFs as a second line of
defence behind keeping those files outside the repository entirely.

Verified: eight files on the remote and no others, confirmed with
`git ls-tree -r origin/main`; no presenter notes, no PDFs, no planning document;
the GitHub API reports the repository public on default branch `main`; a scan of
outbound links in `index.html` and `README.md` returns only the author's own
public sites, two DOIs, COPE, and Creative Commons.

Not verified this pass: GitHub Pages was **not** enabled at push time
(`GET /repos/.../pages` returned 404), so no live URL has been loaded or checked.
The repository description and homepage fields are still empty. `gh` is not
installed on this machine and no API token is configured, so both remain manual
steps.

## 2026-08-01 - Print export exercised, both print stylesheets repaired

Agent: Claude Code. Closes the "no print export generated" open item from the
two entries below.

First export exposed two real defects that page counts alone would have hidden:

- **Deck printed portrait**, so every slide occupied roughly 60% of a sheet with
  a large void beneath it, and the last slide's `page-break-after: always`
  emitted a blank 15th page.
- **Presenter file ran 8 pages** for 1,778 words, fitting only two notes per
  sheet because `break-inside: avoid` pushed the third block over with no
  compensating density.

Fixes:

- Deck: `@page { size: letter landscape; margin: 10mm }`, `.slide` forced to
  `display: grid` with `align-content: center` and `min-height: 190mm` so each
  slide fills its sheet, `.slide:last-child` break reset to `auto`, and the
  decorative `.title-index` hidden. Dead `.notes-drawer` and `.speaker-notes`
  print selectors removed.
- Presenter file: explicit portrait `@page`, and print-specific type and spacing
  throughout. `break-inside: avoid` on `.note` was **kept deliberately** so you
  never turn a page mid-note while presenting; the density fix works around it
  rather than removing it.

Verified by rendering the PDFs, not by counting pages: deck is 14 pages, no
blanks, 792x612pt landscape, and page text is byte-identical to the pre-fix
export except for the `01`/`14` title index deliberately hidden in print;
presenter file is 5 pages (down from 8), no blanks, 612x792pt portrait, with
full text preserved against the pre-fix export and vertical fill improved to
0.74-0.84 on content pages. Visual review of deck pages 3, 8, and 12 and
presenter page 2 confirms intended layout, including that `[data-step]` reveals
all print at full opacity on the dark slides.

Committed artifacts: `../Four-Relationships-deck.pdf` and
`../AI-Ethics-Session-Presenter-Notes.pdf`. Note that the deck PDF lives beside
the deck folder rather than inside it, and the notes PDF inherits the same
private handling as its HTML source.

Known and accepted: the four-card relationship grid on slide 3 prints as 2x2
rather than 4-across, because the 900px breakpoint fires against the print
layout width. On a landscape sheet the 2x2 arrangement is more legible than four
narrow columns, so it was left alone. The four dark slides print full-bleed dark;
that is deck fidelity, but it is toner-expensive if anyone prints the deck on
paper rather than reading the PDF.

Not verified this pass: A4 paper. Both stylesheets name US Letter explicitly.

## 2026-08-01 - Presenter notes split out of the deck

Agent: Claude Code, at the author's request. Supersedes the initial build entry's
open item about whether speaker notes should ship.

The notes are not to be accessible to anyone but the presenter, so they were
removed from the deck entirely rather than hidden inside it. A `hidden` aside is
still in the DOM and still in view-source, so hiding would not have met the
requirement. This log is itself public, so it describes the notes only as
private presenting guidance and does not summarize what is in them.

- Removed all fourteen `<aside class="speaker-notes">` blocks from `index.html`,
  along with the Notes button, the notes drawer markup, and the `N` row in the
  keyboard-help dialog.
- Wrote the notes to `../AI-Ethics-Session-Presenter-Notes.html`, which sits
  **outside this folder on purpose**. If this folder becomes a repository, the
  notes are not in it and cannot be published by accident. Moving that file in
  here would undo the separation.
- The presenter file is standalone: a timing rail, then all fourteen slides'
  notes with their `[Sources]` lines, styled to match and set up to print. It
  carries a private-handling banner and `noindex`. It does **not** sync with the
  deck; cross-window sync was considered and rejected because it would require
  the public deck to broadcast state for a private consumer's benefit.
- `presentation.js` now **diverges** from
  `diss-proposal-defense/presentation/presentation.js`. A `hasNotes` guard makes
  the notes UI optional, so the engine tolerates the absent drawer instead of
  throwing on `notesButton.addEventListener`. The divergence is five early
  returns and one conditional listener block. Port upstream fixes around it.

Verified: after the strip, DOM queries return zero `.speaker-notes`, no
`notesDrawer`, no `notesButton`, no "presenter notes" text in the keyboard-help
dialog, and no match for `Talk track` or `[Sources]`, the two structural
headings used throughout the notes, anywhere in `document.body.innerHTML`;
pressing `N` and toggling overview (which
calls `closeNotes` internally) both complete without throwing; the console is
clean; the engine still reports 14 slides with one active. The out-of-bounds
probe with every reveal forced returns 14/14 clear at the native viewport and at
simulated 1920x1080, 1366x768, 1280x720, and 1024x768. The presenter file renders
14 note blocks, none empty, all 14 carrying a `[Sources]` line, with its
private-handling banner intact.

Not verified this pass: no print export of either file was generated, so the
presenter file's print stylesheet remains unexercised. The viewport caveat from
the initial build still stands.

## 2026-08-01 - Initial build

Agent: Claude Code, from a session design written the same day.

Created a 14-slide deck for a 30-minute guest session in the dissertation
chair's AI Ethics in Education course. Source material: the controlling
Chapters 1-3 proposal (controlling working copy, July 24, 2026), the public
repository governance files, and the course invitation. The proposal's document
ID is deliberately not recorded here; this file is public.

Structure decisions worth keeping:

- **The organizing claim is four relationships, not a tool list.** Subject,
  assistant, data, infrastructure, each with a different obligation. A tool list
  is obsolete within two model releases; the four-way distinction transfers to
  any dissertation topic, which is what makes the session worth a doctoral
  seminar's time.
- **Slides 5 through 7 quote the proposal verbatim** (AI Use Disclosure,
  Chapter Three's negative rule, the Appendix H memo template field list) rather
  than paraphrasing. The chair asked how AI was *discussed in the work*, so the
  work should speak.
- **Slide 12 names four unsolved problems and defends none of them.** An ethics
  class will raise them regardless; raising them first is the credibility move.
- Terminology follows `pedagogical-friction/AGENTS.md`: no case-study framing,
  infrastructural friction as conditioning base rather than a co-equal fourth
  dimension, Miner (2026a) Zenodo and (2026b) article with no 2026c, and no em
  dashes in user-facing copy.

Engine: `presentation.js` is reused **unchanged** from
`diss-proposal-defense/presentation/presentation.js`. If that engine gains fixes,
port them here rather than diverging. `presentation.css` is a new, leaner
stylesheet (roughly 600 lines against the source deck's 47 KB) carrying the same
palette variables and shell idiom, plus components this deck needs and the
source deck does not: relationship grid, rule list, demo list, tension list,
resource list, question list.

Verified: page loads with no console errors; engine initializes (slide total
reports 14, progress bar and hash routing update); presenter-notes drawer opens
and renders per-slide notes; an out-of-bounds probe with **every reveal forced**
returns 14/14 clear at the native 1280x800 viewport and at simulated 1920x1080,
1366x768, 1280x720, and 1024x768; visual review of slides 3, 12, and 13
confirms intended layout on light and dark variants.

Not verified this pass:

- The four non-native sizes were simulated by forcing explicit dimensions on
  `.presentation-shell`, **not** by a true viewport resize. The browser pane's
  `resize_window` timed out. Because slides use `container-type: inline-size`,
  width-driven typography is exercised correctly, but true viewport resize has
  not been directly measured.
- No print export was generated. Print rules exist (`@media print` forces the
  revealed state, drops chrome, one slide per page) but are unexercised.
- Touch swipe navigation and the 620px breakpoint are unexercised.
- Slide 10's three external links were confirmed live on 2026-07-31 per the
  ecosystem memo, not re-fetched during this build.

Open item: this deck is local only. It has not been committed, pushed, or given
a GitHub Pages URL. If it is published, decide first whether the speaker notes
should ship, since they carry private presenting guidance.
