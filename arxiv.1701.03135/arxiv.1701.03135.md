# Review of "Guaranteed recovery of quantum processes from few measurements"

*Chris Ferrie* [&#64;csferrie](https://twitter.com/csferrie), [csferrie.com](https://csferrie.com/)

This is an open peer review of arxiv:1701.03135v3, [Guaranteed recovery of quantum processes from few measurements](https://arxiv.org/abs/1701.03135v3) by Martin Kliesch, Richard Kueng, Jens Eisert, and David Gross.

**TO JOURNAL EDITORS:** You are free to use the contents of the [repository](https://github.com/csferrie/openreviews) as you see fit.

**DISCLAIMER:** A referee necessarily spends *far* less time than the authors on the paper. *In fact, I have a confession: I didn't finish reading the detailed sections of the proofs or the appendix.* As such, this report surely contains errors. I would love for you to point them out so I can correct them. Otherwise, this report is provided without warranty of any kind, including its suitability as a resource for making decisions affecting the careers of the authors of the paper. 

## Tweetable summary of my report

A complete discussion of quantum process tomography via compressed sensing techniques. Essential reading for the quantum tomographer!

### Summary of claims and results

This work contains several related results all relevant to the estimation of quantum processes. The main contribution are theorems providing sufficient state preparation and measurement models to guarantee recovery of an unknown process with *few* measurements, where few means asymptotically optimal up to log factors. While these models are not the most natural from current experimental perspectives, they are feasible. Addressing this further, the authors provide some numerical evidence that recovery is possible with a constant overhead in scaling using the most common experimental model.

All-in-all, this is an important result in quantum process tomography and useful contribution to the literature.

### Correctness

Though I did not check the details presented in the proofs which appear in extreme detail in Sec. III, I believe the results to be correct for the following reasons: (1) I agree with the conceptual arguments presented; (2) the results are not surprisingly different from previous work; and, (3) I know the work of the authors well and trust them.

### Accessibility

Every paper should have this structure. The non-technical summary and arguments are extremely readable. The concise, but complete comparison to previous work is useful. It provides a well-thought through defense of the choices made in the model *and* notes ways to generalize the result. But most importantly, it is *complete*. It contains all the details and auxillary results needed to fully understand the paper. 

### Reproducibility

The paper provides all the details necessary to reproduce the theoretical results. 

The reproducibility of the numerical results is more questionable. There is quite a bit of detail in the methodology and tools used.  This is probably sufficient for the first set of numerical results, which are demonstrative and serve to produce the figures that are used to illustrate the main theoretical results. 

The results of Sec II E rely on numerics, but are justified by some intuition on the structure of Pauli measurements. It would be nice to be able to look at the code to enhance one's confidence in those results.
And, to be fair, the authors did offer to provide the code when I requested it.

### Final verdict

This is a technical paper with relevance to both theoretical and experimental quantum process estimation. The authors have done a great job abstracting the technical details, providing a nice summary. I thus expect it to be readable in part to an audience broader than quantum tomography experts. For those, however, this is essential reading. 

### Recommendations

I really have no recommendations here. I suspect, as this is the third version of the paper, many improvements have been made at the suggestion of other commenters.


