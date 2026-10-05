# Lebesgue积分经典应用

>**第一类应用是级数逐项积分**
>若 $f_n\in L^1$，且
>$$
>\sum_{n=1}^{\infty}\|f_n\|_1 =\sum_{n=1}^{\infty}\int|f_n|<\infty,
>$$
那么 $\sum_nf_n$ 几乎处处绝对收敛，其和属于 $L^1$，并且
>$$
>\int\left(\sum_{n=1}^{\infty}f_n\right) = \sum_{n=1}^{\infty}\int f_n.
>$$

证明分两步：先由单调收敛定理得到 $g=\sum_n|f_n|$ 满足 $\int g=\sum_n\int|f_n|<\infty$，因此 $g<\infty$ 几乎处处，保证级数几乎处处绝对收敛；再对部分和 $S_N=\sum_{n=1}^Nf_n$ 使用 $|S_N|\le g$，由 DCT 交换极限与积分。

这里控制的不是单独某一项，而是**所有项绝对值之和**。同时还有误差估计
$$
\left\|\sum_{n=1}^{\infty}f_n-\sum_{n=1}^Nf_n\right\|_1
\le\sum_{n>N}\|f_n\|_1\longrightarrow0.
$$
所以该定理也保证部分和在 $L^1$ 中收敛。

例如，固定 $0<r<1$，在 $[0,r]$ 上展开 $(1+x)^{-1}=\sum_{n=0}^{\infty}(-1)^nx^n$。因为
$$
\sum_{n=0}^{\infty}\int_0^r x^n\,dx
=\sum_{n=0}^{\infty}\frac{r^{n+1}}{n+1}
\le\frac r{1-r}<\infty,
$$
所以可以逐项积分，得到 $\displaystyle\log(1+r)=\sum_{n=0}^{\infty}\frac{(-1)^nr^{n+1}}{n+1}$。

---

>**第二类应用是 $L^1$ 逼近**
>对任意 $f\in L^1$ 和任意 $\varepsilon>0$，存在可积简单函数 $\varphi$，使
>$$
>\boxed{\|f-\varphi\|_1<\varepsilon.}
>$$

这叫作“可积简单函数在 $L^1$ 中稠密”。它比“每个可测函数都是简单函数的逐点极限”更强，因为现在误差是在积分意义下趋于零。

证明方法是：选取简单函数 $\varphi_n\to f$，同时使 $|\varphi_n|\le|f|$。于是每个 $\varphi_n$ 都可积，并且
$$
|\varphi_n-f|\le2|f|\in L^1,\qquad |\varphi_n-f|\to0.
$$
DCT 立即给出 $\|\varphi_n-f\|_1\to0$。

在 $\mathbb R$ 上取 Lebesgue–Stieltjes 测度时，还能进一步用**紧支撑连续函数**逼近，即存在连续且在某个有界区间之外为零的 $h$，使 $\|f-h\|_1<\varepsilon$。其证明过程是：
$$
\text{可积函数}\ \longrightarrow\ \text{可积简单函数}
\ \longrightarrow\ \text{有限个区间示性函数的线性组合}
\ \longrightarrow\ \text{紧支撑连续函数}.
$$
中间一步使用测度的逼近性质：有限测度集 $E$ 可以用有限个有界开区间的并 $U$ 逼近，而
$$
\|\mathbf1_E-\mathbf1_U\|_1=\mu(E\triangle U).
$$
最后，把区间示性函数的两个跳跃处改成越来越窄的连续斜坡；这些连续函数逐点趋于示性函数，并受可积的区间示性函数控制，因此再次由 DCT 得到 $L^1$ 逼近。

这个定理提供了以后分析中非常常见的证明策略：**先对简单函数或连续函数证明结论，再利用 $L^1$ 逼近把结论推广到一般可积函数。**

---

>**第三类应用是含参积分的连续性**
>设
>$$
>F(t)=\int_X f(x,t)\,\mathrm{d}\mu(x),
>$$
>并假设每个 $f(\cdot,t)$ 都可积。若 $f(x,t)\to f(x,t_0)$ 对每个 $x$ 成立，而且在 $t_0$ 的某个邻域内有共同的可积上界 $|f(x,t)|\le g(x)$，那么
>$$
>\boxed{\lim_{t\to t_0}F(t) = \int_X\lim_{t\to t_0}f(x,t)\,\mathrm{d}\mu(x) = F(t_0).}
>$$

严格地说，任取 $t_n\to t_0$，对函数列 $f(x,t_n)$ 使用 DCT，再利用序列刻画连续性即可。控制函数只需在 $t_0$ 附近有效，因为连续性是局部性质。

---

>**第四类应用是积分号下求导（2.27b）。** 若 $f(x,t)$ 关于 $t$ 可微，且在 $t_0$ 附近有
>$$
>\left|\frac{\partial f}{\partial t}(x,t)\right|\le g(x), \qquad g\in L^1,
>$$
>那么
>$$
>F'(t_0)=\int_X\frac{\partial f}{\partial t}(x,t_0)\,\mathrm{d}\mu(x).
>$$

为什么控制导数就够了？因为求导等于对差商取极限：
$$
\frac{F(t_0+h)-F(t_0)}h
=\int_X\frac{f(x,t_0+h)-f(x,t_0)}h\,\mathrm{d}\mu(x).
$$
实值情形由中值定理，差商的绝对值不超过 $g(x)$，于是可以使用 DCT；复值情形分别处理实部和虚部即可。**这里真正交换的是“差商的极限”和积分。**

例如，对 $t>0$，令 $F(t)=\int_0^\infty e^{-tx}\,\mathrm{d}x=1/t$。在 $t_0>0$ 附近，可以限制 $t\ge t_0/2$，于是
$$
\left|\frac{\partial}{\partial t}e^{-tx}\right| = xe^{-tx}\le xe^{-t_0x/2},
$$
右边可积，所以 $F'(t)=-\int_0^\infty xe^{-tx}\,\mathrm{d}x=-1/t^2$，从而 $\int_0^\infty xe^{-tx}\,\mathrm{d}x=1/t^2$。这里必须检查导数的可积上界，不能只根据“被积函数可以求导”就直接把导数移入积分号。
