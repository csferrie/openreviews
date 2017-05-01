# Review of "Generating 3 qubit quantum circuits with neural networks"

Chris Ferrie

This is an open peer review of arxiv:1703.10743, [Generating 3 qubit quantum circuits with neural networks](https://arxiv.org/abs/1703.10743) by Michael Swaddle *et al*.

**TO JOURNAL EDITORS:** You are free to use the contents of the [repository](https://github.com/csferrie/openreviews) as you see fit.

**DISCLAIMER:** A referee necessarily spends *far* less time than the authors on the paper. As such, this report surely contains errors. I would love for you to point them out so I can correct them. Otherwise, this report is provided without warranty of any kind, including its suitability as a resource for making decisions affecting the career of the authors of the paper.

## Tweetable summary of my report

Highly recommended read for its accessibility and reproducibility, but lacks the analysis to live up to its claims. #workinprogress

### Summary of claims and results

The authors seem to define quantum compilation the same way I would define *quantum control*. Namely, given a set of control Hamiltonians, design the interaction strength to generate a target unitary. The standard approach—as far as I understand—is a numerical gradient-based optimization using classical simulation to evaluate the objective function. The authors propose the following two-step alternative:
* First break up the path from the the initial gate to the target into sequence of unitaries which approximate a geodesic curve in $SU(d)$;
* Second, for each of those unitaries, find the set of controls to achieve those, with the idea that—given they are "close" together—it should be easier than traditional approaches.

The authors achieve this to some extend by training a neural network with simulated trajectories. Though, as I outline below, much more analysis is required to warrant suggesting this as a viable alternative to traditional methods. Though they did *not* emphasize it, I see the provided code and data as the most valuable research output.

### Correctness

Given I was able to reproduce the results, I have no doubt the results obtained are correct. I do have some concerns, though, in the relevance of the result to quantum control:
* The authors seem to truncate the unitaries to the real part of each entry. Are two unitaries that are close in their real part actually close? I don't think they are.
* The training data for the second stage control problem does not use the the gates generated from the first part. They simply generate random controls to define a target. It would be far more convincing if the gates used in the first stage where used in the second stage. After all, this is how it would necessarily be done in practice.

### Accessibility

The paper is quite short, but not necessarily dense. I am neither an expert in geometric quantum nor the architecture of neural networks—yet, I was able to quickly grasp the main idea of the paper. That being said, there were a few points which I got hung up on. 
* The discussion of the problem of quantum compilation, or control, lacks context. It attempts to be broad, but would leave a non-expert thinking: a good approximation to $U$ is of course $U$. It should be discussed earlier—and made explicit—hat the basis for the sub-algebra is somehow an experimental constraint or set of available controls. 
* The crucial part of the geodesic equation seems to be the projection onto the sub-algebra. This should be explicitly defined.
* The network design is lacking everything but a bare description—why this rather than something else? Is there some intuition at least?
* Fidelity is the standard metric used in quantum control (and something like diamond norm is the ultimate figure of merit for quantum gate comparisons). The real part of the individual entries seems to be quite difficult to justify from an operational perspective. Such choices need to be explained and defended.

### Reproducibility

Relative to other research in quantum information theory, this work gets top marks for reproducibility. However... given the author's eagerness to go above and beyond what is expected in a physics paper, I'm going to make some further suggestions for improvement in the hopes that the reproducibility aspect is more transparent.

The code is not well organized or documented. Since it is quite minimal and I had some basic knowledge in the software used, I was able to figure out how it works. But, I doubt most of the target audience of this paper could make use of it. Indeed, I immediately ran into errors when attempting to run the code, making the saved trained model useless to me. To be fair, I did not attempt to contact the authors about this since—as the authors themselves point out—the model can be trained quite quickly on a reasonable GPU (as you will see below).

The data was generated with separate software—Mathematica. I do not have a Mathematica license so did not attempt to reproduce the data. Given the authors were already using numpy, it would have been straightforward to generate the data in python as well.

### Methodology

I think here is where the paper falls short. The analysis of the results of the network training are not subjected to any anaylsis beyond plotting the results. Crucially(!):
* How does this method compare to existing methods for:
    * The geodesic approach?
    * The local decomposition?
* Further to that, does the claim that the lack of redundancy using the geodesic provides an effective alternative hold up to numerical tests? (It would be straightforward given the infrastructure the authors have build to test the claims of their own paper!)
* (Even for the small examples) How do the results depend on the parameters of the neural network?

### Final verdict

The authors provided the code to generate the data, the data themselves, the code to train the network, and the trained network!  Indeed, if I was so inclined, I could immediately build on their work without any uncertainty and this is far more than I can say for anything else I've read recently on [quant-ph]([https://arxiv.org/list/quant-ph/recent). This is an immensely impressive effort in a field which neither rewards or encourages it. The standard approach to publishing is to obscure your result to the point of either not being about to reproduce it, or give yourself plausible deniability should it be wrong. I applaud the authors for their bravery in exposing their work for detailed criticism. 

I see this as a (very useful!) set of lab notes rather than a complete scientific result because of the lack of comparisons to existing methods and variations in the proposed method. More analysis and discussion of the results is required. 