# Day 3 · Turning Text into Data

Counting words sounds simple until you have to define a word. That definition shapes every measurement that follows, so it's where we begin.

```{admonition} Companion notebook—*Turning text into data*
:class: tip
Open **Day 3 Notebook—Turning text into data.ipynb** in Colab and run along as you read.

🔧 *TO BUILD:* paste the Colab launch link once the book is on GitHub.
```

## What is a word?

Take "the cat sat on the mat." How many words is that? How many *distinct* words? Are "sat" and "sit" the same word? Three units are useful here:

- a **token** is each running word,
- a **type** is each distinct form,
- a **lemma** is the dictionary headword that groups inflected forms (*blew*, *blow*, *blowing* → *blow*).

Your count changes depending on which you mean, and choosing is already an interpretive act.

### Discussion questions
- "The cat sat on the mat" has six tokens but five types. Which count would you use to compare two texts, and why?
- Treating "sat" and "sit" as one word is convenient but discards information. When might that distort your results?
- In a language you know, where are the boundaries of a "word" genuinely unclear?
- Who decides what counts as a unit—the language, the writing system, or the analyst?

## The two oldest tools

A **frequency list** ranks words by how often they occur. A **concordance**, or keyword-in-context, shows every occurrence of a word alongside its neighbors. Neither is sophisticated, and both remain useful, because regularities that are invisible in running text become obvious once the occurrences are stacked together.

### Discussion questions
- A frequency list puts the dullest words on top. What does that tell you, and what does it hide?
- What can a concordance show you that reading the text straight through cannot?

## Build the pipeline

Open the notebook and run it on the supplied text:

- Run the tokenizer and record the token and type counts.
- Produce the frequency list. What are the five most common words? Are they what you expected?
- Build a concordance for a word of your choice and note one thing about how it's used.

## Linking

A glossary connects a word to its meaning across texts and languages—structurally, a mapping from a word to an entry.

> 🔧 *TO BUILD:* map a few words to real glossary entries once the linking step exists.

```{admonition} Project check-in
:class: note
What's your corpus, and what will count as a single unit in it—token, lemma, or sign?
```
