# 非负函数的 Lebesgue 积分

---

### 一、核心目的：从集合的“大小”到函数的“总量”

根据上一章，测度 $\mu(E)$ 衡量集合 $E$ 的大小；\
而积分希望衡量函数相对于测度的总量。最基本的要求是 $\int\chi_E\,d\mu=\mu(E)$：高度为 $1$、底集为 $E$ 的函数，其总量就是 $E$ 的测度 (按照传统度量的面积定义方式)；高度为 $a\ge 0$ 时，总量自然应为 $a\mu(E)$。

💡因此，先给有限层的简单函数定义积分，再用简单函数从下方逼近一般函数。\
**原因**：先处理非负函数，是因为各部分只会累加，允许总量为 $+\infty$，**不会出现 $\infty-\infty$ 的歧义**。整个构造的主线结构为：


> **集合的测度 $\longrightarrow$ 简单函数积分 $\longrightarrow$ 非负函数积分 $\longrightarrow$ 极限与积分的交换**


---

### 二、定义：先有限求和，再取上确界

给定测度空间 $(X,\mathcal M,\mu)$，记

$$
L^+=\{f:X\to[0,\infty]\mid f\text{ 可测}\}.
$$

这里允许函数取 $+\infty$，也允许积分为 $+\infty$。

>[!note] **定义**.(非负简单函数的积分)
>设 $\phi=\sum_{j=1}^m a_j\chi_{E_j}$ 是标准表示，其中 $a_j$ 是有限的非负数，$E_j$ 是相应的可测水平集，彼此不交。定义
>
>$$
>    \int\phi\,d\mu=\sum_{j=1}^m a_j\mu(E_j),\qquad 0\cdot\infty:=0.
>$$

💡定义保证：即使某个集合测度无限，函数在其上恒为 $0$ 时，对积分的贡献仍是 $0$。
通过对集合取[共同细分](methods/共同细分.md)，可以验证积分不依赖具体的简单函数表示。

>[! NOTE] **定义.**(一般非负可测函数的积分)
>对 $f\in L^+$，定义
>
>$$
>\int f\,d\mu=\sup\left\{\int\phi\,d\mu:\ \phi\text{ 是简单函数},\ 0\le\phi\le f\right\}.
>$$

对 $A\in\mathcal M$，约定 $\int_A f\,d\mu:=\int f\chi_A\,d\mu$。

**关键区分：**每个 $f\in L^+$ 的积分都有定义，取值在 $[0,\infty]$；但称其“可积”时，要求 $\int f\,d\mu<\infty$。

---

### 三、基本性质：直接从定义得到

📕针对非负简单函数有如下性质：

> [! NOTE]- **非负齐次性、可加性、单调性、关于集合构成测度**
>
>| 性质 | 内容 |
>|---|---|
>| 非负齐次性 | $\int c\phi\,d\mu=c\int\phi\,d\mu$，$0\le c<\infty$ |
>| 可加性 | $\int(\phi+\psi)\,d\mu=\int\phi\,d\mu+\int\psi\,d\mu$ |
>| 单调性 | $\phi\le\psi\Rightarrow\int\phi\,d\mu\le\int\psi\,d\mu$ |
>| 关于集合构成测度 | $A\mapsto\int_A\phi\,d\mu$ 是 $\mathcal M$ 上的测度 |

**Proof idea.** 把 $\phi,\psi$ 的水平集细分为 $E_j\cap F_k$，然后使用测度的可加性。推广到一般 $f,g\in L^+$ 后，**单调性与非负齐次性可直接从上确界定义得到；可加性则在单调收敛定理之后证明。**这是 Folland 的重要逻辑顺序。

---

### 四、核心定理：本章的重点🚩

💡**定理核心内容：把取上界 $\sup$ 变成集合中某个字列的极限。**

根据简单函数逼近定理，我们知道对每个 $f\in L^+$，存在非负简单函数列 $\phi_n\uparrow f$。一种具体构造是

$$
\phi_n(x)=2^{-n}\left\lfloor 2^n\min\{f(x),2^n\}\right\rfloor.
$$

但此时还需要证明：**函数递增逼近时，积分也会逼近。**

>[! NOTE]- **定理.** (单调收敛定理 MCT)
>若 $f_n\in L^+$ 且 $f_n\uparrow f$，则
>
>$$
>\int f\,d\mu=\lim_{n\to\infty}\int f_n\,d\mu.
>$$
>
>等式允许两边都是 $+\infty$，不要求各个 $f_n$ 可积。[Proof](mathhub/MCT.md)

> [! NOTE]- **定理.**(可列可加性)
> 若 $f_n\in L^+$，则
>
>$$
>\int\sum_{n=1}^{\infty}f_n\,d\mu=\sum_{n=1}^{\infty}\int f_n\,d\mu.
>$$

**Proof idea.** 先取简单函数 $\phi_n\uparrow f$、$\psi_n\uparrow g$，对 $\phi_n+\psi_n\uparrow f+g$ 应用 MCT，得到一般非负函数的有限可加性；再对部分和 $S_N=\sum_{n=1}^Nf_n\uparrow\sum_{n=1}^\infty f_n$ 应用 MCT。

📕因此，**非负函数的级数可以直接逐项积分，无须预先证明积分之和有限。**这里非负性保证了部分和递增。

> [! note]- 推论：**积分的值仅取决于函数是否几乎处处 (a.e.) 相等。**
>
>- 对 $f\in L^+$，$\int f\,d\mu=0\iff f=0\quad\mu\text{-a.e.}$
>
>**Proof.** 若积分为 $0$，令 $A_n=\{f\ge1/n\}$，则 $0=\int f\,d\mu\ge\mu(A_n)/n$，故每个 $A_n$ 都是零测集，而 $\{f>0\}=\bigcup_nA_n$。反之，若 $f=0,a.e.$，则每个 $0\le\phi\le f$ 的简单函数积分都是 $0$，取上确界即可。
>
>- 若 $f,g\in L^+$ 且 $f=g$ ，则二者积分相等。MCT 中的 $f_n\uparrow f$ 也可以只要求几乎处处成立。

⚠️**注意可测性仍须保证：**在非完备测度空间中，任意修改零测集上的值，可能破坏可测性。

> [!note]- **定理.** (Fatou Lemma)
> 对任意非负可测函数列 $f_n$，
>
>$$
>\int\liminf_{n\to\infty}f_n\,d\mu\le\liminf_{n\to\infty}\int f_n\,d\mu.
>$$

**Proof idea：把任意序列变成递增序列**。令 $g_k=\inf_{n\ge k}f_n$，则 $g_k\uparrow\liminf_n f_n$，且 $\int g_k\,d\mu\le\inf_{n\ge k}\int f_n\,d\mu$。应用 MCT 即得结论。

>特别地，若 $f_n\to f$ a.e. 且 $f\in L^+$，则 $\int f\,d\mu\le\liminf_n\int f_n\,d\mu$。

💡**MCT 在递增条件下给出等式；Fatou 在一般非负条件下保留一个方向的不等式。**


