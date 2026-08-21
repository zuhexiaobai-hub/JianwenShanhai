# Extension-theorem

设 $\mathcal{A}$ 为一个代数(半代数可以根据有限并生成为代数)。
> [!tldr] **定理**
> 设 $\mu_{0}$ 为 $\mathcal{A}$ 上的一个预测度，并由
> 
> $$
>	\mu^{*}(E) = \inf \left\{  \sum_{n=1}^{\infty}\mu_{0}(E_{n}) : E_{n} \in \mathcal{A}, E \subset \bigcup_{n=1}^{\infty}E_{n} \right\}
> $$
> 确定了外测度，根据[[Caratheodory构造法]]可知它在 $\sigma$-代数
> $$
>	\mathcal{M} = \{ E \subset X : 对\,\forall\, A \subset X, 有 \,\mu^*(E) = \mu^*(E \cap A) + \mu^*(E \setminus A)  \}
> $$
> 上为一个完备测度[^1]。$\mathcal{A} \subset \mathcal{M}$，即有 $\sigma(\mathcal{A}) \subset \mathcal{M}$。$\mu = \mu^*|_{\sigma(\mathcal{A})}$ 为 $\sigma(\mathcal{A})$ 上的测度，满足：
> 
> $$
>	\mu(A) = \mu_{0}(A), \quad A \in \mathcal{A}
> $$
> 即 $\mu$ 为 $\mu_{0}$ 从 $\mathcal{A}$ 到 $\sigma(\mathcal{A})$ 的一个延拓。
>
>**唯一性** 如果 $\mu_{0}$ 是 $\sigma$-finite 的[^2]，那么生成的延拓测度 $\mu$ 唯一确定。



[^1]: 参考 [[测度]]

[^2]: 参考 [[sigma-finite]]
