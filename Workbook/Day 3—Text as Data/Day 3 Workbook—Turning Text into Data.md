# Day 3 · Turning Text into Data

Counting words sounds simple until you have to define a word. That definition shapes every measurement that follows, so it's where we begin.

```{admonition} Companion notebook: *Turning text into data*
:class: tip
Open **Day 3 Notebook—Turning text into data.ipynb** in Colab and run along as you read.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/christiancasey/measuring-manuscripts/blob/main/Workbook/Day%203%E2%80%94Text%20as%20Data/Day%203%20Notebook%E2%80%94Turning%20text%20into%20data.ipynb)
```

## What is a word?

Take "the cat sat on the mat." How many words is that? How many *distinct* words? Are "sat" and "sit" the same word? Three units are useful here:

- a *token* is each running word,
- a *type* is each distinct form,
- a *lemma* is the dictionary headword that groups inflected forms (*swim*, *swimming*, *swam*, *swum*).

Your count changes depending on which you mean, so always be clear about which one you're counting.

"The cat sat on the mat" has six tokens. But *the* appears twice, so it has only five types. If you grouped *sat* under the lemma *sit*, the lemma count would track yet a third number. None of these is the "real" count. They answer different questions. Tokens tell you how long the text is. Types tell you how varied its vocabulary is. Lemmas tell you how many distinct ideas are in play once you set inflection aside.

This matters because almost every later measurement is built on one of these three. A frequency list counts tokens per type. A vocabulary-richness score compares types to tokens. A search for a verb across a corpus usually wants the lemma, not the surface form. Fix the unit first, or the numbers downstream won't mean what you think.

### Discussion questions

- "The cat sat on the mat" has six tokens but five types. Which count would you use to compare two texts, and why?
- Treating "sat" and "sit" as one word is convenient but discards information. When might that distort your results?
- In a language you know, where are the boundaries of a "word" genuinely unclear?

## Tokenizing: cutting the stream into units

Before you can count anything, you have to cut the text into pieces. That step is called *tokenization*, and the obvious method, splitting on the spaces, is only a first move. The spaces between words are a fact about *writing*, not about *language*, and they don't carve the text the way you'd want.

Punctuation rides along with words. Split "root." on spaces and you get the token `root.`, with the period stuck on. To a computer, `root.` and `root` are two different strings, so the same word at the end of a sentence counts as a different type. Strip the punctuation and they merge again. Capitalization does the same thing: `The` at the start of a sentence and `the` in the middle are different strings until you lowercase everything. These look like trivial cleanups, but each one changes the type count, and you saw in the notebook that simply lowercasing and stripping punctuation collapsed several apparent types into one.

Then come the hard cases that no amount of stripping fixes cleanly:

- *Contractions*. Is *don't* one token or two (*do* + *n't*)? English grammar treats it as two words fused. A naive splitter keeps it as one.
- *Clitics*. Small grammatical elements that attach to a host word. French *l'eau* or *j'ai*, the possessive *-'s* in English, the Greek postpositive particles. Each is arguably its own unit glued to its neighbor.
- *Hyphenation*. Is *well-known* one token or two? Is a word broken across a line-end one word or two fragments?

Every one of these is a fork in the road, and the count you get depends on which branch you take.

### Word division without spaces

Now drop the convenience of spaces entirely. Many writing systems didn't use them. Ancient Greek, Latin, Egyptian, and Akkadian were often written in *scriptio continua*: a continuous stream of letters with no gaps, no word breaks, sometimes no punctuation:

```
THEQUICKBROWNFOXJUMPSOVERTHELAZYDOG
```

A modern reader of English can re-segment that, because they already know the words. A computer can't *a priori*, and neither can a reader who doesn't already know the language. This is not a minor inconvenience. In Egyptian deciding where one word ends and the next begins is a genuine scholarly problem. Egyptian is written without consistent word spacing. Coptic uses some spacing and punctuation, but compound forms, attached articles, and bound prepositions mean that what counts as a single "word" is an editorial decision made text by text.

Even English carries a trace of the problem. Chaucer's scribes wrote *noot* for *ne woot* ("does not know") and *nyste* for *ne wiste* ("did not know"), fusing the negative particle onto the verb. Is *noot* one word or two? A modern edition prints it as one, but its grammar is two, and a frequency count that keeps *noot* whole quietly disagrees with one that splits it. A language written without consistent spacing, like Egyptian, meets this on every line rather than in a handful of contracted forms.

So the lesson is concrete: the unit you choose changes every later number. A different tokenization gives you a different token count, a different type count, a different frequency list, a different set of hapax legomena. Whenever you compare two measurements, check that they were tokenized the same way first.

### Discussion questions

- Splitting on spaces fails on contractions, clitics, and hyphens. Pick one and describe how you'd decide where the boundary goes.
- *Scriptio continua* has no spaces at all. What information would you need before you could divide it into words?
- If Coptic has no settled word division, what happens when two scholars tokenize the same text differently and then compare their counts?

## Types, tokens, lemmas, and the rare words

With the text tokenized, the three units from earlier become measurable. A few terms make the rest of the day easier.

A *hapax legomenon* (plural *hapax legomena*, Greek for "said once") is a word that appears exactly once in a text. There are always far more of them than you'd guess, often a third to a half of all the types in a short text. Hapax matter because they're where the unusual vocabulary lives, and because their number tells you something about how open-ended a text's word stock is.

The *type-token ratio* (TTR) is the number of types divided by the number of tokens. A text with 100 tokens and 80 types has a TTR of 0.80. One with 100 tokens and 40 types has a TTR of 0.40. The higher the ratio, the more varied the vocabulary looks.

There's a catch you must internalize, because it trips up nearly everyone the first time. **TTR falls as a text gets longer.** A short text quickly runs out of new words to introduce (how many ways can you say *the*), so the longer it runs, the more it reuses words it already has, and the ratio drops. This means you cannot compare the raw TTR of a 200-word text against a 20,000-word text and conclude that the first has "richer" vocabulary. The difference is mostly just length. To compare vocabulary richness across texts of different sizes, you have to control for length: sample equal-sized chunks, or use a measure designed to be length-stable. The notebook demonstrates the fall directly by subsampling one text at growing sizes and watching the ratio slide downward.

### Discussion questions

- Half the types in a short text might be hapax legomena. Does that make them noise to ignore, or signal to investigate?
- Two texts have TTRs of 0.7 and 0.4. Before concluding the first has richer vocabulary, what's the first thing you'd check?
- You want to compare vocabulary richness across a 500-word letter and a 50,000-word chronicle. How would you make that comparison fair?

## The frequency distribution

A *frequency list* ranks words by how often they occur. A *concordance*, or keyword-in-context, shows every occurrence of a word alongside its neighbors. Neither is terribly sophisticated, yet both remain useful, because regularities that are invisible in running text become obvious once the occurrences are stacked together.

Build a frequency list for almost any text and the top of it is dull. The most common words are function words (the, and, of, to, a, in) the grammatical glue that holds sentences together. They carry little topical meaning on their own, and they sit at the top of every list in the language regardless of subject. Below them come the *content words*: the nouns, verbs, and adjectives that tell you what the text is actually about.

Because the top of the list is so predictable, people often filter it out. A *stopword* list is a set of common function words you remove before counting, so that the content words rise to the top and the frequency list starts telling you about *this* text rather than about English in general. The notebook shows a before-and-after: filter the stopwords and the same passage suddenly foregrounds *man*, *good*, *worthy*, *fair* instead of *the* and *and*.

Two cautions. First, the dull top of the list isn't worthless. Function-word frequencies are exactly what authorship-attribution studies measure, because writers use *the* and *of* in stable, personal proportions they can't easily disguise. So "dull" depends on the question. Second, stopword lists are language-specific and never neutral. A word that's pure glue in one text (*shall*, *thy*) might be a key term in another. Strip thoughtlessly and you can delete the thing you were looking for.

### Discussion questions

- A frequency list puts the dullest words on top. What does that tell you, and what does it hide?
- Removing stopwords makes content words visible but throws information away. When would you keep the function words instead?
- In a corpus you care about, name one word that's a stopword in most texts but a key term in yours.

## Concordances: keyword in context

A concordance lists every occurrence of a chosen word together with the words on either side of it. Reading a text straight through, you meet each use of a word once, scattered, pages apart. A concordance stacks them so you can read down the column and see the word's behavior all at once: which words it keeps company with, which senses it carries, whether it's always literal or sometimes figurative.

This is not a new idea. Concordances to the Bible were built by hand over years. The great medieval concordance to the Latin Vulgate, organized under Hugh of Saint-Cher in the thirteenth century, reportedly took a team of hundreds of friars to compile. Concordances to the Quran were assembled by the same patient, line-by-line labor. People did this work by hand, for decades, because the result was worth it: a concordance lets you ask "everywhere this word occurs, what does it mean?", the exact question that close, linear reading answers slowly and incompletely. A computer builds one in a fraction of a second, which is the whole point of doing it by machine.

### Discussion questions

- What can a concordance show you that reading the text straight through cannot?
- People spent years building Bible concordances by hand. What does that tell you about how valuable the result was?
- Pick a word you'd want to study in your own text. What would you hope to learn from seeing all its occurrences stacked?

## Collocations and n-grams

Words keep company. *Strong* goes with *coffee*, not *powerful coffee*. *Heavy* goes with *rain*, not *strong rain*. These habitual pairings are *collocations*, and they're a first, rough measure of meaning by association. The linguist J. R. Firth's line was "you shall know a word by the company it keeps." If you collect the words that sit next to a chosen word across a whole text, the frequent neighbors sketch how that word is actually used, often more honestly than a dictionary definition.

A related tool is the *n-gram*: a run of *n* consecutive tokens. A *bigram* is a pair (*worthy man*, *for to*). A *trigram* is a triple (*he was a*). Counting the frequent bigrams and trigrams of a text gives you a first window on its phraseology: its set phrases, its formulae, its turns of speech. This is especially powerful for traditional and formulaic texts. Liturgy, legal documents, oral-derived poetry, and scribal colophons are full of fixed phrases, and the frequent n-grams pull those formulae straight out of the text without your having to know them in advance.

The *General Prologue* is a clean test case. Run the n-gram counter on it and the top trigram is *he was a*, the formula that opens one pilgrim portrait after another ("He was a verray, parfit, gentil knyght"). The bigram *for to* before an infinitive recurs throughout as a fixed Middle English construction. Neither is a phrase you would think to search for in advance. The count pulls them out on its own, which is the whole use: it surfaces a text's habitual phrasing before you know to look for it.

### Discussion questions

- "Strong coffee" works. "Powerful coffee" doesn't. What does a word's collocates tell you that its definition might not?
- Frequent bigrams and trigrams pull out a text's set phrases. What kinds of text would you expect to be full of them?
- If you ran an n-gram count on your own corpus, what recurring phrase do you suspect it would surface?

## Lemmatization, stemming, and searching

Earlier we said a lemma groups inflected forms under one headword. Getting from surface forms to lemmas is *lemmatization*, and doing it properly is hard, because a real lemmatizer has to know the whole language: that *went* belongs to *go*, that *mice* belongs to *mouse*, that a given Coptic form is the bound state of a particular verb. It needs a dictionary and morphological rules, not just string trimming.

The cheap alternative is *stemming*: chop off the ends of words by rule so that related forms collapse to a common stub. A stemmer turns *running*, *runs*, and *runner* into something like *run*, but it does it blindly. (It might also turn *universe* and *university* into the same stem, and it produces stubs that aren't real words.) Stemming is fast and crude. Lemmatization is slower and correct. For a language with rich morphology, like Egyptian or Coptic, only real lemmatization gives trustworthy counts, and the notebook's tiny hand-built lemma map is only a stand-in for a proper tool.

Often you don't need to lemmatize the whole text. You just want to *find* something. For that, learn a little about *regular expressions* ("regex"): a compact pattern language for searching text. A plain search finds one exact string. A regex finds a *pattern*. A few basics carry you a long way:

- `.` matches any single character
- `*` means "zero or more of the previous thing"
- `[aeiou]` matches any one vowel
- `colou?r` matches both *color* and *colour* (the `?` makes the *u* optional)
- `wind|sun` matches either word.
- and much more...

With regex you can pull every word starting with a given root, every spelling variant of a name, every date, every form of a verb whose endings you know, across an entire corpus at once. The notebook includes a short regex search you can adapt to your own text.

Regex is a big topic, but the basics can be learned fairly quickly. For this, we will all work together on some [RegEx Crosswords](https://regexcrossword.com/).

### Discussion questions

- Stemming might collapse *universe* and *university* to one stub. When is that crude behavior acceptable, and when is it a problem?
- A real lemmatizer needs to know the whole language. What does that imply about lemmatizing a language whose grammar is still partly reconstructed?
- Name one thing you'd want to find across your whole corpus that an exact-string search would miss but a regex pattern could catch.

## Build the pipeline

Open the notebook and run it on the supplied text:

- Run the tokenizer and record the token and type counts.
- Produce the frequency list. What are the five most common words? Are they what you expected? Now filter the stopwords and look again.
- Watch the type-token ratio fall as the sample grows.
- Build a concordance for a word of your choice and note one thing about how it's used.
- Count the frequent bigrams and trigrams, and try a regex search over the text.

```{admonition} Project check-in
:class: note
What's your corpus, and what will count as a single unit in it: token, lemma, or sign?
```
