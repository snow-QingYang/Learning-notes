# Statistics Mechanics review

## Some important concepts
### 1. Gibbs distribution
$$P_{\beta}(\mathrm{d}\sigma) := \frac{1}{Z(\beta)} \exp\{-\beta H(\sigma)\} \nu_{0}(\mathrm{d}\sigma).$$
### 2. Partition Function 
$$Z(\beta) := \int_{\Omega} \exp\{-\beta H(\sigma)\} \nu_{0}(\mathrm{d}\sigma),
$$
### 3. Ensemble Average
$$\langle f \rangle_{\beta} := \int_{\Omega} f(\sigma) P_{\beta}(\mathrm{d}\sigma).$$

### 4. Perturbed Hamiltonian 
$$H_{\lambda}(\sigma) := H(\sigma) + \lambda M(\sigma)
$$
### Useful proposition
$$
\partial_{\lambda} F(\beta, \lambda) = \langle M \rangle_{\beta, \lambda},$$
We define 
$$f(\beta, \lambda) := \lim_{n \to \infty} \frac{F_n(\beta, \lambda)}{n}, \quad
m_{\star}(\beta, \lambda) := \lim_{n \to \infty} \frac{\langle M \rangle_{\beta, \lambda}}{n}.
$$
And we have
$$\partial_{\lambda} f(\beta, \lambda) = m_{\star}(\beta, \lambda)
$$

## Free energy approach
1. Find:
    - A configuration space $\Omega$ and a reference measure $\nu_0$
    - An observable $M : \Omega \to \mathbb{R}$,
    - A perturbed Hamiltonian $H_{\lambda} : \Omega \to \mathbb{R}, H_{\lambda}(\sigma) = H_0(\sigma) + \lambda M(\sigma)$,
    - so that $\mathbb{P}_{\beta,\lambda} \propto \exp(-\beta H_{\lambda}(\sigma))$,
    such that $\mathbb{E}[X_n] = \langle M \rangle_{\beta,\lambda}$ for some $\beta, \lambda$.
2. Calculate the free energy density analytically
    $$f(\beta, \lambda) = \lim_{n \to \infty} -\frac{1}{n \beta} \mathbb{E} \left[ \log \int_{\Omega} \exp\{-\beta H_{\lambda}(\sigma)\} \nu_{0}(\mathrm{d}\sigma) \right].$$
3. $m_{\star} = \lim_{n \to \infty} \mathbb{E}[X_n] = \partial_{\lambda} f(\beta, \lambda)$.


## Replica Method
It is hard for us to calculate  $\mathbb{E}[\log Z]$   so we use this formula:
$$\mathbb{E}[\log Z] = \lim_{ k \to 0 } {\frac{1}{k}\log\mathbb{E}[Z^k]} $$

so when we are doing free energy calculation, we can apply this method to calculate the free energy:
1.  $$S(k,\beta, \lambda) = \lim_{ n \to \infty } {\frac{1}{n}\log}\mathbb{E}[Z_{n}^k] = \sup_{Q}U(Q)$$
2. $$\phi(\beta,\lambda)=\lim_{ k \to 0 }{\frac{1}{k}}S(k,\beta.\lambda) $$
3. $$\phi(\lambda)= \lim_{ \beta \to \infty } {\frac{1}{\beta}\phi(\beta,\lambda)}$$
4. $$m(\lambda) = \partial_{\lambda} \phi(\lambda)$$
This is the general recepe for mean fields calculation.
# Some mathematic methods

## 1. Delta function
This function is commonly used in Physics.
1.  $$\mu(\{a\}) = 1, \, \mu(\{\mathbb{R}/\{a\}\}) = 0$$ 
2. $$\delta(x-a) = \lim_{\sigma \to 0} \phi_\sigma (x-a), \text{ where } \phi_\sigma (x-a) \text{ is the Gaussian density with mean } a \text{ and variance } \sigma^2.$$  
3.   $$\int f(x) \delta(x-a) dx = \lim_{\sigma \to 0} \int f(x) \phi_\sigma (x-a) dx, \text{ for some test function } f.$$
4. $$f(a) = \int_{\mathbb{R}} f(x) \delta(x-a) \, dx$$
5.  The Fourier Transform$$a \in \mathbb{R}, \, \delta(x - a) = \frac{1}{2\pi} \int_{-\infty}^{+\infty} e^{ip(x-a)}d\mathbf{p}$$ $$a \in \mathbb{R}^d, \, \delta(x - a) = \frac{1}{(2\pi)^d} \int_{-\infty}^{+\infty} e^{i \langle \mathbf{p}, \mathbf{x} - \mathbf{a} \rangle} \, d\mathbf{p}$$
## 2. Gaussian Identity Formula

$$\exp \left\{ \frac{\| \mathbf{x} - \mathbf{a} \|_A^2}{2} \right\} = \det(A)^{-\frac{1}{2}} \int \frac{1}{(\sqrt{2\pi})^d} \exp \left\{ \langle \mathbf{p}, \mathbf{x} - \mathbf{a} \rangle - \frac{1}{2} \| \mathbf{p} \|_{A^{-1}}^2 \right\} d\mathbf{p}$$

$$\exp \left\{ -\frac{\| \mathbf{x} - \mathbf{a} \|_A^2}{2} \right\} = \det(A)^{-\frac{1}{2}} \int \frac{1}{(\sqrt{2\pi})^d} \exp \left\{ i \langle \mathbf{p}, \mathbf{x} - \mathbf{a} \rangle - \frac{1}{2} \| \mathbf{p} \|_{A^{-1}}^2 \right\} d\mathbf{p}$$
Where $\|x\|_{A} = (x^TAx)^{\frac{1}{2}}$

## 3. Laplace Method
$$\text{If } f_n(\lambda) \to f(\lambda) \text{ as } n \to \infty, \text{ then } \int_{\mathbb{R}^k} \exp\{n f_n(\lambda)\} d\lambda \dot{=} \sup_{\lambda \in \mathbb{R}^k} \exp\{n f_n(\lambda)\}.
$$
$$\text{where } a_n \dot{=} b_n \iff \lim_{n \to \infty} \frac{1}{n} \log a_n = \lim_{n \to \infty} \frac{1}{n} \log b_n$$

# Statistical Model Set up

### $\mathbb{Z_{2}}synchronization$


$$\theta = (\theta_1, \theta_2, \ldots, \theta_n)^{T} \in \mathbb{R}^n, \quad \theta_i \overset{\text{i.i.d.}}{\sim} \text{Unif}(\mathbb{Z}_2 = \{\pm 1\}), \quad \theta \in \{\pm 1\}^n. $$
$$Y = \frac{\lambda}{n} \theta \theta^{T} + W \in \mathbb{R}^{n \times n}, \quad W \sim \text{GOE}(n).$$
Obeserve $Y$ and estimate $\theta$ 

### Spiked GoE model

We consider a symmetric random matrix $\mathbf{A} \in \mathbb{R}^{n \times n}$,  $mathbf{A} = \lambda \mathbf{u} \mathbf{u}^\top + \mathbf{W}$  where $\lambda \geq 0$ is the signal to noise ratio, $$\mathbf{u} \in \mathbb{S}^{n-1} \equiv \{ \mathbf{x} \in \mathbb{R}^n : \|\mathbf{x}\|_2 = 1 \}$$
is a spike vector, and 
$$\mathbf{W} \sim \text{GOE}(n): \text{ } \mathbf{W} \in \mathbb{R}^{n \times n} \text{  is a symmetric matrix, } W_{ij} \sim \mathcal{N}(0, 1/n) \text{ for } 1 \leq i < j \leq n, \text{ and } W_{ii} \sim \mathcal{N}(0, 2/n) \text{ for } 1 \leq i \leq n.$$


I have completed this part of the study, but the calculation detail is still being organized


# Concentration Inequality

I have finished reading this part. Still writing the notes.... 





