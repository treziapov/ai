L1: Regularization for sparsity
- Problem: sparse vectors often contain many dimensions
    creating a feature cross results in even more dimensions
    model size may become huge and requires more RAM
- Want: to drop weights to 0 where possible
    helps reduce RAM and noise
- Could create a regularization (L0) term that penalizes the count of non-zero coffeicients
    turns our convex optimization problem into non-conver (NP hard)
- Can user L1 regularization as approximation to L0

L1 vs L2 regularization
- L2 penalizes weight^2
- L1 penalizes |weight|

