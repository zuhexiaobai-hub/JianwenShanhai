**Problem.** 如果某个函数满足
$$
    f'(t) \to +\infty, \qquad t \to +\infty \tag{1}
$$
显然可以推出充分大的区间内，${}f(t){}$ 单调递增，那么 ${}f(t){}$ 的阶可以被限制在多大以上呢？

---

>[!note] **Lemma 1.**
>如果可导函数 ${}f{}$ 满足条件 ${}(\text{1}){}$，那么 ${}f{}$ 超线性增长，即当 ${}t \to +\infty{}$ 时，有
>$$
>\frac{f(t)}{t} \to +\infty
>$$
>但是，对任意 ${}\varepsilon > 0{}$，均存在满足 ${}(\text{1}){}$ 的 ${}f{}$，满足 ${}f(t) = \mathcal{o}(t^{1+\varepsilon}){}$。

构造可以取 ${}f(t) = t\log\log t{}$，并可以加强：任意给定正整数 ${}n{}$，存在 ${}f{}$ 使得 ${}f(t) = \mathcal{O}(t\log^n t){}$。
并且还可以证明：

>[!note] **Lemma 2.**
>任何一个给定的函数 ${}H(t) \to +\infty{}$，均存在一个 ${}f{}$
>$$
>f'(t) \to +\infty \quad \text{且} \quad \frac{f(t)}{tH(t)} \to 0 \qquad (t \to +\infty).
>$$


