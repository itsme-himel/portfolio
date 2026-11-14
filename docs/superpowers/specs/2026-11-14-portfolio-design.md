# Portfolio site: design

## Intent
A single-page personal portfolio that reads as professional with an academic side.
Minimal, plain wording, no marketing language.

## Goals
- One page holding: About, Experience (2), Research (ongoing Master's thesis), Education (2),
  Projects, Certifications, Activities, contact links.
- Readable on a phone, by keyboard, in light and dark, and when printed (doubles as a PDF CV).

## Non-goals
Blog, contact form, analytics, animation, skill bars, CMS, multiple pages.

## Anti-goals
Buzzwords or filler sentences. Empty sections. Anything that looks like a template.

## Approaches considered
- A, Document: one serif column, thesis first. Suits academic readers; gets long as projects grow.
- B, Sidebar: identity and section nav fixed on the left, content on the right, experience first.
  Suits recruiters; looks sparse if content is thin. **Chosen by the owner.**

## Design (B)
- Layout: 15rem left column (name, one-line role, section nav, contact links, CV link), sticky on
- Phone: only a Menu button shows at the top of the page; once the name scrolls away a bar appears behind it with the name and current section; the nav and the four links slide in from the right as a panel. Without JavaScript the nav stays in the page.
  wide screens; content column on the right. Below ~640px the sidebar becomes a header and the nav
  a wrapped row of links.
- Section order: About, Experience, Research, Education, Projects, Skills, Certifications, Activities. Skills is four labelled rows using the same library labels as the project tech stacks; no bars or ratings.
- Entries: title, organisation, date right-aligned in monospace, then up to three plain bullets.
  Projects are full-width cards: title, one-line summary, two or three points, then a "Tech stack" row of library labels under a rule.
- Thesis: its own Research section, marked "In progress", with working title, supervisor and
  expected date. No claimed results.
- Type: IBM Plex Sans for text, IBM Plex Mono for dates and stack labels. 16px base, text columns
  capped near 62 characters.
- Colour: IBM Carbon greys with its blue as the single accent (labels, links, results, current nav item); light grey page with white cards. Light and dark follow the device by default; a three-icon switch (light, system, dark) in the sidebar and the phone menu overrides it and is remembered. Contrast at least 4.5:1.
- Behaviour: nav links are in-page anchors; a small inline script underlines the current section in the nav. Sections below the first screen fade in on scroll; A click or tap leaves a three-ring ripple; a resting mouse gets fainter ripples at 5, 10 and 15 seconds, then none until it moves. all motion is off under reduced-motion, without JavaScript, and in print.

## Builder's calls (not decided by the owner)
- Plain `index.html` + `styles.css`, no framework or build step.
- Hosted on GitHub Pages from this repo (URL `<user>.github.io/portfolio`).
- Fonts from Google Fonts with a system fallback stack.
- Metadata: title, description, canonical, Open Graph tags, favicon. No JSON-LD.
- Print stylesheet hides the nav and lays the page out in one column.

## Needed from the owner
Real content for every section (a CV is enough), plus the email and profile links to show.
