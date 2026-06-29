# Day 0 · A Taste of the Course

This is a single ninety-minute sample of a two-week course, *Measuring Manuscripts*. We are going to move fast and skip most of the *how*. The point today is to show the *sort of thing* the course does: turn old texts and scripts into things you can count, then ask questions no amount of reading by hand could settle. A dozen quick demonstrations on real manuscripts, from counting words to teaching a machine to read handwriting. No programming background is needed, and everything runs in your browser.

*Philology* (from the Greek for "love of words") is the careful study of old texts: what a text says, how it came to us, and what it meant to the people who wrote it. *Computational philology* is the same craft with a computer doing the parts no person can do by hand. Given one word, it finds every place that word appears across thousands of texts. Given one sign, it ranks the most similar shapes out of thousands of manuscripts. It does not replace reading. It answers questions reading cannot reach alone, then sends you back to the text with new facts.

```{admonition} Companion notebook: *A Taste of the Course*
:class: tip
Everything below happens live in the notebook. Open it in Colab and run the cells as we go.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/christiancasey/measuring-manuscripts/blob/main/Workbook/Day%200%E2%80%94Teaser/Day%200%20Notebook%E2%80%94A%20Taste%20of%20the%20Course.ipynb)
```
## First, be the editor

We rarely have the original of anything. Chaucer's *Canterbury Tales* survive in about eighty handwritten copies, no two identical, and none in his own hand. Each copy is a *witness*: it testifies, imperfectly, to what Chaucer wrote. When witnesses disagree, someone has to weigh them and decide. That is *textual criticism*.

Try it. Four scribes copied the same couplet. No two agree. What did line A originally say?

|               | line A ends…                  | line B ends…        |
| ------------- | ----------------------------- | ------------------- |
| **Witness 1** | …to seken straunge *contrees* | …in sondry *londes* |
| **Witness 2** | …to seken straunge *strondes* | …in sondry *londes* |
| **Witness 3** | …to seken straunge *londes*   | …in sondry *londes* |
| **Witness 4** | …to seken straunge *contrees* | …in sondry *londes* |

The couplet rhymes, and line B ends in *londes*, so line A should rhyme with it. *strondes* (Witness 2) rhymes and is the original. *contrees* is the majority, two votes out of four, and it does not rhyme, so it loses despite the count. *londes* (Witness 3) just repeats the rhyme word a line early, a copying slip. The majority can be wrong, and counting witnesses is not the same as weighing them. With four copies this is hard. With eighty, only a computer can line them all up.

## The tour

What follows is a run through the notebook. Each stop is a real method from the course, shown in a few seconds.

### Part 1 · Text as data

We load the opening of the General Prologue and turn it into something countable, then do the same to the whole text.

- *Counting.* A passage becomes a list of words. Tokens are running words, types are distinct words, and their ratio is a first measure of vocabulary.
- *Zipf's law.* Rank every word by frequency and a strikingly regular curve appears: a few words do most of the work, a long tail shows up once each. Counting found a pattern nobody put there.
- *A concordance.* Pick any word and pull up every place it occurs, in context. Philologists once spent years building these by hand.
- *The formulae.* Count runs of two and three words and a text's set phrases surface on their own. In Chaucer's portraits, *he was a* opens one pilgrim after another.
- *One number for a text.* Shannon entropy reduces a whole text to its average surprise per word. Shuffle the words and the number does not budge, which shows exactly what the measure does and does not see.

### Part 2 · Weighing the witnesses

- *Two copies disagree.* The computer shows you exactly where two versions of a line part, and the rhyme settles which reading is Chaucer's.
- *Four witnesses at once.* Line up the same line as four real scribes wrote it, word by word, and the disagreements (mostly spelling) jump out. A computer does this across eighty manuscripts in one pass.

### Part 3 · Script as data

This is where the course turns from text to handwriting, and where computation does things no eye can.

- *One sign, many hands.* A letter is not one shape. We load real drawings of a single ancient Egyptian sign, *G17* (the owl), and you can see at a glance that no two scribes drew it the same way twice.
- *How a machine reads handwriting.* This is the core of *handwritten text recognition* (HTR), the technology that turns photographed manuscripts into searchable text. The teaching example is handwritten digits: we load seventy thousand of them, train a classifier on a few thousand, and watch it read thousands it has never seen at over ninety percent accuracy. The interesting part is the digits it gets wrong, which are the ones a person would squint at too.
- *From digits to scribes.* The very same method, run on the owls, sorts them into recurring forms, one of which appears almost only in a single text. This reproduces a published result about scribal habits.

### Part 4 · Even the sound

- *Building a voice.* A vowel is just a buzz shaped by the mouth. The notebook builds the five vowels from a handful of numbers each and plays them aloud, then slides one vowel from the back of the mouth to the front by turning a single dial. You hear speech assembled from numbers.
- *A lost pronunciation.* We have no recording of Chaucer, yet his meter and broken rhymes record roughly how his English sounded. The long vowels later slid around the mouth in a chain called the *Great Vowel Shift*, and the notebook draws that movement through the same vowel space.
- *A dead language, measured.* Coptic has not been spoken natively in centuries, and scholars still argue over its vowels. Measure real recordings and each Coptic letter lands at a definite point on the chart. The synthesizer then rebuilds each vowel from those numbers, so you can hear it. Real audio, an ancient language, its vowels recovered and spoken again.

### Discussion questions

- Which of these would you most want to run on a text, script, or language you care about?
- Where could a computer answer in an afternoon something that would take a person a lifetime?
- The machine that reads digits also makes mistakes. Where would you still want a human checking its work?

## Real projects to look at

- [The Zodiac Glossary](https://zodiac-edit.fly.dev/), a digital edition lining up astronomical terms across languages
- [Isut](https://isut.uliege.be/), the hieratic sign database the owl data come from
- [Hieratic Sign Complexity over Time](https://writingthroughtime.github.io/hieratic-complexity-and-sign-names/), an interactive companion to a printed paper