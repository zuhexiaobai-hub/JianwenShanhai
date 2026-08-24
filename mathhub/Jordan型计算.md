# Jordan型计算
📕本节的目的是，任意给定一个复数域上的矩阵 $A$，求出 $A$ 的 Jordan 标准型，即存在矩阵 $P$，使得

$$
    P^{-1}AP = J.
$$

求出对应的 $P$ 与 $J$。

---

对于一般的矩阵，我们自然希望它的相似标准型可以做到对角矩阵，但当然不可能每个矩阵都能像这般简单。对应的，我们有 Jordan 标准型。(以下讨论都在复数域上)\
💡本节不讲 Jordan 型具体来源，纯计算。

> [!note] **定理**
> 给定复数域上的矩阵 $A$，且其初等因子组为
>
> $$
>     (\lambda-\lambda_1)^{r_1},(\lambda-\lambda_2)^{r_2},\cdots,(\lambda-\lambda_k)^{r_k}.
> $$
>
> 则 $A$ 相似于分块对角矩阵
>
> $$
>     J=
>     \begin{pmatrix}
>         J_1 & & & \\
>         & J_2 & & \\
>         & & \ddots & \\
>         & & & J_k
>     \end{pmatrix}.
> $$
>
> 其中 $J_i$ 为 $r_i$ 阶矩阵，且
>
> $$
>     J_i=
>     \begin{pmatrix}
>         \lambda_i & 1 & & & \\
>         & \lambda_i & 1 & & \\
>         & & \ddots & \ddots & \\
>         & & & \ddots & 1 \\
>         & & & & \lambda_i
>     \end{pmatrix}.
> $$