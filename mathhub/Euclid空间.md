# 内积与 Euclid 空间

> [!note] **定义**
> 数域 $\mathbb{R}$ 上的双线性函数 $(\cdot,\cdot)$ 被称为一个**内积**：如果 $(\cdot,\cdot)$ 是**对称正定**的。一个带有内积的线性空间 $V$ 被称为**Euclid空间**。

1. 内积也可以用 $[\cdot,\cdot]$ 表示。
2. $\displaystyle (x,y)\triangleq\sum_{i=1}^{n}x_iy_i$ 就是一个 $\mathbb{R}^{n}$ 上的内积。

> [!note] **定义**
> 设 $V$ 是数域 $\mathbb{R}$ 上的 Euclid 空间。
> 1. 如果 $(x,y)=0$，我们称 $x,y$ **正交**，记作 $x\perp y$。
> 2. 我们称 $\|x\|\triangleq\sqrt{(x,x)}$ 为 $x$ 的**长度**。
> 3. 称向量组 $\{\alpha_1,\alpha_2,\ldots,\alpha_s\}\subset V$ 是**正交向量组**，如果
> $$
>     \alpha_i\perp\alpha_j,\quad\forall\,1\leq i<j\leq s.
> $$
> 
> 4. 称向量组 $\{\alpha_1,\alpha_2,\ldots,\alpha_s\}\subset V$ 是**标准正交向量组**，如果
> $$
>     (\alpha_i,\alpha_j)=\delta_{ij},
>     \quad i,j=1,2,\ldots,s.
> $$
> 
> 5. 称向量组 $\{\alpha_1,\alpha_2,\ldots,\alpha_n\}\subset V$ 是**标准正交向量基**，如果 $\dim V=n$ 且
> $$
>     (\alpha_i,\alpha_j)=\delta_{ij},
>     \quad i,j=1,2,\ldots,n.
> $$

下面我们将任意一组线性无关的向量化为标准正交向量基: \
给定一个线性无关组 $(\alpha_{1},\alpha_{2},\cdots,\alpha_{n})$, 需要分两步进行:
1. 正交化: 取
   
$$
    \left\{
    \begin{aligned}
        \beta_1 &= \alpha_1, \\
        \beta_k &= \alpha_k-\sum_{j=1}^{k-1}\frac{(\alpha_k,\beta_j)}{(\beta_j,\beta_j)}\beta_j.
    \end{aligned}
    \right.
$$

容易验证 $(\beta_{1},\beta_{2},\cdots,\beta_{n})$ 为正交向量组.

2. 单位化: 取 $e_{i} = \frac{\beta_{i}}{\|\beta_{i}\|}$, 那么我们有 $(e_{1},e_{2},\cdots,e_{n})$ 为标准正交向量组.

这种方法称为 **Gram-Schmidt 正交化**.