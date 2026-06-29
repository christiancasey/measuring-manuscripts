# Day 2 · Lining Up the Witnesses

A text that survives in several copies is never copied perfectly. The differences between copies are evidence. Today you'll line the copies up to see where they agree and differ, and work out which readings are Chaucer's.

```{admonition} Companion notebook: *Lining up the witnesses*
:class: tip
Open **Day 2 Notebook—Lining up the witnesses.ipynb** in Colab and run along as you read.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/christiancasey/measuring-manuscripts/blob/main/Workbook/Day%202%E2%80%94Textual%20Criticism/Day%202%20Notebook%E2%80%94Lining%20up%20the%20witnesses.ipynb)
```

## What textual criticism is

Before printing, every copy of a text was written out by hand. A scribe sat with one copy in front of him, the *exemplar*, and produced another. The next scribe copied that one, and so on down the generations. No human hand reproduces a few thousand words without slipping, and each slip is itself copied forward into everything that descends from it. After a few hundred years of this, no two surviving copies of a long text agree throughout. The *Canterbury Tales* survives in around eighty manuscripts, and not one pair of them is identical.

Textual criticism is the discipline that works backward through that process. Its first goal is to recover what the author actually wrote, or, where there was never a single original, to reconstruct the earliest recoverable form of the text. Its second goal is to understand the *tradition* itself: how the copies are related, which descends from which, where and how the text changed as it was passed along. The two goals support each other. You reconstruct the original by understanding how the copies drifted from it, and you understand the drift by seeing what the copies did to the original.

The raw material is disagreement. Each surviving copy is a *witness*: it testifies, imperfectly, to what the author wrote. A place where the witnesses disagree is a *variant*. Lay the copies out in a table (one column per position in the text, one row per witness) and the variants are easy to find. CollateX produces that table for you. The rest of the day is about reading it.

### Discussion questions

- Textual criticism has two goals: recover the original, and map the tradition. When might these pull in different directions?
- With only one copy of a text, what can you not learn that several copies would tell you?
- The *Canterbury Tales* has no single original. Chaucer died with it unfinished. What does an editor reconstruct when there was never one author's-hand copy to begin with?
- A printed book has thousands of identical copies. Why does textual criticism have so little to say about most modern books, and so much to say about manuscripts?

## The vocabulary of variants

Once you have witnesses lined up, you need names for the ways they differ. There are only four basic kinds of change a scribe can make at a given spot.

- *Substitution*. One word or phrase replaces another. Yesterday's puzzle is a substitution: where Chaucer wrote *strondes*, copies show *contrees*, *costes*, *shores*, *londes*.
- *Omission*. A word, line, or whole passage drops out. The scribe's eye skips it, or his exemplar already lacked it.
- *Addition*. Something not in the exemplar appears: a word filled in to smooth the sense, a gloss that wandered in from the margin, a pious phrase a scribe added by habit.
- *Transposition*. The same words appear in a different order. *the holy blisful martir* becomes *the blisful holy martir*.

Cutting across these four is a more important distinction. A *substantive* variant changes the sense or the wording: *strondes* versus *contrees* is substantive. An *accidental* variant changes only the spelling, punctuation, or word-division without touching the sense: *knyght* versus *knight*, *worthi* versus *worthy*. Middle English had no fixed spelling, so accidentals are everywhere, and most of them tell you nothing about what the author wrote. They can still be useful (a scribe's spelling habits help locate his dialect), but when you are trying to recover the text, you weigh the substantives and set the accidentals aside. In the notebook, turning on near-matching is exactly this move: it tells CollateX to treat *worthi* and *worthy* as the same word so the genuine variants stand out.

### Discussion questions

- Classify each of these: (a) *seke* for *seeke*, (b) a missing line, (c) *fox* changed to *hound*, (d) *holy blisful* swapped to *blisful holy*.
- Why are accidental variants nearly worthless for recovering the author's text but still useful for placing a scribe?
- An addition and a substitution can look alike in a collation table. How would you tell, for a given column, whether a witness added a word or replaced one?

## How scribal errors arise

Variants are not random noise. Scribes make a small number of recognizable mistakes, over and over, for reasons rooted in how copying actually works: reading a few words, holding them in mind, writing them down, looking back to find the place. Knowing the catalogue lets you spot which reading is the error and which is what the scribe was copying *from*.

- *Eye-skip (parablepsis)*. The scribe's eye loses its place and jumps. This is the general category. The next two are its common forms.
- *Homoeoteleuton*. When two nearby words or lines end the same way, the eye returns from the writing-hand to the wrong one and skips the text in between. Yesterday's *strondes / londes* puzzle is exactly this trap sprung in reverse: the line endings *-ondes* look alike, and one scribe wrote *londes* in the upper line by pulling it down from the lower. Similar endings cause whole lines to vanish, too: if two lines both end in *seeke*, a scribe can copy the first, glance back, land on the second *seeke*, and continue, dropping everything between.
- *Haplography*. A repeated letter, syllable, or word gets written once instead of twice. *that that* becomes *that*.
- *Dittography*. The opposite slip: something written once gets copied twice. *the the martir*.
- *Misreading similar letterforms*. In the script of the period, letters like *c* and *t*, *u* and *n*, long-*s* and *f* are easy to confuse. A scribe reading a worn or hasty exemplar guesses, and a plausible wrong word results. Many substantive variants start as a single misread letter.
- *Dialect "correction."* A scribe rewrites the spelling, and sometimes the words, toward his own dialect, the way a modern typist might quietly change *colour* to *color*. He isn't trying to alter the text. He's normalizing it. The fingerprints this leaves are how you place a scribe geographically.
- *Contamination*. A scribe consults more than one exemplar: copying mostly from one but correcting against another, or switching partway through. Contamination is the great spoiler of textual criticism, because it lets a reading jump sideways between branches that are otherwise unrelated.

Most of these are honest mistakes, not interventions. A scribe trying hard to copy faithfully still skips, still misreads, still normalizes by reflex. That's why the same error type recurs across centuries and languages: it comes from the mechanics of the task, not from any one scribe's carelessness.

### Discussion questions

- Two lines of a poem both end in *londes*. Walk through how homoeoteleuton would make a scribe drop the line between them.
- *strondes* became *londes* in one copy by eye-skip from the line below. Which of the error types above is that, and why is the rhyme the thing that exposes it?
- Why is contamination so much harder to deal with than a simple copying error? What does it do to the idea of a clean family tree?
- A scribe's dialect "corrections" are mistakes from the editor's point of view but evidence from the linguist's. Give an example of each use.

## The editor's reasoning

Knowing how errors arise tells you what *kinds* of variants to expect. The next question is how to choose between them. Editors reason in two complementary ways: from the relationships among the copies, and from the character of the readings themselves.

The first way is *recensio*: reconstructing the family tree of the manuscripts so you can see which readings are early and which are late. The crucial principle is that you build the tree from **shared errors, not shared correct readings**. Two copies that both read *strondes* might agree simply because *strondes* is what the author wrote. Every faithful copy will have it, so it groups nothing. But two copies that share the *same distinctive mistake* almost certainly inherited it from a common ancestor, because the same specific error is unlikely to happen twice independently. Shared errors are the threads that tie the tree together. Trace them and you arrive at the *archetype*: the lost ancestor from which all surviving copies descend, the earliest point the evidence can reach. The archetype is not the author's original (it may already contain errors), but it is as far back as the witnesses let you go.

This is why **the majority is not authority**. A reading can be common because it spread: one early error copied into dozens of descendants outnumbers the true reading preserved in a single conservative copy. The notebook's vote makes this concrete: count the four witnesses and *contrees* wins two to one, yet *contrees* cannot be right, because it doesn't rhyme with *londes*. The lone witness with *strondes* outweighs the majority. Counting copies measures how widely a reading spread, not whether it's original.

The second way reasons from the readings themselves, using rules of thumb about which direction change tends to run.

- *Lectio difficilior potior*: the harder reading is the stronger. Scribes simplify: they swap a rare word for a common one, smooth a rough construction, replace the unexpected with the expected. So when two readings are otherwise balanced, the more difficult one is likelier original, because it's easier to explain how it became the easy reading than the reverse. *strondes* is the rare word, while *contrees* and *londes* are the ordinary ones a scribe would drift toward.
- *Lectio brevior*: the shorter reading is often preferable. Scribes tend to add (a clarifying word, a filled-out phrase) more readily than they cut. A shorter reading is therefore frequently the earlier one. (This is a tendency, not a law. Omission by eye-skip cuts the other way.)

Both rules ask the same underlying question: which reading better explains the existence of the others? You adopt the reading from which you can most plausibly derive the rest by known scribal habits.

### Discussion questions

- Why do shared *errors* tie manuscripts together while shared *correct readings* don't?
- The archetype is the earliest reading the witnesses can reach, but it isn't necessarily the author's original. How can those two differ?
- *strondes* is supported by one copy, *contrees* by two. Apply *lectio difficilior potior*. Which wins, and what does the rhyme add to the argument?
- Give a case where *lectio brevior* and the eye-skip rule point in opposite directions. How would you decide?

## Stemmatics: the family tree of copies

Putting recensio on a systematic footing is the *stemmatic* or *Lachmannian* method, named for the nineteenth-century philologist Karl Lachmann. The idea is to draw the *stemma*, the genealogical tree of the manuscripts, and then let the tree decide variants mechanically wherever it can.

The reasoning is the one you already have, made explicit. Collect the shared errors. Each distinctive error that several copies share marks them as a group descending from a common ancestor that first made that mistake. A mini-example:

- Witness A reads *seken*.
- Witnesses B and C both read *seke*: the same dropped syllable, a distinctive shared slip.
- The simplest explanation is that B and C inherited *seke* from a common ancestor that already had the error. A descends from a different line that kept *seken*.

So B and C share an ancestor that A does not. Find enough shared errors and the groupings stack into a tree. Once the tree stands, many variants resolve on their own: where two branches descend independently from the archetype and they agree, that agreement reaches back to the archetype, and a third branch that disagrees is the outlier. You reconstruct the archetype reading by reading the tree, branch against branch, instead of counting copies.

Texts mutate like DNA, and that's not just an analogy. It's why the method transfers. Copying introduces change: a slip, a correction, a dropped word. This is close enough to biological mutation that the same tree-building tools carry over. Measure how different each pair of witnesses is, and you can build a tree that groups the most similar copies: a first hypothesis about which copy descends from which. The notebook does exactly this with a distance measure and a dendrogram.

It stays a hypothesis, and the method has real limits.

- **Two scribes can make the same easy error independently.** A common, obvious slip (dropping a final *-e*, simplifying a rare word) can crop up in two unrelated copies by chance, and the tree can't distinguish that from shared descent. Only *distinctive* shared errors are safe evidence. Trivial ones mislead.
- **Contamination breaks the tree.** If a scribe copied from two exemplars, his copy belongs to two branches at once, and no single tree fits. Readings leak across branches that should be independent.
- **Lost witnesses leave gaps.** We have what survived, not what existed. Whole branches are gone, and the archetype we reconstruct may sit far below the author's original, with the intervening copies all lost.

A clean stemma is the ideal case. Real traditions (the *Canterbury Tales* among them) are contaminated, full of gaps, and resist a single tidy tree. That doesn't make the method useless. It makes the tree a hypothesis to test against everything else you know, which is where the rest of the course comes in.

### Discussion questions

- In the *seken / seke* mini-example, why does the shared *seke* group B and C, while a shared *seken* would group nothing?
- Why must the shared errors that build a stemma be *distinctive*? What goes wrong if you build the tree from trivial, common slips?
- The two earliest *Canterbury Tales* copies, Hengwrt and Ellesmere, were written by the *same* scribe and still disagree and arrange the tales differently. What does that do to any attempt at a clean stemma?
- Contamination and lost witnesses both break the Lachmannian ideal. Which would worry you more for a heavily copied text like Chaucer's, and why?

## Before you run anything

Read the witness passages and underline two places where the copies disagree. For each, name the variant type (substitution, omission, addition, transposition) and guess which reading is the scribal change and which is being copied *from*. Then predict which two witnesses are most alike before the computer answers.

The lines below are the opening of the *General Prologue* as four early scribes wrote it. The letter þ is just an old way of writing *th* (so *þe* is *the*).

**Hengwrt (Hg)**

> Whan that Aueryll wt his shoures soote \
> The droghte of March hath perced to the roote \
> And bathed euery veyne in swich lycour \
> Of which vertu engendred is the flour

**Ellesmere (El)**

> WHan that Aprill with hise shoures soote \
> The droghte of March hath perced to the roote \
> And bathed euery veyne in swich licour \
> Of which vertu engendred is the flour

**Harley 7334 (Ha4)**

> Whan that aprille with his schowres swoote \
> The drought of Marche haþ perced to þe roote \
> And bathud euery veyne in swich licour \
> Of which vertue engendred is þe flour

**Laud (La)**

> WHan þat Aprill wyþe his schoures soote \
> Þe drought of Marche haþe perced to þe roote \
> And baþes euery veyne in suche lycoure \
> Of whiche vertue engender is þe floure

## Run the collation

Open the notebook and run the cells to produce the alignment table and the variant graph. Find a column where the witnesses split and record the variants. Work through the worked example that names error types. Then build the tree and see which witnesses group together, and try the small stemma-from-shared-errors toy that shows B and C clustering because they share a mistake.

## Read the result

- Which two witnesses agree most often? Did that match your prediction?
- Choose one variant. Which reading would you adopt as editor, and which scribal habit explains the others?
- The vote picks *contrees* and loses. Rhyme and the rarer-word rule recover *strondes* from a single copy. Which principle from today did each step use?

### Discussion questions

- In the line-23 example, Hengwrt reads *was* and Ellesmere reads *were*. Both are the earliest and most authoritative copies, and they disagree. Which would you print, and what would you appeal to: agreement with *compaignye*, agreement with *nyne and twenty*, the relative authority of the copy?
- The dendrogram groups the closest copies. Where it groups two witnesses, how would you check whether that's shared descent or just two scribes making the same easy error?
- The *strondes* puzzle was built to come out clean. Line 23 doesn't. What makes a real variant harder to settle than the textbook one?

```{admonition} Project check-in
:class: note
Does your text survive in more than one version? If so, whose disagreements would be worth mapping? If not, what else could you compare?
```
