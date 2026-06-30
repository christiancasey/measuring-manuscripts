# Day 0 · A Taste of the Course

This is a ninety-minute sample of a two-week course, *Measuring Manuscripts*. Its aim is a modest one. It does not set out to teach the methods, which is the work of the course itself, but only to show the kinds of things they make possible. We will run a dozen of them on real manuscripts and watch what they produce, from counting the words of a poem to teaching a machine to read handwriting. No background in programming is assumed, and everything runs in a web browser.

### Getting started questions

- What does Philology mean to you?
- Can you already think of some ways we might use computers to do it?
- What do we gain with computational approaches and what do we lose?

*Philology*, from the Greek for "love of words", is the careful study of old texts: what a text says, how it has come down to us, and what it meant to the people who wrote it. *Computational philology* is the same craft carried out with a computer doing the parts no person could manage by hand. Given a single word, it can find every place that word occurs across thousands of texts. Given a single sign, it can rank the most similar shapes among thousands of manuscripts. It is not a substitute for reading. It answers questions that close reading cannot reach on its own, and returns us to the text with new facts in hand.

```{admonition} Companion notebook: *A Taste of the Course*
:class: tip
Everything below happens live in the notebook. Open it in Colab and run the cells as we go.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/christiancasey/measuring-manuscripts/blob/main/Workbook/Day%200%E2%80%94Teaser/Day%200%20Notebook%E2%80%94A%20Taste%20of%20the%20Course.ipynb)
```

## First, be the editor

We rarely possess the original of anything. Chaucer's *Canterbury Tales* survive in roughly eighty handwritten copies, no two identical and none in his own hand. Each copy is a *witness*, an imperfect testimony to what he wrote, and where the witnesses disagree someone must weigh them and decide. That work is *textual criticism*.

Consider a small instance of it. Four scribes copied the same couplet, and no two of them agree. What did the first line originally say?

|               | line A ends…                  | line B ends…        |
| ------------- | ----------------------------- | ------------------- |
| **Witness 1** | …to seken straunge *contrees* | …in sondry *londes* |
| **Witness 2** | …to seken straunge *strondes* | …in sondry *londes* |
| **Witness 3** | …to seken straunge *londes*   | …in sondry *londes* |
| **Witness 4** | …to seken straunge *contrees* | …in sondry *londes* |

The couplet rhymes, and the second line ends in *londes*, so the first line ought to rhyme with it. *strondes*, in Witness 2, does rhyme, and is the original reading. *contrees* is the majority, two of the four copies, and yet it does not rhyme and so cannot be right. That is worth pausing over: the majority reading is not always the correct one, and counting the witnesses is not the same as weighing them. *londes*, in Witness 3, simply repeats the rhyme word a line too early, an ordinary slip of the eye. With four copies the reasoning is manageable by hand. With eighty, only a computer can hold them all up to the light at once.

## The tour

What follows is a walk through the companion notebook. Each stop is a method drawn from the course itself, shown here in a few seconds rather than taught in full.

### Part 1 · Text as data

We take the opening of the *General Prologue*, turn it into something countable, and then do the same to the whole text.

- *Counting.* A passage becomes a list of words. The running words are *tokens*, the distinct ones *types*, and the ratio between them is a first, rough measure of how varied the vocabulary is.
- *Zipf's law.* Ranked by frequency, the words of a text fall along a strikingly regular curve, a few of them carrying most of the burden and a long tail occurring once each. The pattern is not one we impose. Counting reveals it.
- *A concordance.* Every occurrence of a chosen word, gathered together with its context. Scholars once spent years compiling these by hand.
- *The formulae.* Counting short runs of words brings a text's set phrases to the surface, among them the *he was a* that opens one pilgrim portrait after another.
- *One number for a text.* *Shannon entropy* reduces a whole text to its average surprise per word. Shuffling the words leaves it unchanged, which shows precisely what the measure registers and what it ignores.

#### Discussion questions

- How can we use these sorts of data to understand a text better?
- How might they mislead?

### Part 2 · Weighing the witnesses

- *Two copies disagree.* The computer locates exactly where two versions of a line part, and the rhyme decides which reading is Chaucer's.
- *Four witnesses at once.* The same line as four scribes wrote it, aligned word by word, so that the disagreements stand out. What is feasible by hand for four copies a computer performs for eighty.

#### Discussion questions

- What is an *Urtext* and why would we want such a thing?
- What are some alternatives to viewing texts this way?

### Part 3 · Script as data

Here the course turns from the words of a text to the shapes that carry them, and computation begins to do what no unaided eye can.

- *One sign, many hands.* A letter is not a single shape but a range of them. We load real drawings of one ancient Egyptian sign, *G17* (the owl), and the variation is plain at a glance.
- *Reading handwriting by machine.* This is *handwritten text recognition* (HTR), the technology that turns photographed manuscripts into searchable text. The standard example is handwritten digits: seventy thousand of them, a classifier trained on a few thousand, and an accuracy above ninety percent on digits it has never seen. The instructive part is where it errs, on the very figures a person would also find ambiguous.
- *From digits to scribes.* The same method, applied to the owls, sorts them into recurring forms, one of which appears almost only in a single text. This reproduces a published result about scribal habit.

#### Discussion questions

- What are the advantages of OCR/HTR? The disadvantages?
- Why might we want to quantify sign shapes?
- Why and how do handwritten scripts change?

### Part 4 · Even the sound

- *Building a voice.* A vowel is a buzz shaped by the mouth. The notebook builds each of the five vowels from a few numbers and plays it aloud, then slides one vowel from the back of the mouth to the front by altering a single value, so that speech can be heard assembled from numbers.
- *A lost pronunciation.* We have no recording of Chaucer, and yet his meter and his broken rhymes preserve a rough record of how his English sounded. The long vowels later migrated around the mouth in the chain of changes called the *Great Vowel Shift*, which the notebook draws as movement through the vowel space.
- *A dead language, measured.* Coptic has had no native speakers for centuries, and its vowels remain disputed. Measured from real recordings, each Coptic letter settles at a definite point on the chart, and the synthesizer rebuilds each vowel from those measurements so that it can be heard once more.

#### Discussion questions

- How much can we ever really know about the spoken reality of a dead language?
- When hypothesizing about ancient phonetics, how can we check our work?

- How do these risks compare to those of traditional philology?

## Real projects to look at

- [The Zodiac Glossary](https://zodiac-edit.fly.dev/), a digital edition lining up astronomical terms across languages
- [Isut](https://isut.uliege.be/), the hieratic sign database the owl data come from
- [Hieratic Sign Complexity over Time](https://writingthroughtime.github.io/hieratic-complexity-and-sign-names/), an interactive companion to a printed paper

### Wrapping up questions

- Where might a computer answer in an afternoon a question that would take a person a lifetime?
- Which of these techniques would you most want to run on a text, script, or language of your own?
- What are the risks of these approaches and how do we mitigate them?
