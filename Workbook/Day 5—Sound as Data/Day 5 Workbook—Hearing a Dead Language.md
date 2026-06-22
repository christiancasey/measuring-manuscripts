# Day 5 · Hearing a Dead Language

No one has heard Chaucer's English spoken, and no one has heard Coptic spoken in centuries. Yet we can say a surprising amount about how both sounded. Today we work out how, starting from a poem and ending at a measurement.

```{admonition} Companion notebook—*Measuring vowels*
:class: tip
Open **Day 5 Notebook—Measuring vowels.ipynb** in Colab and run along as you read. You'll build a vowel from scratch, listen to it, then measure it back.

🔧 *TO BUILD:* paste the Colab launch link once the book is on GitHub.
```

## How do we know Chaucer rhymed?

Yesterday's text already left clues. Chaucer writes in couplets, in a steady ten-beat line—but the rhythm only works if you pronounce things we have since dropped. The opening keeps its beat only when you sound the final *-e* in *soote* (say it *SOH-tuh*) and give *Aprille* its full three syllables. The meter records a pronunciation we no longer use.

Rhyme records more. Some of Chaucer's rhymes no longer rhyme for us, because the vowels of English shifted in the centuries after him—the change called the Great Vowel Shift. Where a rhyme has broken on the page, it tells us the two words once sounded alike, and roughly how.

So the text carries evidence about its own sound. To use that evidence, though, we need a way to talk about sound precisely. That's what phonetics gives us.

### Discussion questions
- The meter only works if the silent *-e* wasn't silent. Is that a discovery about the language, or just a convenient assumption that makes the lines scan?
- If two of Chaucer's words rhyme on the page but not in your mouth, which one changed—the spelling, or the sound?
- We will never have a recording of Chaucer. What would even count as evidence that a reconstruction of his pronunciation is right?

## A crash course in phonetics

Phonetics is the study of speech sounds as physical events: how the body makes them, and what they look like as sound. None of it needs prior training. You already do all of it every time you talk.

**Speech is moving air.** The lungs push air up through the throat; the vocal folds in the larynx can buzz or stay open; and above them the tongue, lips, teeth, and palate shape the stream into separate sounds. Those movable parts are the **articulators**.

**Consonants** are pinned down by three things:

- **place**—where the air is squeezed or stopped: the lips, the teeth, the ridge behind the teeth, the hard palate, the soft palate, the throat;
- **manner**—how it's squeezed: fully stopped (as in *p*), forced through a narrow gap (as in *s*), and so on;
- **voicing**—whether the vocal folds are buzzing. *s* and *z* share place and manner; the only difference is that *z* is voiced. Put a finger on your throat and hold "sssss," then "zzzzz." You'll feel it switch on.

**Vowels** are open sounds, shaped mainly by where the tongue sits. Two dimensions carry most of it:

- **height**—how high the tongue rides (high in *beet*, low in *bat*);
- **backness**—how far forward or back (front in *beet*, back in *boot*);

plus **rounding**—whether the lips are pursed (they are in *boot*).

**The IPA.** Ordinary spelling is a poor guide to sound. English spells one sound many ways and one letter many sounds—*through, though, tough, cough*. The International Phonetic Alphabet fixes one symbol to one sound, so [k] always means the sound in *cat*, in any language. Phoneticians lay the vowels out on a chart shaped like the mouth: high and front at the top left, low and back at the bottom right. That chart is the map we'll drop real measurements onto in a moment.

![IPA Chart](https://www.internationalphoneticassociation.org/sites/default/files/IPA2005_3000px.png)

### Discussion questions
- Say "buzz" and "bus" with a finger on your throat. What is the single difference between *z* and *s*?
- Why is ordinary spelling a bad way to record pronunciation? Give an example from a language you know.
- The vowel chart is shaped like the inside of the mouth. Why might that be the natural way to arrange them?

## Vowels as two numbers

Here is the bridge from the body to the data. When you hold a vowel, the cavity of your mouth resonates at particular frequencies, called **formants**, and the two lowest ones are enough to tell vowels apart. The first, **F1**, tracks tongue height—a low tongue gives a high F1. The second, **F2**, tracks how far forward the tongue is—a front tongue gives a high F2.

Plot F1 against F2 and every vowel becomes a point. A speaker's vowels form a cloud, the **vowel space**, shaped like that same chart from the mouth. Different speakers and dialects shift the cloud around, which is exactly what makes it useful: the shape is a fingerprint of how someone speaks. The notebook measures formants from a real sound and draws the space.

### Discussion questions
- If two speakers say "the same vowel" but get different formant numbers, in what sense is it the same vowel?
- F1 and F2 capture vowel identity well. What about a vowel do they leave out?

## The Great Vowel Shift

Now we can say precisely what changed between Chaucer and us, because the change was a movement through exactly this space. Over roughly 1400–1700 the long vowels of English all shifted, and they shifted in a chain.

Chaucer's long vowels had their "continental" values—the ones the letters still carry in most European languages. His ⟨i⟩ in *ryde* sounded like our *ee*; his ⟨ou⟩ in *hous* sounded like our *oo*; his long ⟨a⟩ in *name* was *ah*; and the ⟨oo⟩ of *soote* and *roote*, two words from the very first lines, was a long *oh*, not our *oo*. Read the opening with those values and the rhymes lock back into place.

Then every long vowel rose, each climbing into the slot above it. The two already at the top, *ee* and *oo*, had nowhere higher to go, so they broke apart into diphthongs: Chaucer's *ryde* (*reede*) became *ride*, his *hous* (*hoose*) became *house*. Spelling, meanwhile, had just been frozen in place by the printing press—which is why English vowels are still spelled for a pronunciation we abandoned four centuries ago.

**Why did it happen?** Nobody is sure. The shift is far better documented than explained. The mechanism is usually drawn as one of two shapes:

- a **pull chain**: the top vowels diphthongized first, opening a gap that pulled the vowel beneath up to fill it, and so on down the line;
- a **push chain**: a lower vowel began rising first and crowded the one above it, shoving the whole series upward until the top vowels were forced out into diphthongs.

Same result, opposite causality—the question is only which vowel moved first. The triggers people propose for that first move (dialect contact after the plague, prestige imitation, the pull of French) are educated guesses. The notebook draws the whole chain as arrows around the vowel space, where the circular motion is easy to see.

### Discussion questions
- Pull chain and push chain predict the same modern vowels. What kind of evidence could ever decide between them?
- Spelling froze halfway through the shift. Is a frozen spelling a defect or a gift?
- Why does the Great Vowel Shift make English so weird among the world's languages?

## Measuring real vowels

In the notebook we build a vowel from scratch—synthesize a sound with chosen formants, listen to it, then measure it back—so you can watch the measurement recover what we put in. Once you trust the tool on a sound you control, you turn it on real speech: record a few vowels, pull out F1 and F2, and plot your own vowel space. Compare your cloud with a neighbor's. Where they differ, ask whether it's dialect, anatomy, or just a noisy recording.

## From living sound to a dead language

Coptic—the last stage of Egyptian—was written in letters borrowed from Greek, and no one knows how those letters map onto real spoken vowels. We read the consonants with some confidence, relatively speaking. But there's a second, stranger window: a medieval manuscript that writes *Arabic*—a living language—in *Coptic* letters. It's a copy of the *Sayings of the Desert Fathers*, made when Coptic was fading but still read, by someone fluent enough in the script to spell another language with it. A living language we can still hear, written in the script we're trying to decode. In miniature, it's a Rosetta Stone for Coptic pronunciation.

The tempting way to read it is by eye: find a word, see which Coptic letter sits over which Arabic sound, declare a result. The study's central point is that this is exactly how you fool yourself. Choose your examples and you can "prove" almost any pronunciation you like. The evidence will oblige, and your own expectations will pick the examples for you. So the method refuses the eye. A program aligns the whole text, Coptic letter against Arabic letter, and measures how strongly each pair travels together (a correlation called the phi coefficient).

The dull results are the proof it works: the letters everyone already agrees on—⟨ⲗ⟩, ⟨ⲙ⟩, ⟨ⲛ⟩ for *l, m, n*—come out firmly paired, as they must. The interesting results are the payoff, the cases where a letter behaves differently than the handbooks assume: ⟨ⲅ⟩, normally read *g*, lining up with [ɣ]; ⟨ⲃ⟩, normally *b*, lining up with [w]; a fresh possibility for the sound of ⟨ϫ⟩. The same machine that confirms the obvious is the one you then trust on the doubtful. The notebook runs a small version of that measurement and draws the correlation table as a colormap.

That study handled the consonants. The vowels are the harder half, and where this morning's tools come back: measure the vowels of the living Arabic dialects with the formant code you already have, line them against the Coptic spellings, and reason toward sounds no one has heard in a thousand years. That part is still to come.

The reasoning leans on assumptions, and the discipline is in stating them out loud: that the living language keeps the relevant distinctions, that the spelling is shallow enough to trust, that the scribe heard what we think he heard. None of it is certain. All of it is more than we had.

> 🔧 *TO BUILD:* a panel from the paper's alignment colormap (the full Coptic–Arabic correlation table), and—later—a slice of the vowel data to measure here. Paper and code: *Casey 2023, "Egyptian Phonology Beginning from the End"* and github.com/christiancasey/coptic-arabic.

### Discussion questions
- The method won't let a human look at the data until the very end. What does that buy you and what might it miss?
- Reconstructing a dead language's sounds from a living one rests on assumptions. Which one seems most dangerous to you?
- Chaucer's pronunciation and Coptic's sounds are reached by different routes: rhyme and meter for one, a living language in a borrowed script for the other. What do the two approaches have in common?

```{admonition} Project check-in
:class: note
Could measured sound inform your text: loanwords, transcriptions, rhyme, or meter?
```
