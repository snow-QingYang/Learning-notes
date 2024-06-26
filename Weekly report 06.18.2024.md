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
### Linear Representation Settings

Given an input  $x \in \mathbb{R}^d$ , contrastive learning aims to learn a low-dimensional representation $h = f(x; \theta) \in \mathbb{R}^r$ by contrasting different samples, that is, maximizing the agreement between positive pairs, and minimizing the agreement between negative pairs. Suppose we have $n$ data points  $X = [x_1, x_2, \ldots, x_n] \in \mathbb{R}^{d \times n}$ . The contrastive learning task can be formulated to the following optimization problem: 
$$
\min_\theta \mathcal{L}(\theta) = \min_\theta \frac{1}{n} \sum_{i=1}^n \ell(x_i, \mathcal{B}_i^{\text{Pos}}, \mathcal{B}_i^{\text{Neg}}; f(\cdot; \theta)) + \lambda R(\theta),
$$
### Linear contrasive loss
$$ 
\ell(x, \mathcal{B}_x^{\text{Pos}}, \mathcal{B}_x^{\text{Neg}}, f(\cdot; \theta)) = - \sum_{x^{\text{Pos}} \in \mathcal{B}_x^{\text{Pos}}} \frac{\langle f(x, \theta), f(x^{\text{Pos}}, \theta) \rangle}{|\mathcal{B}_x^{\text{Pos}}|} + \sum_{x^{\text{Neg}} \in \mathcal{B}_x^{\text{Neg}}} \frac{\langle f(x, \theta), f(x^{\text{Neg}}, \theta) \rangle}{|\mathcal{B}_x^{\text{Neg}}|}
$$

### Generation for Augmented Pairs 
The loss function of the self-supervised contrastive learning problem can then be written as: 

$$ \mathcal{L}_{\text{SelfCon}}(W) = - \frac{1}{2n} \sum_{i=1}^{n} \sum_{v=1}^{2} \left[ \langle W g_v(x_i), W g_{[2] \setminus \{v\}}(x_i) \rangle - \sum_{j \neq i} \sum_{s=1}^{2} \frac{\langle W g_v(x_i), W g_s(x_j) \rangle}{2n - 2} \right] + \frac{\lambda}{2} \|WW^{\top}\|_F^2.
$$
### Random Masking Augmentation
The two views of the original data are generated by randomly dividing its dimensions into two sets, that is, $g_1(x_i) = A x_i$, and $g_2(x_i) = (I - A) x_i$, where $A = \text{diag}(a_1, \ldots, a_d) \in \mathbb{R}^{d \times d}$ is the diagonal masking matrix with $\{a_i\}_{i=1}^{d}$ being i.i.d. random variables sampled from a Bernoulli distribution with mean $1/2$ 

In this paper, they focus only on random masking augmentation. (We need to study the generative self-supervised learning, which random masking plays a major role)

### Spiked Covariance Model
In this paper, we use spiked covariance model
$$ 
x = U^\star z + \xi, \quad \text{Cov}(z) = \nu^2 I_r, \quad \text{Cov}(\xi) = \Sigma, 
$$
where $z \in \mathbb{R}^r$ and $\xi \in \mathbb{R}^d$  are both zero mean sub-Gaussian independent random variables, and  $\nu \in \mathbb{R}$  is a constant representing the signal strength. In particular,  $U^\star \in \mathbb{O}_{d,r}$  and$(\Sigma = \text{diag}(\sigma_1^2, \ldots, \sigma_d^2)$ . The first term  $U^\star z$  represents the signal of interest residing in a low-dimensional subspace spanned by the columns of  $U^\star$ . The second term $\xi$ is the dense noise with heteroskedastic noise. 
It was proposed from the empirical observation that the eigenvalues of the sample covariance matrix of phoneme data have few ”spikes”, which corresponds to the low-dimensional structure of data generation.
## Autoencoders, GANs and PCA


## Theorems
### Proposition 5 
For two fixed augmentation functions \( g_1, g_2 : \mathbb{R}^d \rightarrow \mathbb{R}^d \), denote the augmented data matrices as  $X_1 = [g_1(x_1), \cdots, g_1(x_n)] \in \mathbb{R}^{d \times n}$  and  $X_2 = [g_2(x_1), \cdots, g_2(x_n)] \in \mathbb{R}^{d \times n}$, when the augmented pairs are generated as in Definition 1, all the optimal solutions of contrastive learning problem are given by:
$$
W_{CL} = C \left( \sum_{i=1}^r u_i \sigma_i v_i^{\top} \right)^{\top}, 
$$


where  $C > 0$  is a positive constant,  $\sigma_i$  is the $i$ -th largest eigenvalue of the following matrix:
$$
 X_1 X_2^{\top} + X_2 X_1^{\top} - \frac{1}{2(n-1)} (X_1 + X_2) (1_n 1_n^{\top} - I_n) (X_1 + X_2)^{\top}, 
$$
Proof: I have understod the proof part. So I will skip this.

### Recovery ability of autoencoder
### Theorem B.7 (Restatement of Theorem 13)

Consider the spiked covariance model  $\text{Eq.}(5)$ , under Assumptions 8-10 and  $n > d \gg r$ , let  $W_{AE}$ be the learned representation of autoencoder with singular value decomposition $W_{AE} = (U_{AE} \Sigma_{AE} V_{AE}^\top)^\top$  as in $\text{Eq.}(7)$ . If we further assume $\{ \sigma_i^2 \}_{i=1}^d$  are different from each other and $\sigma_{(1)}^2 / (\sigma_{(r)}^2 - \sigma_{(r+1)}^2) < C_\sigma$ for some universal constant \( C_\sigma \). Then there exist two universal constants \( C_\rho > 0, c \in (0, 1) \), such that when \( \rho < C_\rho \), we have

\[ 
\mathbb{E} \| \sin \Theta (U^\star, U_{AE}) \|_F \geq c \sqrt{r}.
\]

(38)
