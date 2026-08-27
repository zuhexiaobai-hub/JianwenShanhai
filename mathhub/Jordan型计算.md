# Jordan型计算
📕本节的目的是，任意给定一个复数域上的矩阵 $A$，求出 $A$ 的 Jordan 标准型，即存在矩阵 $P$，使得

$$
    P^{-1}AP = J.
$$

求出对应的 $P$ 与 $J$。

对于一般的矩阵，我们自然希望它的相似标准型可以做到对角矩阵，但当然不可能每个矩阵都能像这般简单。对应的，我们有 Jordan 标准型。(以下讨论都在复数域上)\
💡本节不讲 Jordan 型具体来源，纯计算。

---

第一种方法是利用代数重数和几何重数。先介绍两种重数。对于 $n$ 阶矩阵 $A$ 的某一个特征值 $\lambda_{0}$：
- **代数重数**：$\lambda_{0}$ 在特征多项式 $\det(\lambda I - A)$ 中的重数，记为 $m_{a}(\lambda)$。
- **几何重数**：特征子空间 $V_{\lambda_{0}}$ 的维数。即 $\dim V_{\lambda_{0}} = \dim\ker(A - \lambda_{0}I) = n - \mathrm{rank}(A - \lambda_{0}I)$。记为 $m_{g}(\lambda_{0})$。

对任意特征值均有：

$$
	1 \le m_{g}(\lambda) \le m_{a}(\lambda)
$$

两者在 Jordan 标准型里的含义：
- $m_{a}(\lambda_{0}) =$ $\lambda_{0}$ 对应 Jordan 块的阶数之和。并且有 $\sum_{i}m_{a}(\lambda_{i}) = n$。
- $m_{g}(\lambda_{0}) =$ $\lambda_{0}$ 对应 Jordan 块的个数。

仅根据这两项无法求出完整的 Jordan 标准型，因为只能初步确定特征值 $\lambda_{0}$ 对应块的阶数和为 $m_{a}(\lambda_{0})$，而无法确定它们的分拆。而下面需要确定每个块的大小：\
💡对于每个 $\lambda_{0}$：规定 $d_{0} = 0$，记 $d_{k} = \dim\ker((A - \lambda_{0}I)^k) = n - \mathrm{rank}((A - \lambda_{0}I)^k)$，特别的 $d_{1} = m_{g}(\lambda_{0})$ 。那么

>$d_{k} - d_{k-1} =$ 阶数 $\ge k$ 的 Jordan 块个数。

依次计算 $d_{1},d_{2},d_{3},\cdots$，直到某个 $d_{k} = m_{a}(\lambda)$。

---

第二种方法是利用：相似 $\Longleftrightarrow$ 特征矩阵的初等因子相同。
> [!note] **定理**(利用初等因子组)
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