# Four Relationships

A 14-slide HTML deck for a 30-minute guest session in a doctoral **AI Ethics in Education**
course, taught by the dissertation chair.

**Working title:** *Four Relationships: What It Took to Write About Cognitive Bypass Using Tools
Built to Bypass Cognition*

## What it is

The session answers the chair's specific ask (how AI platforms were used in the proposal, how they
were included in the work, and how they were discussed in the work) by refusing the tool-tour
format. Its organizing claim is that the proposal has **four distinct relationships** with
generative AI, each carrying a different ethical obligation:

1. **Subject** — the study is about tertiary algorithmicity and pedagogical friction
2. **Assistant** — bounded support during proposal development, disclosed in the front matter
3. **Data** — AI output as a prespecified, nonparticipant comparison source
4. **Infrastructure** — the public GitHub Pages ecosystem around the study

Most disclosure statements collapse all four into one sentence. Naming the collapse is the
contribution to the course, and it transfers to any dissertation topic.

Slide 8 grounds that framework in one completed decision trace from the July 24 methodology
revision: the task, material supplied, AI contribution, verification, researcher decision, and
effect on the study. The example is public-safe and contains no participant material.

Every claim on a slide traces to the controlling Chapters 1–3 proposal (July 24, 2026).

## Structure

```
index.html        All 14 slides. No speaker notes, by design
presentation.css  Styles, harmonized with the diss-proposal-defense palette
presentation.js   Deck engine, from diss-proposal-defense/presentation
README.md         This file
AGENT_LOG.md      Append-only record of agent-assisted changes
```

There is **no build step** and **no data collection**. Vanilla HTML, CSS, and JS.

## Presenter notes live outside this folder

This deck is **publication-safe**: it contains no presenter notes in the DOM, no notes drawer, and
no notes control. The notes are in

```
../AI-Ethics-Session-Presenter-Notes.html
```

deliberately stored **outside this repository** so that publishing the deck cannot expose them. They
are private presenting guidance and are not part of the session material.

If you ever move that file in here, you have undone the separation. Don't. `.gitignore` guards
against it as a second line, but the real protection is that the file lives somewhere else.

The presenter file is a standalone printable brief: a timing rail, then all fourteen slides' notes
in order with their `[Sources]` lines. It does not sync with the deck. Open it on a second screen,
on a phone, or print it.

## Run locally

Open `index.html` directly, or serve the folder:

```bash
python -m http.server 8000
```

## Presenting

| Key | Action |
|---|---|
| `←` `→` `Space` | Previous / next (steps through reveals first) |
| `Home` `End` | First / last slide |
| `O` | Slide overview |
| `F` | Fullscreen |
| `?` | Shortcut help |

Reveals change **opacity only**, never layout, so nothing reflows inside a slide that already fits.
Unrevealed content stays in the DOM and in the accessibility tree: the steps pace the presenter,
they do not gate content. Print and `prefers-reduced-motion` force the fully revealed state.

Slide 11 is the only live demo. **Pre-load the pedagogical-friction card sort before class** and
keep a screenshot as a fallback. The dissertation overview and browser-local instrument preview
are reference links for later exploration, not additional live stops.

## Study stage

The study is at the proposal stage, before data collection and IRB approval. Slide 10 links the
instrument preview at `dissertationquestionsbeta`, which is a **draft instrument preview and
collects nothing**. Nothing in this session recruits participants, pilots instruments, or gathers
data, and nothing said in the room is data.

## Boundaries

Public-facing session material only. No participant data, transcripts, consent records, IRB-protected
content, district specifics, committee deliberations, credentials, or tokens. This deck collects
nothing and adds no analytics.

## Terminology

Follows the **final submitted** Chapters 1–3 language, matching `pedagogical-friction/AGENTS.md`:

- Qualitative-dominant convergent mixed methods study. **No case-study framing.**
- Three learner-facing friction dimensions (noetic, rhetorical, existential) on **infrastructural
  friction as the conditioning base**, not four co-equal dimensions.
- Three pressures of tertiary algorithmicity: noetic displacement, rhetorical saturation,
  existential abstraction.
- Miner (2026a) = the Zenodo evidence arc. Miner (2026b) = the *i.e.: inquiry in education* article.
  There is no Miner (2026c).
- User-facing copy avoids em dashes by author preference.

## License

Dual-licensed to separate code from scholarship, matching the rest of the ecosystem:

- **Code** (HTML, CSS, JavaScript): [MIT License](LICENSE).
- **Written and scholarly content** (slide prose, framework descriptions):
  [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/), reuse and adapt with attribution to
  Micah J. Miner.

The Pedagogical Friction framework and its terminology are the author's scholarly work. Please cite
the dissertation and related publications when building on them.

## Planning material

The full session design (minute-by-minute run of show, the cut line if running long, and the
reasoning behind the resource selections) is kept privately outside this repository, alongside the
presenter notes.
