# Day 8 · From Curiosity to Project

A technique isn't a project. Today you turn an interest into a question you can actually answer, with a method, a dataset, an expected result, and a clear sense of the method's limits. This is where the project gets its structure.

```{admonition} Companion notebook: *Your project, in skeleton*
:class: tip
Open **Day 8 Notebook—Your project, in skeleton.ipynb** in Colab and run along as you read.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/christiancasey/measuring-manuscripts/blob/main/Workbook/Day%208%E2%80%94Research%20Questions/Day%208%20Notebook%E2%80%94Your%20project%2C%20in%20skeleton.ipynb)
```

## From topic to question

A topic is a region you find interesting. A question is something with an answer. "Scribal variation in the *Canterbury Tales*" is a topic. You could spend a career in it. "Do the Hengwrt and Ellesmere copies disagree more on rare words than on common ones?" is a question, because there's a fact of the matter and a way to find it.

The test is simple. A question is answerable when you can name three things in advance: the data you'd look at, the measurement you'd take, and the result that would settle it one way or the other. If any of the three is missing, you still have a topic. "Was this scribe careless?" fails the test as written. There's no stated data, no measurement, and no result that would count as an answer. "Does this scribe's letter-spacing vary more than a control scribe's, on the same passage?" passes: a dataset (two copies of one passage), a measurement (spacing per line), and a comparison that comes out one way or the other.

Most projects start life as topics. The work of Day 8 is the conversion. You are not looking for the most important question. You are looking for the smallest honest one that still interests you.

### Discussion questions

- Name a topic you care about, then try to carve one answerable question out of it. What did you have to throw away to make it answerable?
- For your question, can you state the data, the measurement, and the deciding result? Which of the three is hardest to pin down?
- Is a small, answerable question always worth more than a large, vague one? When might the vague version be the better thing to chase?

## Scoping to two weeks and a laptop

The honest constraint is time and equipment. You have a few days, a laptop, Colab, and the techniques from Days 2–7. That rules a lot of things out, and it's better to find that out now than on Day 9.

Three limits matter most. **Data you can get.** If the manuscripts you want aren't transcribed, photographed, or downloadable, the project can't run, however good the question. Eighty *Canterbury Tales* witnesses exist. You can reach a handful in clean transcription, not all eighty. **Data small enough to handle.** A method that's instant on ten lines may stall on ten thousand pages, and you won't have time to optimize it. **A method you've already seen work.** Day 8 is not the day to learn a new technique from scratch. Pick from what's on the shelf.

Scoping down is not a defeat. A question about one scribe's spelling in one tale is a real result. A question about "medieval scribal practice" is a literature review you don't have time to write. When in doubt, shrink the dataset, shrink the time span, shrink the claim, and keep the question.

### Discussion questions

- What's the smallest dataset that would still let you answer your question? Could you prototype on ten lines before scaling up?
- Which of the three limits (data you can get, data small enough to handle, a method you've seen work) is most likely to bite your project?
- If you had to cut your project in half today, what would you cut, and what would survive?

## Operationalizing

An abstract claim has to become something countable before you can test it. This translation step is called operationalizing, and it is where most of the rigor in a quantitative project lives. You take a word that means many things ("careless," "formulaic," "distinctive") and you commit to one specific number that stands in for it.

Take "this scribe is careless." On its own it can't be measured. Careless about what? You choose a stand-in: variation in sign shape across lines that should be identical, or the rate of corrected errors, or inconsistency in how one word is spelled. Each is a defensible reading of "careless," and each is countable with a technique you already have. The number won't capture everything the word means (a scribe can be careless in ways that don't show up in spacing) but it gives you something to test, and it forces you to say exactly what you meant.

Worked examples from this course's own toolkit:

- **"This tale is more formulaic."** Operationalize as repeated *n*-grams per thousand words (Day 3), or as lower entropy in the word distribution (Day 6). Higher repetition, lower entropy: that's "formulaic," made countable.
- **"These two copies are close."** Operationalize as the number of agreeing readings in a collation (Day 2), or as cosine similarity between their feature vectors (Day 7). A percentage of agreement is a number you can defend.
- **"These two scribes write the same letter differently."** Operationalize as the distance between the average shapes of that letter, measured the way Day 4 measures sign shapes. A bigger distance is a bigger difference.
- *"This vowel shifted."* Operationalize as a change in formant values between two pronunciations (Day 5). The vowel space moves, and the movement is a number.

The same pattern shows up with hieratic. "Hieratic is messier than hieroglyphic" only becomes a research result once "messier" is fixed to a specific measure: say, the spread of shapes for one sign across a corpus. Until then it's an impression.

> 🔧 TO BUILD: drop in a worked operationalization from the hieratic sign-variation work: the abstract claim, the chosen measure, and one number that came out of it.

### Discussion questions

- Pick an abstract word you'd use about your material: "careless," "ornate," "conservative," "archaic." What's one number that could stand in for it? What does the number miss?
- Two people operationalize "formulaic" differently, one with *n*-grams and one with entropy. Could they reach opposite conclusions? Does that mean the question was ill-posed?
- Your operationalization is a choice. How would you defend yours to a skeptic who thinks the word means something else?

## Hypotheses and deciding the measure first

A hypothesis is a statement of what you expect, made before you look. It does two jobs. It commits you to an outcome, so the result can surprise you, and a result that can't surprise you isn't worth collecting. And it gives the measurement a target, so you know in advance what would count as confirmation and what would count as refutation.

The discipline that makes this work is deciding the measure before you see the result. You fix the operationalization, the dataset, and the threshold first. Then you run it. If you choose the measure after seeing the data, you will, without meaning to, choose the one that flatters the answer you wanted. This is called fishing, and it is the single easiest way to fool yourself in a quantitative project. The defense is order: hypothesis, then measure, then data, then result.

State the hypothesis sharply enough that it could fail. "Hengwrt and Ellesmere agree on more than 90% of substantive readings in the General Prologue" is a real hypothesis. Run the collation and it's above or below 90%. "The two copies are similar" is not, because no result could contradict it.

And say, before you run anything, what would change your mind. If the answer is "nothing would," the project is an exercise in confirmation, not inquiry. Write the disconfirming result down next to the hypothesis so you can't quietly forget it later.

### Discussion questions

- Write your hypothesis as a sentence that could turn out false. What specific result would falsify it?
- What would change your mind? If you can't name a result that would, what does that tell you about the question?
- Why is it so tempting to pick the measure after seeing the data, and what concretely stops you from doing it?

## Choosing a method to fit the question

The method should follow from the question, not the other way around. A common failure is starting from a technique you liked and bending a question to fit it. Start instead from what you want to know, and let that point at one of the course's techniques.

A rough map from question-types to methods:

- **"Where does this word appear, and in what company?"** → concordance and frequency counts (Day 3).
- **"Where do these copies agree and disagree?"** → collation and alignment (Day 2).
- **"Which of these shapes are most alike?"** → shape or feature similarity (Day 4).
- **"How did this sound, and how did it change?"** → formants and the vowel space (Day 5).
- **"How predictable, repetitive, or constrained is this text?"** → entropy and information measures (Day 6).
- **"How do these many items group when I can't eyeball them all?"** → clustering and projection (Day 7).

If your question doesn't map cleanly onto one of these, that's useful information. Either the question needs sharpening until it does, or it needs a method this course didn't teach, in which case scope tells you to pick a different question for now.

### Discussion questions

- Which technique does your question point at? Did you arrive at the question first, or the technique first, and does the order worry you?
- Could your question be answered two different ways? What would each method catch that the other would miss?
- Is there a question you'd love to ask that none of the six methods can reach? What's blocking it: data, method, or scope?

## Common failure modes

Most projects that stall do so for one of a few predictable reasons. Knowing the shapes in advance helps you catch yourself.

- *Scope creep*. The question quietly grows. One scribe becomes all the scribes. One tale becomes the whole poem. Each addition feels small. Together they make the project unfinishable. Fix the scope in writing and treat any expansion as a decision, not a drift.
- **A question no available data can answer.** The question is fine. The data to answer it don't exist, or you can't reach them in two weeks. Check that the data are in hand *before* you fall in love with the question.
- *Confirmation bias*. You measure until the result agrees with you, then stop. Deciding the measure first is the structural defense. Naming the disconfirming result is the second.
- **Confusing a tool for a question.** "I'll make a concordance" is a tool, not a question. A concordance of *what*, to find out *what*? The tool is the means. The question is "does *sely* shift from 'blessed' to 'hapless' across these texts?" If you can't say what the tool is for, you don't yet have a project.

### Discussion questions

- Which of these four failures is your project most exposed to right now? What's one concrete thing you'll do today to guard against it?
- "I'll build a concordance" hides a question. What's the actual question behind the tool you're drawn to?
- Have you ever kept measuring until you got the answer you wanted? How would you know, from the outside, that someone had done that?

## Naming one honest limitation

Every result has a soft spot. The strongest version of your project names it out loud, up front, before anyone else does. This isn't modesty for its own sake. An unnamed limitation is one you haven't thought about, and it's the one that sinks you in discussion.

A limitation is specific. Not "this might be wrong," but "I have only three witnesses, so I can't tell a scribal habit from an accident," or "my sign-shape measure ignores ink thickness, which may carry some of the difference I'm attributing to the hand," or "the transcription I'm using already normalizes spelling, so any spelling result is partly the editor's, not the scribe's." Each names the exact thing that could undercut the result, which also tells you what you'd need to fix it.

Write your one honest limitation before you have a result, not after. The ones you find afterward are too easy to discount.

### Discussion questions

- What's the single most likely reason your result could be misleading? State it in one specific sentence.
- Does naming a limitation weaken a project or strengthen it? Whom is the limitation for—you, or your reader?
- If you had one more week, would you spend it fixing your limitation or sharpening your question? Why?

## Your project spec

Fill this in as completely as you can. Rough answers are fine, and a partner will help sharpen them.

1. *The interest*: what are you curious about?
2. *The answerable question*.
3. *Hypothesis*: what you expect, and why.
4. *Dataset*: what data, from where, and how much.
5. *Method*: concordance, alignment, clustering, formants, entropy, and so on.
6. *The result*: what will show it?
7. *One real limitation*: what could undercut it?

Then trade with a partner: is the question answerable with that dataset, and what's the biggest risk to finishing?

### Discussion questions

- Read your partner's spec back to them in one sentence. Did you get the question right? If not, the spec needs work.
- Where is your partner's biggest risk to finishing: data, method, scope, or time? What would you cut first?
- Which of the seven lines was hardest for you to fill in? That's usually where the project is weakest.

```{admonition} Project check-in
:class: note
Leave today with a one-page outline and a checklist for Day 9: data in hand, method prototyped, a first plot.
```
