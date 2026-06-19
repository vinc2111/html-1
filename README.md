# HTML Arbejdsbogen

An interactive, self-contained workbook that teaches the basics of **HTML** to
children (around 12 years old), in **Danish**, with every example tied to
**mathematics**. It was built as a companion to a maths course: the student
learns to build web pages while practising numbers, tables, geometry and data.

> The interface and all explanations are in Danish. The code (HTML tags) is in
> English, because that is how HTML works everywhere — the lessons point out
> what the key tag names mean.

---

## What it is

- **A single HTML file.** No installation, no internet connection, no
  dependencies. Double-click it and it runs.
- **28 lessons across 7 parts**, from "what is a tag?" all the way to building a
  complete web page.
- Each lesson has:
  - a short explanation (in Danish),
  - the tags being learned,
  - a **live editor** where the student types HTML on the left and sees the
    result on the right, instantly,
  - a **"Din tur"** (your turn) challenge, most with an **"Ekstra"** stretch
    task for fast finishers.
- **Plain, browser-default styling on purpose.** It is meant to look like a
  hand-written HTML page rather than a designed app — which doubles as a
  teaching example (see *View Source*, below).

---

## How to use it

### For the student
1. Open `html-arbejdsbogen.html` in any web browser (just double-click it).
2. Read a lesson, type in the left box, and watch the right box change.
3. Do the **Din tur** tasks. Press **Nulstil** to reset a box if you get stuck.

It works fully offline. Nothing is saved, collected, or sent anywhere.

### For the teacher
- Let the student attempt the **Din tur** challenges before helping — that is
  where most of the learning happens.
- The **Ekstra** tasks are there to soak up time from students who race ahead.
- The lessons build in order, but the table of contents links straight to any
  lesson, so it is easy to jump around.
- Because the page itself is plain HTML, you can open its source
  (`Ctrl + U`, or right-click → *View Source*) to show the student that this
  very page is made from the same tags they are learning.

---

## Contents

| Part | Focus | Lessons |
|------|-------|---------|
| **Del 1 – Det grundlæggende** | Headings, paragraphs, bold/italic, line breaks, comments, special characters (incl. maths symbols × ÷ π) | 7 |
| **Del 2 – Struktur og lister** | Bullet/numbered lists, nested lists, description lists (a maths glossary) | 3 |
| **Del 3 – Links og billeder** | Links, anchors and new tabs, images, figures with captions | 4 |
| **Del 4 – Tabeller** | Table basics, a full multiplication grid, a small data table | 3 |
| **Del 5 – Tegning med SVG** | Shapes, polygons, a bar chart, plotting a point on axes | 4 |
| **Del 6 – Stil og farve** | The `style` attribute, the `<style>` block, boxes, classes | 4 |
| **Del 7 – Sæt det hele sammen** | The full page skeleton, collapsible quiz answers, a final project | 3 |

**Total: 28 lessons.**

---

## Customising it

All lessons live in a JavaScript array called `lessons`, near the bottom of the
file. Each entry looks like this:

```js
{
  part: "Del 1: Det grundlæggende",   // which part it belongs to
  nav:  "Overskrifter",               // short title (used in the contents list)
  title:"Overskrifter",               // full lesson title
  body: `<p>...forklaring...</p>`,    // the explanation (HTML)
  tags: ["&lt;h1&gt;","&lt;p&gt;"],   // the tags being learned
  code: `<h1>Hej</h1>`,               // the starting example in the editor
  challenge: ["Opgave 1", "Ekstra: ..."]  // the "Din tur" tasks
}
```

A few tips:

- **Change the example names.** The examples use *Mia* and *Maja*; search the
  `code` fields and replace them with your student's name.
- **Add a lesson.** Copy an existing entry, change the fields, and it will
  appear automatically (in its part, in the contents list, and as a section).
- **Showing tag brackets as text.** Inside `body`, `tags` and `challenge`, write
  `&lt;` and `&gt;` instead of `<` and `>` so the brackets display as text
  rather than being treated as real HTML.

---

## Technical notes

- One file; all CSS and JavaScript are inline.
- The live previews run inside sandboxed `<iframe>`s (`sandbox=""`), so whatever
  the student types is isolated, cannot run scripts, and cannot affect the page.
- No external libraries, web fonts, or network requests.
- Progress is not saved — refreshing the page starts everything clean.

---

## Related

- **`javascript-arbejdsbogen.html`** — a follow-on workbook that teaches
  JavaScript (making pages interactive: calculators, loops, a dice game, a quiz)
  once HTML is comfortable.

---

## License

Released under the **MIT License** — see [`LICENSE`](./LICENSE). You are free to
use, share, modify and adapt this, including in classrooms. Remember to replace
the placeholder name in the `LICENSE` file with your own.

> **Choosing a license:** MIT is a simple, permissive choice that covers this
> well. If you would rather license the lessons as educational *content*,
> **Creative Commons Attribution 4.0 (CC BY 4.0)** is a common alternative for
> teaching materials. Either is fine for a classroom resource.
