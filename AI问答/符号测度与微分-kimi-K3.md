好的，这是实分析（以 Folland / Rudin 体系为例）中"符号测度与微分"这一章的核心内容梳理。

## 一、符号测度（Signed Measures）

**定义**：可测空间 $(X, \mathcal{M})$ 上的符号测度 $\nu$ 是一个函数 $\nu: \mathcal{M} \to [-\infty, +\infty]$，满足：

1. $\nu(\varnothing) = 0$；
2. $\nu$ 至多取 $+\infty$、$-\infty$ 中的一个（避免 $\infty - \infty$）；
3. 可数可加性：对互不相交的 $\{E_j\}$，$\nu(\bigcup E_j) = \sum \nu(E_j)$（且级数绝对收敛当左边有限时）。

典型例子：$\nu(E) = \int_E f\,d\mu$，其中 $f$ 是扩充实值可积函数（至少 $f^+$ 或 $f^-$ 可积）。

**正集与负集**：$E$ 称为正集（negative 类似），若对一切可测 $F \subset E$ 有 $\nu(F) \geq 0$。

**Hahn 分解定理**：存在正集 $P$ 与负集 $N$ 使 $X = P \cup N$，$P \cap N = \varnothing$。分解在"零测集意义下"唯一。

**Jordan 分解定理**：存在唯一的正测度对 $\nu^+, \nu^-$（至少一个有限），使得
$$\nu = \nu^+ - \nu^-, \qquad \nu^+ \perp \nu^-$$
即二者相互奇异（分别集中在 $P$ 和 $N$ 上）。称 $|\nu| = \nu^+ + \nu^-$ 为**全变差测度**，$\|\nu\| = |\nu|(X)$ 为全变差范数。全体有限符号测度在此范数下构成 Banach 空间。

积分定义：$\int f\,d\nu = \int f\,d\nu^+ - \int f\,d\nu^-$。

## 二、Lebesgue–Radon–Nikodym 定理

**绝对连续**：$\nu \ll \mu$ 指 $\mu(E) = 0 \Rightarrow \nu(E) = 0$。对有限符号测度有等价刻画：$\forall \varepsilon > 0,\ \exists \delta > 0$，$\mu(E) < \delta \Rightarrow |\nu(E)| < \varepsilon$。

**奇异**：$\nu \perp \mu$ 指存在 $E \sqcup F = X$ 使 $\nu$ 集中在 $E$、$\mu$ 集中在 $F$。

**定理**（设 $\nu$ 为 $\sigma$-有限符号测度，$\mu$ 为 $\sigma$-有限正测度）：存在唯一的分解
$$\nu = \lambda + \rho, \qquad \lambda \perp \mu,\quad \rho \ll \mu,$$
且存在 $\mu$-可积的 $f$（唯一 a.e.）使 $d\rho = f\,d\mu$。记
$$f = \frac{d\nu}{d\mu} \quad \text{（Radon–Nikodym 导数）}$$

证明思路（von Neumann）：考虑希尔伯特空间 $L^2(\mu + \nu)$ 上的有界泛函 $\ell(f) = \int f\,d\nu$，用 Riesz 表示定理得到密度函数。

**链式法则**与基本性质：若 $\nu \ll \mu$ 且 $g \in L^1(\nu)$，则 $\int g\,d\nu = \int g\frac{d\nu}{d\mu}\,d\mu$；且 $\dfrac{d\nu}{d\lambda} = \dfrac{d\nu}{d\mu}\cdot\dfrac{d\mu}{d\lambda}$（a.e.）。

## 三、Lebesgue 微分理论（$\mathbb{R}^n$ 上）

目标：把微积分基本定理推广到 Lebesgue 积分——何时有
$$f(x) = \lim_{r \to 0} \frac{1}{m(B(r,x))}\int_{B(r,x)} f\,dm \quad \text{a.e.?}$$

**Hardy–Littlewood 极大函数**：对局部可积 $f$，
$$Hf(x) = \sup_{r>0} \frac{1}{m(B(r,x))}\int_{B(r,x)} |f|\,dm$$

**极大定理**（弱 (1,1) 估计）：存在常数 $C$ 使
$$m(\{Hf > \alpha\}) \leq \frac{C}{\alpha}\|f\|_1$$
证明的关键工具是 **Vitali 覆盖引理**（或更精细的 Wiener 覆盖引理，$C = 3^n$）。

**Lebesgue 微分定理**：对 $f \in L^1_{\mathrm{loc}}(\mathbb{R}^n)$，几乎处处有
$$\lim_{r\to 0} \frac{1}{m(B(r,x))}\int_{B(r,x)} |f(y) - f(x)|\,dy = 0$$
这样的 $x$ 称为 **Lebesgue 点**。证明套路：先对连续函数（显然成立），再用连续函数在 $L^1$ 中稠密逼近，误差由极大定理控制——这是"极大函数 + 稠密性"的标准范式。

**推论**：
- 可测集 $E$ 的几乎每一点都是其密度点（$\lim \frac{m(E\cap B_r)}{m(B_r)} = 1$ a.e. on $E$）；
- 若 $F(x) = \int_{-\infty}^x f\,dm$，则 $F' = f$ a.e.。

## 四、有界变差函数与绝对连续函数（$\mathbb{R}$ 上）

**有界变差（BV）**：$F: [a,b] \to \mathbb{R}$ 的全变差 $T_F = \sup \sum |F(x_j) - F(x_{j-1})|$ 有限。等价地，$F$ 是两个增函数之差（Jordan 分解），故 BV 函数 a.e. 可微，且对应一个有限符号测度 $\mu_F$（Lebesgue–Stieltjes 测度）。

**绝对连续（AC）**：$\forall \varepsilon, \exists \delta$，任意有限个总长度小于 $\delta$ 的不相交区间上函数增量之和 $< \varepsilon$。AC ⇒ 一致连续 + BV。

**微积分基本定理**（Lebesgue 版本）：
$$F \text{ 绝对连续} \iff F(x) = F(a) + \int_a^x f(t)\,dt,\quad f \in L^1$$
此时 $F' = f$ a.e.。这正是 Radon–Nikodym 定理在一维的具体化：$F$ 绝对连续 ⟺ 其 Stieltjes 测度 $\mu_F \ll m$。

**奇异函数**：存在连续、单调增、$F' = 0$ a.e. 却非常数的函数（Cantor 函数/"魔鬼阶梯"），对应测度关于 Lebesgue 测度奇异。这正对应 Lebesgue 分解 $\mu_F = \mu_{ac} + \mu_{sing}$（还可再细分出原子部分 $\mu_d$）。

## 主线逻辑

整章的统一视角是：**函数（或测度）之间的"微分"关系 = Radon–Nikodym 导数**。

1. Hahn/Jordan 分解把符号测度拆成正负两部分；
2. Lebesgue–Radon–Nikodym 定理回答"一个测度何时能写成另一个测度的积分"；
3. 极大函数方法把"a.e. 可微"转化为弱型估计 + 稠密性；
4. 一维情形下落实为 AC 函数的基本定理与 BV 函数的 Lebesgue 分解。

如果你在用某本具体教材（Folland 第 3 章、Rudin 第 6–8 章、周民强、Stein 等），或想深入某一部分（比如覆盖引理证明细节、Cantor 函数构造、习题讲解），告诉我，我可以展开讲。