---
title: "数学工具检索索引"
category: "索引"
tags: ["检索", "算法问题", "数学表达式"]
---

# 数学工具检索索引

先匹配问题或表达式，再到笔记检查适用条件。当前共 **8 篇工具笔记**；符号约定见 [使用说明](README.md)。

## 按数学学科

| 分类 | 已有笔记 |
| --- | --- |
| 线性代数 | [Hermitian 矩阵](linear-algebra/hermitian-matrix.md) · [正定矩阵与半正定矩阵](linear-algebra/positive-definite-semidefinite-matrices.md) · [Cholesky 分解](linear-algebra/cholesky-decomposition.md) · [广义瑞利商](linear-algebra/generalized-rayleigh-quotient.md) |
| 矩阵微积分 | 待补充 |
| 凸分析 | [凸集](convex-analysis/convex-set.md) · [凸函数与凹函数](convex-analysis/convex-concave-functions.md) |
| 优化方法 | [凸优化问题](optimization-methods/convex-optimization-problem.md) · [半正定松弛（SDR）](optimization-methods/semidefinite-relaxation.md) |
| 概率统计 | 待补充 |
| 信息论 | 待补充 |

## 按算法问题

| 遇到的问题 | 入口与覆盖范围 |
| --- | --- |
| 分式优化、接收 SINR 最大化 | [广义瑞利商](linear-algebra/generalized-rayleigh-quotient.md)：固定 Hermitian 矩阵的二次型比值，分母矩阵正定；一般分式规划方法待补充 |
| 非凸约束、RIS 单位模、秩一约束 | [凸集](convex-analysis/convex-set.md) 判断集合；[SDR](optimization-methods/semidefinite-relaxation.md) 处理可提升为矩阵线性表达式的二次模型 |
| 矩阵求逆、反复求解线性方程 | [正定性](linear-algebra/positive-definite-semidefinite-matrices.md) 检查条件；[Cholesky](linear-algebra/cholesky-decomposition.md) 通过三角方程计算正定矩阵的逆作用；一般矩阵求逆引理待补充 |
| 特征值优化、选择最优波束方向 | [Hermitian 矩阵](linear-algebra/hermitian-matrix.md) 的谱结构；[广义瑞利商](linear-algebra/generalized-rayleigh-quotient.md) 的极值；矩阵本身含优化变量的特征值优化方法待补充 |
| 判断模型能否按凸优化求全局解 | [凸集](convex-analysis/convex-set.md) → [凸函数与凹函数](convex-analysis/convex-concave-functions.md) → [凸优化问题](optimization-methods/convex-optimization-problem.md) |
| 信道估计、协方差和功率建模 | [Hermitian 矩阵](linear-algebra/hermitian-matrix.md)、[正定性](linear-algebra/positive-definite-semidefinite-matrices.md)；正则化最小二乘求解见 [Cholesky](linear-algebra/cholesky-decomposition.md) |

## 按常见数学表达式

| 表达式或记号 | 对应工具 |
| --- | --- |
| $A=A^H$，$A=U\Lambda U^H$ | [Hermitian 矩阵](linear-algebra/hermitian-matrix.md) |
| $x^HAx\ge0$，$A\succeq0$，$H^HH+\alpha I$ | [正定矩阵与半正定矩阵](linear-algebra/positive-definite-semidefinite-matrices.md) |
| $A=LL^H$，$Ax=b$，$A^{-1}b$ | [Cholesky 分解](linear-algebra/cholesky-decomposition.md)（$A\succ0$） |
| $\frac{x^HAx}{x^HBx}$，$Ax=\lambda Bx$ | [广义瑞利商](linear-algebra/generalized-rayleigh-quotient.md)（$A=A^H,\ B\succ0$） |
| $\theta x+(1-\theta)y$，$0\le\theta\le1$ | [凸集](convex-analysis/convex-set.md) |
| $\nabla^2f(x)\succeq0$，$\log\det X$ | [凸函数与凹函数](convex-analysis/convex-concave-functions.md)（需检查定义域） |
| $\min f_0(x)$，$f_i(x)\le0$，$Ax=b$ | [凸优化问题](optimization-methods/convex-optimization-problem.md) |
| $W=ww^H$，$w^HQw=\operatorname{tr}(QW)$，$\operatorname{rank}(W)=1$ | [半正定松弛（SDR）](optimization-methods/semidefinite-relaxation.md) |

新增知识使用 [笔记模板](templates/math-tool.md)，维护规则见 [AGENTS.md](AGENTS.md)。
