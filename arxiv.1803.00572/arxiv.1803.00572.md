# Review of "Recovering quantum gates from few average gate fidelities"

*Chris Ferrie* [&#64;csferrie](https://twitter.com/csferrie), [csferrie.com](https://csferrie.com/)

This is an open peer review of arxiv:1803.00572v1, [Recovering quantum gates from few average gate fidelities](https://arxiv.org/abs/1803.00572v1) by Ingo Roth, Richard Kueng, Shelby Kimmel, Yi-Kai Liu, David Gross, Jens Eisert, and Martin Kliesch.

**TO JOURNAL EDITORS:** You are free to use the contents of the [repository](https://github.com/csferrie/openreviews) as you see fit.

**DISCLAIMER:** A referee necessarily spends *far* less time than the authors on the paper. As such, this report surely contains errors. I would love for you to point them out so I can correct them. Otherwise, this report is provided without warranty of any kind, including its suitability as a resource for making decisions affecting the career of the authors of the paper.

## Tweetable summary of my report

Theorems and numerics and experimental relevance, oh my! #openscience

### Summary of claims and results

The authors demonstrate that average gate fidelities between an unknown channel and random Clifford gates can be used to reconstruct the channel with compressed sensing-like accuracy (quadratic improvement over standard techniques). This is an important result as average gate fidelities are well-understood and often the preferred data extracted from characterisation experiments.

### Correctness

With 26 pages, 30-something proofs, and over 200 equations, there is bound to be an error somewhere. But I didn't find it. So let's go with, yeah, it's probably correct.

I definitely agree with the interpretation of the results and the less provable claims pertaining to the relevance and importance of the results. I appreciated the discussion about the limitations of the results and necessary and potential future work.

### Accessibility

This is a model academic paper. It distills all of the details into a readable summary; it also presents those details in a well-organised and expository way; it provides the source code for the numerical experiments; and explains the details of the choices made in performing those experiments. 

If anything negative can be said about the presentation of the research, it is that the code is noticeably disorganised relative to the theoretical exposition. However, I'm not entirely sure one could do better with borrowed MATLAB scripts. In any case, it is still far beyond what is currently expected for research in this field.

### Reproducibility

The paper provides all the details necessary to reproduce the results. 

### Final verdict

This is a highly technical paper with potentially immediate relevance to experimental practice—a rare combination. But the authors have done well to abstract those technical details into a readable summary of the contribution, making it accessible to a wide audience. I would not hesitate to recommend this to a student working on this or related problems.

### Detailed Recommendations

Mostly nitpicking, but I felt I should at least make some recommendations:

1. "In layman’s terms, we demonstrate that Clifford-group based measurements, are also sufficiently unstructured that they can be
used for compressed sensing." This is Layman's terms? Hahahaha... things look pretty small from the Ivory Tower, indeed.

2. Unless I have been misled—which is entirely possible—the en dash (–) should not be used in place of parentheses. This occurs in several place in the manuscript and should be replaced by em dashes (—).

3. "We emphasise that the main contributions of this work are of theoretical nature (we prove several Theorems)." That parenthetical comment though. Yeah..., when the last theorem is labeled "Theorem 39" it's kind of obvious. Really, what's the point of this emphasis? Are the authors afraid someone might mistake this for—gasp!—*computational* work?