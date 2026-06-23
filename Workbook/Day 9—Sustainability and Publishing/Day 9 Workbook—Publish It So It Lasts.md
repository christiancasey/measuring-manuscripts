# Day 9 · Publish It So It Lasts

By the end of today your project will have a real web address. The harder goal is to publish it so that it still works years from now.

```{admonition} Companion notebook—*Getting your work onto the web*
:class: tip
Open **Day 9 Notebook—Getting your work onto the web.ipynb** in Colab and run along as you read.

🔧 *TO BUILD:* paste the Colab launch link once the book is on GitHub.
```

## Why projects die

Think of an online tool you once relied on that no longer exists. Digital scholarship dies in a handful of predictable ways, and knowing them is most of the defense.

**Link rot.** A URL you cited points to nothing. The page moved, the domain lapsed, the site was redesigned and the old addresses were not kept. Studies of scholarly citations routinely find that a large share of cited links are dead within a few years. A footnote that reads "see http://…" is a promise the web rarely keeps.

**Servers that stop being paid for.** Many projects run on a rented server: a machine somewhere that costs money every month and needs someone to log in and update it. When the grant ends, the postdoc leaves, or the card on file expires, the bill goes unpaid and the site goes dark. The work was never on the open web in any durable sense; it was a performance that stopped when the funding did.

**Dependency and version rot.** Code depends on other code—a charting library, a database driver, a particular version of Python. Those pieces keep changing. A project that ran perfectly in 2019 may now throw errors because a library it called was rewritten or removed. Nobody touched your code; the ground under it shifted.

**The bus factor.** "Bus factor" is a blunt question: how many people would have to be hit by a bus before the project becomes unmaintainable? For most scholarly software the answer is one. One person knows how it was set up, where the data lives, which undocumented step makes it work. When they move on, the knowledge leaves with them and the project quietly becomes unfixable.

**Formats that become unreadable.** Data saved in a proprietary or obscure format depends on a particular program to open it. When that program is discontinued or changes, the file becomes a brick. Plenty of 1990s research data now sits in formats nobody can open without effort.

Each of these is avoidable, and the rest of today is about avoiding them.

### Discussion questions

- Think of a digital resource you relied on that disappeared. Which of these causes do you think killed it?
- Once the funding ends, whose job is it to keep a scholarly project running—the author, the institution, or the field?
- Your own project this fortnight has a bus factor of one: you. What would a stranger need in order to take it over?
- Which is the more dangerous kind of loss—a dead link you can see is broken, or a file that still exists but can no longer be opened?

## The durable pattern

The single most useful distinction in this whole topic is **static** versus **dynamic**.

A **dynamic site** builds each page when you ask for it. A live server runs code, often queries a database, and assembles the page on the spot. This is powerful—search boxes, user logins, results computed on demand—but everything that makes it powerful is also what makes it fragile. It needs a running machine, a maintained database, and current code, indefinitely. Stop paying or stop maintaining, and the whole thing stops.

A **static site** is just files sitting on a disk: HTML pages, images, a CSV or JSON of your data. There is no code running to serve them, nothing to query, nothing to keep current. A web server hands the file to the browser unchanged. Static sites are far less flexible, but they are dramatically more durable, cheaper to host, easier to archive, and trivial to copy. A folder of files can be backed up, emailed, dropped into a repository, or burned to a disc. A running server cannot.

For most research outputs—a figure, a table, an interactive chart, a short write-up—static is not a compromise. It is the right answer. You can compute whatever you like on your own machine, then publish the *results* as static files.

**GitHub Pages** is the tool we will use. GitHub is a website where people store code and files in "repositories." Pages is a free feature that takes the files in a repository and serves them as a website at a public address. It is free, it is run by a large company with no reason to take it down, and because the source is just files in a repository, you always hold a complete copy. If Pages vanished tomorrow, your site would survive as the folder it always was.

### Discussion questions

- "Static files, no server" trades flexibility for longevity. When is that trade worth making, and when isn't it?
- What kinds of scholarly tools genuinely need to be dynamic, and could not be reduced to static files?
- GitHub is a private company. Is depending on it any safer than depending on a university server? What protects you here that did not protect the dead projects above?
- A static site can't search itself or update on its own. How would you work around that for a project that grows over time?

## The pieces of a lasting project

A live URL is the start, not the finish. A project that lasts carries a few more things with it.

**A README.** This is a plain-text file that explains the project to a stranger—and the most important stranger is you, three years from now, having forgotten everything. A good README says what the project is, who made it, where the data came from, what the files are, and how to rebuild the result from scratch. It is the cheapest insurance against the bus factor, and the single thing that most often keeps a project usable.

**A license.** A license tells people what they may legally do with your work. This matters more than it sounds. Under copyright law, **"no license" does not mean "free to use"—it means the opposite.** With no license attached, the default is that nobody may legally copy, reuse, or build on your work; they have to ask. An explicit license removes that doubt. For text, images, and data, **CC BY** (Creative Commons Attribution) is the common scholarly choice: anyone may reuse it as long as they credit you. For code, use an **OSI-approved** license such as **MIT**—a short, permissive license that lets others use your code while protecting you from liability. Content and code can carry different licenses in the same project.

**Open, documented data formats.** Save your data in formats that do not depend on any one program: **CSV** for tables, **JSON** for structured data, plain **text** for notes. These are open, human-readable, and openable by countless tools, now and in the future. Avoid proprietary formats as your formats of record. And document the data: a column called `freq` means nothing to a stranger unless something says it holds normalized word frequency per thousand words.

**An archived snapshot for citation.** A live site changes; a citation needs to point at something fixed. Services like **Zenodo** take a frozen copy of your project and mint a **DOI**—a permanent identifier, the same kind of stable address a journal article gets. Zenodo is run by CERN and designed for long-term preservation, so the snapshot remains citable even if your GitHub repository changes or disappears. The pattern is: develop on GitHub, then deposit a frozen, citable version on Zenodo when you reach a milestone.

### Discussion questions

- A README has to be written for a reader who knows nothing. What is hardest to write down because it lives only in your head?
- "No license means nobody may reuse it." Does that change how you read the dead links and orphaned datasets you've run into?
- Why publish both a live GitHub site *and* a frozen Zenodo snapshot? What does each one do that the other can't?
- Why is `freq` a bad column name to leave undocumented, and what would you write to fix it?

## FAIR and metadata, lightly

You will hear the acronym **FAIR**: data should be **F**indable, **A**ccessible, **I**nteroperable, and **R**eusable. Stripped of bureaucracy, it just collects the habits above. *Findable* means it has a stable address and enough description to turn up in a search—a DOI and a clear title do most of this. *Accessible* means someone can actually retrieve it without special permission or dead links. *Interoperable* means it's in open formats other tools can read—CSV and JSON again. *Reusable* means it carries a license and enough documentation that reuse is legal and possible.

**Metadata** is data about your data: title, author, date, description, license, the meaning of each field. It is what lets a project be found and understood by someone who did not make it. You do not need a formal metadata standard for a course project. A clear README, a license file, and a short data dictionary already cover most of FAIR. Treat the principles as a checklist, not a form to fill out.

### Discussion questions

- Of the four FAIR principles, which does your project already satisfy, and which would take the most work?
- "Accessible" does not mean "open to everyone"—it can mean clearly stated access conditions. When might a manuscript project need restricted access?
- Metadata is effort spent for a reader who may never come. What's the argument for doing it anyway?

## Reproducibility

"It runs on my machine" is not enough. A result that exists only as a process on your laptop dies with your laptop. Reproducibility means someone else—again, possibly future-you—can take your inputs and your steps and arrive at the same result.

Two habits get you most of the way. First, **publish static outputs**: the actual figure, the actual table, saved as files, so the result survives even if the code that made it later breaks. Second, **document the steps**: say where the data came from and how to run the analysis, so the result can be regenerated, not just trusted. The notebook for this course is itself the documented procedure—open it in Colab, run it top to bottom, and the same inputs produce the same files every time. That is reproducibility at the scale of a course project: a notebook anyone can rerun, plus the static outputs it produces, plus a README that ties them together.

Use your own running project as the test. By Day 10 you should be able to hand a stranger your repository and have them rebuild your result from the README alone. The Git/GitHub handout and the template repository give you the scaffolding to do it.

### Discussion questions

- Why publish the finished figure as a file rather than only the code that draws it? What does each protect against?
- A notebook "runs on your machine" today. What could stop it from running in five years, and which of today's habits guards against that?
- If you handed your repository to the person beside you right now, where exactly would they get stuck?

## Publish your page

- Follow the Git and GitHub handout and start from the project template.
- Create your repository, add your files, commit, and enable Pages.
- Record your live URL.

> 🔧 *TO BUILD:* the Git/GitHub step-by-step handout, and the project template repository.

```{admonition} Project check-in
:class: note
Is your page live? What still needs to go on it before Day 10?
```
