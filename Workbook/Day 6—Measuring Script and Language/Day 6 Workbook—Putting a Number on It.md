# Day 6 · Putting a Number on It

```{important}
You absolutely must watch this video before this class: [Reinventing Entropy | Compression is Intelligence Part 1](https://youtu.be/l6DKRf-fAAM). You will be quizzed on its contents to verify that you've watched it. None of this makes sense without this information (pun intended).
```

```{admonition} Companion notebook: *Putting a number on a text*
:class: tip
Open **Day 6 Notebook—Putting a number on a text.ipynb** in Colab and run along as you read.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/christiancasey/measuring-manuscripts/blob/main/Workbook/Day%206%E2%80%94Measuring%20Script%20and%20Language/Day%206%20Notebook%E2%80%94Putting%20a%20number%20on%20a%20text.ipynb)
```

## Surprise, measured

Consider two reports: the sun rose this morning, and it snowed in July. The rarer event carries more information when it occurs. *Entropy* is the average of that information across a text: a single number for how predictable the next symbol is. Low entropy means predictable and redundant. High entropy means the opposite.

That is the headline. The rest of this section explains where the number comes from, because the formula is short and you can work it by hand.

### Information as surprise

Start with one event, not a whole text. Information theory measures the *information* in an outcome by how surprising it is. An outcome you were already sure of carries none. An outcome you would never have guessed carries a lot. The quantity we use is

$$ \text{information} = \log_2 \frac{1}{p} = -\log_2 p $$

where $p$ is the probability of the outcome. The logarithm is base 2, so the unit is the *bit*. One bit is the information in a single fair coin flip: two equally likely outcomes, $p = \tfrac{1}{2}$, and $-\log_2 \tfrac{1}{2} = 1$.

Why a logarithm, and why base 2? Three reasons, all practical.

- **Sure things carry nothing.** If $p = 1$, then $-\log_2 1 = 0$. An event you were certain of tells you nothing when it happens.
- **Rare things carry more.** As $p$ shrinks toward 0, $-\log_2 p$ grows without bound. The snow in July is worth more bits than the sunrise.
- **Independent events add up.** Two coin flips have four equally likely outcomes, $p = \tfrac14$, worth $-\log_2 \tfrac14 = 2$ bits, exactly one bit per flip, added. The logarithm is what turns multiplying probabilities into adding information.

A bit is also a count of yes/no questions. If a symbol carries 3 bits, you would need about three well-chosen yes/no questions to pin it down. That is a useful way to feel what the number means: bits are guesses.

### Working one entropy by hand

*Entropy* is the *average* information per symbol, weighted by how often each symbol occurs. Write it out for a source that emits four symbols (call them A, B, C, D) with these probabilities:

- A: $p = \tfrac12$
- B: $p = \tfrac14$
- C: $p = \tfrac18$
- D: $p = \tfrac18$

(They sum to 1, as probabilities must.) Each symbol carries $-\log_2 p$ bits of information, and we weight each by how often it appears:

$$ H = -\sum_i p_i \log_2 p_i $$

Take it term by term.

- A: $-\tfrac12 \log_2 \tfrac12 = \tfrac12 \times 1 = 0.5$
- B: $-\tfrac14 \log_2 \tfrac14 = \tfrac14 \times 2 = 0.5$
- C: $-\tfrac18 \log_2 \tfrac18 = \tfrac18 \times 3 = 0.375$
- D: $-\tfrac18 \log_2 \tfrac18 = \tfrac18 \times 3 = 0.375$

Add them: $H = 0.5 + 0.5 + 0.375 + 0.375 = 1.75$ bits per symbol. On average, each symbol from this source carries 1.75 bits.

Compare that to the most unpredictable four-symbol source possible: all four equally likely, $p = \tfrac14$ each. Then $H = -4 \times \tfrac14 \log_2 \tfrac14 = 2$ bits, the maximum for four symbols, which is just $\log_2 4$. Our source comes in below that, at 1.75, because A is common and easy to guess. The more lopsided the probabilities, the lower the entropy. The notebook computes exactly this, term by term, on a tiny string so you can watch the sum build.

### Discussion questions

- Entropy reduces a whole text to a single number. What does that number capture, and what does it flatten?
- A redundant text and a dense, surprising one serve different purposes. When is each a virtue?
- Our four-symbol source scored 1.75 bits against a maximum of 2. What kind of text would push the number right up to the maximum, and what would drag it toward zero?
- The unit is "bits per symbol." Why does the *per symbol* part matter when you compare two texts of very different length?

## Entropy of a text

To measure the entropy of a real text, you treat it as a source: count how often each symbol occurs, turn the counts into probabilities, and run the same sum. The symbol can be a letter or a word, and the choice changes the number, so always say which you mean.

A high-entropy text is hard to predict symbol by symbol. A low-entropy text is easy. English running prose sits well below its maximum, which is the interesting part.

### Redundancy and compression

The gap between a text's entropy and the maximum entropy for its alphabet is its *redundancy*. If a 27-symbol alphabet (26 letters plus space) were used with every symbol equally likely, the maximum would be $\log_2 27 \approx 4.75$ bits per letter. Real English runs far lower (roughly 1 to 1.5 bits per letter once you account for context) because letters are not equally likely (*e* is everywhere, *q* and *z* are rare) and because they follow rules (*q* is nearly always followed by *u*). The shortfall is redundancy:

$$ \text{redundancy} = 1 - \frac{H}{H_{\max}} $$

Redundancy is not waste. It is what lets you read a smudged manuscript, finish a friend's sentence, or guess a word the scribe dropped. It is also the reason text *compresses*: a file compressor works by spending fewer bits on the predictable parts. The closer a text sits to its maximum entropy, the less it compresses, because there is less redundancy to remove. Pure random noise is incompressible. A text full of repetition shrinks dramatically. Redundancy and compressibility are two views of the same fact. The notebook measures redundancy for letters and reports it as a percentage.

### Discussion questions

- Redundancy lets you read damaged text. Give a concrete example from manuscript work where redundancy saved a reading.
- A heavily abbreviated medieval script squeezes out redundancy on the page. What does that predict about how hard it is to read, and to expand?
- If two manuscripts of the same work report different redundancy, name a dull reason that has nothing to do with the scribes.

## What entropy cannot see

Here is a limitation worth knowing before you lean on the number. Entropy counts symbols. It does not care about their order. Take a text, shuffle its words into a random sequence, and the word-entropy does not change at all: the counts are identical, so the probabilities are identical, so the sum is identical. The notebook does exactly this and prints the two numbers side by side: they match.

That means entropy is blind to syntax. A grammatical sentence and the same words scrambled into nonsense score the same. Anything that lives in the *order* of symbols (grammar, meter, the difference between a sentence and a word-salad) is invisible to plain entropy. This is not a flaw to apologize for. It is a fact about what the measurement is. Knowing it tells you when entropy is the wrong tool and when it is the right one.

### Predictability from context

To put some of the order back, measure surprise *in context*. *Conditional entropy* asks: given the previous symbol, how surprising is the next one? In English, knowing the last letter was *q* makes the next letter almost certainly *u*, so the surprise of that next letter is tiny. Knowing the last letter was *e* narrows things much less. Averaged over the text, conditional entropy is lower than plain entropy whenever context helps, and for natural language it always helps.

You can keep going: condition on the last two letters, the last three, and the per-symbol surprise keeps dropping as more context is allowed. That declining sequence is one way people estimate the true entropy of a language. The notebook builds a simple version using letter *bigrams* (pairs of adjacent letters) and shows the next-letter surprise falling once the previous letter is known.

One more term you will meet: *perplexity*, which is just $2^H$. If entropy is in bits, raising 2 to that power gives the *effective number of choices*. An entropy of 2 bits means perplexity 4: on average, the next symbol behaves as if there were 4 equally likely options. Perplexity restates entropy in a unit that is sometimes easier to picture: a count of live possibilities rather than a count of bits.

### Discussion questions

- Shuffle the words and entropy is unchanged. Name two things about a text that this proves entropy cannot measure.
- Conditional entropy is lower than plain entropy for real language. Why does that have to be true, rather than just happening to be?
- Perplexity turns 2 bits into "4 effective choices." For your own writing system, would you expect more or fewer effective choices than English, and why?
- If two scripts have the same plain entropy but different conditional entropy, what does the difference tell you?

## Word length and information

Entropy also explains a pattern you have already half-seen. Back on Day 1 we plotted word length against word frequency and got a messy cloud. The mess was the raw frequency axis. Measure instead each word's *information*, its surprisal written -log2(p), which is exactly the per-word quantity the entropy sum averages, and plot that against length. The relationship is clean and points the natural way: the more information a word carries, the longer it tends to be. *The*, *of*, *and*, *to* carry almost no information and are tiny, while the rarest words carry the most and run longest.

This is what an efficient code looks like. Shannon's source coding theorem says the ideal length of a codeword is its information content, -log2(p) bits, which is why Morse gives the common letter *e* a single dot and saves long strings for rare letters. Entropy is the average of that same information across the whole vocabulary, the floor on how short the typical word can be, and a language that ties length to information is pressing toward that floor. The pattern even has a name, *Zipf's law of abbreviation*. The length-and-information line and the entropy number are two views of one fact: language behaves like a code under pressure to stay brief.

## Zipf's law

Rank the words of almost any text from most to least frequent and plot rank against frequency on logarithmic axes, and the result is close to a straight line. The pattern holds across languages and periods. Whether it's a deep fact or a near-inevitable one is a real and worthwhile argument.

### Rank, frequency, and the straight line

The recipe is simple. Count every word. Sort the counts from largest to smallest. The most common word gets rank 1, the next rank 2, and so on. *Zipf's law* says frequency is roughly inversely proportional to rank: the word at rank 2 appears about half as often as the word at rank 1, rank 3 about a third as often, rank 10 about a tenth. In symbols,

$$ \text{frequency} \approx \frac{C}{\text{rank}} $$

for some constant $C$.

Why plot it on *log–log axes*, logarithm of rank against logarithm of frequency? Because that relationship, $f \approx C / r$, becomes a straight line when you take logs of both sides: $\log f \approx \log C - \log r$. A straight line with **slope near $-1$**. The log–log plot turns a sharply curved relationship into something your eye can check at a glance: is it straight, and is the slope about $-1$? The notebook produces the plot and then fits the slope numerically. On a short text the line is ragged and the slope wanders, which is itself a lesson about sample size.

### Better fits, and vocabulary growth

Real texts bend away from the straight line at both ends: the very most common words and the long tail of rare words. Two refinements are worth naming.

- *Zipf–Mandelbrot*. Add a small constant to the rank: $f \approx C / (r + b)^a$. The extra parameters bend the curve to fit the high-frequency end better. It is the same idea with more flexibility.
- *Heaps' law*. A separate but related pattern about *vocabulary growth*. As a text gets longer, you keep meeting new words, but more and more slowly. Heaps' law says the number of distinct words (types) grows as a power of the total number of words (tokens): $V \approx K \, N^\beta$, with $\beta$ usually between 0.4 and 0.6. Early on, almost every word is new. Deep into a long text, new words are rare. The notebook plots vocabulary against length as the sample grows, so you can watch the curve flatten.

### Why Zipf might arise, and why the curve proves little

One classic explanation is the *principle of least effort*: speakers economize by reusing a few words constantly, listeners would prefer many specific words, and the compromise between the two pressures lands on a Zipf-like distribution. It is a plausible story about language.

Here is the catch. Random typing also produces a Zipf curve. Imagine a monkey hitting keys at random, including a space bar. The "words" are the runs of letters between spaces. Short words come out far more often than long ones simply because a space is more likely to fall soon than late, and that alone yields a clean rank-frequency line with slope near $-1$. No grammar, no meaning, no least effort. The notebook generates exactly this gibberish and plots it. The curve is as tidy as the one from real prose.

So finding Zipf's law in a text shows much less than it first appears. The curve is nearly inevitable for anything that chops a stream into tokens of varying length. It is evidence of very little on its own.

### Discussion questions

- Zipf's law holds across languages and centuries. Does a pattern that universal tell us something deep, or something trivial?
- If random gibberish also follows Zipf's law, what has finding it in a real text actually shown?
- Heaps' law says new words keep arriving but ever more slowly. What does that predict about estimating a medieval author's full vocabulary from one surviving work?
- The principle of least effort is a story that fits the data. The monkey is another. How would you tell which one is doing the work?

## The skeptic's method

The skeptic's move is the same every time, and it generalizes far beyond Zipf and entropy. You measure something, find a difference or a pattern, and before calling it meaningful you do two things.

First, **name a dull explanation**. The difference between your two texts might come from nothing more interesting than length, genre, or sample size. A longer text has a richer vocabulary by Heaps' law alone. A legal document and a lyric poem differ in word frequencies for reasons that have nothing to do with the question you care about. A tiny sample is noisy, and noise can look like signal.

Second, **build a comparison the dull explanation cannot survive**. The standard tool is a *null model* or *permutation test*: produce a version of your data in which the interesting effect has been destroyed but the dull properties are kept, then measure both and compare. If your real result is no different from the null, the dull explanation accounts for it and you have nothing. If your real result stands clearly outside a whole spread of shuffled or randomized baselines, the dull explanation has been ruled out.

The notebook does this twice. The shuffle test keeps every word and its count but destroys word order, showing that entropy cannot tell the two apart. The gibberish test keeps "tokens between spaces" but destroys all language, showing that a Zipf curve survives with no meaning behind it. Both are null models: a meaningless version of the data, measured the same way, to see whether your number can tell the difference.

### Be skeptical

This is the part that matters most. You'll find a difference between two texts. Before calling it meaningful, name a dull explanation: length, genre, sample size. The notebook makes the point directly: random gibberish also produces a clean Zipf curve, and shuffled text scores the same entropy. A pattern, on its own, establishes very little. The result you can trust is the one that survives its own null version.

### Discussion questions

- Before trusting any measured difference between two texts, what is the first dull explanation you should rule out?
- How would you design a comparison so that a dull explanation could not account for the result?
- A permutation test keeps the dull properties and destroys the interesting one. For a measurement you care about, what exactly would you shuffle, and what would you keep fixed?
- Suppose your real result sits in the middle of the shuffled baselines. What have you learned, and what should you do next?

```{admonition} Project check-in
:class: note
What single number or distribution could your project measure, and what would a meaningless version of your data look like? If you can't tell the two apart, you don't yet have a result.
```
