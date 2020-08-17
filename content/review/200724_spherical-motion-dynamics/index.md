---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Spherical Motion Dynamics of Deep Neural Networks with Batch Normalization and Weight Decay"
paper_authors: "Ruosi Wan, Zhanxing Zhu, Xiangyu Zhang, Jian Sun"
paper_date: "June 2020"
paper_tldr: "DNNs trained with weight decay and batch normalization reach learning equilibrium on the surface of a sphere in parameter space and their limit angular update can be computed a priori."
url_pdf: https://arxiv.org/abs/2006.08419 

authors: [javier]
date: 2020-08-01T09:19:16-07:00

# Schedule page publish date (NOT publication's date).
publishDate: 2020-08-12T09:19:16-07:00

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["0"]

tags: ["Learning Dynamics", "Theory"]
categories: []
---

### Review

#### Summary
- Batch normalization induces scale invariance of the loss with respect to the weights (i.e. $L(x; \theta) = L(x; k \theta)$, for parameters $\theta$ with BN. This expression is not mathematically precise).
- The scale invariance implies in $<\theta_t, \partial L / \partial \theta |_{\theta = \theta_t}> = 0$
- A DNN trained with BN and WD using SDGM, with WD $\lambda$, Momentum $\alpha \geq 0$ and LR $\eta$ has an angular update $\Delta_t$ satisfying
$$
\lim_{t\rightarrow \infty}\Delta_t \simeq \sqrt{\dfrac{2\eta\lambda}{1+\alpha}}
$$
- At equilibrium, the "force" pulling the weights towards the origin (from the weight decay term) and the "force" pushing the weights orthogonally balance out, resulting in movement on the surface of a sphere, with a fixed angular update at every step in training. 
- Properties of Spherical Motion Dynamics:
  - Scale-invariant weights do not suffer from vanishing or exploding gradients. 
  - SGDM cannot get trapped in local minima, since it guarantees an angular update size on $\mathcal{S}^{p-1}$. 
  - With SGDM weights will not converge unless the LR $\eta$ is manually decreased.  

#### Comments
- The theory shown does not seem to consider the role of the batch size in the stochasticity of the training process. 
- The authors' discussion on the Linear Scaling Principle (rescaling the learning rate with the batch size) is not entirely clear to me. It seems the main takeaway is that when rescaling the LR by a factor of $k$ to use a batch size that is $k$ times larger, then the angular update is affected mainly by the change in the rescaling of the LR (which scales with $\sqrt k$). 
  - The authors compare the angular update between $w_t$ and $w_{t+1}$ for the larger batch size against the cumulative angular update over $k$ steps for the smaller batch.  We interpret this to mean the angular update between $w_t$ and $w_{t+k}$, since we cannot say anything about the additivity of the angular updates.
  - The cummulative angular update for small batch is larger than the single step angular update for larger batch size. In fact, we can approximately observe:

  $$
  \dfrac{\Delta_t^{256}(w_t, w_{t+k})}{\Delta_t^{k256}(w_t, w_{t+1})} \lessapprox 
  \sqrt k = \dfrac{\sqrt{2\eta\lambda/(1+\alpha)}}{\sqrt{2k\eta\lambda/(1+\alpha)}}
  $$


