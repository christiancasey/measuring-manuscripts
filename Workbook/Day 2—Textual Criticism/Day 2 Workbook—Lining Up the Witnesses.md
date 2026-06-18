# Day 2 · Lining Up the Witnesses

A text that survives in several copies is never copied perfectly. The differences between copies are evidence. Today you'll line the copies up to see them clearly, then make the judgments the computer can't.

```{admonition} Companion notebook—*Lining up the witnesses*
:class: tip
Open **Day 2 Notebook—Lining up the witnesses.ipynb** in Colab and run along as you read.

🔧 *TO BUILD:* paste the Colab launch link once the book is on GitHub.
```

## Witnesses and variants

Yesterday you edited by hand. Today the computer does the alignment. Each surviving copy is a **witness**; a place where witnesses differ is a **variant**. Lay the copies out in a table—one column per position in the text, one row per witness—and the variants are easy to find. CollateX produces that table for you.

### Discussion questions
- A variant is just a place where copies disagree. Are all variants equally informative, or are some kinds more revealing than others?
- A scribe might change a text by error, by correction, by taste, or by censorship. How could you tell these apart?
- With only one copy of a text, what can you not learn that several copies would tell you?

## Texts mutate like DNA

Copying introduces change: a slip, a correction, a dropped word. This is close enough to biological mutation that the same methods carry over. Measure how different each pair of witnesses is, and you can build a tree that groups the most similar copies—a first hypothesis about which copy descends from which. It stays a hypothesis. Two scribes can make the same easy error independently, and the tree can't distinguish that from shared descent.

### Discussion questions
- Where does the comparison with DNA hold, and where does it break down? (A scribe, unlike a gene, can read what it copies.)
- A family tree of manuscripts is a hypothesis. What evidence could confirm or undermine it?
- Two scribes can make the same easy mistake independently. How might that fool a method that groups copies by shared readings?

## Before you run anything

Read the witness passages and underline two places where the copies disagree. Predict which two witnesses are most alike before the computer answers.

> 🔧 *TO BUILD:* 3–4 real witness passages of the same text (e.g. the *General Prologue* in Hengwrt, Ellesmere, and Caxton's print).

## Run the collation

Open the notebook and run the cells to produce the alignment table and the variant graph. Find a column where the witnesses split and record the variants. Then build the tree and see which witnesses group together.

## Interpret

- Which two witnesses agree most often? Did that match your prediction?
- Choose one variant. Which reading would you adopt as editor, and why?
- What does the alignment not tell you, and where do you still need a human?

```{admonition} Project check-in
:class: note
Does your text survive in more than one version? If so, whose disagreements would be worth mapping? If not, what else could you compare?
```
