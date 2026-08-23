# $\lambda$-矩阵

📕对于矩阵的相抵关系，我们有一个量可以直接去判断两个矩阵是否相抵，即：**矩阵的秩**。[矩阵](矩阵.md)\
我们想找到关于矩阵相似的充要条件。

**经过研究我们指出如下定理：**

> [!note] **定理**
> 给定数域 $\mathbb{F}$ 上的矩阵 $A,B$，则 $A$ 与 $B$ 相似的充要条件为 $\lambda$-矩阵 $\lambda I-A$ 与 $\lambda I-B$ 相抵。

---

📕**我们这就给出 $\lambda$-矩阵的一些定义及基础定理。**

首先注意到 $\lambda I-A$ 是如下这样的矩阵：

$$
    \begin{pmatrix}
        \lambda-a_{11} & -a_{12} & \cdots & -a_{1n} \\
        -a_{21} & \lambda-a_{22} & \cdots & -a_{2n} \\
        \vdots & \vdots & \ddots & \vdots \\
        -a_{n1} & -a_{n2} & \cdots & \lambda-a_{nn}
    \end{pmatrix}.
$$

我们抽象出如下 $\lambda$-矩阵：

> [!note] **定义**（$\lambda$-矩阵）
> $$
>     A(\lambda)=
>     \begin{pmatrix}
>         a_{11}(\lambda) & a_{12}(\lambda) & \cdots & a_{1n}(\lambda) \\
>         a_{21}(\lambda) & a_{22}(\lambda) & \cdots & a_{2n}(\lambda) \\
>         \vdots & \vdots & \ddots & \vdots \\
>         a_{m1}(\lambda) & a_{m2}(\lambda) & \cdots & a_{mn}(\lambda)
>     \end{pmatrix}.
> $$
>
> 其中 $a_{ij}(\lambda)$ 是以 $\lambda$ 为未定元的数域 $\mathbb{F}$ 上的多项式。上述这样的矩阵，称为 $\lambda$-矩阵。

**接下来自然需要定义 $\lambda$-矩阵的运算。**\
💡$\lambda$-矩阵的加法、数乘及乘法都与普通数字矩阵的运算相同，==只需将数字运算转换成多项式运算==，而多项式运算我们已经定义过。接下来需要定义 $\lambda$-矩阵的相抵。即需定义 $\lambda$-矩阵的初等行（列）变换：

> [!note] **定义**（$\lambda$-矩阵的初等行（列）变换）
> 1. 将 $A(\lambda)$ 的两行（列）对换。
> 2. 将 $A(\lambda)$ 的第 $i$ 行（列）乘以 $\mathbb{F}$ 中的非零常数 $c$。
> 3. 将 $A(\lambda)$ 的第 $i$ 行（列）乘以 $\mathbb{F}$ 上的多项式 $f(\lambda)$ 后加到第 $j$ 行（列）上去。

> **注.**
> 1. 可以发现 $\lambda$-矩阵的前两个初等变换的定义与数字矩阵的完全一样。
> 2. ⚠️但第三个不同，这导致我们数字矩阵的一些结论无法完全照搬到 $\lambda$-矩阵，请读者注意。

自然而然，引出三个初等 $\lambda$-矩阵，以及对应的初等矩阵对应初等变换定理：

> [!note] **定义**（初等 $\lambda$-矩阵）
> 1. 将 $n$ 阶单位阵的第 $i$ 行与第 $j$ 行对换，记为 $P_{ij}$。
> 2. 将 $n$ 阶单位阵的第 $i$ 行乘以非零常数 $c$，记为 $P_i(c)$。
> 3. 将 $n$ 阶单位阵的第 $i$ 行乘以多项式 $f(\lambda)$ 后加到第 $j$ 行上去得到的矩阵，记为 $T_{ij}(f(\lambda))$。


> [!note] **定义**($\lambda$-矩阵的相抵)
> 若 $A(\lambda),B(\lambda)$ 是同阶 $\lambda$-矩阵且 $A(\lambda)$ 经过 $\lambda$-矩阵的初等变换后可变为 $B(\lambda)$，则称 $A(\lambda)$ 与 $B(\lambda)$ 相抵。

> [!note] **定理**
> 对 $\lambda$-矩阵 $A(\lambda)$ 施行第 $k\,(k=1,2,3)$ 类初等行(列)变换等于用第 $k$ 类初等 $\lambda$-矩阵左(右)乘以 $A(\lambda)$。

逆矩阵：
> [!note] **定义**
> 若 $A(\lambda),B(\lambda)$ 都是 $n$ 阶 $\lambda$-矩阵，且
>
> $$
>     A(\lambda)B(\lambda)
>     =
>     B(\lambda)A(\lambda)
>     =
>     I_n,
> $$
>
> 则称 $B(\lambda)$ 是 $A(\lambda)$ 的逆 $\lambda$-矩阵，这时称 $A(\lambda)$ 为可逆 $\lambda$-矩阵，在没有歧义的情况下，简称为可逆阵。

📕设 $M(\lambda)$ 是一个 $n$ 阶 $\lambda$-矩阵，则 $M(\lambda)$ 可以化为如下形状：

$$
    M(\lambda) = M_m\lambda^m + M_{m-1}\lambda^{m-1} + \cdots + M_0.
$$

其中 $M_i$ 为数域 $\mathbb{F}$ 上的 $n$ 阶数字矩阵。因此，一个多项式矩阵可以化为系数为矩阵的多项式，反之亦然 (这是显然的，通过矩阵加法就可以得到)。接下来给出 $\lambda$-矩阵版本的带余除法：

> [!note] **引理**
> 设 $M(\lambda)$ 与 $N(\lambda)$ 是两个 $n$ 阶 $\lambda$-矩阵且都不等于零。
>
> 又设 $B$ 为 $n$ 阶数字矩阵，则必存在 $\lambda$-矩阵 $Q(\lambda)$ 及 $S(\lambda)$ 和数字矩阵 $R$ 及 $T$，使得
>
> $$
>     M(\lambda) = (\lambda I-B)Q(\lambda)+R,
> $$
>
> $$
>     N(\lambda) = S(\lambda)(\lambda I-B)+T.
> $$

核心定理为如下：

> [!note] **定理**
> 给定数域 $\mathbb{F}$ 上的矩阵 $A,B$，则 $A$ 与 $B$ 相似的充要条件为 $\lambda$-矩阵 $\lambda I-A$ 与 $\lambda I-B$ 相抵。

接下来我们自然想知道 $\lambda$-矩阵的相抵标准型是什么了，我们当然希望任何一个 $\lambda$-矩阵都相抵于一个对角 $\lambda$-矩阵。我们有如下定理：

> [!note] **定理**
> 设 $A(\lambda)$ 是一个 $n$ 阶 $\lambda$-矩阵，则 $A(\lambda)$ 相抵于对角阵
>
> $$
>     \operatorname{diag}
>     \bigl\{
>         d_1(\lambda),
>         d_2(\lambda),
>         \ldots,
>         d_r(\lambda),
>         0,
>         \ldots,
>         0
>     \bigr\}.
> $$
>
> 其中 $d_i(\lambda)$ 是非零首一多项式，且
>
> $$
>     d_i(\lambda)\mid d_{i+1}(\lambda)
>     \qquad
>     (i=1,2,\ldots,r-1).
> $$
> ---
> 称上段中的
>
> $$
>     \operatorname{diag}
>     \bigl\{
>         d_1(\lambda),
>         d_2(\lambda),
>         \ldots,
>         d_r(\lambda),
>         0,
>         \ldots,
>         0
>     \bigr\}
> $$
>
> 为 $A(\lambda)$ 的**法式**或**相抵标准型**。


> [!note] **推论**
> 设 $A$ 是数域 $\mathbb{K}$ 上的 $n$ 阶矩阵，则 $A$ 的特征矩阵 $\lambda I_n-A$ 必相抵于
>
> $$
>     \operatorname{diag}
>     \bigl\{
>         1,\ldots,1,
>         d_1(\lambda),\ldots,d_m(\lambda)
>     \bigr\}.
> $$