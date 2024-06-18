## Paper reading 
I have been reading the main parts of this paper：**The Power of Contrast for Feature Learning: A Theoretical Analysis**  And I am currently working on the proof parts of this paper. Here is the summary of what I have read:

### Review of contrasive learning
There are two common approaches for feature extraction I am not familar with contrasive learning. So I read the SimCLR work.
![[Pasted image 20240618213000.png]]
1. A stochastic data augmentation that transforms the data into a positive pair
2. A neural network base encoder f (·) that extracts representation vectors from augmented data examples
3. A small neural network projection head g(·) that maps representations to the space (smaller dimension)
4. A contrastive loss function defined for a contrastive prediction task
In this paper, the second part is based on ResNet (He et al., 2016).

The Learning process
![[Pasted image 20240619003346.png]]
## Theoretical Analysis of Contrasive learning

In this paper, a theoretical framework is established to study contrastive learning under **the linear representation setting**. They provide a theoretical analysis on the **spiked covariance model** and theoretically justify why contrastive learning outperforms **standard autoencoders** and **generative adversarial networks (GANs)** 
Conclusion: contrastive learning is able to remove more noise by constructing contrastive samples via augmentations.
## Model Setup
### 2.1 Linear Representation Settings for Contrastive Learning

Given an input  $x \in \mathbb{R}^d$ , contrastive learning aims to learn a low-dimensional representation $h = f(x; \theta) \in \mathbb{R}^r$ by contrasting different samples, that is, maximizing the agreement between positive pairs, and minimizing the agreement between negative pairs. Suppose we have $n$ data points  $X = [x_1, x_2, \ldots, x_n] \in \mathbb{R}^{d \times n}$ . The contrastive learning task can be formulated to the following optimization problem: 
$$
\min_\theta \mathcal{L}(\theta) = \min_\theta \frac{1}{n} \sum_{i=1}^n \ell(x_i, \mathcal{B}_i^{\text{Pos}}, \mathcal{B}_i^{\text{Neg}}; f(\cdot; \theta)) + \lambda R(\theta), 