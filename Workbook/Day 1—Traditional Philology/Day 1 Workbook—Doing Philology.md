# Day 1 · Doing Philology

# Philology

Today is all about philology in the broad sense: what it is, what it's for, why we like it, and where it typically runs into obstacles. One useful way of framing what we are learning in this course is to think of it as tools for breaking through those barriers, so it's a good idea to start by feeling them out ourselves. By the end of today's lesson, you should be able to articulate a wishlist of abilities. What would you do if you could wave a magic wand over a text and learn anything you want to know about it? Computational philology provides the magic, but first we need to figure out what we want to do and why.
## Traditional Philology

*Philology* (from the Greek for "love of words") is the careful study of old texts: what a text says, how it came to be, what it meant to the people who wrote it, and (with some linguistics mixed in) what it can tell us about ancient languages.
### Discussion questions
- What do you already know about philology as a method of study?
- Which academic disciplines rely predominantly on philological methods?
- What are some examples of philological tasks?
- Can you think of any texts that have become known through the work of philologists?
- What can a text tell us that its author never meant to record?
- What is the difference between philology and linguistics?

Middle English is the sweet spot for this. It is strange enough that reading it is real work, but close enough to modern English that you can do that work yourself instead of taking a translator's word for it, but without needing years of language courses. We will spend today on the opening of Chaucer's *Canterbury Tales*, for two reasons: one short passage runs through nearly everything traditional philology does, and the poem survives in some eighty handwritten copies, exactly the material the next nine days need.

```{admonition} Companion notebook—*A text three ways*
:class: tip
Open **Day 1 Notebook—A text three ways.ipynb** in Colab and run along as you read.

🔧 *TO BUILD:* paste the Colab launch link once the book is on GitHub.
```

## The text: the General Prologue

Chaucer wrote the *Canterbury Tales* in the 1390s and left them unfinished at his death in 1400. Here is the opening of the General Prologue in his Middle English, followed by a plain modern rendering. Read the Middle English first.

```
Whan that Aprille with his shoures soote,
The droghte of March hath perced to the roote,
And bathed every veyne in swich licóur
Of which vertú engendred is the flour;
Whan Zephirus eek with his swete breeth
Inspired hath in every holt and heeth
The tendre croppes, and the yonge sonne
Hath in the Ram his halfe cours y-ronne,
And smale foweles maken melodye,
That slepen al the nyght with open ye,
So priketh hem Natúre in hir corages,
Thanne longen folk to goon on pilgrimages,
And palmeres for to seken straunge strondes,
To ferne halwes, kowthe in sondry londes;
And specially, from every shires ende
Of Engelond, to Caunterbury they wende,
The hooly blisful martir for to seke,
That hem hath holpen whan that they were seeke.
```

```
When April with its sweet showers
has pierced the drought of March to the root,
and bathed every vein in that liquid
by whose power the flower is brought forth;
when the west wind too, with its sweet breath,
has quickened in every wood and field
the tender shoots, and the young sun
has run half his course in the Ram,
and the small birds make melody
that sleep all night with open eyes
(so Nature pricks them in their hearts)—
then people long to go on pilgrimages,
and pilgrims to seek foreign shores
and far-off shrines, known in various lands;
and especially, from every shire's end
of England, to Canterbury they travel,
to seek the holy blessed martyr
who helped them when they were sick.
```

## Almost-English

You just read a six-hundred-year-old text and understood most of it. That is the gift of Middle English, and also its trap. Reading Chaucer is a constant, low-grade act of translation, and the words that look most familiar are the ones most likely to deceive you.

### Discussion questions
- A modern edition can keep Chaucer's spelling or modernize it, gloss the hard words or leave them. What does each choice give the reader, and what does it take away?
- Whose voice are you hearing when you read a modernized Chaucer, his or the editor's?
- Can you think of an English word whose meaning has shifted within living memory?

## The life of a text

Textual criticism begins with a basic fact: we rarely have the original. With the *Canterbury Tales* the problem is almost the opposite of a lost text, and no easier.

- *No final version*. Chaucer died with the *Tales* unfinished and never fixed their order. There is no last copy in his own hand. Arguably no single "original" ever existed.
- *Eighty-odd witnesses*. The poem survives in around eighty manuscripts, no two identical. The two earliest and best, *Hengwrt* and *Ellesmere*, were written by the same professional scribe, and even they disagree and arrange the tales differently.
- *A named scribe*. That scribe may have been one *Adam Pinkhurst*, identified in 2004 by Linne Mooney (an identification some scholars now dispute). If it holds, he is the same Adam whom Chaucer scolded in a short poem for careless copying:

  > Adam scriveyn, if ever it thee bifalle / Boece or Troylus for to wryten newe, / Under thy long lokkes thou most have the scalle, / But after my makyng thow wryte more trewe...

  > Roughly: *Adam, if you ever copy out my Boethius or Troilus again, may you get scabs under those long locks of yours unless you write it more faithfully.*

Each copy is a *witness*: it testifies, imperfectly, to what Chaucer wrote. When witnesses disagree (and across eighty copies they disagree constantly), the editor has to weigh them and decide. Doing that by hand across eighty manuscripts is one of the walls this course is built to break through.

### Discussion questions
- If there was never a single "original" *Canterbury Tales*, what is an editor even trying to reconstruct?
- When eighty copies disagree, is the majority reading the best one? When might the majority be wrong?
- Chaucer caught his scribe erring within his own lifetime. How much more drifts in over six hundred years of copying?
- The two best copies were made by the *same* scribe. Why would they still differ?

## Be the editor

Four scribes each copied the same couplet from the General Prologue. No two agree. Work out what line A originally said.

|               | line A ends…                    | line B ends…          |
| ------------- | ------------------------------- | --------------------- |
| **Witness 1** | …to seken straunge *contrees* | …in sondry *londes* |
| **Witness 2** | …to seken straunge *strondes* | …in sondry *londes* |
| **Witness 3** | …to seken straunge *londes*   | …in sondry *londes* |
| **Witness 4** | …to seken straunge *contrees* | …in sondry *londes* |

What did the line say? Write down your best guess and how you would defend it.

With four copies it is hard. With eighty it is hopeless by hand. Tomorrow we line them all up by computer, recover the reading together, and see whether you were right.

## The words that fool you

Middle English is full of words that look like ones you know and mean something else. Read these, write down what you think each bold word means, then check the gloss.

- *Of which *vertú* engendred is the flour*
- *So priketh hem Natúre in hir *corages**
- a man Chaucer calls *nyce*
- a *sely* widow
- a *lewed* man

Glosses:

- *vertú* = power, the force that makes plants grow (not *virtue*)
- *corages* = hearts, spirits, desires (not *courage*)
- *nyce* = foolish, ignorant (not *nice*)
- *sely* = innocent, blessed, or hapless, the ancestor of *silly*
- *lewed* = unlearned, lay, as opposed to clergy (not *lewd*)

Each is a small trap, and the only sure defense is evidence. To know what *sely* meant to Chaucer, you would want every place he uses it, lined up side by side. *If only* we could pull all of those up at once.

## Manuscript as data

![Hengwrt Prologue](https://upload.wikimedia.org/wikipedia/commons/0/02/HengwrtChaucerOpening.jpg)
Take a stab at transcribing the text you see in this photo of the Hengwrt Manuscript. You can use the transcription to help you, partially, but note that they are not identical.
```
Whan that Aprille with his shoures soote,
The droghte of March hath perced to the roote,
And bathed every veyne in swich licóur
Of which vertú engendred is the flour;
Whan Zephirus eek with his swete breeth
Inspired hath in every holt and heeth
The tendre croppes, and the yonge sonne
Hath in the Ram his halfe cours y-ronne,
And smale foweles maken melodye,
That slepen al the nyght with open ye,
So priketh hem Natúre in hir corages,
Thanne longen folk to goon on pilgrimages,
And palmeres for to seken straunge strondes,
To ferne halwes, kowthe in sondry londes;
And specially, from every shires ende
Of Engelond, to Caunterbury they wende,
The hooly blisful martir for to seke,
That hem hath holpen whan that they were seeke.
```

### Discussion questions
- What barriers do you encounter while transcribing this manuscript?
- What might make this task easier?
- What are the new problems that "making things easier" raises?
## Hearing a lost pronunciation

One last obstacle, and a strange one: we can partly recover how Chaucer's English *sounded*, centuries before any recording, from the text alone. Two clues do it.

First, *meter*. Chaucer's line is a ten-beat rhythm, and the opening only keeps that rhythm if you pronounce things we have since dropped: sounding the final *-e* in *soote* (SOH-te) and giving *Aprille* its full three syllables. The meter quietly records a pronunciation we no longer use.

Second, *rhyme*. Some of Chaucer's rhymes no longer rhyme for us, because the long vowels of English shifted afterward (the change called the [Great Vowel Shift](https://en.wikipedia.org/wiki/Great_Vowel_Shift)). Where a rhyme has broken, it tells us the two words once sounded alike, and roughly how.

So a poem on a page turns out to carry its own soundtrack, if you know how to read it.

### Discussion questions
- If meter and rhyme preserve pronunciation, what can the written text never tell us about how Chaucer sounded?
- A scribe who "corrects" Chaucer's spelling toward his own dialect leaves fingerprints. How might those help place him?
- We have no recording of Chaucer, yet we claim to know roughly how he sounded. How much should we trust that?

## Computational Philology

*Computational philology* refers to any attempt to use computers to aid in these tasks. Broadly defined, any philological exercise undertaken with a computer (such as editing a text transcription in Microsoft Word) might be called "computational philology", but in practice the term refers to quantitative studies of texts, often done on a scale that no human could achieve in a reasonable timeframe. If it can't be done by hand but can be done with a computer, it's computational philology.
### Discussion questions
- What are some examples of tasks that computers can do easily but human scholars cannot?
- What might a philologist's wishlist look like? Which facts about a text might they want to have at their fingertips to aid in their studies?
- Where is the line between a tool that merely speeds up a task and one that lets you ask a question you couldn't ask before?
- Editing a transcription in Word fits the broad definition but not the practical one. Why does scale change what we're willing to call computational philology?
- Can you think of a question about a text that would take a person a lifetime but a computer an afternoon?
### What a computer adds

A computer doesn't read a text the way you do, and it isn't meant to. What it offers is scale and precision. Given one word, it can find every place that word appears across thousands of texts. Given one sign, it can rank the most similar shapes out of thousands of manuscripts. None of this replaces close reading. It answers questions close reading can't approach on its own. In the best cases, the answers that computers provide lead to new and more interesting questions, and these send us back to the original texts, armed with new facts, to investigate further.
### Trying it out in Colab

Now we'll move to the Notebook to see some basic computational techniques in action. 

```{admonition} Companion notebook—*A text three ways*
:class: tip
Open **Day 1 Notebook—A text three ways.ipynb** and scroll to *Measuring: which words repeat?*.

🔧 *TO BUILD:* paste the Colab launch link once the book is on GitHub.
```
### Discussion questions
- Of the demonstrations you saw, which one surprised you the most? Why?
- Which demonstration would you most want to run on a text you care about?

## Your project

The course ends with one project of your own: a single technique, built and published online over the two weeks. Each day closes with a short check-in, so the project takes shape as you go rather than all at once at the end. Some options you might consider (but are not limited to) are:

- a *concordance*: every occurrence of a word, shown in context
- a *variant alignment*: several copies of one text, lined up
- a *morphological tagging* demonstration
- a *paleographic clustering* of sign shapes
- a *diachronic frequency* comparison across time

You don't need to choose yet. It's enough to know which one interests you, and what text, script, or language you'd want to work on.
### Discussion questions
- What texts do you plan to work with in this course?
- What kinds of questions would you like to investigate?