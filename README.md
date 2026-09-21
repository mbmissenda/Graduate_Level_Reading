# Graduate_Level_Reading

# Skim Smart, Read Deep

**A single-file, self-contained web resource that teaches graduate students when to skim a research paper, when to read it deeply, and how to move from either one into properly cited writing.**

Built for master's students in complementary and integrative health at Notre Dame of Maryland University (ISCI-630a and ISCI-631), and written so that faculty in any applied health or social science discipline can adopt it with light edits.

---

## Who this is for

New master's students routinely arrive with one reading gear — start at the first word, end at the last, feel guilty about anything skipped — and that gear fails in the first week of graduate coursework. The usual faculty response is to tell students to "skim," which most of them hear as permission to read carelessly.

This page treats selective reading as a distinct, teachable technique with its own procedure, and spends most of its length on the judgment that surrounds it: *how do I know which gear this paper deserves, and what can I honestly write on the basis of the reading I actually did?*

It is designed for asynchronous use. A student can work through it alone in about twenty minutes without any instructor present.

---

## Quick start

There are three ways to use this, in increasing order of effort.

**1. Link to it.** Publish it on GitHub Pages (instructions below) and drop the link in your Canvas module. This is the lowest-friction option and the one that works best on phones.

**2. Embed it.** Put an `<iframe>` in a Canvas page pointing at your published URL. See the embedding section for the caveats — there are real ones.

**3. Fork and adapt it.** Everything is in one HTML file with no build step and no dependencies. Change the course names, swap the worked example for a paper from your own syllabus, rewrite the quiz. See the adaptation map.

---

## What's on the page

| # | Section | What it does |
|---|---------|--------------|
| 1 | Skimming isn't cheating | Reframes selective reading as expert behavior, grounded in published research on how scholars at different career stages actually read |
| 2 | Decide before you read | An interactive three-question tool that recommends a reading depth, plus a course-specific scenario the student toggles between |
| 3 | Three gears of reading | Triage skim (2–4 min), working skim (10–20 min), deep read (45–90+ min), each with defined inputs and outputs |
| 4 | When to go deep | Two-column decision criteria, including a callout on why integrative health raises the bar |
| 5 | How to skim | The six-stop reading path with timings, plus five technique cards |
| 6 | Worked example | The six-stop path applied to a real course reading, ending in what that skim does and doesn't license the student to write |
| 7 | Deep reading & notes | Two-pass structure, a copyable note template, and the three-voices note-marking convention |
| 8 | Notes to writing | APA 7th edition: paraphrase, quotation mechanics, in-text reference table, reference list entries |
| 9 | Self-check | Five scenario questions with explanatory feedback |
| 10 | Pocket checklist | Printable, organized by moment rather than by topic |
| 11 | References | Full APA entries for everything cited |

Between the checklist and the references sits a one-click **"Was this page useful?"** widget that sends anonymous feedback to a Google Form you own. It does nothing until you connect it — see *Collecting feedback*.

---

## Why it's built this way

If you plan to adapt the page, these are the design decisions worth preserving — or at least worth breaking deliberately rather than by accident.

**Purpose sets depth, not the paper.** The page's central claim is that reading depth is a property of the student's purpose, not of the document. The same twelve-page trial deserves three minutes or ninety depending on whether the student is surveying a field or building an argument on it. Every section returns to this, and the decision tool exists to make the judgment concrete rather than exhortative.

**Gears, not on/off.** Framing reading as three named gears gives students vocabulary for a decision they were previously making unconsciously and guiltily. It also makes "shift up" a normal move rather than an admission of failure.

**The integrity bridge is load-bearing.** The most important passage on the page is the rule that you cite at the depth you actually read. Skimming taught without that rule produces students who cite effect sizes they saw only in an abstract. If you cut anything, don't cut this.

**The three voices.** Section 7 teaches marking exact words, paraphrase, and the student's own thinking as distinct categories in their notes. Most accidental plagiarism at the master's level is a note-taking failure three weeks upstream of the draft, not an act of dishonesty. This convention addresses the actual cause.

**Methods as the finding.** In complementary and integrative health, "ginger reduced nausea" is unusable without species, plant part, extraction, standardization, and dose. Conventional pharmacological trials often let a reader skim the methods and still roughly trust the headline; ours frequently do not. The page treats intervention characterization as a deep-read trigger in its own right, and marks safety, dosing, interaction, and contraindication claims as never-skim.

**The worked example teaches scope, not just procedure.** Section 6 ends by naming what the example study can and cannot support — it can tell you how those patients reasoned, it cannot tell you how many people think that way, whether the finding generalizes to U.S. patients, or whether the modality works. Source misuse at this level is rarely invention; it is quietly stretching a study past what its design carries. That box is where the page earns its keep.

**The chosen example has no limitations section.** This is deliberate and worth keeping in whatever example you substitute, if you can find one. The skim path tells students to read the limitations paragraph; in this paper there isn't one. The page frames that as a finding *about the paper* rather than a failed skim, and hands the scoping work back to the student. It is the moment where procedure turns into judgment.

---

## Adapting it for your course

Everything lives in `skim-smart-read-deep.html`. Line numbers refer to the file as shipped.

**Course names and branding**

| What | Where |
|---|---|
| Browser tab title | line 6, `<title>` |
| Institution line in the header | line 461, `<p class="kicker">` |
| Course names under the header | line 464, `<div class="hero-meta">` |
| Toggle button labels | line 578, `.cbtn` buttons |
| Footer | line 1193 |
| Feedback settings | lines 1340–1345, `FEEDBACK_PREFILL_LINK` and `PAGE_VERSION` |
| Color palette | lines 13–17, the `--navy` and `--gold` CSS variables |

The palette is defined once as CSS custom properties at the top of the `<style>` block. Changing `--navy` and `--gold` re-themes the entire page. If you substitute your own institutional colors, check them against a contrast tool first — the shipped palette passes WCAG AA at every text size, and it is easy to break that with a lighter gold.

**The course scenarios**

Lines 582–597 hold two `.course-ex` panels, one per course, swapped by the toggle. To add a third course, copy a panel, give it a new `data-course-panel` value, and add a matching `.cbtn` button with the same `data-course` value. The JavaScript picks it up automatically — no other changes needed.

The two shipped scenarios encode a real pedagogical difference worth preserving if it applies to your courses. One assumes assigned readings; the other assumes students find their own sources. Where students do their own searching, triage skimming isn't a time-saving convenience, it *is* the assignment — an assigned reading has already passed through the instructor's judgment, while a search result has passed through nothing but a keyword match.

**The worked example (Section 6)**

Lines 784–855. To substitute a paper from your own syllabus, walk it through the same six stops and rewrite each step with what a student would actually see. The two-column "you can write / you cannot write" box at the end is the part that matters most; write it last, after you've decided what the study's design genuinely supports.

Choose an open-access paper so students can follow along without hitting a paywall.

**The quiz**

Lines 1034–1080. Each question is a `<fieldset>`. Mark the correct option with `data-correct="true"` on its `<input>`; the scoring script counts them automatically, so you can add or remove questions freely. The `<div class="fb">` under each question holds the feedback shown after checking. Write the feedback to explain the reasoning rather than to announce the answer — the distractors were chosen to be tempting, and several of the explanations address why the *wrong* answer appeals.

---

## Embedding in Canvas

**Do not paste the HTML into the Canvas rich content editor.** Canvas sanitizes pasted content and strips `<script>` and `<style>` tags, which would silently remove the decision tool, the course toggle, the quiz, and the entire visual design. What survives is unstyled text. This is the most common way an otherwise working page gets broken.

Publish the file somewhere first, then either link to it or embed the published URL:

```html
<p>
  <iframe src="https://YOUR-USERNAME.github.io/YOUR-REPO/?course=630a"
          title="Skim Smart, Read Deep: reading strategy guide"
          width="100%"
          height="1400"
          style="border:1px solid #dce2ea; border-radius:8px;"
          loading="lazy">
  </iframe>
</p>
```

An honest caveat: this page is long, and an iframe of a long page produces a nested scrollbar inside the Canvas content area. Some students find that awkward, and it is mildly hostile on phones. **A plain link usually serves students better than an embed here.** If you want the page to feel native to the module, consider embedding only as a visual anchor and putting the real link directly beneath it.

The `title` attribute on the iframe is not optional — screen reader users need it to know what the frame contains.

---

## Publishing on GitHub Pages

1. Create a new repository (public, if you want students to reach it without signing in).
2. Add `skim-smart-read-deep.html` to the repository. **Rename it to `index.html`** if you want a clean URL like `https://username.github.io/reading-guide/` rather than one ending in the filename.
3. Go to **Settings → Pages**.
4. Under **Source**, choose **Deploy from a branch**, select `main` and `/ (root)`, and save.
5. Wait a minute or two, then visit the URL GitHub shows you on that settings page.

Updates work the same way: commit a change to the file and the published page refreshes within a minute or so. Students who bookmarked the URL always see the current version, which is one of the real advantages over distributing a file.

---

## Collecting feedback

The page ends with a **Was this page useful? Yes / Somewhat / No** widget. One click records the rating; an optional comment box appears afterward. GitHub Pages can't store anything itself, so responses go to a Google Form you create, and land in its Responses tab and a linked Google Sheet. Setup takes about ten minutes, once.

Until you connect it, the widget still appears and still thanks students, but nothing is recorded — it prints a warning to the browser console instead. **Do the test in step 5 before you post the link.**

### 1. Create the form

At [forms.google.com](https://forms.google.com), start a blank form and add four questions, in any order:

| Question | Type | Notes |
|---|---|---|
| Was this page useful? | Multiple choice | Options must be exactly **Yes**, **Somewhat**, **No**. Leave **Required** off. |
| Course | Short answer | |
| Comment | Paragraph | Optional. Leave this question out and the comment box disappears from the page. |
| Page version | Short answer | |

The rating question must *not* be required. Comments are sent as their own row with the rating left blank, so a student who rates and comments isn't counted twice — a required rating would reject those rows.

### 2. Check three settings — this is where it usually breaks

Under the form's **Settings** tab, **Responses** section:

- **Collect email addresses** → *Do not collect*
- **Limit to 1 response** → *off*
- **Restrict to users in [your organization]** → *off* (only appears on institutional Google accounts)

Each of these requires students to sign in to Google, and any sign-in requirement silently blocks every submission from the page. Nothing will error. Responses simply never arrive.

### 3. Get the pre-filled link

In the form editor, open the **⋮** menu (top right) and choose **Get pre-filled link**. Fill it in like this:

- **Was this page useful?** → select *Yes*
- **Course** → type `COURSE`
- **Comment** → type `COMMENT`
- **Page version** → type `PAGE`

Click **Get link**, then **Copy link**. Those placeholder words are how the page works out which Google field is which, so type them exactly.

### 4. Paste it into the page

Open the HTML file and find this line (line 1340):

```js
var FEEDBACK_PREFILL_LINK = 'PASTE_YOUR_GOOGLE_FORM_PREFILLED_LINK_HERE';
```

Select only the words `PASTE_YOUR_GOOGLE_FORM_PREFILLED_LINK_HERE` and paste your link over them. **Keep the single quotes on both sides and the semicolon at the end.** It should look like this, with your own, longer link:

```js
var FEEDBACK_PREFILL_LINK = 'https://docs.google.com/forms/d/e/1FAIpQL.../viewform?usp=pp_url&entry.123=Yes&entry.456=COURSE';
```

The quotes tell the browser where the link starts and ends; without them the page's script stops working, and the decision tool and quiz break along with the feedback widget. Commit the change.

### 5. Test it

Open your published page in a **private/incognito window**, click a rating, and send a test comment. Refresh the form's **Responses** tab; two rows should appear within a few seconds. Delete them afterward. (The private window matters: the page remembers anyone who has already answered, so your normal browser will show the thank-you instead of the buttons.)

### 6. Post a link per course

Add `?course=` to the link or iframe address you post in each course:

```
https://YOUR-USERNAME.github.io/YOUR-REPO/?course=630a
https://YOUR-USERNAME.github.io/YOUR-REPO/?course=631
```

This does two things. It tags every response with its course, so you can compare them. And it opens that course's scenario in Section 2 by default, so students land on the example written for them. A link without the parameter still works; its responses are tagged `unspecified`.

### Reviewing the responses

**The quick view.** The form's **Responses → Summary** tab draws a chart of Yes / Somewhat / No automatically and lists the comments beneath it. Comment rows leave the rating blank, so the chart counts each student once. Each comment starts with the student's rating in brackets — `[No] The APA section was too long` — so you can read it in context.

**By course.** Click the green **Link to Sheets** icon in the Responses tab. Every submission becomes a timestamped row. To compare courses, select the data and choose **Insert → Pivot table**: put *Course* in **Rows**, *Was this page useful?* in **Columns**, and *Was this page useful?* again in **Values** summarized by **COUNTA**.

**Before and after a revision.** When you meaningfully revise the page, change `PAGE_VERSION` (line 1345) — to `2027-01`, say. Every response records the version it rated, so you can filter the sheet and compare. Changing it also lets students who rated the old version rate the new one.

**Reading it honestly.** A few things to keep in mind:

- Expect small numbers, and a self-selected group: students who loved the page or found it frustrating are likelier to click than the middle. With small counts, the comments usually tell you more than the percentages.
- "Already answered" is remembered per browser, not per person. A student on a second device or in a private window can rate twice, and some browsers don't let embedded pages remember anything at all, so an iframe in Canvas may show the buttons again on a return visit. Treat the counts as approximate.
- The page can confirm a response *left the student's browser*, not that Google stored it; Google doesn't send a reply a web page is allowed to read. The test in step 5 is what confirms the connection works.
- This uses Google Forms' standard submission address, which is widely used this way but isn't an official, documented API. If responses stop arriving someday, that's the first thing to check. Glance at the Responses tab now and then.

**Want an analysis?** Download the sheet as CSV (**File → Download → Comma-separated values**) and bring it to whoever — or whatever — you'd like to help read it.

---

## Accessibility

The page was built to WCAG 2.1 AA and verified rather than assumed:

- Every text/background pair in the palette passes AA contrast; the lowest measured ratio is 5.2:1, against a 4.5:1 requirement.
- Heading levels descend without skipping, so screen reader users can navigate by structure.
- All interactive elements are keyboard reachable, with a visible gold focus ring that meets contrast requirements on every background used.
- Collapsible sections use native `<details>`/`<summary>` rather than custom JavaScript widgets, so they work with assistive technology by default.
- The decision tool and quiz results are announced via `role="status"` and `aria-live`, so a screen reader user hears the recommendation without having to hunt for it.
- No horizontal scrolling at 390px, 768px, or 1100px viewport widths.
- `prefers-reduced-motion` is respected.
- A skip link precedes the header.
- The feedback widget's buttons are real `<button>` elements, its comment box has a visible label, its border meets the 3:1 contrast required for form controls, and after a click, focus moves to the thank-you message so screen reader users hear that their answer was received.
- No images, so no alt text debt — the visual interest comes from typography and layout.
- Print styles expand all collapsed sections, drop the interactive controls, and append URLs after links, so a printed copy is complete and usable.

If you re-theme the page, contrast is the thing most likely to break. Everything else survives color changes.

---

## Suggested assignment pairings

The page teaches a skill but doesn't assess it. A few pairings that make it graded rather than optional:

**Reading log (low stakes, recurring).** Students keep one document with a row per source: full APA reference, gear used, one-sentence takeaway, and whether they might cite it. Collect it twice a term. This makes the gear decision visible and catches the student who is deep-reading everything and drowning, as well as the one skimming everything and citing abstracts.

**Scope statement (attached to any paper).** For their two most important sources, students submit one sentence each: "This study can tell me ______, and it cannot tell me ______." Quick to grade, and it surfaces overreach before it reaches the draft.

**Skim-then-deep comparison.** Students triage-skim an assigned paper, write their takeaway, then deep-read it and write a second takeaway. The reflection is on what changed — which is the most direct way to teach the limits of skimming without simply asserting them.

**Search screening log (for courses where students find their own sources).** Students record how many results they screened, how many survived triage, and why they discarded three specific ones. This assesses the judgment that self-directed source-finding actually requires.

---

## Learning outcomes this supports

Adapt the verbs to your own outcome language:

- Determine appropriate reading depth for a research article based on the reader's purpose and intended use.
- Locate a study's research question, design, sample, findings, and stated limitations efficiently and non-linearly.
- Distinguish claims a study's design can support from claims it cannot.
- Take structured research notes that reliably distinguish quotation, paraphrase, and original thought.
- Integrate sources into scholarly writing using APA 7th edition in-text citation and reference formatting.

---

## Evidence base

The page's central claim — that selective, non-linear reading is what experienced researchers actually do, and that it can be explicitly taught — rests on:

> Hubbard, K. E., & Dunbar, S. D. (2017). Perceptions of scientific research literature and strategies for reading papers depend on academic career stage. *PLOS ONE, 12*(12), Article e0189753. https://doi.org/10.1371/journal.pone.0189753

A survey of 260 undergraduates through faculty. Confidence and skill increased at every career stage, including between postdocs and faculty; readers at different stages valued different sections of the same paper; inexperienced readers found methods and results hardest and undervalued the results section and critical interpretation of data; and experienced researchers overwhelmingly recommended reading selectively rather than straight through. The authors call explicitly for structured instruction rather than vague directions to "read the paper" — which is the gap this resource is built to fill.

The worked example in Section 6 uses:

> Zörgő, S., Purebl, G., & Zana, Á. (2018). A qualitative study of culturally embedded factors in complementary and alternative medicine use. *BMC Complementary and Alternative Medicine, 18*(1), Article 25. https://doi.org/10.1186/s12906-018-2093-0

Open access under CC BY 4.0, so students can reach it freely. The page describes and cites this paper; it does not reproduce it.

Also referenced: the APA *Publication Manual* (7th ed., 2020), and an NCCIH web page used as a group-author citation example. Further reading points to Lie et al. (2016) on master's students and primary literature.

---

## Technical notes

- **One file, no build step.** Open it in a browser and it works.
- **No dependencies** beyond a Google Fonts stylesheet, which degrades gracefully to system serif and sans-serif if blocked or offline. If your institution blocks Google Fonts, delete lines 8–10 and the page still looks fine.
- **No images**, so nothing to lose track of and nothing to host.
- **Network requests:** the Google Fonts stylesheet, and — only if you connect a form and a student clicks a rating — one anonymous submission to your Google Form (a second if they add a comment). Nothing else.
- **What feedback sends:** the rating, the optional comment, the course from the link, and the page version. No name, email, student ID, or Canvas identity. The form doesn't collect email addresses, and Google doesn't show form owners respondents' IP addresses. The comment box asks students not to include their names, but it is free text, so read comments with that in mind. If your institution has a policy on third-party tools for student feedback, check it before you connect the form.
- **Browser storage:** one small entry recording that this browser already rated this version of the page, so returning students aren't asked again. No cookies and no analytics. If storage is blocked, the widget still works; it just can't remember.
- **No tracking of quiz or decision-tool answers.** The self-check is formative and private by design; none of it is sent anywhere. If you need completion data, pair the page with a Canvas quiz rather than instrumenting this one.
- Tested in current Chromium-based browsers at desktop, tablet, and phone widths.

---

## License

Recommended: **Creative Commons Attribution 4.0 International (CC BY 4.0)**, which lets other faculty adapt it for their own courses while keeping attribution intact. Add a `LICENSE` file to the repository to make it official — GitHub will offer CC BY 4.0 as a template when you create one.

If you adapt this page, a line in your footer crediting the original is appreciated but not required beyond what the license specifies.

---

## Questions and contributions

If you adapt this for a different discipline and it works, that adaptation is probably useful to someone else — consider opening a pull request or an issue describing what you changed and why.
