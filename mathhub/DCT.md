>[!note] **定理.**(控制收敛定理 DCT)
>若 $f_n\to f$ a.e.，并且存在非负可积函数 $g$，使对所有 $n$ 都有 $|f_n|\le g$ a.e.，那么
>$$
>f\in L^1,\qquad \|f_n-f\|_1\to0,\qquad \int f_n\to\int f.
>$$

**证明可以直接从 Fatou 引理出发。** 由逐点极限得到 $|f|\le g$ 几乎处处，因此 $f\in L^1$。令 $e_n=|f_n-f|$，则 $0\le e_n\le2g$，且 $e_n\to0$ 几乎处处。对非负函数 $2g-e_n$ 使用 Fatou 引理：
$$
2\int g
=\int\liminf_n(2g-e_n)
\le\liminf_n\int(2g-e_n)
=2\int g-\limsup_n\int e_n.
$$
因为 $\int g<\infty$，可以消去两边的 $2\int g$，得到 $\limsup_n\int e_n\le0$。结合 $\int e_n\ge0$，便有 $\int|f_n-f|\to0$；再用积分三角不等式得到积分收敛。**可积控制函数的作用，在证明中具体体现为：提供非负函数 $2g-e_n$，并允许我们消去有限的 $2\int g$。**
