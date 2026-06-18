# Day 6 · Putting a Number on It

Today you reduce a text to a measurement, and learn to test whether the measurement means anything.

```{admonition} Companion notebook—*Putting a number on a text*
:class: tip
Open **Day 6 Notebook—Putting a number on a text.ipynb** in Colab and run along as you read.

🔧 *TO BUILD:* paste the Colab launch link once the book is on GitHub.
```

## Surprise, measured

Consider two reports: the sun rose this morning, and it snowed in July. The rarer event carries more information when it occurs. **Entropy** is the average of that information across a text—a single number for how predictable the next symbol is. Low entropy means predictable and redundant; high entropy means the opposite.

### Discussion questions
- Entropy reduces a whole text to a single number. What does that number capture, and what does it flatten?
- A redundant text and a dense, surprising one serve different purposes. When is each a virtue?

## Zipf's law

Rank the words of almost any text from most to least frequent and plot rank against frequency on logarithmic axes, and the result is close to a straight line. The pattern holds across languages and periods. Whether it's a deep fact or a near-inevitable one is a real and worthwhile argument.

### Discussion questions
- Zipf's law holds across languages and centuries. Does a pattern that universal tell us something deep, or something trivial?
- If random gibberish also follows Zipf's law, what has finding it in a real text actually shown?

## Measure

Open the notebook:

- Produce the Zipf plot and describe its shape in a sentence.
- Read off the entropy, then compute it for a second text. Which is more predictable?

## Be skeptical

This is the part that matters most. You'll find a difference between two texts; before calling it meaningful, name a dull explanation—length, genre, sample size. The notebook makes the point directly: random gibberish also produces a clean Zipf curve. A pattern, on its own, establishes very little.

### Discussion questions
- Before trusting any measured difference between two texts, what is the first dull explanation you should rule out?
- How would you design a comparison so that a dull explanation could not account for the result?

```{admonition} Project check-in
:class: note
What single number or distribution could your project measure, and what would a meaningless version of your data look like? If you can't tell the two apart, you don't yet have a result.
```
