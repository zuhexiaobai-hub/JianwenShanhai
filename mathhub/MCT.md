# 单调收敛定理 MCT

>[! NOTE] **定理.** (单调收敛定理 MCT)
>若 $f_n\in L^+$ 且 $f_n\uparrow f$，则
>
>$$
>\int f\,d\mu=\lim_{n\to\infty}\int f_n\,d\mu.
>$$
>
>等式允许两边都是 $+\infty$，不要求各个 $f_n$ 可积。

```
Proof 参考 folland，from ChatGPT
```

**Proof.** 由可测函数列的极限仍可测，$f$ 为非负可测函数。由积分的单调性，$\{\int_X f_n\,d\mu\}$ 单调递增，因此其极限 $L\in[0,\infty]$ 存在。又因 $f_n\le f$，有
$$
L:=\lim_{n\to\infty}\int_X f_n\,d\mu\le\int_X f\,d\mu.
$$

为证明反向不等式，任取非负简单函数 $0\le\phi\le f$，固定 $0<\alpha<1$，令
$$
E_n=\{x\in X:f_n(x)\ge\alpha\phi(x)\}.
$$
各 $E_n$ 可测，且由 $f_n\le f_{n+1}$ 得 $E_n\subseteq E_{n+1}$。此外，若 $\phi(x)=0$，则 $x\in E_n$ 对所有 $n$ 成立；若 $\phi(x)>0$，则 $f_n(x)\to f(x)\ge\phi(x)>\alpha\phi(x)$，故充分大的 $n$ 满足 $x\in E_n$。因此 $E_n\uparrow X$。

在 $E_n$ 上有 $f_n\ge\alpha\phi$，在其补集上有 $f_n\ge0$，故 $f_n\ge\alpha\phi\mathbf1_{E_n}$。由积分的单调性及简单函数积分的齐次性，
$$
\int_X f_n\,d\mu\ge\alpha\int_{E_n}\phi\,d\mu.
$$
将 $\phi$ 写成标准表示 $\phi=\sum_{j=1}^{m}a_j\mathbf1_{A_j}$，其中 $a_j\ge0$。由 $A_j\cap E_n\uparrow A_j$ 及测度的下连续性，
$$
\lim_{n\to\infty}\int_{E_n}\phi\,d\mu
=\lim_{n\to\infty}\sum_{j=1}^{m}a_j\mu(A_j\cap E_n)
=\sum_{j=1}^{m}a_j\mu(A_j)
=\int_X\phi\,d\mu.
$$
于是 $L\ge\alpha\int_X\phi\,d\mu$。令 $\alpha\uparrow1$，得到 $L\ge\int_X\phi\,d\mu$；若 $\int_X\phi\,d\mu=\infty$，则任取 $\alpha>0$ 可推出 $L=\infty$。

最后，对所有满足 $0\le\phi\le f$ 的简单函数取上确界，由非负可测函数积分的定义，
$$
L\ge\sup_{\substack{0\le\phi\le f\\\phi\text{ 为简单函数}}}
\int_X\phi\,d\mu
=\int_X f\,d\mu.
$$
结合两个方向的不等式，即得结论。 $\square$