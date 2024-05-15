Non-asymptotic regime:
$$\mathbb{P}\left(\left\lVert \hat{\theta} - \theta \right\rVert_2^2/d \geq C \cdot \left(\frac{d\log d / \delta}{n}\right)\right) \leq \delta.$$
Asymptotic regime:
$$
\lim_{n \to \infty} \mathbb{P}\left(\left|\left\lVert \hat{\theta} - \theta \right\rVert_2^2/n - \mathbb{E}\left[\left\lVert \hat{\theta} - \theta \right\rVert_2^2/n\right]\right| \geq \varepsilon\right) = 0 
$$$$\lim_{n \to \infty} \frac{\mathbb{E}\left[\left\lVert \hat{\theta} - \theta \right\rVert_2^2\right]}{n} = \text{some formula}.
$$
1. Gaussian concentration inequality
Proposition: Let f: $\mathbb{R^{d}} \rightarrow \mathbb{R}$ be an L-Lipschitz function 
Let $G =  (G_{1},\cdots ,G_{\alpha})$ standard Gaussian  $N(0,1)$ 
Then we have 
$$\mathbb{P}\left( \left| f(G) - \mathbb{E}[f(G)] \right| \geq t \right) \leq 2 \cdot \exp\left(-\frac{t^2}{2L^2}\right).$$
Example: consider $f(G) = \frac{1}{n}\sum_{i=1}^{n}G_i$  $\lVert \nabla f(G) \rVert_2 = \lVert n^{-1} 1_n \rVert_2 = \frac{1}{\sqrt{n}}$ 
$f$ is $\frac{1}{\sqrt n}$ - Lipshitz 
Then we have $$\mathbb{P}\left( \left|  \frac{1}{n}\sum_{i=1}^{n}G_i \right| \geq t \right) \leq 2 \cdot \exp\left(-\frac{nt^2}{2}\right).$$
How to prove this theorem:
1. Gaussian Log-Soblov inequality + Herbest 
2. Gaussian Isoperimetric Inequality



Use this inequality for our Asymptotic concentration:

## $\mathbb{Z_2}$ sync problem
$$Y = \frac{\lambda}{n} \theta \theta^{T}+W \in \mathbb{R^{n\times n}}$$
 $W \sim  GOE(n)$   $W_{ij}$ $i.i.d$ $N(0, \frac{1}{n})$  $1\leq i < j \leq n$   $W_{ij} =W_{ji}$  $W_{ii}$ $i.i.d$ $N(0, \frac{2}{n})$ 
 We observe $Y \in \mathbb{R^{n \times n}}$ and estimate $\theta$ 

Spectral estimator: 
  $$\hat{\theta}(Y) = \hat{\theta}_{\text{spec}}(Y) = \arg\max_{\theta \in \mathbb{S}^{n-1}(\sqrt{n})} \langle \theta, Y \theta \rangle/n$$
  Some scaling result (using random matrix theory):
$$\|W\|_{op} \approx 2 $$ $$\|\theta \theta^T\|_{op}\approx  n=\|n\|^2$$
