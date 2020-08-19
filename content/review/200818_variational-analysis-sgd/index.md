---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "A Variational Analysis of Stochastic Gradient Algorithms"
paper_authors: "Stephan Mandt, Matthew D. Hoffman, David M. Blei"
paper_date: "February 2016"
paper_tldr: "Rethinking SGD in the limit of continuous time yields valuable insight, particularly on hyperparameter tuning. This paper introduces the SDE derivation in the previously reviewed 'Three Factors' paper, and elaborates on the minimization of the KL divergence of the stationary distribution of the underlying OU process and the target posterior (and as such relies on the Bayesian view on ML algorithms, rather than the optimization view)."
url_pdf: https://arxiv.org/abs/1602.02666

authors: [javier]
date: 2020-08-18T09:19:16-07:00

# Schedule page publish date (NOT publication's date).
# This page will always be hidden
publishDate: 2020-08-18T09:19:16-07:00

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

- The authors expand on their [previous work](https://opt-ml.org/papers/OPT2015_paper_8.pdf) on the continuous time-limit of SGD. They show how SGD with a constant LR can be modelled as an SDE that reaches a stationary distribution. Further, if the loss function is interpreted as a log-posterior and make the goal to approximate the posterior as well as possible (in terms of KL divergence), the authors derive optimal hyperparameters. 
- 4 key assumptions:
  - The gradient noise is Gaussian
  - The weight estimates are constrained to a small enough region of parameter space that the sampling noise covariance of the stochastic gradients is constant. 
  - The step size is small enough that the discrete Markov Process can be approximated by a continuous time Markov process. 
  - Lastly, the stationary distribution of the process has a closed form solution if we assume we can approximate the loss as a quadratic bowl (we are close to a local minima).
- The authors show how this SDE view is related to stochastic gradient Fisher scoring. 
- The main practical contribution, is that this view provides a way to compute mathematically optimal hyperparameters for a small amount if data, in contrast to the computational burden of cross-validating parameters. 
 

