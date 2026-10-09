

[TOC]

> by 賢者の極北

# 《高等代数简明教程》笔记

## 前备知识

### 复数

- 方程 $x^n-1=0$ 在 $\mathbb C$ 上的 $n$ 个根为 $\renewcommand\i{\mathrm{i}} e^{\frac {2k\pi \i}n}=\cos \frac {2k\pi}n+\i\sin \frac {2k\pi \i}n$, 其中 $k=1,2,\cdots,n$. 

### 数域

## 代数学的经典课题

### 一元高次代数方程

简单介绍经典代数学的重要课题之一：一元高次代数方程。

#### 代数方程与多项式

(代数方程的定义，多项式的定义，二者的关系)

数系怎样扩充才能使所有的一元 $n$ 次代数方程都有根？是否会将数系无尽地扩充下去呢？

**定理 代数学基本定理** 任何数域 $K$ 上的一元 $n$ 次代数方程在 $\mathbb C$ 内必有一个根。

当然，由中学阶段对代数方程的认知，$n$ 次代数方程应当有 $n$ 个复根，这依赖于下述命题。

**命题 多项式的综合除法** 设 $\displaystyle f(x)=\sum_{r=0}^n a_rx^r(a_n\ne 0,n\in\mathbb N_+)$ 是 $K$ 上的 $n$ 次多项式, 而 $a\in\mathbb C$, 则存在一个 $K$ 上的 $n-1$ 次多项式 $q(x)$，使得

$$
f(x)=(x-a)q(x)+f(a)
$$

<details>
    <summary>证明</summary>

我们有

$$
f(x)-f(a)=\sum_{r=0}^n a_r(x^r-a^r)
$$

由于 $x=a$ 是 $x^r-a^r=0$ 的一个根，故当 $r\in\mathbb N_+$ 时存在一个 $K$ 上的 $r-1$ 次多项式 $q_r(x)$ 使得

$$
x^r-a^r=(x-a)q_r(x)
$$

故

$$
f(x)-f(a)=(x-a)\sum_{r=1}^n a_rq_r(x)
$$

则 $\displaystyle \sum_{r=1}^n a_rq_r(x)$ 即为所求的 $n-1$ 次多项式 $q(x)$. 

</details>

由代数学基本定理、多项式的综合除法与数学归纳法立刻可得如下推论。

**推论** 任何数域 $K$ 上的一元 $n$ 次代数方程 $\displaystyle \sum_{r=0}^n a_rx^r=0$ 在 $\mathbb C$ 内必有 $n$ 个根（包括重复）。具体地说，存在 $x_1,x_2,\cdots,x_n\in\mathbb C$ 使得

$$
\displaystyle \sum_{r=0}^n a_rx^r=a_n\prod_{k=1}^n(x-x_k)=a_n(x-x_1)(x-x_2)\cdots(x-x_n)
$$

Frobenius：没有比 $\mathbb C$ 更大的数系。

本小节最后，我们介绍方程根与系数的关系。先引入一种记号。

**定义** 设 $x_1,x_2,\cdots,x_n\in\mathbb C$ 为 $n$ 个复数，从中选取 $r(1\le r\le n)$ 个连乘，并将所得的 $\displaystyle \binom nr=\frac {n!}{r!(n-r)!}$ 个乘积连加起来，所得的复数记为 $\sigma_r(x_1,x_2,\cdots,x_n)$. 例如：

$$
\sigma_1(x_1,x_2,\cdots,x_n)=x_1+x_2+\cdots+x_n
$$

**命题 根与系数的关系** 设数域 $K$ 上的一元 $n$ 次代数方程 $\displaystyle \sum_{r=0}^n a_rx^r=0(a_n\ne 0,n\in\mathbb N_+)$ 在 $\mathbb C$ 上的 $n$ 个根分别为 $x_1,x_2,\cdots x_n$，则

$$
\frac {a_r}{a_n}=(-1)^{n-r}\sigma_{n-r}(x_1,x_2,\cdots,x_n),\forall k\in \{0,1,\cdots,n-1\}
$$

特别地，当 $n=2$ 时有（中学生熟知的）一元二次方程的韦达定理：

$$
-\frac {a_1}{a_2}=x_1+x_2,\quad\frac {a_0}{a_2}=x_1x_2
$$

#### 实数域上代数方程的根

本小节的最后，简单介绍实数域上 $n$ 次代数方程的根。

**命题** 对任何 $\mathbb R$ 上的 $n$ 次代数方程，如果 $z\in\mathbb C$ 为它的一个根，则 $z$ 的共轭复数 $\bar x$ 也为它的根。进而，实数域上的一元奇次代数方程至少有一个实根。

**定理 有理根定理** 给定整系数 $n$ 次代数方程 $\displaystyle \sum_{r=0}^n a_rx^r=0(a_n\ne 0,n\in\mathbb N_+)$，若其存在有理数根，则该有理数的既约分数表示 $\displaystyle \frac pq$ 的分子 $p$ 必为常数项 $a_0$ 的因子，而分母 $q$ 必为最高次项系数 $a_n$ 的因子. 



### 线性方程组

经典代数学的另一个重要课题：多个未知量的一次联立方程组，一次方程也叫线性方程。

矩阵消元法

**定义 线性方程组的初等变换**

## 向量空间与矩阵

回顾上一章出现的线性方程组：

$$\left\{\begin{matrix}
 a_{11}x_1+a_{12}x_2+\cdots+a_{1n}x_n=b_1 &\\
 a_{21}x_1+a_{22}x_2+\cdots+a_{2n}x_n=b_2 &\\
 \cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot& \\
 a_{m1}x_1+a_{m2}x_2+\cdots+a_{mn}x_n=b_m &
\end{matrix}\right.$$

考虑将其改写为如下形式：

$$\begin{bmatrix}
a_{11}\\
a_{21}\\
\vdots\\
a_{m1}
\end{bmatrix}x_1+
\begin{bmatrix}
a_{12}\\
a_{22}\\
\vdots\\
a_{m2}
\end{bmatrix}x_2+\cdots+
\begin{bmatrix}
a_{1n}\\
a_{2n}\\
\vdots\\
a_{mn}
\end{bmatrix}x_n=
\begin{bmatrix}
b_{1}\\
b_{2}\\
\vdots\\
b_{m}
\end{bmatrix}$$

这启发我们：不应仅仅孤立地研究 $m\times (n+1)$ 个系数，而应将其视为 $n+1$ 个 $m$ 元有序组进行研究。

### 向量与向量空间

#### 向量的定义

**定义** 设 $K$ 为一个数域，而 $m\in\mathbb N_{\ge 2}$，称 $K^m:=\underbrace{K\times K\times \cdots \times K}_{m个K}$ 中的 $m$ 元有序组 $(a_1,a_2,\cdots,a_m)$ 为一个 $m$ 维**向量**(vector)，记为

$$
(a_1,a_2,\cdots,a_m)=:\begin{bmatrix}
a_1\\
a_2\\
\vdots\\
a_m
\end{bmatrix}
$$

称 $a_r(r=1,2,\cdots,m)$ 为该向量的第 $r$ 个**分量**或**坐标**，并称 $K^m$ 为一个 $m$ 维**向量空间**. 

因此，我们可以说，**数的有序组就是向量**. 一般用希腊字母 $\alpha,\beta,\gamma,\cdots$ 表示向量。

> 特别地，我们也可以补充定义一元向量为 $K$ 中的一个数。不过，这样的定义是平凡的。

我们在 $K^m$ 内定义向量间的加法运算如下

$$
+:K^m\times K^m\to K^m,(
\begin{bmatrix}
a_1\\
a_2\\
\vdots\\
a_m
\end{bmatrix},
\begin{bmatrix}
b_1\\
b_2\\
\vdots\\
b_m
\end{bmatrix}
)\mapsto
\begin{bmatrix}
a_1\\
a_2\\
\vdots\\
a_m
\end{bmatrix}+
\begin{bmatrix}
b_1\\
b_2\\
\vdots\\
b_m
\end{bmatrix}:=
\begin{bmatrix}
a_1+b_1\\
a_2+b_2\\
\vdots\\
a_m+b_m
\end{bmatrix}
$$

容易验证，$K^m$ 对向量加法运算构成交换群，我们称这个交换群的零元 $(\underbrace{0,0,\cdots,0}_{m个0})$ 为**零向量**，记作 $\textbf 0$。注意这是一个统称，不管该向量的维数是多少，都可以称之为零向量。

此外，我们还定义向量的**数乘**如下

$$
\cdot:K\times K^m\to K^m,(k,
\begin{bmatrix}
a_1\\
a_2\\
\vdots\\
a_m
\end{bmatrix}
)\mapsto k\cdot
\begin{bmatrix}
b_1\\
b_2\\
\vdots\\
b_m
\end{bmatrix}:=
\begin{bmatrix}
ka_1\\
ka_2\\
\vdots\\
ka_m
\end{bmatrix}
$$

> 根据数乘的定义，应该将数写在向量左边，但你如果习惯写在右边的话……那也没问题.jpg

注意数乘并不是 $K^m$ 上的运算，然而其也满足一些良好的性质。

**命题 数乘的基本性质** 设 $K^m$ 为一个 $m$ 维向量空间，$\alpha,\beta\in K^m$，而 $k,l\in K$，则

- $1\cdot \alpha =\alpha$；
- （“结合律”）$k(l\alpha)=(kl)\alpha$；
- （“对数的分配律”）$(k+l)\alpha=k\alpha+l\alpha$；
- （“对向量的分配律”）$k(\alpha+\beta)=k\alpha+k\beta$. 

值得说明的是，交换群 $(K^m,+)$ 所满足的四条性质，与上述数乘的四条性质，这八条性质是向量空间最基本的性质，向量空间的一切基本命题都是由它们推导而来的。

下给出一些重要概念的定义。

**定义 向量组、线性组合与线性表示** 设 $K^m$ 为一个向量空间，而 $\alpha_1,\alpha_2,\cdots,\alpha_s\in K^m(s\in\mathbb N_+)$，则

- 称集合 $V_s:=\{\alpha_1,\alpha_2,\cdots,\alpha_s\}$ 为一个向量组，向量组是无序组；
- 设 $k_1,k_2,\cdots,k_s\in K$，则称向量 $\displaystyle \sum_{r=1}^s k_r\alpha_r=k_1\alpha_1+k_2\alpha_2+\cdots+k_s\alpha_s$ 为向量组 $V_s$ 的一个**线性组合**；
- 记 $\beta:=k_1\alpha_1+k_2\alpha_2+\cdots+k_s\alpha_s\in K^m$，则称向量 $\beta$ 可被向量组 $V_s$ **线性表示**. 

> 向量组定义中的 $s$ 个向量中可能有重复，不过我们有外延公理，无需在意。
特别说明，为了叙述上的方便，我们认为空集是有 $0$ 个向量的向量组。然而，今后若无特别申明，总默认提及的向量组为非空的。

我们看到，根据上述的定义，线性方程组

$$\left\{\begin{matrix}
 a_{11}x_1+a_{12}x_2+\cdots+a_{1n}x_n=b_1 &\\
 a_{21}x_1+a_{22}x_2+\cdots+a_{2n}x_n=b_2 &\\
 \cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot& \\
 a_{m1}x_1+a_{m2}x_2+\cdots+a_{mn}x_n=b_m &
\end{matrix}\right.$$

实际上可以改写为如下的形式：

$$
\alpha_1x_1+\alpha_2x_2+\cdots+\alpha_n x_n=\beta
$$

其中 $\alpha_r:=\begin{bmatrix}
a_{1r}\\
a_{2r}\\
\vdots\\
a_{mr}
\end{bmatrix}(r=1,2\cdots n),\beta:=\begin{bmatrix}
b_{1}\\
b_{2}\\
\vdots\\
b_{m}
\end{bmatrix}$. 

我们看到，该线性方程组解的组数，就是向量 $\beta$ 被向量组 $\{\alpha_1,\alpha_2,\cdots,\alpha_n\}$ 线性表示方法的种数。

#### 向量组的线性相关与线性无关

**定义** 设 $K^m$ 为一个向量空间，给定其中的一个向量组 $\{\alpha_1,\alpha_2,\cdots,\alpha_s\}$，若该向量组确定的一个齐次线性方程组

$$\alpha_1x_1+\alpha_2x_2+\cdots+\alpha_s x_s=\textbf 0$$

有非零解，则称该向量组是**线性相关**(linear dependent)的，否则，称该向量组是**线性无关**的. 

由定义立刻可得如下四个命题。

**命题 线性相关与线性无关的基本性质** 设 $K^m$ 为一个向量空间，给定其中的一个向量组 $V_s:=\{\alpha_1,\alpha_2,\cdots,\alpha_s\}$，则

- 若 $\textbf 0\in V_s$，则向量组 $V_s$ 线性相关；
- 向量组 $\{\alpha\}$ 线性相关当且仅当 $\alpha=\textbf 0$; 
- 向量组 $V_s$ 线性相关且 $s\in\mathbb N_{\ge 2}$，当且仅当存在一个向量 $\alpha\in V_s$ 可被向量组 $V_s\backslash \{\alpha\}$ 线性表示；
- 若向量组 $V_s$ 线性无关，而 $\beta\in K^m$，则 $V_s\cup \{\beta\}$ 线性无关当且仅当 $\beta$ 不能被 $V_s$ 线性表示。

<details>
    <summary>证明</summary>

只证明第四条。$V_s\cup \{\beta\}$ 线性无关显然蕴含 $\beta$ 不能被 $V_s$ 线性表示，只要证后者也蕴含前者。

反设 $V_s\cup \{\beta\}$ 线性相关，则存在一组不全为 $0$ 的数使得

$$
\sum_{r=1}^s k_r\alpha_r +k\beta=\textbf 0
$$

又因 $V_s$ 线性无关，则 $k\ne 0$，移项两边同乘 $\displaystyle -\frac 1k$ 得

$$
\beta=\sum_{r=1}^s (-\frac {k_r}k\alpha_r)
$$

则 $\beta$ 可被 $V_s$ 线性表示，矛盾！<p align="right" > $\square$ </p>

</details>

**例** 给定 $K^m$ 中 $m$ 个向量：

$$
\begin{aligned}
    \varepsilon_1&:=(1,0,0,\cdots,0,0) \\
    \varepsilon_2&:=(0,1,0,\cdots,0,0) \\
    &\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\\
    \varepsilon_m&:=(0,0,0,\cdots,0,1) \\
\end{aligned}
$$

称这些向量 $\varepsilon_1,\varepsilon_2,\cdots,\varepsilon_m$ 为 $m$ 维向量空间的**坐标向量**，它们构成的向量组线性无关。

#### 线性等价与向量组的秩

我们看到，一个线性相关的向量组如果拥有多于两个元素，则其中必有一个向量可被其余的向量线性表示。因此，在某种程度上，这个向量是“多余”的，我们自然想要将其“去掉”。为严格地表达这种想法，下引入一些概念。

**定义 线性等价** 设 $K^m$ 为一个向量空间，而 $s,t\in\mathbb N_+$, 给定其中的两个向量组 $V_s:=\{\alpha_1,\alpha_2,\cdots,\alpha_s\}$ 与 $W_t:=\{\beta_1,\beta_2,\cdots,\beta_t\}$. 若 $V_s$ 的任何向量都能被 $W_t$ 线性表示，且 $W_t$ 的任何向量也都能被 $V_s$ 线性表示，则称这两个向量组是**线性等价**的，记作 $V_s\sim W_t$。

**例** 向量组 $\{\alpha\}$ 与 $\{\alpha,2\alpha,3\alpha,8371894691821234152\alpha\}$ 是线性等价的。

值得指出的是，采用线性“等价”一词是合适的，因为线性等价也满足自反性，对称性与传递性。

下给出本小节的主要概念。

**定义 极大线性无关部分组** 设 $K^m$ 为一个向量空间，给定其中的一个向量组 $V_s:=\{\alpha_1,\alpha_2,\cdots,\alpha_s\}$，如果它与自身的一个线性无关的子集

$$V_r:=\{\alpha_{i_1},\alpha_{i_2},\cdots,\alpha_{i_r}\}(1\le i_1\le i_2\le\cdots \le i_r\le s)$$

线性等价，则称向量组 $V_r$ 为向量组 $V_s$ 的**极大线性无关部分组**。

由这个概念的名字可以看到，“部分”说明 $V_r$ 是原向量组 $V_s$ 的子集，“线性无关”说明 $V_r$ 是线性无关的，而“极大”说明不可能再将某一个 $V_s\backslash V_r$ 中的元素加入 $V_r$ 中却不破坏其线性无关性，因为新加入的元素必然能被 $V_r$ 线性表示。

自然，我们关心所谓的“极大线性无关部分组”是否对所有的向量组均存在？因此，有如下被称为**筛选法**的命题。

**命题 筛选法** 设 $K^m$ 为一个向量空间，给定其中的一个向量组 $V_s:=\{\alpha_1,\alpha_2,\cdots,\alpha_s\}$ 与 $A_0:=\varnothing$. 我们进行如下的筛选：

令 $r$ 依次取值为 $1,2,\cdots,s$，那么

- 若 $A_{r-1}\cup \{\alpha_r\}$ 线性无关，令 $A_{r}:=A_{r-1}\cup \{\alpha_r\}$；
- 若 $A_{r-1}\cup \{\alpha_r\}$ 线性相关，令 $A_{r}:=A_{r-1}$. 

则 $A_s\ne \varnothing$ 当且仅当 $V_s$ 不为零向量组，此时 $A_s$ 就是 $V_s$ 的一个极大线性无关部分组。

<details>
    <summary>证明</summary>

由定义易见 $A_s\ne \varnothing$ 当且仅当 $V_s$ 不为零向量组。这时，$A_1,A_2,\cdots,A_s$ 均是线性无关的，现只要证 $A_s$ 与 $V_s$ 线性等价，又因为 $A_s\subseteq V_s$, 只要证 $V_s$ 中的每个向量都能被 $A_s$ 线性表示。

事实上，对 $\alpha_r\in V_s(r=2,3,\cdots,s)$，有

- 若 $\alpha_r\in A_s$，其显然可被 $A_s$ 线性表示；
- 若 $\alpha_r\notin A_s$，根据定义，这是因为 $A_{r-1}\cup \{\alpha_r\}$ 线性相关，故 $\alpha_r$ 可被 $A_{r-1}\subseteq A_s$ 线性表示。

对 $\alpha_1$，$\alpha_1\notin A_s$ 当且仅当它为零向量，零向量自然可被 $A_s$ 线性表示. <p align="right" > $\square$ </p>

</details>

筛选法向我们保证了，除了零向量组 $\{\textbf 0\}$，任何（非空）向量组都有（非空）极大线性无关部分组。同样，该方法也可用来求极大线性无关部分组。

特别规定，零向量组的极大线性无关部分组为空集。

**例** 给定向量组 $\{\alpha_1,\alpha_2,\alpha_3,\alpha_4,\alpha_5\}$, 其中

$$
\begin{aligned}
    &\alpha_1=(1,0,0), & & \alpha_1=(0,1,0), \\
    &\alpha_3=(0,0,1), & & \alpha_4=(1,1,1), \\
    &\alpha_5=(1,1,0),
\end{aligned}
$$

我们发现，$\{\alpha_1,\alpha_2,\alpha_3\}$ 是它的极大线性无关部分组，但 $\{\alpha_1,\alpha_3,\alpha_4\}$ 也是它的极大线性无关部分组. 

可见，一个向量组的极大线性无关部分组并不是唯一的。这不免令我们担心：同一个向量组的不同极大线性无关部分组，它们的元素数量是否一样多呢？

下通过证明几个命题来给出肯定的答复。~~如果一样多那“极大”这个名字就可以改为“最大”了，所以不这样命名的原因难道是防止剧透？~~

**定理 Steinitz 替换定理** 设 $K^m$ 为一个向量空间，给定其中的两个向量组 $V_s:=\{\alpha_1,\alpha_2,\cdots,\alpha_s\}$ 与 $W_t:=\{\beta_1,\beta_2,\cdots,\beta_t\}$. 若 $V_s$ 线性无关，且其中的每个向量都能被 $W_t$ 线性表示，则

- $s\le t$；
- 特别地，$s=t$ 蕴含 $W_t$ 线性无关，但 $W_t$ 线性无关并不蕴含 $s=t$；
- 存在 $W_t$ 中的 $s$ 个元素 $\beta_{i_1},\beta_{i_2},\cdots,\beta_{i_s}$ 使得 $W_t':=(W_t\cup V_s)\backslash \{\beta_{i_1},\beta_{i_2},\cdots,\beta_{i_s}\}$ 与 $W_t$ 线性等价。

<details>
    <summary>证明</summary>

**证明1** 考虑反证法，不妨设 $s>t$，往证 $V_s$ 线性相关，从而推出矛盾。

要证 $V_s$ 线性相关，只要证齐次线性方程组

$$
\alpha_1x_1+\alpha_2x_2+\cdots+\alpha_s x_s=\textbf 0
$$

有非零解。

既然 $V_s$ 中的每个向量都能被 $W_t$ 线性表示，那不妨设

$$\left\{\begin{matrix}
 \alpha_1=a_{11}\beta_1+a_{12}\beta_2+\cdots+a_{1t}\beta_t &\\
 \alpha_2=a_{21}\beta_1+a_{22}\beta_2+\cdots+a_{2t}\beta_t &\\
 \cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot& \\
 \alpha_s=a_{s1}\beta_1+a_{s2}\beta_2+\cdots+a_{st}\beta_t &\\
\end{matrix}\right.$$

代入上述齐次线性方程组, 按照 $\beta_1,\beta_2,\cdots,\beta_t$ 合并同类项得

$$
(a_{11}x_1+a_{21}x_2+\cdots+a_{s1}x_s)\beta_1+(a_{12}x_1+a_{22}x_2+\cdots+a_{s2}x_s)\beta_2+\cdots+(a_{1t}x_1+a_{2t}x_2+\cdots+a_{st}x_s)\beta_t=\textbf 0
$$

尽管我们不清楚向量组 $W_t$ 是否线性无关（从而上式成立只有等号左边的 $t$ 个系数同时为 $0$），但事实上不难举出符合题设且 $W_t$ 线性无关的例子。因此，试令

$$\left\{\begin{matrix}
 a_{11}x_1+a_{21}x_2+\cdots+a_{s1}x_s=0 &\\
 a_{12}x_1+a_{22}x_2+\cdots+a_{s2}x_s=0 &\\
 \cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot& \\
 a_{1t}x_1+a_{2t}x_2+\cdots+a_{st}x_s=0 &
\end{matrix}\right.$$

这是一个有 $s$ 个未知量而有 $t$ 个方程的齐次线性方程组，由 $s>t$ 知，该方程组必有非零解。

从而，存在一组不全为 $0$ 的数令上式 $\beta_1,\beta_2,\cdots,\beta_t$ 的系数全为 $0$，故原齐次线性方程组确有非零解，$V_s$ 线性相关，矛盾！<p align="right" > $\square$ </p>

**证明2** 先证 $s=t$ 蕴含 $W_t$ 线性无关。

设 $W_t$ 的一个极大线性无关部分组的元素数量为 $t'$，则 $t'\le t = s$，又易见该极大线性无关部分组也能线性表示 $V_s$ 的所有元素，根据（1）又有 $s\le t'$，故 $t'=s=t$，即 $W_t$ 就是自身的一个极大线性无关部分组，得证。

再证 $W_t$ 线性无关并不蕴含 $s=t$，容易举出反例

$$
V_s:=\{(0,1)\},\quad W_t:=\{(0,1),(1,0)\}
$$

显然这时 $s<t$. <p align="right" > $\square$ </p>

**证明3** 不妨设 $t\in\mathbb N_{\ge 2}$（否则 $s=t=1$ 显然成立）, 再设 $V_s$ 与 $W_t$ 中不存在相等的向量，即 $V_s\cap W_t=\varnothing$. 

考虑对 $s=1,2,\cdots t$ 进行归纳。

先设 $s=1$，此时将 $V_s$ 中的唯一一个元素 $\alpha_1$ 放入 $W_t$ 中，得到新向量组 $W_t\sqcup \{\alpha_1\}$，又根据题设有

$$
\alpha_1 =\sum_{r=1}^tk_r\beta_r= k_1\beta_1+k_2\beta_2+\cdots+k_t\beta_t
$$

从而易见 $W_t\sqcup \{\alpha_1\} \sim W_t$. 

又因为 $V_s$ 线性无关，则 $\alpha_1\ne \textbf 0$, 故上式中的 $k_1,k_2,\cdots,k_n$ 不全为 $0$. 不妨记这一不为 $0$ 的项为 $k\beta$, 将其余项移至等号左边，两边同乘 $\displaystyle \frac 1k$ 易知，$\beta$ 能被其余 $t$ 个向量线性表示. 

故令 $W_t':=(W_t\sqcup V_s)\backslash \{\beta\}$，同理 $W_t'\sim W_t\sqcup V_s$，由线性等价的传递性知 $W_t'\sim W_t$. 

下证若 $s\in \{1,2,\cdots,t-1\}$ 时原命题成立，则对于 $s+1$ 原命题也成立。

换言之，对于 $V_{s+1}=\{\alpha_1,\alpha_2,\cdots,\alpha_{s+1}\}$ 的前 $s$ 个元素，我们既已找到可被“替换”的 $s$ 个元素 ${\beta_1,\beta_2,\cdots,\beta_s \in W_t}$ 使得集合

$$
W:=\{\alpha_1,\alpha_2,\cdots,\alpha_{s},\beta_{s+1},\cdots,\beta_t\}
$$

与 $W_t$ 线性等价。那么，再将 $\alpha_{s+1}$ 加入上述集合，则新集合

$$
W\sqcup\{\alpha_{s+1}\}=\{\alpha_1,\alpha_2,\cdots,\alpha_{s},\alpha_{s+1},\beta_{s+1},\cdots,\beta_t\}
$$

必是线性相关的。否则，它拥有 $t+1>t$ 个元素，其中的每一个元素却都可以被 $W$ 线性表示，这与 (1) 的结论矛盾！

则存在 $t+1$ 个数 $k_1',k_2',\cdots,k_{t+1}'$ 使得

$$
\sum_{r=1}^{s+1}k_r'\alpha_r+\sum_{r=s+1}^{t}k_{r+1}'\beta_r=\textbf 0
$$

同样因为 $V_{s+1}$ 线性无关，故 $t-s$ 个系数 $k_{s+2}',\cdots,k_{t+1}'$ 不全为 $0$，同理，$W\sqcup \{\alpha_{s+1}\}$ 中也存在一个 $\beta'\in W_t$ 能够被集合 $W\sqcup \{\alpha_{s+1}\}$ 中的其他 $t$ 个元素线性表示。

只需取 $W_t':=(W\sqcup \{\alpha_{s+1}\})\backslash \{\beta'\}$ 即证. 

综上，当 $V_s\cap W_t=\varnothing$ 时原命题成立。

特别地，当 $T:=V_s\cap W_t\ne\varnothing$ 时，只需取 $V_s\backslash T$ 与 $W_t\backslash T$ 两个不交的集合，按照原命题进行替换得到 $(W_t\backslash T)'$，令 $W_t':=(W_t\backslash T)'\sqcup T$ 即可。<p align="right" > $\square$ </p>

</details>

由替换定理便可得出一个重要推论。

**推论** 两个相互线性等价的向量组，它们的极大线性无关部分组的元素数量相等。

<details>
    <summary>证明</summary>

不妨设 $V_s$ 与 $W_t$ 为两个相互线性等价的向量组，分别设它们的一个极大线性无关部分组为 $V_k$ 与 $W_l$，显然 $V_k$ 与 $W_l$ 仍然线性等价，于是

- 若 $k>l$，由 Steinitz 替换定理的结论（1）知 $V_k$ 线性相关，矛盾！

- 若 $k<l$，由 Steinitz 替换定理的结论（1）知 $W_l$ 线性相关，矛盾！

故只能有 $k=l$. <p align="right" > $\square$ </p>

</details>

由线性无关的自反性自然得知，同一个向量组的不同极大线性无关部分组，它们的元素数量一样多。

**定义 秩** 一个向量组的极大线性无关部分组的元素数量称作该向量组的**秩**(rank).

显然，零向量组的秩为 $0$；本身就线性无关的向量组的秩就是它的元素数量；两个相互线性等价的向量组的秩相等。

关于向量组的秩，有这样一个看上去十分显然却让人非常困惑的命题。

**命题 极大线性无关部分组的任意性** 设向量组 $V_s$ 的秩为 $r(r\in\mathbb N_+)$，则对任何 $V\subseteq V_s$，$V$ 为 $V_s$ 的一个极大线性无关部分组的充要条件是 $V$ 线性无关且秩为 $r$. 

冰雪聪明的 Cirno 同学立刻给出了一个证明。

**证明** 必要性显然，只证充分性。

反设存在一个线性无关且秩为 $r$ 的 $V\subseteq V_s$ 却不为 $V$ 的一个极大线性无关部分组。根据定义，存在 $\beta\in V_s\backslash V$ 不能被 $V$ 线性表示，根据线性无关的基本性质，$V\sqcup \{\beta\}$ 也线性无关。

然而 $V\sqcup \{\beta\}$ 有 $r+1$ 个元素，这与 $V_s$ 的秩为 $r$ 矛盾！ <p align="right" > $\square$ </p>

请你指出 Cirno 的证明存在的问题, 并加以改正. 

<details>
    <summary>解答</summary>

$V\sqcup \{\beta\}$ 有 $r+1$ 个元素究竟如何会与 $V_s$ 的秩为 $r$ 矛盾呢？

诚然 $V_s$ 的秩为 $r$，它的“极大线性无关部分组”只能有 $r$ 个元素，但目前尚未说明 $V\sqcup \{\beta\}$ 就是 $V_s$ 的一个极大线性无关部分组，从而无法造成矛盾。

要从定义说明 $V\sqcup \{\beta\}$ 是 $V_s$ 的一个极大线性无关部分组，只能说明 $V_s$ 的每一个元素均能被 $V\sqcup \{\beta\}$ 线性表示。注意，这与 Cirno 一开始想要证明的，$V_s$ 的每一个元素均能被 $V$ 线性表示是相类似的。

所以，Cirno 的证明实质上是不完整的。若要沿着她的思路进行证明，则必须像这样补充下去：

注意此时已有 $r<s$，不妨设 $k=s-r\in\mathbb N_+$, 并记 $\beta=:\beta_1$. 

- 由 $V_s$ 的秩为 $r$，知 $V\sqcup \{\beta_1\}$ 也不为 $V_s$ 的一个极大线性无关部分组（否则它的元素数量为 $r+1$，矛盾）。然而 $V\sqcup \{\beta_1\}$ 确是线性无关的，则根据极大线性无关部分组的定义，必存在 $\beta_2\in V_s\backslash (V\sqcup \{\beta\})$ 不能被 $V\sqcup \{\beta_1\}$ 线性表示；

- 再考察 $V\sqcup \{\beta_1,\beta_2\}$，由 $V_s$ 的秩为 $r$，知它也不为 $V_s$ 的一个极大线性无关部分组。然而它也是线性无关的，则又能找到能够加入这个集合的 $\beta_3$……

那么，考虑 $V\sqcup \{\beta_1,\beta_2,\cdots\beta_k\}$，这个集合已有 $r+k=s$ 个元素，又是 $V_s$ 的子集，这说明 $V\sqcup \{\beta_1,\beta_2,\cdots\beta_k\}=V_s$，故整个 $V_s$ 线性无关。但这矛盾，因为这时 $V_s$ 自身就为其极大线性无关部分组，但 $s>r$。

</details>

#### 向量及其运算的几何意义

必须说明的是，我们尚未介绍任何解析几何的相关知识，也假设读者并不事先知道这些知识。因此，本部分将要介绍的所谓“几何意义”实质上是“不严谨”的列向量组正好也是~~所以语言风格会更像聊天~~，主要目的是更直观地理解本小节给出的定义和命题。

然而，正如《数学分析笔记》中提到的：

>在研究 $\mathbb R$ 时，我们可以将其看作一条“直线”，亦即所谓**实轴**：每个实数与实轴上的每个点一一对应，实轴上左边的数总是严格地小于右边的数，两实数之差的绝对值就代表它们对应的两点间线段的长度，诸如此类。

这样的几何观点相当直观有效，尽管它尚不能代替分析的证明，但它能成为理解问题的“抓手”，从而引导我们完成证明中特定的一步（如某些量的具体构造），等等。

同研究 $\mathbb R$ 时类似的，在研究二维向量空间 $\mathbb R^2$ 时，我们可以想象两条相互垂直（好，什么是垂直？）的实轴构成的一个平面（好，那什么又是平面？），我们有：

- 不妨称水平以右为正方向的实轴为 $x$ 轴，竖直以上为正方向的实轴为 $y$ 轴；
- 零向量 $(0,0)$ 对应 $x$ 轴与 $y$ 轴的交点，称之为原点 $O$，称这个平面为 $xOy$ 平面；
- 向量 $(a,0)$ 对应 $x$ 轴上的点 $a$，向量 $(0,b)$ 则对应 $y$ 轴上的点 $b$；
- 向量 $(a,b)$ 对应平面内能与 $(0,0),(a,0),(0,b)$ 三点构成一个矩形的点。

我们不加证明（其实根本没法证明）地提出，二维向量空间 $\mathbb R^2$ 中的每个向量与 $xOy$ 平面中的每个点一一对应。

与此同时，$xOy$ 平面中的每个点又与一条以 $O$ 为起点，自身为终点的一条**有向线段**一一对应，这就是“向量”这一名称的来历。

当然，研究三维向量空间 $\mathbb R^3$ 时，我们可以想象在既有的 $xOy$ 平面上增加一条垂直于该平面的实轴，其与 $xOy$ 平面交于 $O$ 点，正方向指向屏幕外，不妨称之为 $z$ 轴。

这三条实轴构成的空间不妨就称之为 $O-xyz$ 空间，由于它们两两垂直，我们仍有：

- 向量 $(a,b,0)$ 对应 $xOy$ 平面的点 $(a,b)$；
- 向量 $(a,0,c)$ 对应 $xOz$ 平面的点 $(a,c)$；
- 向量 $(0,b,c)$ 对应 $yOz$ 平面的点 $(b,c)$；
- 零向量 $(0,0,0)$ 仍然对应 $O-xyz$ 空间的原点 $O$；
- 向量 $(a,b,c)$ 对应平面内能与 $(0,0,0),(a,0,0),(0,b,0),(0,0,c),(a,b,0),(a,0,c),(0,b,c)$ 七点构成一个长方体的点。

我们仍然不加证明（其实根本没法证明）地提出，三维向量空间 $\mathbb R^3$ 中的每个向量也与 $O-xyz$ 空间中的每个点一一对应。

维数更高的向量空间，比如 $\mathbb R^4,\mathbb R^5$ 等等，就无法这样想象了。因此，这样的几何观点更加无法作为证明。

向量加法与数乘的几何意义也可类似地想象（略）

线性组合

向量组的秩：这组向量张成流形的维数。

### 矩阵
#### 矩阵的秩

我们知道，一个线性方程组可以用一个矩阵来代表。因此，我们将矩阵当作“中间量”——先把上一节所得的结果应用于矩阵，再把所得的矩阵相关的结果应用于线性方程组。

##### 行秩与列秩

先给出若干定义以体现矩阵与向量的联系。

**定义** 给定数域 $K$ 上的一个 $m\times n$ 矩阵

$$
\begin{bmatrix}
 a_{11} & a_{12} & \cdots & a_{1n}\\
 a_{21} & a_{22} & \cdots & a_{2n}\\
 \vdots & \vdots & & \vdots\\
 a_{m1} & a_{m2} & \cdots & a_{mn}\\
\end{bmatrix}
$$

我们可以将它的 $n$ 列看作 $n$ 个 $m$ 维向量，称之为 **列向量**，这 $n$ 个向量构成的集合称之为 **列向量组**；同样，我们也可以将它的 $m$ 行看作 $m$ 个 $n$ 维向量，称之为 **行向量**，这 $m$ 个向量构成的集合称之为 **行向量组**. 

**定义 行秩与列秩** 一个矩阵的行（列）向量组的秩，称为该矩阵的行（列）秩。

易见，一个矩阵的行向量组与列向量组同由该矩阵的 $m\times n$ 个元素组成. 由此推断，一个矩阵的行秩与列秩之间应当存在某种联系, 但这个联系现在隐藏在一大堆数据（即这 $m\times n$ 个元素）后面, 我们看不清楚. 

在上一章求解一个复杂的线性方程组时, 我们采用初等变换把它化为简单的阶梯形方程组, 后者的解立即可以求出. 现在, 我们也尝试对矩阵使用类似的办法给以简化, 使得简化后的矩阵的行秩与列秩之间的联系水落石出.

**定义 矩阵的初等变换** 对数域 $K$ 上的一个 $m\times n$ 矩阵 $A$，下述三种行（列）变换：

- 交换两行（列）的位置；
- 将某行（列）中的元素均变为原先的 $c(c\in K,c\ne 0)$ 倍；
- 将某行（列）中的元素均乘以常数 $k(k\in K)$，将所得的新行（列）按照顺序加到某行（列）的元素上去。

都被称作**矩阵的初等行（列）变换**。

关于矩阵的初等变换，有如下的命题。

**命题 矩阵初等变换的性质** 矩阵的初等变换有如下性质：

1. 矩阵的初等变换是可逆的。换言之，若矩阵 $A$ 经过了 $s$ 次初等变换得到了矩阵 $B$，则矩阵 $B$ 必可以通过 $s$ 次初等变换重新得到矩阵 $A$；
2. 矩阵的初等行变换不改变其行秩；
3. 矩阵的初等列变换不改变其列秩. 

上述命题不难证明，事实上还有下述命题。

**命题** 矩阵的初等行（列）变换也不改变其列（行）秩。

<details>
    <summary>证明</summary>

先证矩阵的初等行变换不改变列秩。

设 $A$ 为数域 $K$ 上的一个非零 $m\times n$ 矩阵，其列秩为 $r(1\le r\le n)$。

由于矩阵的列变换不改变列秩，不妨设其列向量组 $N_n:=\{\alpha_1,\alpha_2,\cdots\,\alpha_n\}$ 的一个极大线性无关部分组为 $N_r:=\{\alpha_1,\alpha_2,\cdots\,\alpha_r\}$（否则通过列变换将线性无关的 $r$ 列交换到前 $r$ 列即可）。

再设经过若干次行变换后得到的矩阵 $A'$ 的列向量组为 $N_n':=\{\alpha_1',\alpha_2',\cdots\,\alpha_n'\}$，则只需证 $N_r':=\{\alpha_1',\alpha_2',\cdots\,\alpha_r'\}$ 仍是变换后列向量组的一个极大线性无关部分组，只要证：

- $N_r'$ 线性无关；
- $N_n'$ 中的向量均能被 $N_r'$ 线性表示。

不妨将 $N_r$ 按照顺序作为列向量排成矩阵 $B$，将 $N_r'$ 按照同样的顺序作为列向量排成矩阵 $B'$，易见 $B'$ 是矩阵 $B$ 经过若干次行变换得到的。因此，齐次线性方程组

$$
\begin{align}
    \alpha_1x_1+\alpha_2x_2+\cdots+\alpha_rx_r=\textbf 0 \\
    \alpha_1'x_1+\alpha_2'x_2+\cdots+\alpha_r'x_r=\textbf 0
\end{align}
$$

同解。又因为 $(1)$ 只有零解，故 $(2)$ 也只有零解，则 $\{\alpha_1',\alpha_2',\cdots\,\alpha_r'\}$ 线性无关得证。

类似地，对 $N_n'$ 中任何的 $a_i'(i=1,2,\cdots n)$，要证它能被 $N_r'$ 线性表示，只需借助 $a_i$ 能被 $N_r$ 线性表示的条件。

因此，将向量 $a_i$ 添加为矩阵 $B$ 的最后一列得到矩阵 $\bar B$, 将向量 $a_i'$ 添加为矩阵 $B'$ 的最后一列得到矩阵 $\bar {B'}$. 易见 $\bar B'$ 也是矩阵 $\bar B$ 经过若干次行变换得到的。将 $\bar B$ 与 $\bar B'$ 看作增广矩阵，则线性方程组

$$
\begin{align}
    \alpha_1x_1+\alpha_2x_2+\cdots+\alpha_rx_r=\alpha_i \\
    \alpha_1'x_1+\alpha_2'x_2+\cdots+\alpha_r'x_r=\alpha_i'
\end{align}
$$

也同解。而根据 $a_i$ 能被 $N_r$ 线性表示, 知 $(3)$ 有解，故 $(4)$ 也有解，则 $N_n'$ 中的向量均能被 $N_r'$ 线性表示证毕。

综上，已证明了矩阵的初等行变换不改变列秩。

再证明矩阵的初等列变换不改变行秩，注意此时不可直接仿照上述方法，因为线性方程组的系数矩阵或增广矩阵不能作列变换，否则可能改变原方程组的解。

考虑将 $A$ 的列向量组 $N_n=\{\alpha_1,\alpha_2,\cdots\,\alpha_n\}$ 按照顺序作为行向量排成矩阵 $A^T$, 易见，将 $A^T$ 的列向量组按照顺序作为行向量排成的矩阵也是 $A$. 我们称矩阵 $A^T$ 与矩阵 $A$ 互为**转置矩阵**. 

请读者自行验证：对 $A$ 作一次列变换再转置，所得的矩阵也可以由 $A^T$ 作一次行变换得到，如图： 

$$
\begin{array}{lcl}
 &A &\xrightarrow[\text{}]{列变换}  &A'\\
 &\downarrow & &\downarrow  \\
 &A^T &\xrightarrow[\text{}]{行变换} &(A')^T
\end{array}
$$

由数学归纳法可证，对 $A$ 作任一次列变换再转置，所得的矩阵也可以由 $A^T$ 作相同次数的列变换得到，如图: 

$$
\begin{array}{lclclclclclclclc}
 &A &\xrightarrow[\text{}]{列变换} &A' &\xrightarrow[\text{}]{列变换} & A''&\cdots &\xrightarrow[\text{}]{列变换} &A^{(n)}\\
 &\downarrow & &\downarrow & &\downarrow & & &\downarrow\\
 &A^T &\xrightarrow[\text{}]{行变换} &(A')^T &\xrightarrow[\text{}]{行变换} & (A'')^T&\cdots &\xrightarrow[\text{}]{行变换} &(A^{(n)})^T
\end{array}
$$

> 其中 $A^{(n)}$ 表示 $A$ 后 $n$ 个 $'$.  

因此，矩阵 $A$ 进行若干次列变换后得到 $A'$，考虑它的转置矩阵 $(A')^T$，该矩阵可以由 $A^T$ 进行若干次行变换得到，故 $(A')^T$ 的列秩等于 $A^T$ 的列秩，而这两者分别等于 $A'$ 的行秩与 $A$ 的行秩。

综上，已证明了矩阵的初等列变换不改变行秩。原命题证毕。<p align="right" > $\square$ </p>

</details>

上述证明中出现的转置矩阵的概念非常重要。

##### 矩阵的标准形

综合上述命题，我们发现，矩阵的初等行（列）变换均不改变其行秩与列秩。因此，我们考虑同时对矩阵作初等行变换与初等列变换，具体地说，对于 $K$ 上的一个非零 $m\times n$ 矩阵

$$
\begin{bmatrix}
 a_{11} & a_{12} & \cdots & a_{1n}\\
 a_{21} & a_{22} & \cdots & a_{2n}\\
 \vdots & \vdots & & \vdots\\
 a_{m1} & a_{m2} & \cdots & a_{mn}\\
\end{bmatrix}
$$

我们依次执行如下步骤：

1. 不妨设 $a_{11}\ne 0$（否则，通过初等行、列变换将不为零的元素移动到这个位置来），随后将第 $2,3,\cdots,m$ 行分别加上第一行的 $\displaystyle -\frac {a_{21}}{a_{11}},-\frac {a_{31}}{a_{11}},\cdots,-\frac {a_{m1}}{a_{11}}$ 倍，得到

$$
\begin{bmatrix}
 a_{11} & a_{12}' & \cdots & a_{1n}'\\
 0 & a_{22}' & \cdots & a_{2n}'\\
 \vdots & \vdots & & \vdots\\
 0 & a_{m2}' & \cdots & a_{mn}'\\
\end{bmatrix}
$$

2. 再将第一列乘以 $\displaystyle \frac 1{a_{11}}$，得到

$$
\begin{bmatrix}
 1 & a_{12}' & \cdots & a_{1n}'\\
 0 & a_{22}' & \cdots & a_{2n}'\\
 \vdots & \vdots & & \vdots\\
 0 & a_{m2}' & \cdots & a_{mn}'\\
\end{bmatrix}
$$

3. 再将第 $2,3,\cdots,m$ 列分别加上第一行的 $-a_{12}',-a_{13}',\cdots,a_{1n}'$ 倍，得到

$$
\begin{bmatrix}
 1 & 0 & \cdots & 0\\
 0 & a_{22}'' & \cdots & a_{2n}''\\
 \vdots & \vdots & & \vdots\\
 0 & a_{m2}'' & \cdots & a_{mn}''\\
\end{bmatrix}
$$

4. 如果 $m=1$ 或 $n=1$，那我们的工作就到此为止了，因为 $a_{11}$ 已经在这个矩阵的最后一行或最后一列。若 $m\ge 2$ 且 $n\ge 2$，则可以对右下角的 $(m-1)\times (n-1)$ 矩阵继续进行步骤 $(1)\sim (4)$——除非它是一个零矩阵，如果这样，我们直接打住即可。

最终，原先的矩阵进过若干次步骤 $(1)\sim (4)$ 的初等变化，会得到下列三种情况之一（未写出部分均是 $0$）：

$$
\begin{array}{ccc}
&\begin{bmatrix}
 1 &  &  &  &  &  &  & \\
  & \ddots  &  &  &  &  &  & \\
  &  & 1 &  &  &  &  & \\
  &  &  & 0 &  &  &  & \\
  &  &  &  & \ddots &  &  & \\
  &  &  &  &  & 0 & \cdots & 0
\end{bmatrix},
&\begin{bmatrix}
 1 &  &  &  &  &   \\
  & \ddots  &  &  &  &   \\
  &  & 1 &  &  &   \\
  &  &  & 0 &  &  \\
  &  &  &  & \ddots &   \\
  &  &  &  &  & 0 
\end{bmatrix},
&\begin{bmatrix}
 1 &  &  &  &  &   \\
  & \ddots  &  &  &  &   \\
  &  & 1 &  &  &   \\
  &  &  & 0 &  &  \\
  &  &  &  & \ddots &   \\
  &  &  &  &  & 0 \\
  &  &  &  &  & \vdots  \\
  &  &  &  &  & 0 \\
\end{bmatrix} \\
&(m<n)&(m=n)&(m>n)
\end{array}
$$

这三种情况的共同点是：均只由 $0$ 或 $1$ 构成，$1$ 只分布在对角线上而其余元素均是 $0$. 称它们为矩阵的**标准形**，不难看出，零矩阵也可以当作是标准形，只不过其中没有 $1$ 只有 $0$。

易见，标准形中 $1$ 的数量就是其行秩与列秩。因此，我们得到了一个重大发现！

**命题** 矩阵的行秩等于列秩。
**定义** 称矩阵 $A$ 的行秩或列秩为矩阵 $A$ 的**秩**，记作 $\mathrm{rank}(A)$。

今后，我们便可以通过将矩阵化为标准形来求其秩，也可以将向量组按行（列）排成矩阵，再将矩阵化为标准型来求其秩。

然而，将矩阵化为标准形毕竟麻烦。由此，我们又得到一种求矩阵的秩（当然，也是求向量组的秩）的办法，即**阶梯化法**。

**定义 行（列）阶梯形矩阵** 称一个矩阵为行（列）阶梯形矩阵，若：

事实上，这种办法还可求向量组的极大线性无关部分组。

（摸了）

#### 线性方程组的理论课题

##### 齐次线性方程组的基础解系

考查数域 $K$ 上的齐次线性方程组

$$\left\{\begin{matrix}
 a_{11}x_1+a_{12}x_2+\cdots+a_{1n}x_n=0 &\\
 a_{21}x_1+a_{22}x_2+\cdots+a_{2n}x_n=0 &\\
 \cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot& \\
 a_{m1}x_1+a_{m2}x_2+\cdots+a_{mn}x_n=0 &
\end{matrix}\right.$$


**定义 解向量**

齐次线性方程组的解向量具有如下性质。

**命题** 考查数域 $K$ 上的齐次线性方程组

$$\left\{\begin{matrix}
 a_{11}x_1+a_{12}x_2+\cdots+a_{1n}x_n=0 &\\
 a_{21}x_1+a_{22}x_2+\cdots+a_{2n}x_n=0 &\\
 \cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot& \\
 a_{m1}x_1+a_{m2}x_2+\cdots+a_{mn}x_n=0 &
\end{matrix}\right.$$

若向量 $\eta=(k_1,k_2,\cdots,k_n)\in K^n$ 为该齐次线性方程组的解向量，则：

- 任取 $k\in K$，$k\eta$ 也为该齐次线性方程组的解向量；
- 若向量 $\eta'=(l_1,l_2,\cdots,l_n)\in K^n$ 也为该齐次线性方程组的解向量, 则 $\eta+\eta'$ 也为该齐次线性方程组的解向量. 

易见，若找到了齐次线性方程组的一组解向量 $\{\eta_1,\eta_2,\cdots,\eta_n\}$，则它们的任意线性组合也是该方程组的一个解向量。为此，我们引入如下的概念。

**定义 基础解系** 齐次线性方程组的一组解向量 $\{\eta_1,\eta_2,\cdots,\eta_n\}$ 若满足：

- $\{\eta_1,\eta_2,\cdots,\eta_n\}$ 线性无关；
- 该齐次线性方程组的任一解向量都可被 $\{\eta_1,\eta_2,\cdots,\eta_n\}$ 线性表示。

则称这组解向量 $\{\eta_1,\eta_2,\cdots,\eta_n\}$ 为原齐次线性方程组的一个**基础解系**。

##### 基础解系的求法

##### 线性方程组的一般理论

**定理 线性方程组有解判别定理** 数域 $K$ 上的线性方程组有解的充要条件是其系数矩阵与增广矩阵的秩相同。

#### 矩阵的运算

前已引入了矩阵的概念，但主要是作为研究线性方程组的解系的工具，矩阵这一概念的内涵尚不深刻。

##### 矩阵的加法与数乘

同向量。

##### 矩阵的乘法

向量是多行一列的特殊矩阵。

矩阵与向量相乘，向量的行数必须等于矩阵的列数。

矩阵与矩阵相乘，左侧矩阵的列数必须等于右侧矩阵的行数。

##### 矩阵与向量空间之间的映射

##### 矩阵运算的性质

数域 $K$ 上的矩阵运算满足如下性质。

**命题 矩阵运算的性质** 设 $A,B,C$ 是数域 $K$ 上的矩阵，下总假设它们两两之间可以进行矩阵乘法：

- （矩阵乘法结合律）$A(BC)=(AB)C$; 
- （矩阵乘法对加法的分配律）$A(B+C)=AB+AC,(A+B)C=AC+BC$; 
- （矩阵乘法与数乘的“结合律”）任给 $k\in K$, $k(AB)=(kA)B$; 
- （矩阵乘法与转置的关系）任给 $k\in K$, $(A+B)^T=A^T+B^T,(kA)^T=kA^T,(AB)^T=B^TA^T$. 

值得注意的是：矩阵乘法没有交换律和消去律，两个非零矩阵作乘法可能得到零矩阵。

##### 矩阵运算与秩的关系

#### 矩阵及其运算的几何意义



#### 方阵

数域 $K$ 上的 $m\times n$ 矩阵对应着向量空间 $K^n$ 到 $K^m$ 之间的一个映射。特别地，如果 $m=n$，这个正方形的矩阵（简称**方阵**）就对应着向量空间 $K^n$ 到它自身的一个映射，这样的映射又被称作一种“变换”。

不同于非方阵与向量相乘时会“丢失”或“增添”分量，方阵对向量

#### 分块矩阵

## 行列式

