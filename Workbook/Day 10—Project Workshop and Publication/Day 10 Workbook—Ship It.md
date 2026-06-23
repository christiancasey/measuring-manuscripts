# Day 10 · Ship It

The last day. You finish, publish, present, and help assess each other's work, then consider what it would take to turn a small model into real research.

```{admonition} Companion notebook—*Build space*
:class: tip
Open **Day 10 Notebook—Build space.ipynb** in Colab and run along as you read.

🔧 *TO BUILD:* paste the Colab launch link once the book is on GitHub.
```

## Finishing, not polishing

A finished, published project is worth more than an ambitious, broken one. This is the most useful thing to know on the last day, and it runs against instinct. You have spent two weeks learning techniques, and the temptation now is to add one more—a second dataset, a fancier figure, an extra step you saw on Day 7. Resist it. The extra step is where projects die. It introduces a bug you don't have time to fix, and you end the day with a half-finished thing that runs on your laptop and nowhere else.

The minimum that counts as done is small and exact: one technique, run on real data, producing one result, published at a URL anyone can open. That is a complete project. It is not a small one because it is unambitious; it is small because it is bounded, and a bounded thing can be finished. A concordance of one word across the manuscripts you have is done. A morphological tagging of one passage is done. The Zodiac Glossary you saw on Day 1 began as exactly this kind of bounded thing and grew later.

Protect the build time. For the rest of this class, the work is assembly, not invention. Pull the method you already wrote from the day it belongs to, point it at your final data, save the figure, and publish. If something breaks, cut it rather than chase it. A result you can stand behind beats a result you can only describe.

### Discussion questions

- What is the smallest version of your project that you would still be proud to publish?
- Name one feature you have been tempted to add this week. What would it cost you in time, and what would break if it failed?
- Is there a step in your pipeline you don't fully trust? Could you cut it and still have a complete result?

## Finish and publish

Run your analysis, save the single figure that carries your result, and use the Day 9 steps to put it online.

**Publication checklist:** ☐ live at a URL ☐ title and your name ☐ a one-paragraph description ☐ README ☐ license.

Each item earns its place. The URL is what makes the project real to anyone but you; a notebook on your machine is not published. Your name attaches the work to a person who did it. The one-paragraph description tells a stranger what they are looking at before they read any code—what the question was and what the figure shows. The README is the same courtesy for anyone who opens the repository: what the files are, how to run them, where the data came from. The license tells people what they may do with it; without one, the legal default is that they may do nothing. None of these takes long, and a project missing them looks unfinished even when the analysis is sound.

## How to give a five-minute talk

You will present your project to the room. Five minutes is short, which is a gift: it forces you to say only what matters. A short research talk has four parts, in this order.

- **The question.** One sentence. What did you want to know? Not the whole field, not why manuscripts matter—the specific thing you set out to measure.
- **The method.** What you did, in plain terms. "I aligned four copies of this passage and counted where they disagree." Enough that the room knows what kind of work produced the result, not a tour of your code.
- **The result.** Show the one figure. Point at it and say what it shows. This is the center of the talk; everything else exists to get the audience here and help them read it.
- **One honest lesson.** What you learned, including what didn't work. A line that didn't align, data that was dirtier than expected, a pattern you can't yet explain. This is the most interesting part of any real talk and the part beginners cut first.

Spend most of your five minutes on the result. The single figure should carry it: if you built the figure well, you can put it on screen, say one sentence, and let people look. Talk to a mixed room. Your audience knows philology but not your code, or knows code but not your text; assume neither, and define the one or two terms that matter. The common mistakes are easy to name and easy to avoid—too much setup before any result, no clear result at all, and reading the slides aloud instead of talking to the people in front of you. If you find yourself explaining your fifth methodological choice and haven't shown the figure, stop and show the figure.

### Discussion questions

- State your question in one sentence, out loud. Did it come out clean, or did you need three sentences? What was the extra detail you wanted to add, and can it wait?
- Which single figure carries your result? If you could show only that and say nothing, would the room understand it?
- What is the one honest lesson from your project—the thing that didn't work, or surprised you? Why is that worth saying in public?
- Think of a talk you have sat through that lost you. What did the speaker do, and how will you avoid it?

## Critique

You will hear every project and respond to each. Good critique is specific and generous at once, and both halves take practice. The structure is fixed and worth keeping: for each project, give **one strength, one question, one suggestion**.

- **One strength.** Name something that worked, specifically. "The figure is clear" helps; "putting the two readings on the same axis made the disagreement obvious at a glance" helps more, because it tells the person what to keep.
- **One question.** Ask about something you genuinely don't understand or want to know—a choice, a number, a next step. A real question is a compliment; it means the work made you curious.
- **One suggestion.** Offer one concrete thing they could try. Not "make it better"—"a second text from the same period would show whether this pattern is specific to this scribe."

Specific beats vague every time, in both directions. Vague praise ("nice job") gives the person nothing to build on, and vague criticism ("it's a bit confusing") gives them nothing to fix. Point at the thing.

Separate the work from the person. You are critiquing a concordance, not a colleague. Say "the figure" and "this choice," not "you should have." And when the critique is aimed at you, take it the same way: the goal is a better project, not a defended one. The reflex is to explain why you did what you did—resist it long enough to hear the point. "Good idea, I hadn't thought of that" and a note in your notebook is a better response than a justification. You can always disagree later; you cannot un-hear a defensive reply that closed the conversation early. The people in this room are the easiest expert audience you will ever get. Use them.

### Discussion questions

- Recall the last time someone critiqued your work. Did you listen or defend? What would have helped you listen better?
- What is the difference between a question that helps a project and a question that just tests the presenter?
- When you receive a suggestion you disagree with, what is a good way to respond in the moment without either caving or arguing?

## Where it could go

If you continued, what would you add or ask next—more data, a sharper question, a collaborator, a venue? A solid project from these two weeks could reasonably join a catalog of lightweight digital projects and keep developing.

It is worth being clear about what separates a course project from real research, because the gap is smaller than it looks and made of specific things. Four of them matter most.

- **Scale.** You worked with the data you could gather in two weeks—a handful of witnesses, one passage, a few hundred signs. Research runs the same method across enough material that the result could not have happened by chance. The technique often doesn't change; the amount of data does.
- **The question.** A course project demonstrates a technique. Research answers a question someone in the field actually has and doesn't yet know the answer to. Sharpening "here is a concordance" into "does this scribe prefer this spelling, and is that diagnostic of his dialect?" is the move that turns a demonstration into an argument.
- **The data.** Real research stands on data you can defend—a known corpus, a documented source, transcriptions someone can check. Where your data came from and how clean it is becomes part of the claim, not a footnote.
- **Originality.** Research tells the field something it didn't already know. That bar is lower than it sounds. A careful measurement of a text nobody has measured this way is original, even if the method is borrowed.

The concrete next steps follow from the gaps. Add more data and the result either holds or it doesn't, and either way you learn something. Sharpen the question until it is one a specialist would want answered. Find a collaborator who has the text, the language, or the manuscript access you lack—most real digital humanities work is two people, one who knows the method and one who knows the material. And find a venue: a project page that grows, a poster at a workshop, a short writeup, a place where the work meets readers. The Zodiac Glossary and Isut you saw on Day 1 are both this—a bounded technique, published, then grown over time by someone who kept going.

### Discussion questions

- Looking back over the two weeks, which technique most changed how you think about texts?
- Of the four gaps above—scale, question, data, originality—which is the smallest for your project, and which is the largest?
- What would you need—time, data, collaborators, a venue—to turn your project into something publishable?
- Who in this room, or in your own field, would make a good collaborator on the next version, and what would each of you bring?

```{admonition} Project check-in
:class: note
Name the single next step you'd take with another week.
```
