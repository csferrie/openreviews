# Review of "Neural-Network Heuristics for Adaptive Bayesian Quantum Estimation"

*Chris Ferrie* [&#64;csferrie](https://twitter.com/csferrie), [csferrie.com](https://csferrie.com/)

This is an open peer review of arxiv:2003.02183v1, [Neural-Network Heuristics for Adaptive Bayesian Quantum Estimation](https://arxiv.org/abs/2003.02183v1) by Lukas J. Fiderer, Jonas Schuff, and Daniel Braun.

**TO JOURNAL EDITORS:** You are free to use the contents of the [repository](https://github.com/csferrie/openreviews) as you see fit.

**DISCLAIMER:** A referee necessarily spends *far* less time than the authors on the paper. As such, this report surely contains errors. I would love for you to point them out so I can correct them. Otherwise, this report is provided without warranty of any kind, including its suitability as a resource for making decisions affecting the career of the authors of the paper.

### Tweetable summary of my report

Next level heuristics for adaptive quantum estimation. #Bayesorbust

### Summary of claims and results

The authors propose and test several novel heuristics for adaptive Bayesian estimation. These are based on reinforcement learning (RL), which is a machine learning framework for decision making in the presence of feedback. The overall protocol is quite versatile and is probably better viewed as an alternative framework for adaptive Bayesian estimation than a specific algorithm. Using the framework, the authors gain superior performance for the problem of phase estimation in the presence of dephasing noise and experimental constraints. Several regimes are considered in simulation and the RL method is shown to outperform existing approaches. Significantly, the results include all code used to perform the simulations and build and train the models.

### Correctness

The methodology is sound. The conclusions are probably more strongly stated than is warranted. The code contains thousands of lines, which I have not thoroughly checked, but utilizes well-tested packages and produces results that are consistent. I would say overall, yes, the paper is correct.

### Accessibility

This is very readable paper only for someone that has some background in at least a few of the topics. It is quite far on the succinct side. I am at least aware of many of the topics, and so I had no problem following. Perhaps I even appreciated the conciseness. I mean, I really enjoyed this paper. I'm not sure, though, if it would be considered too dense for a non-expert. For example, reinforcement learning is explained in one picture and a few sentences and then it is stated that trust region policy optimization (TRPO) is used to approximate it. Some more plausible justification for these choices should be emphasised before diving head first into the results of numerical experiments.

### Reproducibility

The paper provides all the details necessary to reproduce the results including the source code and trained models. This is a model example of computational work.

### Final verdict

This work represents an important step in the field of quantum metrology. It underscores the fact that existing best practice is missing out on potentially orders of magnitude in accuracy. Whereas, the reinforcement learning approach appears to be robust, providing consistently better performance. 

I have some reservations about the strength of the stated conclusions and would say the authors have not adequately stated the limitations of their framework.

### Detailed Recommendations

In no particular order at all:

0. As noted above, the paper is lacking on pedagogy. This is fine, but some of the choices made are not clearly  stated and justified (TRPO, CEM, SMC, particular algorithm parameters, etc.) and maybe only acceptable for an expert. A non-expert would be thoroughly confused. The authors should state clearly the choices that have been made and the justification for them. This may require more exposition.

1. The conclusions are either too strongly stated or not sufficiently argued. For one, why does superior results on a single example suggest the method should be suitable for other problems, especially given it computational overhead? How was the one example where TRPO gives a large improvement found? How typical would we expect this to be? Given the examples are dimensionless, is this regime physically relevant?

2. Using Qinfer, it is quite easy to calculate the Bayesian Cramer Rao Bound numerically. There is also some built in functionality to do this. In Ref. [7], we demonstrated the near-optimality of some of our heuristics by showing how close they came to this lower bound. Since the authors have record the data, it should be straightforward to add the lower bound to the plots. Without it, we can say only that TRPO is best among what could be all terrible heuristics! (Note that the assumptions of BCRB don't automatically apply to uniform priors. But, calculating the variance in the prior should be easy.)

3. It would appear that the authors have only tried a single prior distribution. If they have tried other priors, would the conclusions hold? Perhaps they have and not reported on that data if they have it. This should be stated explicitly and emphasised. Some comment on why they believe the conclusion will hold under other, perhaps even more reasonable, choices of prior is warranted.

4. Were different particle numbers tried for SMC? Perhaps the other heuristics perform better with higher particle number? Surely some initial runs with differing particle number was tried. Any comments on these? 

5. Fig. 3 is remarkable for an unstated reason: ellipses! It suggests that TRPO very quickly approximates a normal distribution. In most of our prior analytical work, we dealt with this approximate (assumed asymptotic) regime. Perhaps TRPO (and it's inherited computational cost) need only be run for a short number of experiments before moving to a simpler analytic solution? Have the authors checked the posterior for normality?

6. What's with the "Supplementary Material"? This should just be another appendix.

7. Not all of the references have clickable DOIs and/or arXiv links.