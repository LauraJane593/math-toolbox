---
title: "凸优化问题"
category: "优化方法"
tags: ["凸优化", "全局最优", "严格凸", "资源分配", "信道估计"]
---

# 凸优化问题（Convex Optimization Problem）

### 1. 一句话理解

在凸可行域上最小化凸函数，或最大化凹函数，使局部最优也具有全局最优保证。

### 2. 触发条件

论文声称“可转化为凸问题”，或需要检查功率分配、最小二乘、矩阵优化能否直接使用凸优化算法时。

### 3. 适用条件

- 标准形式中 $x\in D\subseteq\mathbb R^n$，$D$ 为非空凸集；$f_0,f_i:D\to\mathbb R$ 为凸函数。
- 等式必须为仿射形式 $Ax=b$，$A\in\mathbb R^{q\times n}$、$b\in\mathbb R^q$。一般非线性等式不能直接按此标准形式判凸。
- 复向量或 Hermitian 变量按实向量空间处理。仿射矩阵半正定约束也定义凸集，可构成凸问题。
- 凸性本身不保证可行、最优值有限或最优值可达；使用“最优解”前要确认存在性。

### 4. 核心结论

标准凸优化形式为

$$
\begin{aligned}
\min_{x\in D}\quad &f_0(x)\\
\text{满足}\quad &f_i(x)\le0,\quad i=1,\ldots,m,\\
&Ax=b.
\end{aligned}
$$

其可行集 $\mathcal F=\{x\in D:f_i(x)\le0,\ Ax=b\}$ 为凸集，任意局部最优解都是全局最优解。最大化凹函数可对目标取负转为此形式。

若 $f_0$ 在 $\mathcal F$ 上严格凸，则最优解**若存在便唯一**。非空紧致可行集加连续目标是最优解存在的一组充分条件，不是必要条件。

若 $f_0$ 在包含 $\mathcal F$ 的开集上可微且在 $\mathcal F$ 上凸，则对 $x_\star\in\mathcal F$，一阶最优性条件为

$$
x_\star\text{ 全局最优}\iff
\nabla f_0(x_\star)^T(x-x_\star)\ge0,\qquad\forall x\in\mathcal F.
$$

边界最优点无需满足 $\nabla f_0(x_\star)=0$；约束问题不能只检查无约束驻点。

### 5. 在无线通信中的应用

对 $K\ge1$ 个互不干扰的并行子信道，固定归一化增益 $a_k\ge0$，总功率 $P\ge0$，

$$
\max_{p\in\mathbb R^K}\ \sum_{k=1}^K\log_2(1+a_kp_k)
\quad\text{满足}\quad p_k\ge0,\ \sum_{k=1}^Kp_k\le P
$$

是凹目标最大化问题。其可行域非空紧致、目标连续，因此全局最优解存在；若所有 $a_k>0$，目标严格凹，解唯一。

### 6. 相关工具

- [凸集](../convex-analysis/convex-set.md)：判断可行域。
- [凸函数与凹函数](../convex-analysis/convex-concave-functions.md)：判断目标和不等式方向。
- [Cholesky 分解](../linear-algebra/cholesky-decomposition.md)：求解正定二次模型。
- [半正定松弛](semidefinite-relaxation.md)：将部分非凸二次问题松弛为凸问题。
