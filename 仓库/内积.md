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
