# Why chooses Adam over solving the eigenvalues of hessian matrix?

>Confirm correctness with professors

<script src='https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.4/MathJax.js?config=default'></script>

$$\vec{x}=v_0t+\frac{1}{2}at^2$$
## Why Adam?
The initial loss function of weights and biases is known after an epoch. However, we aren’t going to solve it because of the increment of the time complexity.

```math
O(Adam)=O(ngd)
O(solve eigenvalues of hessian)>O(n^4)
T(Adam)<T(SGD)
```
Hence, we choose Adam instead of the alternate method.

## The training process
<div class="sl-block is-focused" data-block-type="image" data-name="image-ffe7ae" style="width: 960px; height: 597.483px; left: 0px; top: 74px; min-width: 1px; min-height: 1px;" data-origin-id="e6c9ddc09a410f78c6f404117c785593"><div class="sl-block-content" style="z-index: 11;"><img style="" data-natural-width="1716" data-natural-height="1068" data-lazy-loaded="" src="https://s3.amazonaws.com/media-p.slid.es/uploads/1169602/images/9645003/Screenshot_from_2022-06-15_23-13-54.png"></div></div>
1. The input vector isn’t a batch. One inputs the vector to compute the loss function of a batch with Adam (minimizing the gradient of loss function ). Nonetheless, one only updates biases and weights every time an epoch terminates.
2. One will walk to the minima faster if one has a more optimized learning rate function.

## [Quantum Gradient Descent and Newton](https://arxiv.org/pdf/1612.01789.pdf)

>(BTW, QAE (Annealing) can solve the eigenvalues of a matrix with higher dimensions than VQE (Quantum gates). It is because the qubits aren't enough.
