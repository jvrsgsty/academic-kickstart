---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Three Factors Influencing Minima in SGD"
paper_authors: "Stanisław Jastrzębski, Zachary Kenton, Devansh Arpit, Nicolas Ballas, Asja Fischer, Yoshua Bengio, Amos Storkey"
paper_date: "November 2017"
paper_tldr: "Batch size, learning rate and gradient covariance influence minima. LR/BS ratio is key in the width of the minima, impacting generalization. SGD as SDE discretization. Experimental validation of theory."
url_pdf: https://arxiv.org/abs/1711.04623

authors: [javier]
date: 2020-08-12T09:19:16-07:00

# Schedule page publish date (NOT publication's date).
publishDate: 2020-08-12T09:19:16-07:00

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["0"]


tags: ["Learning Dynamics", "Theory", "SGD"]
categories: []


---

### Review

#### Summary
- SGD performs similarly for different batch sizes, but a constant LR/BS ratio. 
- The authors note that SGD with the same LR/BS ratio are different discretizations of the same Stochastic Differential Equation. 
- LR schedules and BS schedules are interchangeable, what matters, again, is what the LR/BS looks like. 
- Width of minima is defined in terms of the trace of the Hessian $Tr(H)$ at the minima: lower trace = wider minima. 
  - Assumption 1: At a local minima, loss surface approximated via a quadratic bowl. This lets training process be approximated by Orenstein-Unhlenbcek process. 
  - Assumption 2: $H$ is approximated via the covariance matrix of the stochastic gradients ($H=C$ relies on $C$ being anisotropic). 
- Larger LR/BS correlates with wider minima, giving better generalization. 
- However, larger $\beta$, with constant $\frac{LR}{BS}=\frac{\beta \eta}{\beta S}$ causes the approximation to the SDE to break down, leading to lower performance.
- Discretization errors become aparent at large learning rates. 
- Central Limit Theorem assumptions break down for small dataset, large batches. 


