# Set up the model
$\theta = (\theta_{1}, \theta_{2},\dots, \theta_n)^{T} \in \mathbb{R^n}$  $\theta_{i}$  i.i.d $Unif(\mathbb{Z^2})$       $\theta = \{\pm 1\}^n$ 
$$Y = \frac{\lambda}{n} \theta \theta^{T}+W \in \mathbb{R^{n\times n}}$$ $W \sim  GOE(n)$   $W_{ij}$ $i.i.d$ $N(0, \frac{2}{n})$  $1\leq i \leq n$  $W_{ij} =W_{ji}$ 
We observe $Y \in \mathbb{R^{n \times n}}$ and estimate $\theta$ 
Expected risk: $$R(\hat{\Theta}) = \mathbb{E}_{\theta \sim \text{unif}(Z_2^n)} \left\Vert \hat{\Theta}(Y) - \theta \theta^T \right\Vert_F^2/n^2
$$
## Statistical Estimator
#### MLE 
$$\hat{\Theta}_{ML}(Y) = \arg\max_{\sigma \in \Theta_n} L(\sigma | Y) 
= \arg\min_{\sigma} \left\Vert Y - \lambda\sigma^T\sigma/n \right\Vert_F^2 
$$

$$\hat{\Theta}_{ML}(Y) = \arg\max_{\sigma \in \{\pm1\}^{n}}<\sigma,Y\sigma>  $$
#### Risk function
$$R(\hat{\theta}, \theta) = \mathbb{E}_{X \sim \mathbb{P}_{\theta}} L(\hat{\theta}(X), \theta) = \int_X L(x, \theta) \mathbb{P}_{\theta}(dx).
$$
$\text{Expected risk is } R_B(\hat{\theta}, Q) = \int_{\Theta} R(\hat{\theta}, \theta)Q(d\theta).$

#### Bayes estimator 
$\text{Bayes risk is } R_B(Q) = \inf_{\hat{\theta}:X \rightarrow A} R_B(\hat{\theta}, Q).$
$\text{Bayes estimator is } \hat{\theta}_{\text{Bayes}} = \arg \min_{\hat{\theta}:X \rightarrow A} R_B(\hat{\theta}, Q).$

