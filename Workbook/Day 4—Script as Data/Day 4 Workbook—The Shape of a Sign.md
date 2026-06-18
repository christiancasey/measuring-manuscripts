# Day 4 · The Shape of a Sign

A letter is not one shape but a range of shapes; no two scribes, and no two centuries, draw it the same way. Today you'll measure how close those shapes are to one another.

```{admonition} Companion notebook—*Measuring the shape of a sign*
:class: tip
Open **Day 4 Notebook—Measuring the shape of a sign.ipynb** in Colab and run along as you read.

🔧 *TO BUILD:* paste the Colab launch link once the book is on GitHub.
```

## Graph vs. grapheme

Write the letter "a" five times, quickly. The five are not identical. The **grapheme** is the abstract letter; each inked instance is a **graph**. The same grapheme appears as very different graphs from one hand to the next, and that variation is measurable. It can indicate period, scribe, or genre.

### Discussion questions
- If a letter can be drawn in countless ways, what makes two marks the same letter?
- Scribal variation is usually treated as noise. When might it be the signal you are after?
- What can the shape of a sign tell you that its identity cannot?

## Digitizing is the hard part

Before a sign can be measured it has to be separated from the page, and that's where the difficulty lies. Signs touch, overlap, and break, so deciding where one ends and the next begins is often genuinely unclear. Automatic handwriting recognition handles clean printed Latin script well and damaged, variable, non-Latin scripts poorly—which is exactly the material this kind of work involves.

### Discussion questions
- Deciding where one sign ends and the next begins is often a judgment call. What is at stake in getting it wrong?
- Why do automatic tools handle printed Latin script well and the scripts we care about poorly?

## Explore Isut

Open **Isut's Guesser**, draw a sign, and see what it returns. Then look through the sign analysis view and find a sign whose shape clearly varies across texts.

> 🔧 *TO BUILD:* the Isut link for the class, and a small set of real sign crops for the notebook.

## Measure similarity

The notebook converts each sign image into numbers and scores every pair for similarity. Pick a sign and find its nearest matches by shape. Do they agree with your eye? Where they don't, the disagreement tells you something about what the features actually capture.

```{admonition} Project check-in
:class: note
Is the script itself your variable? What hands, periods, or genres might you compare by shape?
```
