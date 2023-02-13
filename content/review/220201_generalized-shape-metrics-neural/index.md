---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Generalized Shape Metrics on Neural Representations"
paper_authors: "Alex Williams, Erin Kunz, Simon Kornblith, Scott Linderman"
paper_date: "October 2021"
paper_tldr: "This paper highlights issues that can occur when represtation similarity metrics are not *metrics* in the mathematical sense. The authors formulate novel metrics based on previous approaches, by getting them to satisfy the triangle inequality, including one geared specifically for CNNs. They demonstrate theis methods are effective and scalable to large numbers of specimens."
url_pdf: https://proceedings.neurips.cc/paper/2021/file/252a3dbaeb32e7690242ad3b556e626b-Paper.pdf 

authors: [javier]
date: 2021-02-07T09:19:16-07:00

# Schedule page publish date (NOT publication's date).
publishDate: 2022-02-07T09:19:16-07:00

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["0"]

tags: ["Neural Representations", "Metrics", "Representation Similarity"]
categories: []
---

### Review

#### Summary
- The authors build on ideas from the statistical shape analysis literature to 
  develop similarity measures that are metrics: that are positive, symmetric and
  respect the triangle inequality. 
- They highlight how quantifying the similatiry between matrices of high dimensional
  vectors in $\mathbb R^n$ over a set of $m$ reference stimuli is complicated.
- Previous approaches include PLS regressiom (which is asymmetric), CCA, CKA, 
  and RSA (which are symmetric, but do not satisfy the triangle inequality), among others. 
- The authors define representations as equivalent if they are linearly mappable 
  to each other within a set of allowable transformations $\mathcal G$, and highlight 
  that nonlinear mappings may be achieved by preprocessing the features with a 
  nonlinear function. 
- $\mathcal G$ is normally the set of orthogonal transforms with determinant of 1, 
  but here the authors generalize this to suit the use case of quantifying dissimilarity 
  in neural representations. 
  - In particular, they propose $\mathcal G$ be the group of linear isometries, 
    i.e. distance-preserving transforms, which turns out to be a subgroup of the
    set of orthogonal transformations (without the det = 1 condition). 
- Dependig on the desired notion of representational simlilarity, the authors exhibit how 
  to define certain metrics where similarity can be assesed:
  - Up to permutation (linear ssignment problem)
  - Up to rotation (orthogonal Procrustes problem)
  - Up to a an affine transform (related to CCA)
  - Up to nonlinear transforms (in the appendix, related to CKA)
- The authors also define a metric for convolutional layers that leverages the 
  spatial structure of conv layers and relies the group of circular shifts and 
  Kronecker products.
- The authors present some experimental results on neural mouse data and NAS-Bench-101 data:
  - They show how trinagle inequality violations occur in practice (though not always, depending on the dataset) for commonly 
    used simmilarity measures, and that generalized shape metrics correct for this. 
  - They show that neural representation metric spaces can be embeded in Euclidean 
    spaces but suggest using a higher number of embedding dimensions than what is normally
    used. 
  - They show such embeddings of neural data preserve neural hierarchy structure and
    are scientifically interpretable. 
  - They show that in artificial NNs, the representations show consistent structure across layers. 

#### Comments
- 

