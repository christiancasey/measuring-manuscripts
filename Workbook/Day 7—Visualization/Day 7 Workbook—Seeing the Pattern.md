# Day 7 · Seeing the Pattern

You can't see fifty dimensions at once. Today you compress them to two so the structure becomes visible, then check whether the compression has misled you.

```{admonition} Companion notebook—*Seeing the pattern*
:class: tip
Open **Day 7 Notebook—Seeing the pattern.ipynb** in Colab and run along as you read.

🔧 *TO BUILD:* paste the Colab launch link once the book is on GitHub.
```

## Why reduce dimensions

Each item you study—a sign, a vowel, a text—can be described by many numbers at once, which places it in a high-dimensional space no one can picture. **Dimensionality reduction** finds a two-dimensional view that keeps as much structure as possible, so clusters become visible. The compression distorts, and different methods distort differently.

- **PCA** is linear and fast, and its axes are interpretable. It can blur fine structure, but it's hard to mislead with.
- **UMAP** and **t-SNE** are nonlinear and better at separating clusters, but the distances between clusters can be unreliable, so don't read meaning into the gaps.

### Discussion questions
- Compressing fifty dimensions to two always loses something. How would you judge whether what survives is trustworthy?
- PCA, UMAP, and t-SNE can give different pictures of the same data. If they disagree, which do you believe, and how would you choose?
- A cluster in a plot is a hypothesis, not a fact. What would convince you a cluster is real?

## Warm-up

Suppose you had to place every classmate on a two-dimensional chart so that similar people sit close together. Which two axes would you choose, and what would the chart leave out? That's the problem in miniature.

## Project the data

Open the notebook:

- Run PCA, sketch the result, and circle any clusters.
- Run UMAP on the same data. Did the clusters change? Which view do you trust more, and why?
- Pick an outlier. Is it a real exception or a digitization error, and how would you check?

The notebook also runs UMAP twice with different random seeds, so you can watch the gaps between clusters shift while the clusters themselves hold.

```{admonition} Project check-in
:class: note
What single image would make your finding clear at a glance?
```
