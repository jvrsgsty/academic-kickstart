---
title: "Two Routes to Scalable Credit Assignment without Weight Symmetry"
date: 2020-03-01
publishDate: 2020-07-09T20:23:32.256661Z
authors: ["Daniel Kunin", "Aran Nayebi", "javier", "Surya Ganguli", "Jon Bloom", "Daniel LK Yamins"]
publication_types: ["1"]
abstract: "The neural plausibility of backpropagation has long been disputed, primarily for its use of non-local weight transport - the biologically dubious requirement that one neuron instantaneously measure the synaptic weights of another. Until recently, attempts to create local learning rules that avoid weight transport have typically failed in the large-scale learning scenarios where backpropagation shines, e.g. ImageNet categorization with deep convolutional networks. Here, we investigate a recently proposed local learning rule that yields competitive performance with backpropagation and find that it is highly sensitive to metaparameter choices, requiring laborious tuning that does not transfer across network architecture. Our analysis indicates the underlying mathematical reason for this instability, allowing us to identify a more robust local learning rule that better transfers without metaparameter tuning. Nonetheless, we find a performance and stability gap between this local rule and backpropagation that widens with increasing model depth. We then investigate several non-local learning rules that relax the need for instantaneous weight transport into a more biologically-plausible 'weight estimation' process, showing that these rules match state-of-the-art performance on deep networks and operate effectively in the presence of noisy updates. Taken together, our results suggest two routes towards the discovery of neural implementations for credit assignment without weight symmetry: further improvement of local rules so that they perform consistently across architectures and the identification of biological implementations for non-local learning mechanisms."
featured: true
publication: "ICML 2020"

links:
- name: Blog Post
  url: https://ai.stanford.edu/blog/icml-2020/#two-routes-to-scalable-credit-assignment-without-weight-symmetry
url_preprint: https://arxiv.org/abs/2003.01513
url_pdf: http://proceedings.mlr.press/v119/kunin20a.html 
url_slides: https://icml.cc/virtual/2020/poster/6706
url_code: https://github.com/neuroailab/neural-alignment
url_video: https://www.youtube.com/watch?v=fC_E0dO3Rfo

tags: ["ICML", "Learning Rules", "Deep Learning"]
---

