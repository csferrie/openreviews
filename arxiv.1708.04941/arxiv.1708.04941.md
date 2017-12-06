# Review of "Minimax estimation of qubit states with Bures risk"

*Chris Ferrie* [&#64;csferrie](https://twitter.com/csferrie), [csferrie.com](https://csferrie.com/)

This is an open peer review of arxiv:1708.04941v2, [Minimax estimation of qubit states with Bures risk](https://arxiv.org/abs/1708.04941v2) by Anirudh Acharya and Mǎdǎlin Guţǎ.

**TO JOURNAL EDITORS:** You are free to use the contents of the [repository](https://github.com/csferrie/openreviews) as you see fit.

**DISCLAIMER:** A referee necessarily spends *far* less time than the authors on the paper. As such, this report surely contains errors. I would love for you to point them out so I can correct them. Otherwise, this report is provided without warranty of any kind, including its suitability as a resource for making decisions affecting the career of the authors of the paper.

## Tweetable summary of my report

Essential reading for quantum statisticians. Generalize to multiple qubits? #challengeaccepted

### Summary of claims and results

The authors demonstrate a measurement strategy that is proven to be optimal (in a specific and well-motivated sense) for two common figures of merit used in qubit tomography. The result is asymptotic and relies on previous results deriving the asymptotic distribution of qubit states. 

### Correctness

The authors have used a clever combination of known techniques to prove their result. I believe the results to be correct.

### Accessibility

The paper is clearly meant for a specialised audience. The authors do a good job, however, of abstracting the details and distilling the result for a non-expert in the introductory section. My only concern is the lack of detail on LAN given the results rely heavily on it. 

### Reproducibility

The paper is quite detailed, which allowed me to follow all of the calculations. As noted below, however, I am confused about Figure 1; I believe the risk is being plotted but the text, which I am suppose to "see for details", says the figure is showing the Bayes risk. I don't think in this case it is essential, but I would like to point out that all of this confusion could have been avoided if the code to produce this figure was provided. I could see at once what is being plotted. Reproducible science is about making as many steps as possible explicit so confusion is always avoided.  

### Final verdict

This is an excellent paper. At some point, more general results will supercede these. But, in the meantime, this is essential reading for anyone working on or interested in the mathematical statistics of quantum systems.

### Detailed Recommendations

#### More important

1. LAN is used at several crucial steps, but is hard to sort out how when you are not in the details of the calculation. Would it be possible to summarize the facts from LAN that are used into a separate lemma?

2. Heterodyne measurements are referred to but not defined. Many non-(quantum optics) people will be reading this and not know what that is.

3. Section 5 confuses me. I think I understand what is going on, but the risk function is defined in several non-equivalent ways. For example, the Bayes risk is written down as depending on $\mu$ and referred to as being plotted as a function of $\mu$ even though it shouldn't depend on $\mu$ (since $\mu$ is averaged out). I don't even have a clear suggestion as to what needs to be done here but I encourage the authors to take a second look at Section 5.

#### Less important

Please resolve the following issues:

4. LAN is used several times before it is defined. 

5. In the introduction, $\lambda_{\rm max}$ is used but not yet defined.

6. Vectors are usually written as "row vectors", but occasionally a transpose is inserted. That should be sorted out at least for consistency.