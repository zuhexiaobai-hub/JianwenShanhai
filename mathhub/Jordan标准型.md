# Jordan 标准型

>[!NOTE] **定义**(Jordan块)
>设 $n \in \mathbb{N}, a \in \mathbb{C}$，称
>
>$$
>	J_{n}(a) = \left(\begin{matrix}
>	a & 1 & &  \\
>	& a & \ddots & \\
>	& & \ddots & 1 \\
>	& & & a
>	\end{matrix}\right)
>$$
>
>为 **Jordan 块**。

下面我们介绍 Jordan 块的一些基本性质。
1. $J_n(a)$ 的特征多项式和极小多项式都是 $(x-a)^n$。

2. 设 $f\in\mathbb{C}[x]$，则

   $$
      f\left(J_n(a)\right)=
      \begin{pmatrix}
      f(a) & \dfrac{f'(a)}{1!} & \dfrac{f''(a)}{2!} & \cdots & \dfrac{f^{(n-2)}(a)}{(n-2)!} & \dfrac{f^{(n-1)}(a)}{(n-1)!} \\
      & f(a) & \dfrac{f'(a)}{1!} & \dfrac{f''(a)}{2!} & \ddots & \dfrac{f^{(n-2)}(a)}{(n-2)!} \\
      & & f(a) & \dfrac{f'(a)}{1!} & \ddots & \vdots \\
      & & & f(a) & \ddots & \dfrac{f''(a)}{2!} \\
      & & & & \ddots & \dfrac{f'(a)}{1!} \\
      & & & & & f(a)
      \end{pmatrix}.
   $$

   特别地，

   $$
      J_n^2(0)=
      \begin{pmatrix}
      0 & 0 & 1 & \cdots & 0 \\
      & 0 & 0 & \ddots & \vdots \\
      & & 0 & \ddots & 1 \\
      & & & \ddots & 0 \\
      & & & & 0
      \end{pmatrix},
      \qquad
      J_n^3(0)=
      \begin{pmatrix}
      0 & 0 & 0 & 1 & \cdots & 0 \\
      & 0 & 0 & 0 & \ddots & \vdots \\
      & & 0 & 0 & \ddots & 1 \\
      & & & 0 & \ddots & 0 \\
      & & & & \ddots & 0 \\
      & & & & & 0
      \end{pmatrix},
      \qquad\cdots,\qquad
      J_n^{n-1}(0)=
      \begin{pmatrix}
      0 & \cdots & 0 & 1 \\
      & \ddots & & \vdots \\
      & & 0 & 0 \\
      & & & 0
      \end{pmatrix}.
   $$

3. 和 $J_n(a)$ 乘法可交换的矩阵一定是 $J_n(a)$ 的多项式。

我们有核心是定理：

> [!NOTE] **定理** (Jordan 标准型定理)
>
> 设 $A$ 是 $n$ 阶复矩阵，则存在可逆复矩阵 $P$ 和 Jordan 块 $J_{n_1}(\lambda_1),J_{n_2}(\lambda_2),\cdots,J_{n_s}(\lambda_s)$，使得
>
> $$
>    A \quad \text{is similar to} \quad\operatorname{diag}\left\{J_{n_1}(\lambda_1),J_{n_2}(\lambda_2),\cdots,J_{n_s}(\lambda_s)\right\},
> $$
>
> 且 $J_{n_1}(\lambda_1),J_{n_2}(\lambda_2),\cdots,J_{n_s}(\lambda_s)$ 不计次序是唯一的。我们称 $\operatorname{diag}\left\{J_{n_1}(\lambda_1),J_{n_2}(\lambda_2),\cdots,J_{n_s}(\lambda_s)\right\}$ 是 $A$ 的 Jordan 标准型。
> 
> ---
>
>**注.** 交换两个 Jordan 块顺序后得到的新矩阵仍然和原矩阵相似，故可以不计顺序。

事实上，矩阵的相似不随域的扩张而改变。而如果矩阵 $A,B$ 在 $\mathbb{C}^{n \times n}$ 上相似，谈在更小的域内是否相似是无意义的。Jordan 标准型的计算参考[Jordan型计算](mathhub/Jordan型计算.md)。