# AI Tools for Doctoral Work

A nine-slide HTML deck for a 20-minute guest session in a doctoral **AI Ethics in Education** course.

## Purpose

The session gives doctoral students an accessible overview of common AI-supported research tools without centering the presenter's dissertation. It focuses on practical choices students can transfer to their own work:

- matching a tool to a specific scholarly task;
- distinguishing general assistants from research-focused tools;
- moving from discovery to a decision that can be explained;
- prompting for questions and critique before finished prose;
- verifying claims, quotations, citations, and methodological details; and
- protecting privacy, authorship, evidence quality, access, and rights.

The timing is designed for **15 minutes of presentation and five minutes of discussion**.

## Tools covered

- General assistants: ChatGPT, Claude, and Gemini
- Research-focused tools: Elicit and NotebookLM
- Source-of-record tool: Zotero
- Essential complements: library databases, Google Scholar, citation trails, and librarians

The deck treats capabilities as changeable and emphasizes task fit, data controls, institutional policy, and verification over brand loyalty.

## Structure

~~~text
index.html        Nine slides and all public session content
presentation.css  Responsive presentation styling
presentation.js   Keyboard, touch, overview, fullscreen, and progress controls
README.md         Project description and use instructions
AGENT_LOG.md      Append-only record of agent-assisted changes
~~~

There is no build step, analytics, form, or data collection. The deck uses vanilla HTML, CSS, and JavaScript.

## Run locally

Open `index.html` directly, or serve the folder:

~~~bash
python -m http.server 8000
~~~

## Presenting

| Key | Action |
|---|---|
| `Left arrow` `Right arrow` `Space` | Previous or next slide |
| `Home` `End` | First or last slide |
| `O` | Slide overview |
| `F` | Fullscreen |
| `?` | Shortcut help |

No speaker notes are included in the public repository. Print mode reveals all content and formats each slide as a landscape page.

## Boundaries

This is a general educational overview. It contains no participant data, research instruments, dissertation methods, unpublished findings, private notes, credentials, or tokens. It does not replace institutional, instructor, IRB, publisher, or legal guidance.

## License

- **Code** (HTML, CSS, JavaScript): [MIT License](LICENSE)
- **Written session content**: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/), reuse and adapt with attribution to Micah J. Miner
