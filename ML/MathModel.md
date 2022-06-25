# Why chooses Adam over solving the eigenvalues of hessian matrix?

>Confirm correctness with professors

## Why Adam?
The initial loss function of weights and biases is known after an epoch. However, we aren’t going to solve it because of the increment of the time complexity.

```math
O(Adam)=O(ngd)
O(solve eigenvalues of hessian)>O(n^4)
T(Adam)<T(SGD)
```
Hence, we choose Adam instead of the alternate method.

## The training process
1. The input vector isn’t a batch. One inputs the vector to compute the loss function of a batch with Adam (minimizing the gradient of loss function ). Nonetheless, one only updates biases and weights every time an epoch terminates.
2. One will walk to the minima faster if one has a more optimized learning rate function.

## [Quantum Gradient Descent and Newton](https://arxiv.org/pdf/1612.01789.pdf)

>(BTW, QAE (Annealing) can solve the eigenvalues of a matrix with higher dimensions than VQE (Quantum gates). It is because the qubits aren't enough.