---
title: "无线通信算法数学工具库"
category: "项目说明"
tags: ["MIMO", "RIS", "波束赋形", "信道估计", "无线资源优化"]
---

# 无线通信算法数学工具库

面向阅读论文、推导公式和设计算法的快速查阅库。每篇笔记回答：**什么时候用、需要什么条件、能得到什么结论**，默认控制在 1～2 分钟内浏览完毕。

从 [检索索引](index.md) 开始，可按学科、算法问题或数学表达式定位工具。初始包含 8 篇工具笔记；索引标注尚未覆盖的方向，不把相近工具当作完整解法。

## 项目结构

```text
math-toolbox/
├── README.md                 使用说明与记号约定
├── AGENTS.md                 后续维护规范
├── index.md                  三种检索入口
├── templates/math-tool.md    新笔记模板
├── linear-algebra/           Hermitian、正定性、Cholesky、广义瑞利商
├── matrix-calculus/          矩阵微积分（待扩充）
├── convex-analysis/          凸集、凸函数与凹函数
├── optimization-methods/     凸优化问题、半正定松弛
├── probability-statistics/   概率统计（待扩充）
└── information-theory/       信息论（待扩充）
```

空分类中的 `.gitkeep` 仅用于让 Git 保留目录，加入首篇笔记时可移除。

## 记号与阅读约定

- 默认讨论有限维空间，矩阵和向量可以为复数；$A^H$ 表示共轭转置（conjugate transpose），$A^T$ 表示转置。
- $I_n$ 是 $n$ 阶单位矩阵，$\operatorname{tr}$ 表示迹（trace），$\operatorname{rank}$ 表示秩（rank）；$\|x\|_2^2=x^Hx$。
- $A\succeq0$、$A\succ0$ 分别表示 Hermitian 半正定、正定，**不是逐元素比较**；$A\succeq B$ 表示 $A-B\succeq0$。
- 凸性在实向量空间意义下定义。复向量视为实部与虚部拼接的实向量；Hermitian 矩阵组成实向量空间。
- “当且仅当”表示充要条件；“若……则……”表示充分条件；必要条件不会单独用来保证结论。
- 使用标准 Markdown 相对链接，行内公式用 `$...$`，独立公式用 `$$...$$`。GitHub、Obsidian 可渲染公式；VS Code 的显示效果取决于其 Markdown 预览对数学公式的支持。

## 日常使用

直接用自然语言提出任务即可，例如：

- 新增：“新增一篇 Schur 补笔记，重点解释它如何把波束赋形中的矩阵逆约束转成 LMI。”
- 修改：“检查并补全广义瑞利商笔记的适用条件，保持精简。”
- 查找：“论文中出现 $w^HAw/(w^HBw)$，帮我定位工具并判断能否使用。”

后续维护遵循 [AGENTS.md](AGENTS.md)：先检索，再更新或新增，同时维护索引与相关链接。新文件以 [模板](templates/math-tool.md) 为起点。

## 本地版本管理

在本目录使用 `git status` 查看状态。修改完成后，可用 `git add .` 和 `git commit -m "描述本次知识更新"` 保存版本；用 `git log --oneline` 查看历史。若尚未设置提交身份，先在本仓库配置自己的 `user.name` 和 `user.email`。仓库只保存在本地，不配置远程仓库。

## 核查参考资料

以下为定义与条件的核查入口；笔记中的通信例子按各自给定的模型推导。

- Boyd、Vandenberghe：[Convex Optimization（作者主页与全文入口）](https://web.stanford.edu/~boyd/cvxbook/)。第 2～4 章对应凸集、凸函数与凸优化问题；附录 A.5 对应矩阵性质和广义特征值。
- Vandenberghe：[Cholesky factorization 讲义](https://www.seas.ucla.edu/~vandenbe/133A/lectures/chol.pdf)。核查正定性、复数矩阵分解及线性方程求解条件。
- Boyd、Vandenberghe：[Semidefinite Programming Relaxations of Non-Convex Problems in Control and Combinatorial Optimization](https://web.stanford.edu/~boyd/papers/relaxations.html)。核查二次优化的半正定松弛思路。
