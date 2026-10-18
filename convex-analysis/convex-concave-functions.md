---
title: "凸函数与凹函数"
category: "凸分析"
tags: ["凸函数", "凹函数", "Hessian", "二次型", "log-det", "速率优化"]
---

# 凸函数与凹函数（Convex and Concave Functions）

### 1. 一句话理解

凸函数的图像不高于任意两点之间的连线，凹函数反之；判断曲率后才能决定适合最小化还是最大化。

### 2. 触发条件

遇到二次型、Hessian 矩阵（Hessian matrix）、$\log(1+ap)$ 或 $\log\det X$，需要判断目标或约束的曲率时。

### 3. 适用条件

- 定义要求 $f:D\to\mathbb R$，$D$ 为实向量空间中的凸集。
- 使用梯度或 Hessian 判据时，进一步假设 $D\subseteq\mathbb R^n$ 为非空开凸集，$f$ 分别可微或二阶连续可微。复变量需转为实坐标，不能直接把实 Hessian 公式当成复数求导规则。

### 4. 核心结论

$f$ 为凸函数的充要条件是，对所有 $x,y\in D$、$\theta\in[0,1]$，

$$
f(\theta x+(1-\theta)y)\le\theta f(x)+(1-\theta)f(y).
$$

$f$ 凹当且仅当 $-f$ 凸。在上述可微条件下，一阶充要判据为

$$
f(y)\ge f(x)+\nabla f(x)^T(y-x),\qquad\forall x,y\in D.
$$

在上述二阶条件下，$f$ 凸当且仅当 $\nabla^2 f(x)\succeq0$ 对所有 $x\in D$ 成立。Hessian 处处正定是严格凸（strictly convex）的充分条件，非必要条件。

常用实例：对固定 $Q=Q^H\in\mathbb C^{n\times n}$，二次型（quadratic form）$x^HQx$ 在 $\mathbb C^n$ 上凸当且仅当 $Q\succeq0$；对数行列式（log-determinant）$\log\det X$ 在 $X\in\mathbb C^{n\times n}$、$X=X^H\succ0$ 上凹，这里的 $\log$ 为自然对数。

凸函数的次水平集（sublevel set）$\{x\in D:f(x)\le t\}$ 凸；凹函数的超水平集（superlevel set）$\{x\in D:f(x)\ge t\}$ 凸，$t\in\mathbb R$。

### 5. 在无线通信中的应用

固定归一化信道增益 $a\ge0$、功率 $p\ge0$ 时，速率 $r(p)=\log_2(1+ap)$ 满足

$$
r''(p)=-\frac{a^2}{\ln2\,(1+ap)^2}\le0.
$$

故速率对 $p$ 凹，可在凸功率域上最大化。若分母包含其他待优化用户的干扰功率，多用户速率一般不联合凹，不能直接套用此结论。

### 6. 相关工具

- [凸集](convex-set.md)：定义域与水平集的基础。
- [正定矩阵与半正定矩阵](../linear-algebra/positive-definite-semidefinite-matrices.md)：二次型和 Hessian 的判定。
- [凸优化问题](../optimization-methods/convex-optimization-problem.md)：正确组合目标与约束。
