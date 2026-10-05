我们沿着 **“定义积分 → 建立 $L^1$ → 控制收敛 → 逼近与交换运算 → 联系经典积分”** 展开。固定测度空间 $(X,\mathcal M,\mu)$，以下函数均可测，简写 $\int f=\int_Xf\,d\mu$。内容对应 Folland §2.3。

---

**1．定义积分：把新对象拆成已经会处理的对象。** 上一节已经定义了非负函数的积分，取值可以是 $+\infty$。现在要处理一般实值、复值函数，基本方法就是把它们拆成非负函数。

对实值函数，定义 $f^+=\max(f,0)$、$f^-=\max(-f,0)$，于是
$$
f=f^+-f^-,\qquad |f|=f^++f^-,\qquad f^\pm\ge0.
$$
注意，$f^-$ 表示负值的大小，所以仍然非负。只要 $\int f^+$、$\int f^-$ 至少有一个有限，就定义
$$
\int f:=\int f^+-\int f^-.
$$
如果二者都为 $+\infty$，积分就没有定义，因为不能计算 $\infty-\infty$；如果二者都有限，则称 $f$ **可积**。由非负函数积分的可加性，
$$
\int|f|=\int f^++\int f^-
\quad\Longrightarrow\quad
\boxed{f\text{ 可积}\iff\int|f|<\infty.}
$$
这解释了一个容易混淆的区别：$\int f=+\infty$ 可以有意义，但这时不能说 $f$ 可积。**“可积”要求正负两部分的总量都有限，不依赖两个无穷大量相互抵消。**

例如，$f(x)=2x-1$ 在 $(0,1)$ 上满足 $f^+=(2x-1)\mathbf1_{(1/2,1)}$、$f^-=(1-2x)\mathbf1_{(0,1/2)}$，因此
$$
\int_0^1f^+=\int_0^1f^-=\frac14,\qquad
\int_0^1f=0,\qquad \int_0^1|f|=\frac12.
$$
这里的抵消发生在两个有限数之间，完全没有问题。

对复值函数，写成 $f=u+iv$，其中 $u=\operatorname{Re}f$、$v=\operatorname{Im}f$。仍以 $\int|f|<\infty$ 定义可积。由于
$$
|u|,\ |v|\le|f|\le|u|+|v|,
$$
所以 $f$ 可积当且仅当 $u,v$ 都可积，此时定义
$$
\boxed{\int f=\int u+i\int v.}
$$
例如，$f(x)=(1+i)x^{-1/2}$ 在 $(0,1)$ 上满足 $\int|f|=2\sqrt2<\infty$，所以可积，且 $\int f=2+2i$。至此，实值和复值函数的可积性由同一个条件统一起来：**绝对值的积分有限。**

---

**2．建立 $L^1$：让积分可以运算，让误差可以衡量。** 定义积分之后，要确认它具有线性性和适当的估计，再把所有可积函数组织成一个空间。

**线性性（2.21）保证通常的代数运算仍然成立。** 若 $f,g$ 可积，$a,b\in\mathbb C$，则
$$
|af+bg|\le |a||f|+|b||g|
\quad\Longrightarrow\quad af+bg\text{ 可积},
\qquad
\boxed{\int(af+bg)=a\int f+b\int g.}
$$
证明实值函数的可加性时，有一个值得掌握的技巧：不能写 $(f+g)^+=f^++g^+$，这个等式一般不成立。令 $h=f+g$，正确的恒等式是
$$
h^++f^-+g^-=h^-+f^++g^+.
$$
两边都是非负函数，可以使用上一节的可加性；各项积分又都有限，因此积分后移项，就得到 $\int h=\int f+\int g$。复值情形分别处理实部和虚部即可。

**积分三角不等式（2.22）负责估计大小。** 对任何可积函数，
$$
\boxed{\left|\int f\right|\le\int|f|.}
$$
实值情形由 $\left|\int f^+-\int f^-\right|\le\int f^++\int f^-$ 直接得到。复值情形的证明技巧是“旋转”：若 $z=\int f\ne0$，取 $\alpha=\overline z/|z|$，则 $|\alpha|=1$、$\alpha z=|z|$，所以
$$
\left|\int f\right|
=\operatorname{Re}\!\left(\alpha\int f\right)
=\int\operatorname{Re}(\alpha f)
\le\int|\alpha f|
=\int|f|.
$$
这个证明把复数的模转化成了实数之间的比较。

**几乎处处相等（2.23）说明积分忽略零测集上的差异。** 对可积函数，
$$
\boxed{\int|f-g|=0\iff f=g\quad\mu\text{-几乎处处}.}
$$
其中“积分为零推出几乎处处为零”的理由是：令 $h=|f-g|$，则
$$
\frac1n\mu\{h>1/n\}\le\int h=0,
\qquad
\{h>0\}=\bigcup_{n=1}^{\infty}\{h>1/n\}.
$$
每个集合都是零测集，可数并仍是零测集。注意，必须对**非负函数 $h$** 使用这个结论；一般函数的积分为零，可能只是正负抵消。

教材还给出一个更强的识别方式：
$$
f=g\ \text{几乎处处}
\iff
\int_Ef=\int_Eg\quad\text{对每个可测集 }E.
$$
为什么要求“每个 $E$”？因为这样就能单独检查差值为正的区域，不能再让别处的负值抵消它。复值函数则分别检查实部和虚部。

因此，我们把几乎处处相等的可积函数视为同一个元素，得到 **$L^1(\mu)$**，并定义
$$
\|f\|_1:=\int|f|,\qquad
d(f,g):=\|f-g\|_1=\int|f-g|.
$$
$\|f-g\|_1$ 衡量函数之间的**总绝对误差**。把几乎处处相等的函数视为同一个元素，才能保证 $d(f,g)=0$ 真正意味着两个元素相同。

这一层最有用的结果是
$$
\boxed{\left|\int f_n-\int f\right|\le\|f_n-f\|_1.}
$$
所以，**$L^1$ 收敛一定推出积分收敛**。反过来不成立，因为积分的误差可能通过抵消变小，而总绝对误差并没有变小。

还有一个辅助性质：若 $f\in L^1$，那么它的非零点集是 $\sigma$-有限的。事实上，令 $E_n=\{|f|>1/n\}$，则 $\mu(E_n)\le n\|f\|_1<\infty$，而 $\{f\ne0\}=\bigcup_nE_n$。这说明，即使整个测度空间很大，可积函数的非零部分仍能被可数个有限测度集覆盖。

---

**3．控制收敛定理：从逐点信息获得积分的稳定性。** 前面已经知道，只要证明 $\|f_n-f\|_1\to0$，积分收敛就随之成立。但实际题目通常只告诉我们 $f_n(x)\to f(x)$。两者之间的桥梁就是控制收敛定理。

**控制收敛定理（DCT，2.24）：** 若 $f_n\to f$ 几乎处处，并且存在非负可积函数 $g$，使对所有 $n$ 都有 $|f_n|\le g$ 几乎处处，那么
$$
\boxed{f\in L^1,\qquad \|f_n-f\|_1\to0,\qquad \int f_n\to\int f.}
$$
这里有两个不能遗漏的条件：**同一个 $g$ 控制所有 $n$，而且 $g$ 必须可积。** 仅仅每个 $f_n$ 都可积，甚至 $\sup_n\int|f_n|<\infty$，都不够。

**证明可以直接从 Fatou 引理出发。** 由逐点极限得到 $|f|\le g$ 几乎处处，因此 $f\in L^1$。令 $e_n=|f_n-f|$，则 $0\le e_n\le2g$，且 $e_n\to0$ 几乎处处。对非负函数 $2g-e_n$ 使用 Fatou 引理：
$$
2\int g
=\int\liminf_n(2g-e_n)
\le\liminf_n\int(2g-e_n)
=2\int g-\limsup_n\int e_n.
$$
因为 $\int g<\infty$，可以消去两边的 $2\int g$，得到 $\limsup_n\int e_n\le0$。结合 $\int e_n\ge0$，便有 $\int|f_n-f|\to0$；再用积分三角不等式得到积分收敛。**可积控制函数的作用，在证明中具体体现为：提供非负函数 $2g-e_n$，并允许我们消去有限的 $2\int g$。**

例如，在 $(0,\infty)$ 上，
$$
f_n(x)=\frac{e^{-x}}{1+x/n}\longrightarrow e^{-x},
\qquad 0\le f_n(x)\le e^{-x},\qquad \int_0^\infty e^{-x}\,dx=1.
$$
因此 DCT 给出 $\displaystyle\lim_n\int_0^\infty\frac{e^{-x}}{1+x/n}\,dx=1$。解这类题并不需要先算出每个积分；检查极限和控制函数即可。

对照反例：在 $(0,1)$ 上令 $f_n=n\mathbf1_{(0,1/n)}$。虽然每个点都有 $f_n(x)\to0$，但 $\int f_n=1$。它们不可能有共同的可积上界，否则就与 DCT 矛盾。这里正好体现了**逐点误差趋于零，不等于总误差趋于零**。

---

**4．展开应用：把不同操作改写为“取极限”，再应用 DCT。** 本节后面的定理看起来不同，证明思路却高度统一：找出要取极限的函数列，再寻找可积控制函数。

**第一类应用是级数逐项积分（2.25）。** 若 $f_n\in L^1$，且
$$
\sum_{n=1}^{\infty}\|f_n\|_1
=\sum_{n=1}^{\infty}\int|f_n|<\infty,
$$
那么 $\sum_nf_n$ 几乎处处绝对收敛，其和属于 $L^1$，并且
$$
\boxed{\int\left(\sum_{n=1}^{\infty}f_n\right)
=\sum_{n=1}^{\infty}\int f_n.}
$$
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

**第二类应用是 $L^1$ 逼近（2.26）。** 对任意 $f\in L^1$ 和任意 $\varepsilon>0$，存在可积简单函数 $\varphi$，使
$$
\boxed{\|f-\varphi\|_1<\varepsilon.}
$$
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

**第三类应用是含参积分的连续性（2.27a）。** 设
$$
F(t)=\int_X f(x,t)\,d\mu(x),
$$
并假设每个 $f(\cdot,t)$ 都可积。若 $f(x,t)\to f(x,t_0)$ 对每个 $x$ 成立，而且在 $t_0$ 的某个邻域内有共同的可积上界 $|f(x,t)|\le g(x)$，那么
$$
\boxed{\lim_{t\to t_0}F(t)
=\int_X\lim_{t\to t_0}f(x,t)\,d\mu(x)
=F(t_0).}
$$
严格地说，任取 $t_n\to t_0$，对函数列 $f(x,t_n)$ 使用 DCT，再利用序列刻画连续性即可。控制函数只需在 $t_0$ 附近有效，因为连续性是局部性质。

**第四类应用是积分号下求导（2.27b）。** 若 $f(x,t)$ 关于 $t$ 可微，且在 $t_0$ 附近有
$$
\left|\frac{\partial f}{\partial t}(x,t)\right|\le g(x),
\qquad g\in L^1,
$$
那么
$$
\boxed{F'(t_0)=\int_X\frac{\partial f}{\partial t}(x,t_0)\,d\mu(x).}
$$
为什么控制导数就够了？因为求导等于对差商取极限：
$$
\frac{F(t_0+h)-F(t_0)}h
=\int_X\frac{f(x,t_0+h)-f(x,t_0)}h\,d\mu(x).
$$
实值情形由中值定理，差商的绝对值不超过 $g(x)$，于是可以使用 DCT；复值情形分别处理实部和虚部即可。**这里真正交换的是“差商的极限”和积分。**

例如，对 $t>0$，令 $F(t)=\int_0^\infty e^{-tx}\,dx=1/t$。在 $t_0>0$ 附近，可以限制 $t\ge t_0/2$，于是
$$
\left|\frac{\partial}{\partial t}e^{-tx}\right|
=xe^{-tx}\le xe^{-t_0x/2},
$$
右边可积，所以 $F'(t)=-\int_0^\infty xe^{-tx}\,dx=-1/t^2$，从而 $\int_0^\infty xe^{-tx}\,dx=1/t^2$。这里必须检查导数的可积上界，不能只根据“被积函数可以求导”就直接把导数移入积分号。

**5．连接经典积分：确认新理论包含旧理论，并展示一个应用。** 本节最后回答两个问题：Lebesgue 积分与熟悉的 Riemann 积分有什么关系？如何用积分定义新函数？

**Riemann 与 Lebesgue 积分的关系（2.28）：** 对闭区间 $[a,b]$ 上的有界实值函数 $f$，有以下两个结论：如果 $f$ Riemann 可积，那么它也 Lebesgue 可积，且两种积分相等；并且
$$
\boxed{f\text{ Riemann 可积}
\iff f\text{ 的不连续点集具有 Lebesgue 测度 }0.}
$$
第一个结论的证明骨架是用上下阶梯函数夹逼：Riemann 可积意味着能找到下阶梯函数 $g_n$ 与上阶梯函数 $G_n$，满足 $g_n\le f\le G_n$，且它们的积分差趋于零。选择逐次加细的分割后，$g_n$ 单调增加、$G_n$ 单调减少；极限之间的非负差积分为零，因此二者几乎处处相等，夹在中间的 $f$ 就具有同一个 Lebesgue 积分。判别准则则进一步把上下和之差与函数在小区间上的振幅联系起来。

典型例子是 $f=\mathbf1_{\mathbb Q\cap[0,1]}$：它处处不连续，所以不 Riemann 可积；但它只在一个零测集上非零，因此 Lebesgue 可积且积分为 $0$。还应区别**正常 Riemann 积分**与**反常积分**：某些条件收敛的反常积分有有限极限，但并不绝对可积，因此不对应可积函数的 Lebesgue 积分。

**Gamma 函数展示怎样把前面的理论用于一个具体对象。** 对 $\operatorname{Re}z>0$，定义
$$
\Gamma(z)=\int_0^\infty t^{z-1}e^{-t}\,dt.
$$
首先检查可积性。令 $\sigma=\operatorname{Re}z>0$，则 $|t^{z-1}e^{-t}|=t^{\sigma-1}e^{-t}$：在 $0$ 附近，$\int_0^1t^{\sigma-1}\,dt<\infty$；在无穷远处，指数衰减使它可积。因此这个复值积分确实有定义。

再在有限区间上分部积分，并让端点趋于 $0$ 与 $\infty$，得到
$$
\Gamma(z+1)=z\Gamma(z),\qquad
\Gamma(1)=1,\qquad
\Gamma(n+1)=n!.
$$
所以 Gamma 函数把阶乘延伸到了更广的参数范围。递推式还允许继续向左延拓：选取整数 $m$ 使 $\operatorname{Re}(z+m)>0$，用
$$
\Gamma(z)=\frac{\Gamma(z+m)}{z(z+1)\cdots(z+m-1)}
$$
定义非正整数以外的复数处的值；递推关系保证选择不同的 $m$ 不会改变结果。

学习时可以给每一层设一个具体目标：**定义层能判断积分是否存在；$L^1$ 层会估计误差；DCT 能独立证明并找到控制函数；应用层能辨认应该对部分和、逼近函数还是差商使用 DCT；最后能清楚区分 Lebesgue 积分、Riemann 积分和反常积分。**


```
from ChatGPT
```
