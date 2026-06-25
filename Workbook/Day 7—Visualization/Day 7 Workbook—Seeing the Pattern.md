# Day 7 · Seeing the Pattern

You can't see fifty dimensions at once. Today you compress them to two so the structure becomes visible, then check whether the compression has misled you.

NOTE: Last week a recommended a video a background for the day's discussion. At that time, it wasn't essential. Today it will be. If you don't yet understand PCA, please watch [this video](https://www.youtube.com/watch?v=_6UjscCJrYE).

```{admonition} Companion notebook: *Seeing the pattern*
:class: tip
Open **Day 7 Notebook—Seeing the pattern.ipynb** in Colab and run along as you read.

🔧 *TO BUILD:* paste the Colab launch link once the book is on GitHub.
```

## Describing one thing with many numbers

By now you have spent several days turning things into numbers. On Day 3 a text became a list of word counts. On Day 4 a sign became a set of shape measurements. On Day 5 a vowel became a pair of formant frequencies. In each case one object stopped being a thing you look at and became a row of numbers.

A row of numbers describing one object is a *feature vector*. The vowel from Day 5 had two features (a first formant and a second formant), so its vector was two numbers long: something like `(650, 1100)`. A sign from Day 4 might have ten or twenty shape measurements (height, width, curvature at five points, the area of the enclosed loop), so its vector is ten or twenty numbers long. A text from Day 3, counted across the thousand most common words, has a vector a thousand numbers long.

Here is the move that makes the rest of the day possible. A vector of two numbers is a point on a flat chart: the first number is how far right, the second is how far up. The Day 5 vowels were exactly this: you plotted them on a chart of F1 against F2 and saw the vowels separate. A vector of three numbers is a point in a room: right, up, and toward you. You can still picture it.

A vector of twenty numbers is a point in a twenty-dimensional space. The arithmetic is identical (twenty coordinates instead of two), but you cannot picture it, because your eyes and your imagination stop at three. The space is real and the points sit somewhere definite in it. You just can't look.

This is the whole problem of the day. Your data live in a space with more dimensions than you can see, and the structure you care about (which signs group together, which texts resemble which) is a fact about how the points sit in that space. You need a way to look at something you can't picture.

### Discussion questions

- On Day 5 each vowel was two numbers and you could plot it directly. Roughly how many numbers describe one sign from Day 4, or one text from Day 3? Why does that make the same kind of plot impossible?
- "A point in twenty-dimensional space" sounds abstract. In what sense is it just a row in a spreadsheet you already made?
- If you can't picture the space, in what sense is the structure in it still real? What would count as evidence that two signs "sit close together" when you can't see them?

## Why high dimensions are hard, not just unviewable

The trouble is worse than not being able to draw the picture. High-dimensional spaces behave in ways that work against you, and the umbrella name for this is the *curse of dimensionality*.

The piece of it that matters today concerns distance. The whole point of measuring your signs or vowels was so you could say two of them are similar (their vectors are close together) and two others are different. In two or three dimensions this works the way your intuition expects: near things are clearly near, far things are clearly far.

As dimensions pile up, that contrast fades. With enough features, almost every pair of points ends up at roughly the same distance from every other. The nearest neighbor is barely nearer than the farthest one. Distance stops sorting things cleanly, which is a problem, because "these signs are close, those are far" is exactly the judgment you want to make.

A plain way to feel it: with one feature, you sort your signs along a line and crowding is obvious. Add features and you give every sign more room to be unlike every other sign in some way. Pile on enough features and everything is a little unlike everything, so nothing stands out as especially similar. The signal you want, real groups, gets diluted by the sheer number of ways things can differ.

This is one reason reducing dimensions is not only about drawing a picture. Squeezing the data down to a few well-chosen dimensions can sharpen distances that high dimensions had smeared out.

### Discussion questions

- If you measured a sign with five features and got clean groups, then added forty more features and the groups blurred, what happened? Did the signs change, or did the measurement?
- "More features must mean more information." When is that true, and when does adding features hurt you?
- The course keeps turning objects into longer and longer vectors. Where might that help, and where might it start to work against you?

## Why reduce dimensions

Each item you study (a sign, a vowel, a text) can be described by many numbers at once, which places it in a high-dimensional space no one can picture. *Dimensionality reduction* finds a two-dimensional view that keeps as much structure as possible, so clusters become visible. The compression distorts, and different methods distort differently.

The goal is to see structure that is genuinely there but invisible in a table of numbers. Stare at a spreadsheet of 150 signs by 20 measurements and you will see nothing: no person reads structure out of three thousand numbers in a grid. Project those 150 points down to a flat chart and a glance can show three clumps, an outlier off to one side, a thin bridge of points between two groups. The structure was always in the data. Reduction makes it something an eye can take in.

Two kinds of structure are worth looking for. *Clusters* (groups of points that sit together) are candidate categories: hands, periods, dialects, scribes. *Outliers* (lone points far from everything) are candidate oddities: a misread sign, a mistyped number, or a genuine exception worth a closer look.

- *PCA* is linear and fast, and its axes are interpretable. It can blur fine structure, but it's hard to mislead with.
- *UMAP* and *t-SNE* are nonlinear and better at separating clusters, but the distances between clusters can be unreliable, so don't read meaning into the gaps.

### Discussion questions

- Compressing fifty dimensions to two always loses something. How would you judge whether what survives is trustworthy?
- PCA, UMAP, and t-SNE can give different pictures of the same data. If they disagree, which do you believe, and how would you choose?
- A cluster in a plot is a hypothesis, not a fact. What would convince you a cluster is real?
- What is the difference between an outlier that is a digitization error and one that is a genuine exception, and would the plot alone ever tell you which it is?

## PCA: the linear view

*Principal Component Analysis* is the first tool to reach for, and the easiest to understand once you see what it is doing.

Picture your points as a cloud in high-dimensional space. The cloud is usually stretched: longer in some directions, flatter in others. PCA looks for the single direction in which the cloud is most stretched out: the direction of greatest *variance*, where the points are most spread apart. That direction becomes the first new axis, the *first principal component*. Then it looks for the next most stretched-out direction at right angles to the first, and that becomes the second component. And so on.

These components are new axes, built from the data rather than handed to you. When you plot the first two, you are looking at the cloud from the angle that shows its widest spread: the most informative flat photograph of a three-dimensional object you could take, generalized to many dimensions.

Two ideas make PCA honest to use.

The first is the *explained variance ratio*. Each component captures some fraction of the total spread in the data. The first might capture 40 percent, the second 25 percent, and so on down. When you plot only the first two components, you are seeing only their share (say 65 percent), and the rest of the structure is flattened out of view. A *scree plot* stacks these fractions as bars from largest to smallest. If the first two bars are tall and the rest are stubs, your two-dimensional picture is faithful. If the bars trail off slowly, much of the structure is hiding in the dimensions you cannot see, and you should not trust the flat picture too far.

The second is *interpretability*. Because each PCA axis is a fixed combination of your original features, you can sometimes read it. Suppose your Day 4 signs were measured for height, width, and loop area. If the first component turns out to be mostly height-minus-width, then "left versus right on the chart" means "tall-narrow signs versus short-wide ones," and that is a statement you can take back to the manuscripts and check. Not every component reads this cleanly, but when one does, PCA hands you an interpretation, not just a picture.

What PCA blurs: it only ever rotates and flattens. It cannot bend the cloud. If your groups are separated in a curved or tangled way rather than along straight directions, PCA may smear them together, and you will need a nonlinear method to pull them apart.

> 🔧 *TO BUILD:* run PCA on this year's real sign-shape vectors from Day 4 and report which original measurements load most heavily on PC1 and PC2, so the axes can be named.

### Discussion questions

- If PC1 and PC2 together explain only 35 percent of the variance, what should you conclude about a tidy-looking cluster in the PCA plot?
- PCA's axes are combinations of your original features. Why does that sometimes let you name an axis, and when would naming it be a stretch?
- PCA can only flatten and rotate, never bend. Imagine two groups of signs arranged so one curls around the other. Why might PCA fail to separate them?
- The scree plot is a check on the picture, not a picture of the data. What decision does it actually help you make?

## UMAP and t-SNE: the nonlinear view

*UMAP* and *t-SNE* work on a different principle, and it is worth understanding because their strength and their danger come from the same place.

Instead of finding straight directions of greatest spread, these methods look at each point's *local neighborhood* (who its nearest neighbors are) and try to build a flat picture in which those same points stay neighbors. They preserve who is near whom, and they are willing to bend and stretch the space however they must to do it. That bending is why they can separate groups that PCA smears: a curved arrangement in high dimensions can be unfolded onto the page.

Each has one main knob.

- For *UMAP* it is `n_neighbors`: how many neighbors count as "local." A small value makes the method nearsighted: it preserves tight local detail and can shatter the data into many small pieces. A large value makes it farsighted: it preserves the broad layout and may merge fine structure. There is no single correct setting. Different values answer slightly different questions, which is why the notebook runs several side by side.
- For *t-SNE* it is `perplexity`, which plays much the same role: roughly how many neighbors each point tries to stay close to. Low perplexity emphasizes small local clumps. High perplexity emphasizes larger groupings.

Now the danger, and it is the most important caveat of the day. Because these methods only promise to keep neighbors together, the parts of the picture they do *not* promise to preserve are exactly the parts an untrained eye reads as meaningful:

- **Distances between clusters are unreliable.** Two clusters drawn far apart are not necessarily more different than two drawn close. The method placed them. The layout between groups is not a measurement.
- **Gap sizes mean nothing.** A wide blank band between two clumps is not evidence of a deep divide. Don't read meaning into the gaps between UMAP clusters.
- **The result is stochastic.** UMAP and t-SNE use randomness, so a different random seed produces a different-looking picture: rotated, reflected, with the clumps shoved into new positions. The clusters themselves usually hold. Their arrangement on the page does not. If a finding survives only at one seed, it is an artifact of that seed, not a result.

So what *can* you trust from a UMAP or t-SNE plot? Which points sit together. That is the one thing these methods are built to get right. Treat the membership of clumps as a real signal and the rest of the layout (distances, gaps, orientation) as decoration the method was free to invent.

### Discussion questions

- UMAP and t-SNE preserve who is near whom but not how far apart groups are. Which questions about your Day 4 signs could you answer from such a plot, and which could you not?
- Two seeds give two different pictures with the same clumps. What does that tell you to ignore, and what does it tell you to trust?
- A colleague points at a wide gap between two clusters and says the two groups of signs are "completely unrelated." On today's terms, what is wrong with that claim?
- `n_neighbors` (or `perplexity`) has no single right value. If three settings give three pictures, how should you report the result honestly?

## Reading a projection honestly

Pull the caveats together into a habit. When you look at any of today's plots, sort what you see into two piles.

Trust: **which points sit together.** If the same points clump in PCA, in UMAP, and in t-SNE, and the clump survives different settings and different seeds, you are looking at real structure.

Don't trust: **exact distances, gap sizes, and orientation.** How far apart two clusters are drawn, how wide the blank between them is, which way the whole picture is turned. These are products of the method, not facts about your manuscripts.

A short checklist for any projection you make:

- Does the same grouping appear across methods, or only in one?
- Does it survive when you change the main knob, and when you change the random seed?
- Is there a known label (period, hand, dialect) that the grouping lines up with?
- For PCA, did the first two components actually keep most of the variance?

A cluster that passes these is a hypothesis worth testing. A cluster that appears in one method, at one setting, at one seed, and matches nothing you know, is a picture and not yet a finding.

### Discussion questions

- Across PCA, UMAP, and t-SNE, suppose the same three groups of vowels appear every time but their arrangement on the page keeps changing. What have you learned, and what have you not?
- Which item on the checklist would be hardest to satisfy with your own project data, and why?
- "A cluster is a hypothesis until tested." What is the cheapest test you could run before claiming a cluster is real?

## Clustering to back up the eye

Eyeballing groups is a start, not a result. Two people can circle different clumps in the same plot. To turn a visual impression into something you can defend, you let an algorithm draw the groups and then score them.

Two clustering methods are worth knowing in plain terms.

- *k-means* asks you to name how many groups you expect (say three) and then sorts every point into the nearest of three centers, nudging the centers until the grouping settles. It is fast and works well when groups are roughly round blobs. Its weakness is that you must pick the number of groups in advance, and a wrong guess forces the data into the wrong shape.
- *Hierarchical clustering* asks for no number. It starts with every point alone, repeatedly merges the two closest groups, and records the whole sequence of merges as a branching tree (a *dendrogram*). You read the tree and cut it where the branches are longest, which tells you how many groups the data actually support. It is slower but it shows you the structure of the merging rather than assuming an answer.

Naming the groups by machine is only half the job. The other half is checking them against something you already know. If you have *true labels* (you know these signs are from the early hand and those from the late one), you can ask how well the machine's grouping matches the truth. The *adjusted Rand index* does this with a single number. It runs from 0 to 1: a score near 1 means the clustering recovered your known groups almost exactly. A score near 0 means it grouped the points no better than chance. "Adjusted" means it already accounts for matches that would happen by luck, so the number is honest.

This closes the loop. The projection suggested three groups. K-means drew them. The adjusted Rand index against your period labels reports whether those drawn groups are the real ones. A high score turns "I think I see three hands" into "the measurements separate three hands, and here is the score."

Outliers deserve the same discipline. A point sitting alone is a candidate, not a verdict. Find it by distance (it is far from every cluster center), then go back to the source. A vowel marooned far from its vowel category might be a genuine rare pronunciation, or it might be a formant mismeasured because the recording was noisy. A sign off on its own might be a real variant form, or two strokes that the segmentation accidentally merged. The plot tells you where to look. Only the manuscript tells you which it is.

> 🔧 *TO BUILD:* cluster this year's real Day 4 sign features with k-means and report the adjusted Rand index against the known hands, plus one outlier traced back to its source image.

### Discussion questions

- k-means makes you choose the number of groups. Hierarchical clustering does not. For your own project data, which would you reach for first, and why?
- An adjusted Rand index of 0.4 against your true labels: is that a failure, or partial structure worth investigating? What would you check next?
- You eyeball four clusters but k-means with k=3 scores higher against the labels than k=4. What might that mean?
- You find an outlier vowel far from every group. List the steps you'd take to decide whether it's a real exception or a measurement error.

## Warm-up

Suppose you had to place every classmate on a two-dimensional chart so that similar people sit close together. Which two axes would you choose, and what would the chart leave out? That's the problem in miniature.

## Project the data

Open the notebook:

- Run PCA, sketch the result, and circle any clusters.
- Check the scree plot. How much of the variance did the two-dimensional picture actually keep?
- Run UMAP on the same data. Did the clusters change? Which view do you trust more, and why?
- Vary `n_neighbors` and watch the picture shift. Which features of it stay put?
- Let k-means draw the clusters and read the adjusted Rand index against the true labels.
- Pick an outlier. Is it a real exception or a digitization error, and how would you check?

The notebook also runs UMAP twice with different random seeds, so you can watch the gaps between clusters shift while the clusters themselves hold.

```{admonition} Project check-in
:class: note
What single image would make your finding clear at a glance?
```
