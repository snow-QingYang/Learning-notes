# 1.1Field theoretic calculations & Large deviations
## 2.1 Delta Function 
$\delta(x-a)$   **Mathematically:**$\mu(\{a\}) = 1, \, \mu(\{R/\{a\}\}) = 0$

$\delta(x - a) = \lim_{\sigma \to 0} \phi_\sigma(x - a)$ where  $\phi_\sigma(x - a)$ is the Gaussian density with mean $a$ and variance  $\sigma^2$. $$ \int f(x) \delta(x - a) dx = \lim_{\sigma \to 0} \int f(x) \phi_\sigma(x - a) dx $$ **Physically:** $$ f(a) = \int_R f(x) \delta(x - a) dx $$ - **Delta Identity Formula:** For  $a \in R$ : $$ \delta(x - a) = \frac{1}{2\pi} \int_{-\infty}^{+\infty} e^{ip(x - a)} dp $$ For $a \in \mathbb{R}^d$: $$ \delta(x - a) = \frac{1}{(2\pi)^d} \int_{-\infty}^{+\infty} e^{i\langle p, x - a \rangle} dp $$ **Intuition:** From the Fourier transform: $$ f(x) = \frac{1}{2\pi} \int_{-\infty}^{+\infty} e^{ipx} \left( \int_{-\infty}^{+\infty} e^{-i\alpha p} f(\alpha) d\alpha \right) dp $$ $$ = \int_{-\infty}^{+\infty} \left( \frac{1}{2\pi} \int_{-\infty}^{+\infty} e^{ip(x - \alpha)} dp \right) f(\alpha) d\alpha $$ And by the identity formula: $$ f(x) = \int_{-\infty}^{+\infty} f(α) \delta(x - α) dα $$

Consider $\sigma_{1}, \dots, \sigma_{k} \in \mathbb{R^n}$  k is fixed and  $n \to \infty$
We let all $\sigma_{i}$ be i.i.d $Unif(S^{n-1}(\sqrt{ n }))$  consider $\sigma$:
$$
\sigma = [\sigma_{1}, \sigma_{}{2}, \dots, \sigma_{k}{}] 
$$
$$
\bar{Q}(\sigma) = \frac{\sigma^{T}\sigma}{n} \in \mathbb{R^{k \times k}} 
$$
Then we consider $Q \in \mathbb{R^{k \times k}}$ , which is symmetric matrix with diagonals entries are all $1$ 

Then $P(\bar{Q}(\sigma) \approx Q)$ 