---
title: "Limiting Dynamics of SGD: Modified Loss, Phase Space Oscillations, and Anomalous Diffusion"
date: 2021-07-19
publishDate: 2021-07-19T20:23:32.256661Z
authors: ["Daniel Kunin", "javier", "Lauren Gillespie", "Eshed Margalit", "Hidenori Tanaka", "Surya Ganguli", "Daniel LK Yamins"]
publication_types: ["1"]
abstract: "In this work we explore the limiting dynamics of deep neural networks trained with stochastic gradient descent (SGD). As observed previously, long after performance has converged, networks continue to move through parameter space by a process of anomalous diffusion in which distance travelled grows as a power law in the number of gradient updates with a nontrivial exponent. We reveal an intricate interaction between the hyperparameters of optimization, the structure in the gradient noise, and the Hessian matrix at the end of training that explains this anomalous diffusion. To build this understanding, we first derive a continuous-time model for SGD with finite learning rates and batch sizes as an underdamped Langevin equation. We study this equation in the setting of linear regression, where we can derive exact, analytic expressions for the phase space dynamics of the parameters and their instantaneous velocities from initialization to stationarity. Using the Fokker-Planck equation, we show that the key ingredient driving these dynamics is not the original training loss, but rather the combination of a modified loss, which implicitly regularizes the velocity, and probability currents, which cause oscillations in phase space. We identify qualitative and quantitative predictions of this theory in the dynamics of a ResNet-18 model trained on ImageNet. Through the lens of statistical physics, we uncover a mechanistic origin for the anomalous limiting dynamics of deep neural networks trained with SGD. "
featured: true
publication: "arXiv"
url_preprint: https://arxiv.org/abs/2107.09133
url_pdf: https://arxiv.org/pdf/2107.09133.pdf
tags: ["Deep Learning", "Theory"]
---

