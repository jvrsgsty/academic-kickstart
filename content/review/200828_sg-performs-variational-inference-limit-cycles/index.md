---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Stochastic gradient descent performs variational inference, converges to limit cycles for deep networks"
paper_authors: "Pratik Chaudhari, Stefano Soatto"
paper_date: "October 2017"
paper_tldr: "The authors present two main results: a thorough mathematical analysis on how SGD performs variational inference and what its steady state behavior looks like: limit cycles. They present empirical quantities similar to the ones we have measured and analyze those compared to the null of Brownian motion." 
url_pdf: https://arxiv.org/abs/1710.11029

authors: [javier]
date: 2020-08-28T19:19:16-07:00

# Schedule page publish date (NOT publication's date).
# This page will always be hidden
publishDate: 2020-08-18T09:19:16-07:00

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["0"]

tags: ["Learning Dynamics", "Theory", "SDE"]
categories: []

---

### Review

#### Summary

##### Variantional inference
- Proof that SGD minimizes a potential along with an entropic regularization term. 
- However, this potential differs from the loss used to compute backpropagation gradients. They are only equal if the gradient noise were isotropic (i.e. a constant multiple of the identity). 
- The gradient noise is highly non-isotropic with a very low rank covariance matrix. 
- The locations in weight space to which SGD "converges" are not true local minima of the original loss:
- Their SDE analysis does not make the same assumptions as previous papers (e.g. quadratic approximation of the loss), even though the SDE they analyze is the same as in the papers I recently reviewed (albeit with different notation). Instead, they show how the continuous-time limit of SGD evolves according to the Fokker-Planck equation.
    - No quadratic assumption on loss
    - No constant covariance (thought experiments show it does not change much)
- The practical implications of their analysis are:
    - The LR should scale linearly with BS to generalize well. 
    - Sampling with replacement is better than without replacement, since the diffusion matrix (i.e. correlation matrix), with a more prononced effect at larger batches. 

##### Limit Cycles
- In a vicinity of a critical point, the weights do not present Brownian motion, rather they have a deterministic component generating loops in weight space. 
- Relevant observables shown:
    - Eigenvalue spectra of covariance matrices over time (does not change much), along with mean and std of eigenvalues, as well as rank. These quantities inform the performance of a given architecture on a dataset.  
    - Fast Fourier Transform of weights over time (should be constant in Brownian motion case). 
    - Auto-correlation of weights (should quickly decay to zero in Brownian motion case).
    - Dimension-normalized gradient norm: they observe it does not decrease wrt the number of epochs and even shows a growing trend. This is justified by the presence of a non-zero force $j(x)$ which is responsible for theobserved Fourier harmonics.  


