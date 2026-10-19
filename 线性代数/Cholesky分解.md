---
aliases:
- Cholesky Decomposition
- Cholesky Factorization
category: 线性代数
tags:
- Cholesky
- 正定
- 矩阵求逆
- 线性方程
- 信道估计
---

# Cholesky分解（Cholesky Decomposition）

### 1. 一句话理解

把 Hermitian 正定矩阵分解成下三角矩阵（lower triangular matrix）与其共轭转置的乘积，通过两次三角求解计算 $A^{-1}b$。

### 2. 触发条件

出现正定方程 $Ax=b$、$A^{-1}b$，尤其是同一 $A$ 对应多个右端项时。

### 3. 适用条件

- $A\in\mathbb C^{n\times n}$、$A=A^H\succ0$，$b\in\mathbb C^n$。
- 标准分解要求下三角因子对角元为正实数。仅半正定时，不保证存在满足此要求的因子，常规正定求解流程可能失败。

### 4. 核心结论

$A$ 正定，当且仅当存在对角元严格为正实数的下三角矩阵 $L$ 满足

$$
A=LL^H,\qquad l_{ii}>0.
$$

在此约定下 $L$ 唯一且可逆。按以下顺序求解：

$$
Ly=b,\qquad L^Hx=y.
$$

所得 $x=A^{-1}b$，但计算时无需显式构造 $A^{-1}$。稠密情形分解复杂度为 $\mathcal O(n^3)$，每个右端项的两次三角求解为 $\mathcal O(n^2)$。

数值计算中，病态或舍入误差可能影响分解；增加对角加载（diagonal loading）会改变原模型，应说明其含义。

### 5. 在无线通信中的应用

对 $y=Hh+n$，其中 $H\in\mathbb C^{m\times n}$、$y,n\in\mathbb C^m$、$h\in\mathbb C^n$，考虑 $\alpha>0$ 的正则化最小二乘（regularized least squares）：

$$
\widehat h=\underset{h\in\mathbb C^n}{\operatorname{argmin}}
\bigl(\|y-Hh\|_2^2+\alpha\|h\|_2^2\bigr),\qquad
(H^HH+\alpha I_n)\widehat h=H^Hy.
$$

左侧矩阵正定，可分解一次，再为多个接收观测求解信道估计；无需假设 $H$ 列满秩。

### 6. 相关工具

- [正定矩阵与半正定矩阵](正定矩阵与半正定矩阵.md)：确认分解条件。
- [广义瑞利商](广义瑞利商.md)：将正定分母变换为普通瑞利商。
- [凸优化问题](../最优化方法/凸优化问题.md)：上述严格凸最小二乘的优化背景。
