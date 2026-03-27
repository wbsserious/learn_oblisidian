https://blog.51cto.com/u_15127621/3260638
#### 1. 基础分行（带对齐）
$$
\begin{align} a &= b + c \\  d &= e + f + g \\ h &= i + j \end{align}
$$
$$
\begin{align*} \sin^2 x + \cos^2 x &= 1 \\ \tan x &= \frac{\sin x}{\cos x} \end{align*}
$$
#### 2. 无对齐的多行公式（gather 环境）
$$
\begin{gather} \int_0^\infty e^{-x^2} dx = \frac{\sqrt{\pi}}{2} \\ \sum_{n=1}^\infty \frac{1}{n^2} = \frac{\pi^2}{6} \end{gather} % 不带编号 \begin{gather*} a + b = c \\ d - e = f \end{gather*}
$$

如果不需要对齐，仅需简单分行，用 `gather` 环境：\

| 排版方式             | 核心特点            | 适用场景             |
| ---------------- | --------------- | ---------------- |
| `align`          | 单 / 多列对齐，每行独立编号 | 多公式对齐（如分类、推导）    |
| `equation+split` | 单行公式拆分，整体一个编号   | 长公式分行（如展开、化简）    |
| `gather`         | 无对齐，多行居中，每行独立编号 | 多个独立公式分行显示       |
| `alignat`        | 自定义多列对齐，可加说明    | 公式 + 文字说明、多组等号对齐 |
| `multline`       | 首左末右，中间居中       | 极长单一公式拆分         |
| 极简 `\\`          | 无环境、无对齐、无编号     | 笔记、快速展示简单多行公式    |
### 二、单个公式内的分行（split 环境）

如果希望多个分行的公式共享一个编号，使用 `split` 环境嵌套在 `equation` 中：

$$
\begin{equation} \begin{split} f(x) &= (x + 1)(x + 2)(x + 3) \\ &= x^3 + 6x^2 + 11x + 6 \\ &= (x^2 + 3x + 2)(x + 3) \end{split} \end{equation}
$$
# 字母上面的符号
$$
\hat{y}
$$
# 开根号
$$
\sqrt{a}
$$
# 字母对照表
## 基础拉丁字母
| 显示效果  | LaTeX 代码                   | 说明                  |
| ----- | -------------------------- | ------------------- |
| A,B,C | `$A, B, C$`                | 大写拉丁字母（直接输入）        |
| a,b,c | `$a, b, c$`                | 小写拉丁字母（直接输入）        |
| A,a   | `$\mathrm{A}, \mathrm{a}$` | 正体字母（非斜体，用于常量 / 单位） |
## 希腊字母（最常用）
### 小写拉丁字母
| 显示效果 | LaTeX 代码     | 显示效果 | LaTeX 代码     | 显示效果 | LaTeX 代码           |
| ---- | ------------ | ---- | ------------ | ---- | ------------------ |
| α    | `$\alpha$`   | β    | `$\beta$`    | γ    | `$\gamma$`         |
| δ    | `$\delta$`   | ϵ    | `$\epsilon$` | ζ    | `$\zeta$`          |
| η    | `$\eta$`     | θ    | `$\theta$`   | ι    | `$\iota$`          |
| κ    | `$\kappa$`   | λ    | `$\lambda$`  | μ    | `$\mu$`            |
| ν    | `$\nu$`      | ξ    | `$\xi$`      | π    | `$\pi$`            |
| ρ    | `$\rho$`     | σ    | `$\sigma$`   | τ    | `$\tau$`           |
| υ    | `$\upsilon$` | ϕ    | `$\phi$`     | χ    | `$\chi$`           |
| ψ    | `$\psi$`     | ω    | `$\omega$`   | φ    | `$\varphi$`（φ 的变体） |
### 大写拉丁字母
| 显示效果 | LaTeX 代码    | 显示效果 | LaTeX 代码     | 显示效果 | LaTeX 代码   |
| ---- | ----------- | ---- | ------------ | ---- | ---------- |
| Γ    | `$\Gamma$`  | Δ    | `$\Delta$`   | Θ    | `$\Theta$` |
| Λ    | `$\Lambda$` | Ξ    | `$\Xi$`      | Π    | `$\Pi$`    |
| Σ    | `$\Sigma$`  | Υ    | `$\Upsilon$` | Φ    | `$\Phi$`   |
| Ψ    | `$\Psi$`    | Ω    | `$\Omega$`   | Ω    | `$\Omega$` |
## 常用变体字母
| 显示效果                   | LaTeX 代码                 | 说明                      |
| ---------------------- | ------------------------ | ----------------------- |
| $\mathbf{a}$           | `$\mathbf{a}$`           | 粗体字母（向量 / 矩阵）           |
| $\boldsymbol{\alpha}$  | `$\boldsymbol{\alpha}$`  | 粗体希腊字母                  |
| $\mathit{A}$           | `$\mathit{A}$`           | 斜体大写字母（默认公式字母已斜体）       |
| $\mathbb{R}$           | `$\mathbb{R}$`           | 空心字母（实数集 / 集合符号）        |
| $\mathcal{A}$          | `$\mathcal{A}$`          | 花体字母（自定义集合 / 函数）        |
| $\mathscr{A}$          | `$\mathscr{A}$`          | 手写体字母（需加载 `mathrsfs` 包） |
| $\hat{a}$              | `$\hat{a}$`              | 字母加帽子（估计值）              |
| $\tilde{a}$            | `$\tilde{a}$`            | 字母加波浪线（波动 / 近似）         |
| $\bar{a}$              | `$\bar{a}$`              | 字母加横线（平均值）              |
| $\dot{a}$              | `$\dot{a}$`              | 字母加点（一阶导数）              |
| $\ddot{a}$             | `$\ddot{a}$`             | 字母加两点（二阶导数）             |
| $\overleftarrow{h_t}$  | `$\overleftarrow{h_t}$`  | 字母加向左箭头                 |
| $\overrightarrow{h_t}$ | `$\overrightarrow{h_t}$` | 字母加向右箭头                 |
## 常用特殊符号（易混淆 / 高频）
| 显示效果 | LaTeX 代码      | 说明        |
| ---- | ------------- | --------- |
| ∞    | `$\infty$`    | 无穷大       |
| ∇    | `$\nabla$`    | nabla（梯度） |
| ∂    | `$\partial$`  | 偏导数符号     |
| ∅    | `$\emptyset$` | 空集        |
| ∀    | `$\forall$`   | 全称量词      |
| ∃    | `$\exists$`   | 存在量词      |
| =   | `$\neq$`      | 不等于       |
| ≤    | `$\leq$`      | 小于等于      |
| ≥    | `$\geq$`      | 大于等于      |
## 大括号
$$at​=\begin{cases}argmax​Q(st​,a)\ \ ​&以概率 1−ε\\UniformRandom(A)&以概率 ε\end{cases}$$