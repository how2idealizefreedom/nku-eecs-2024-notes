<style>
body {
    background-color: #FFFFF8; /* 淡米色护眼色 */
}
/* 自定义引用样式 1 */
.quote-style-1 {
    border-left: 5px solid #007BFF;
    background-color: #f0f8ff; /* 浅蓝色背景 */
    padding: 15px;
    text-align: left; /* 左对齐 */
    font-style: normal; /* 正体 */
}

/* 自定义引用样式 2 */
.quote-style-2 {
    border-left: 5px solid #28a745;
    background-color: #e8f5e9; /* 浅绿色背景 */
    padding: 15px;
    font-weight: normal; /* 取消加粗 */
    text-align: left; /* 左对齐 */
    font-style: normal; /* 正体 */
}

/* 自定义引用样式 3 */
.quote-style-3 {
    border-left: 5px solid #dc3545;
    background-color: #fce4ec; /* 浅红色背景 */
    padding: 15px;
    text-align: left; /* 左对齐 */
    font-style: normal; /* 正体 */
}

/* 自定义引用样式 4 */
.quote-style-4 {
    border-left: 5px solid #9370db;
    background-color: #f0e6f7; /* 淡紫色背景 */
    padding: 15px;
    text-align: left; /* 左对齐 */
    font-style: normal; /* 正体 */
}
</style>
<style>
.custom-details {
    border: 2px solid #d3d3d3; /* 边框颜色为浅灰色 */
    border-radius: 5px; /* 圆角 */
    margin: 10px 0; /* 上下间距 */
    padding: 10px; /* 内边距 */
    background-color: #f0e6f7; /* 默认背景颜色 */
    transition: background-color 0.3s ease; /* 过渡效果 */
}

.custom-details[open] {
    background-color: #F9F9F9; /* 展开时的背景颜色改为浅灰色 */
}

.custom-summary {
    cursor: pointer; /* 鼠标指针样式 */
    font-weight: bold; /* 字体加粗 */
    padding: 5px; /* 内边距 */
    outline: none; /* 去掉默认的轮廓 */
    position: relative; /* 位置相对 */
    font-size: 18px;
}

.arrow {
    display: inline-block; /* 使其可以旋转 */
    transition: transform 0.3s ease; /* 过渡效果 */
    margin-right: 5px; /* 箭头与文本之间的间距 */
}

.custom-details[open] .arrow {
    transform: rotate(90deg); /* 展开时旋转箭头 */
}

</style>
<style>
ul li {
    font-size: 18px;
    line-height: 1.55;
}
ol {
    font-size: 18px;
    line-height: 1.55;
} /* medium.css 的列表样式有点诡异 */

h1 { font: 26pt echo !important; }
h2 { font: 22pt echo !important; }
h3 { font: 16pt echo !important; }

/* 更可爱的前三级标题 */

</style>

> 这是一篇参考《高等代数简明教程》（蓝以中）《高等代数学习指南》（蓝以中）与《Linear Algebra Done Right》(Sheldon Axler)以及本人的《数学分析笔记》写作的个人笔记. 
> Written by 賢者の極北

# 引言：经典代数学的基本课题

## 前备知识

> Before we begin, you must all be warned...nothing here is algebraic. 

得益于《数学分析笔记》的前备知识一章详尽地介绍了大量有用的内容, 因此本章会异常简短, 甚至无需分段. 

先回顾一下有序组的概念. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(有序组)</strong>

设 $a,b$ 是两个数学对象, 定义 $a$ 和 $b$ 的**有序对**为 $(a,b):=\{\{a\},\{a,b\}\}$. 有序对又称作二元有序组. 

$\,$

设 $n\in\mathbb N_{\ge 2}$, 归纳定义数学对象 $x_1,x_2,\cdots,x_n$ 的 $n$ 元**有序组**为 $(x_1,x_2,\cdots,x_{n-1})$ 与 $x_n$ 构成的有序对 $((x_1,x_2,\cdots,x_{n-1}),x_n)$, 简记作 $(x_1,x_2,\cdots,x_n)$. 

</blockquote>

此外, 我们还补充定义任何数学对象 $a$ 的一元有序组 $(a):=a$, 零元有序组 $():=\varnothing$. 一个 $n$ 元有序组的**长度**记作 $n$. 

> 你可以用 $\{a\}$ 表示 $a=(x_1,x_2,\cdots,x_n)$ 的无序组 $\{x_1,x_2,\cdots,x_n)$, 除非上下文使得这与单点集 $\{a\}$ 产生歧义. 

回忆 $n$ 元有序组的性质：$(x_1,x_2,\cdots,x_n)=(y_1,y_2,\cdots,y_n)\iff x_k=y_k(k=1,2,\cdots,n)$. 

再一次, 回顾一下序列的概念. 

一般地, $X$ 上的无穷序列指的是一个映射

$$
x\colon \mathbb N_+ \to X, n\mapsto x_n
$$

记作 $(x_n)_{n\in \mathbb N_+}$, 也可简记作 $(x_n)$. 强调其中的项时可以记作 $(x_1,x_2,\cdots)$, 不在意项的顺序而只在意值域时, 记 $\mathrm{ran}(x)=:\{x_n)$. 

> $\{x_n\}$ 是中学阶段常用的, 代表数列的记号. 

而有限序列则是定义域形如 $\{1,2,\cdots,n)(n\in\mathbb N_+)$ 的映射

$$
x\colon \mathbb \{1,2,\cdots,n) \to X, k\mapsto x_k
$$

下引入一个重要的定义. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义</strong>

设 $X,Y$ 为两个非空集合, 则记号 $X^Y$ 表示全体以 $X$ 为定义域而以 $Y$ 为陪域的函数构成的集合, 即

$$
X^Y:=\{f\in \mathcal P(X\times Y) \mid \forall x\in X \exists ! y\in Y (y=f(x))\}
$$

</blockquote>

我们很容易举出例子, 例如 $C([0,1];\mathbb R) \subseteq \mathbb R^{[0,1]}$；全体实数列的集合为 $\mathbb R^{\mathbb N_+}$. 

在《数学分析笔记》的位置记数法一节中, 我们还证明了, 对任何的 $q\in\mathbb N_{\ge 2}$, 集合 $\{1,2,\cdots,q\}^{\mathbb N}$ 与自然数集的幂集 $\mathcal P(\mathbb N)$ 等势, 又与实数集 $\mathbb R$ 等势. 不过, 当时并没有指出将 $\mathbb N$ 作为上标的具体含义. 

利用这个记号, 我们还能看清为什么幂集 $\mathcal P(X)$ 能够写作 $2^X$. 无穷公理给出的自然数模型认为 $2=\{0,1\}$, 这样 $2^X$ 就是全体以 $X$ 为定义域而以 $\{0,1\}$ 为值域的函数构成的集合, 这样的函数显然为 $X$ 中的每一个元素选择了一个值——要么 $0$, 要么 $1$. 那么, 任何的 $f\in 2^X$ 不就正好对应于一个子集 $\{x\in X\mid f(x)=1\}$ 吗？那么, 考虑映射

$$
g\colon 2^X\to \mathcal P(X), f\mapsto g(f):=\{x\in X\mid f(x)=1\}
$$

请自行验证, 它是双射. 

同时, 这个记号与直积集的记号并不冲突. 设 $n\in\mathbb N_+$, 请解释为什么 $n$ 个 $X$ 的直积能写作 $X^n=X^{\{0,1,\cdots,n-1\}}$. 

今后, 我们也将 $X$ 上的一个 $n$ 元有序组视作 $\{0,1,\cdots,n-1\}$（或 $\{1,2,\cdots,n)$）到 $X$ 的一个映射, 即一个有限序列. 

<排列, 组合>

<数域>

> 如无特别声明, 本笔记用 $K$ 代表数域, 而用 $\mathbb F$ 代表一般的域. 

</blockquote>

## 线性方程组

经典代数学有两大课题：一元高次代数方程, 与多元一次代数方程组. 一元方程又叫作线性方程, 故后者也叫作线性方程组. 如今, 代数学的两门基础课程：抽象代数与线性代数, 则分别建立在对此二者的研究上. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(线性方程组)</strong>

数域 $K$ 上的**线性方程组**是具有如下形式的方程组：

$$\left\{\begin{matrix}
 a_{11}x_1+a_{12}x_2+\cdots+a_{1n}x_n=b_1 &\\
 a_{21}x_1+a_{22}x_2+\cdots+a_{2n}x_n=b_2 &\\
 \cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot& \\
 a_{m1}x_1+a_{m2}x_2+\cdots+a_{mn}x_n=b_n &
\end{matrix}\right.$$

其中 $a_{ij},b_j\in K$. 当 $b_j=0$ 时称作**齐次线性方程组**，否则称作**非齐次线性方程组**. 

$\,$

该方程组的解 $(x_1,x_2,\cdots,x_n)\in K^n$ 称作它的**解向量**, 而矩阵 $A=[a_{ij}]$ 称作它的**系数矩阵**. 

</blockquote>

除非另外声明, 对于变元个数 $n$ 和方程个数 $m$ 不加任何限制, 仅要求它们是正整数. 

有关任何方程的课题都包含着：

- 方程于何条件下有解？有解时，又有多少解？
- 方程有解时，如何求其解？

对于第一个问题，即[线性方程组的理论课题](#线性方程组的理论课题)，我们放到后面去讨论；对于第二个问题，我们可以作一番说道. 值得指出的是，对于一类方程，不了解完满的理论课题并不妨碍我们求解之，线性方程组更是尤甚. 

自然，每种方程都有适于求解之特例. 故解方程的思路之一是采取消元法——在不破坏原方程解集结构, 亦即不增解、不漏解, 的情形下，不断地对原方程作简化，希图将之化为一类可直接求解的形式. 本章介绍的是解线性方程组的经典方法——Gauss-Jordan 消元法。

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(同解)</strong>

若方程 $(1)$ 与方程 $(2)$ 具有相等的解集. 

</blockquote>

以下三种对线性方程组作的变换称作初等变换：

- （对换变换）将第 $i,j$ 个方程交换位置；
- （倍乘变换）将第 $i$ 个方程乘 $k\in K^*$ 倍；
- （倍加变换）将第 $i$ 个方程乘以 $k\in K$ 倍的结果加到第 $j$ 个方程上去. 

<采取消元法解一方程组之例>

**例** 解线性方程组：

$$\left\{\begin{alignat*}{3}
    x_1 &+ 3x_2 &&+ x_3 &&= 2\\
    3x_1 &+ 4x_2 &&+ 2x_3 &&= 9\\
    -x_1 &-5x_2 &&+ 4x_3 &&= 10\\
    2x_1 &+ 7x_2 &&+ x_3 &&= 1\\
\end{alignat*}\right.$$

对上述方程组消元. 

经过上述变换，我们已得到了一个“阶梯形”的线性方程组. 此方程组的最下端是一个一元一次方程，直接解得 $x_3=2$. 接着，将 $x_3=2$ 代入，又解出 $x_2$，最后解出 $x_1$. 即通过回代法求解. 

除了回代的方法，我们还能直接把其余变量都消去，得到三个一元一次方程，直接写出三个解. 

注意到上述过程中变量并未参与实际的运算——即，只要维持各列的位置不变，令系数参与运算，也可解完方程. 因此，接下来我们抛弃线性方程的形式，仅在增广矩阵上操作. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(矩阵的初等行变换)</strong>

设 $A\in M_{m\times n} (K)$, 则下述三种变换称作矩阵 $A$ 的**初等行变换**：

- （交换变换）交换 $A$ 的 $i,j$ 两行；
- （倍乘变换）将 $A$ 的第 $i$ 行变为 $k$ 倍, 其中 $k\in K^*$；
- （倍加变换）将 $A$ 的第 $i$ 行加上第 $j$ 行的 $k$ 倍, 其中 $k\in K$. 

</blockquote>

前已讨论过，对增广矩阵作初等行变换，得到同解的线性方程组. 

结合上述求解过程，我们抽象出一个定义. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(行阶梯形矩阵)</strong>

称 $A\in M_{m\times n} (K)$ 是一个**行阶梯形矩阵**，若：

- $A$ 若有全为零的行（称作**零行**）, 则位于全部非零行的下方. 
- $A$ 的非零行从左至右第一个非零元（称作**主元**）的列指标随行指标增大而严格增大. 

换言之，行阶梯形矩阵是具有以下形式的矩阵：

$$\begin{bmatrix}
& & & \bullet &* &* & \cdots &* &* & \cdots &* &*& \cdots &*&*&\cdots&*\\
& & & & & & & \bullet &* & \cdots &* &*& \cdots &*&*&\cdots&*\\
& & & & & & & & & & & \bullet& \cdots &*&*&\cdots&*\\
& & & & & & & & & & & &\ddots &\vdots &\vdots & &\vdots\\
& & & & & & & & & & & & & \bullet &*&\cdots&*\\
& & & & & & & & & & & & & & & &\\
& & & & & & & & & & & & & & & &\\
\end{bmatrix}$$

其中 $\bullet$ 表示主元（不为零），$*$ 表示任意的元（可能为零），空白部分则全部是 $0$. 

</blockquote>

### 习题

【1】求解线性方程组

$$\left[
\begin{array}{c:c}
\begin{matrix}
 1+a_1 & 1 & \cdots & 1 \\
 1 & 1+a_2 & \cdots & 1 \\
 \vdots & \vdots & & \vdots \\
 1 & 1 & \cdots & 1+a_n \\
\end{matrix}&
\begin{matrix}
b_1\\
b_2 \\
\vdots\\
b_n
\end{matrix}
\end{array}
\right ]$$

【2】求解下述增广矩阵对应的线性方程组

$$\left [
\begin{array}{c:c}
\begin{matrix}
 1 & 2 & \cdots & n-1 & n \\
 n & 1 & \cdots & n-2 & n-1 \\
 \vdots & \vdots & & & \vdots \\
 2 & 3 & \cdots & n & 1 \\
\end{matrix}&
\begin{matrix}
b_1\\
b_2 \\
\vdots\\
b_n
\end{matrix}
\end{array}
\right ]$$


# 线性空间与线性映射

## 线性空间

### 线性空间的定义及其最基本例子

有必要先行介绍线性空间的概念. 在有些人看来, 这不过是一些麻烦的记号. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(线性空间)</strong>

设 $V$ 为一个集合, $\mathbb F$ 为一个域. 若 $V$ 上定义了一种运算 $+_V$ 使得 $(V,+_V)$ 为交换群, 并有映射

$$
\cdot_V\colon K\times V \to V, (k,v)\mapsto k\cdot_V v
$$

满足如下四条性质：

- （不知道起啥名儿）$$1_{\mathbb F}\cdot_V v = v, \forall v\in V;$$ 
- （“结合律”）$$(kl)v =k(lv), \forall k,l\in {\mathbb F}\forall v \in V;$$ 
- （“分配律Ⅰ”）$$(k+l)v =kv+lv, \forall k,l\in {\mathbb F}\forall v \in V;$$
- （“分配律Ⅱ”）$$k(v+\beta) =kv+k\beta, \forall k\in {\mathbb F}\forall v,\beta \in V.$$

则称 $(V,+_V,\cdot_V)$ 为域 ${\mathbb F}$ 上的一个**线性空间**或**向量空间**, 并称域 ${\mathbb F}$ 为线性空间 $V$ 的**基域**. 称 $V$ 中的元素为**向量**(vector), 而称 ${\mathbb F}$ 中的元素为**标量**(scalar). 

$\,$

今后, 在不引起歧义的情况下, 我们简记 $+_V$ 为 $+$, 并称这种运算为**加法**；简记 $\cdot_V$ 为 $\cdot$, 并称这种“运算”为**标量乘法**. 

</blockquote>

> 当基域 $\mathbb F$ 是一个数域时, 可以简称标量乘法为**数乘**. 如无特别说明, 本笔记仅研究数域上的线性空间实例. 

若域 $\mathbb F$ 上的线性空间 $(V,+,\cdot)$ 的加法运算、数乘甚至基域 $\mathbb F$ 都为我们所熟悉, 则可简记 $(V,+,\cdot)$ 为 $V$. 另外, 不难看到, 线性空间 $V$ 要么是无限集, 要么仅以加法零元（称之为**零向量**）为其唯一的元素, 对于后者, 我们称之为**零维空间**. 

> 一般用希腊字母 $\alpha,\beta,\gamma,\cdots$ 表示向量. ~~但我就不用~~但 $\LaTeX$ 输入希腊字母挺烦的. 

线性空间的定义是高度抽象、公理化的, 下给出一个线性空间的重要实例——$\mathbb F^n$. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题</strong>

设 $(\mathbb F,+,\cdot)$ 为一个域, 而 $n\in\mathbb N_{\ge 2}$, 在集合 $\mathbb F^n:=\underbrace{\mathbb F\times \mathbb F\times \cdots \times \mathbb F}_{n个\mathbb F}$ 上定义加法与标量乘法如下

$$
+\colon\mathbb F^n\times \mathbb F^n\to \mathbb F^n,(\begin{bmatrix}
a_1\\a_2\\\vdots\\ a_n
\end{bmatrix},
\begin{bmatrix}
b_1\\b_2\\\vdots\\ b_n
\end{bmatrix}
)\mapsto\begin{bmatrix}
a_1\\a_2\\\vdots\\ a_n
\end{bmatrix}+
\begin{bmatrix}
b_1\\b_2\\\vdots\\ b_n\end{bmatrix}:=
\begin{bmatrix}
a_1+b_1\\a_2+b_2\\\vdots\\ a_n+b_n
\end{bmatrix}
$$

$$
\cdot\colon\mathbb F\times \mathbb F^n\to \mathbb F^n,(k,
\begin{bmatrix}
a_1\\a_2\\\vdots\\ a_n
\end{bmatrix}
)\mapsto k\cdot
\begin{bmatrix}
b_1\\b_2\\\vdots\\ b_n
\end{bmatrix}:=
\begin{bmatrix}
ka_1\\ka_2\\\vdots\\ ka_n
\end{bmatrix}. 
$$

</blockquote>

请读者自行验证, $\mathbb F^n$ 空间连同其上的加法运算和数乘构成 $\mathbb F$ 上的一个线性空间. 

线性空间 $\mathbb F^n$ 因基域 $\mathbb F$ 的选取而具有各种性质, 我们最为熟悉的就是 $\mathbb F=\mathbb R$ 的情形. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(Euclid 空间)</strong>

在上述命题中取 $\mathbb F=\mathbb R$, 所得的线性空间 $\mathbb R^n$ 称作 Euclid 空间. 

</blockquote>

> 一般而言，Euclid 空间指配备了内积的 $\mathbb R^n$，不过我觉得这样叫挺顺口的（）

事实上, 线性空间的概念就源于 Euclid 空间概念的抽象. 

<details class="custom-details">
    <summary class="custom-summary">一些其他线性空间的例子</summary>

（1）考察自然数 $0$ 构成的单点集 $\{0\}$. 定义其上的加法为数之间的加法, 而数乘为数之间的乘法, 则 $\{0\}$ 是任意数域 $K$ 上的零维空间. 

（2）设 $K$ 是一个数域, 考察 $K^X$. 其上的加法和数乘按如下定义（下设 $f,g\in K^X,k\in K$）

$$
f+g\colon X\to K, x\mapsto (f+g)(x):=f(x)+g(x)
$$

$$
k\cdot f\colon X\to K, x\mapsto (k\cdot f)(x):=k\cdot f(x)
$$

则 $K^X$ 是 $K$ 上的线性空间. 

（3）考察（2）的一个实例, 如 $[0,1]$ 上的全体实值函数 $\mathbb R^{[0,1]}$. 

</details>

正如我们倾向研究集合的子集, 引入线性空间的子空间的概念也是有必要的. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(子空间)</strong>

设 $(V,+,\cdot)$ 为域 $\mathbb F$ 上的一个线性空间, 若 $W\subseteq V$ 满足

- （对 $V$ 的加法封闭）$u+v\in W,\forall u,v\in V $; 
- （对 $V$ 的乘法封闭）$k\cdot v\in W, \forall v\in V \forall k\in \mathbb F $. 

则称 $W$ 为 $V$ 的一**线性子空间**. 

</blockquote>

> 按上述定义, $(W,+_W,\cdot_W)$ 也构成线性空间, 其中 $+_w$ 是 $V$ 的加法在 $W\times W$ 上的限制，标量乘法同理. 

在 $\mathbb R$ 上, Riemann 可积函数类 $\mathcal R[a,b]$ 是 $\mathbb R^{[a,b]}$ 的子空间, 而连续函数类 $C[a,b]$ 是 $\mathcal R[a,b]$ 的子空间. 

### 秩与维数

#### Part A: 向量组的线性组合与张成空间

线性空间的元素是向量, 为研究线性空间的一般性质, 自然须从向量入手. 

我们先给出一些定义. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(基本概念)</strong>

设 $V$ 为域 $\mathbb F$ 上的一个非零维线性空间, $n\in\mathbb N_+$, 则

- 称 $V^n$ 中的一个 $n$ 元有序组 $L_n:=(v_1,v_2,\cdots,v_n)$ 为 $V$ 中的一个**向量组**或一组向量(a list of vectors)；
- 设 $(k_1,k_2,\cdots,k_n)\in \mathbb F^n$, 则称向量 $$\displaystyle \sum_{i=1}^n k_iv_i=k_1v_1+k_2v_2+\cdots+k_nL_n$$ 为向量组 $L_n$ 的一个**线性组合**；
- 设 $\beta\in V$, 若存在 $k_1,k_2,\cdots,k_s\in \mathbb F$ 使得 $$u=\sum_{i=1}^n k_iv_i=k_1v_1+k_2v_2+\cdots+k_iv_i$$ 则称向量 $u$ 可被向量组 $v_i$ **线性表示**. 

</blockquote>

> 必须说明的是, 一般认为向量组是有序组. 然而, 有时我们又不太关心它的顺序, 比如考察线性表示时, 因为向量加法可交换. 

先前, 我们认为 $\varnothing$ 是长度为 $0$ 的组, 因此 $\varnothing$ 可以是拥有 $0$ 个向量的向量组, 这是为了叙述的方便. 

不难注意到，给定 $V$ 中一组向量，则全体可被这组向量线性表示的集合应对 $V$ 的加法和乘法均封闭. 因此，得到了一组向量，实质上就得到了 $V$ 的一个子空间. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(张成空间)</strong>

设 $V$ 为域 $\mathbb F$ 上的一个非零维线性空间, 给定其中的一个向量组 $L_n:=(v_1,v_2,\cdots,v_n)$, 则

$$
\{k_1v_1+k_2v_2+\cdots+k_nL_n \in V\mid k_1,k_2,\cdots,k_n\in K\}
$$

是 $V$ 的线性子空间, 称为向量组 $L_n$ **张成的空间**, 记作 $\mathrm{span}(L_n)$, 并称 $L_n$ **张成**了 $\mathrm{span}(L_n)$. 

</blockquote>

$\mathrm{span}(L_n)$ 是 $V$ 的子空间. 

#### Part B: 向量组的线性相关与线性无关

设 $V$ 为域 $\mathbb F$ 上的一个非零维线性空间, 而 $L_n=(v_1,v_2,\cdots,v_n) \in V^n$ 为 $V$ 中的一组向量, 考虑某 $u \in \mathrm{span}(L_n)$．根据张成空间的定义, 存在 $(k_1,k_2,\cdots,k_n)\in \mathbb F^n$, 使得 $u=k_1v_1+k_2v_2+\cdots+k_nL_n$. 

那么, 上式中系数 $(k_1,k_2,\cdots,k_n)\in\mathbb F^n$ 的选取是否唯一？表示法的唯一性是否与 $u$ 有关？

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(线性相关与线性无关)</strong>

设 $V$ 为域 $\mathbb F$ 上的一个非零维线性空间, 给定其中的一个向量组 $(v_1,v_2,\cdots,v_n)$, 存在 $0_\mathbb F\ne (k_1,k_2,\cdots,k_n)\in\mathbb F_n$ 使得

$$k_1v_1+k_2v_2+\cdots+k_nL_n=0_V$$

则称该向量组是**线性相关**(linear dependent)的, 否则, 称该向量组是**线性无关**的. 

</blockquote>

不难利用上述定义回答最开始的问题. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">推论</strong>

设 $V$ 为域 $\mathbb F$ 上的一个非零维线性空间, 给定其中的一个向量组 $L_n:=(v_1,v_2,\cdots,v_n)$, 任取 $u \in \mathrm{span}(L_n)$, 则 $u$ 有唯一表示法的充分必要条件是 $L_n$ 线性无关. 

</blockquote>

<details class="custom-details">
    <summary class="custom-summary">证明</summary>

必要性：任取向量组 $L_n$, 总有 $0_V\in \mathrm{span}(L_n)$, 故 $0_V$ 有唯一表示法. 又因系数全取 $0_\mathbb F$ 自然是表示法, 故它是唯一的, 从而 $L_n$ 线性无关. 

充分性：当 $L_n$ 线性无关时，设 $\beta\in\mathrm{span}(L_n)$ 有两种表示法（$r=1,2$）

$$
\beta= \sum_{i=1}^n k_i^{(r)}v_i
$$

作差即得

$$
0_V= \sum_{i=1}^n (k_i^{(2)}-k_i^{(1)})v_i
$$

所以 $k_i^{(1)}=k_i^{(2)}$. 

</details>

线性相关与线性无关是线性代数中最基本的概念之一. 我们可以从多种角度来考察线性无关向量组与线性相关向量组的本质区别：

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(线性相关与线性无关的基本性质Ⅰ)</strong>

设 $V$ 为域 $\mathbb F$ 上的一个非零维线性空间, 给定其中的一个向量组 $L_n:=(v_1,v_2,\cdots,v_n)$, 则

- 从线性组合的观点看：$L_n$ 线性相关 $\iff$ 存在非零 $(k_1,k_2,\cdots,k_n)\in\mathbb F^n$ 使得 $k_1v_1+k_2v_2+\cdots+k_nL_n=0_V$. 

- 从线性表示的观点看：
     - $n=1$ 时：$L_1=(v_1)$ 线性相关 $ \iff v_1=0_V$; 
     - $n\ge 2$ 时：$L_n$ 线性相关 $\iff$ 存在向量 $v_k$ 能被 $(v_1,v_2,\cdots,v_{k-1})$ 线性表示；
此结果有时又称作**线性相关性引理**. 

- 从张成空间的观点看：$L_n$ 线性无关 $\iff$ $\mathrm{span}(L_n)$ 中任一向量都有唯一的表示法；

- 从与部分组的观点看：$L_n$ 线性无关 $\iff$ $L_n$ 的任一部分组都线性无关. 

</blockquote>

> 由于线性相关与线性无关互为否命题，我们只取容易叙述的一边，另一边的性质只需两边取否即可. 

<details class="custom-details">
    <summary class="custom-summary">证明</summary>

**证明1** 这就是线性无关的定义. 

**证明2** 我们已经证过了. 

**证明3** 考虑线性无关的定义, 存在一非零向量 $(k_1,k_2,\cdots,k_n)\in K^n$ 使得

$$
\sum_{i=1}^n k_iv_i=\textbf 0
$$

那么, 若 $k_n\ne 0$, 则 $L_n$ 即为所求. 若 $k_n=0$, 考察 $k_{n-1}$, 若 $k_{n-1}\ne 0$, 则 $v_{n-1}$ 即为所求……如此重复, 由于 $n$ 为有限数, 这样的重复操作必能完成, 这组数又不全为 $0$, 知原命题成立. 

**证明4** 易. 

</details>

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(线性相关与线性无关的基本性质Ⅱ)</strong>

在上述命题中取 $V=\mathbb F^m$，并记 $v_i:=(a_{1i},a_{2i},\cdots a_{mi})$ 我们还有

- 从线性方程组的观点看，若 $\mathbb F$ 是数域，则 $L_n$ 线性无关 $\iff$ 齐次线性方程组 $$\displaystyle \left\{\begin{matrix}
 a_{11}x_1+a_{12}x_2+\cdots+a_{1n}x_n=0 &\\
 a_{21}x_1+a_{22}x_2+\cdots+a_{2n}x_n=0 &\\
 \cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot& \\
 a_{m1}x_1+a_{m2}x_2+\cdots+a_{mn}x_n=0 &
\end{matrix}\right.$$ 只有零解. 

- 从分量的关系看, 线性无关 $\iff$ 任一截断分量或延伸分量线性无关；线性相关 $\iff$ 任一截断分量或延伸分量线性相关. 

- 从？的观点看，若 $L_n$ 线性无关, 而 $\beta\in V$, 则 $(L_n,\beta)$ 线性无关的充分必要条件是 $\beta$ 不能被 $L_n$ 线性表示. 

</blockquote>

> 注意 $(L_n,\beta)$ 等于 $n+1$ 元有序组 $(v_1,v_2,\cdots,L_n,\beta)$. 

下面这个线性无关向量组的例子是重要的, 稍后我们会诠释它名称的含义. 

**例** 设 $\mathbb F$ 为一个域, 给定 $\mathbb F^n$ 中的 $n$ 个向量：

$$
\begin{aligned}
    \varepsilon_1&:=(1,0,0,\cdots,0,0) \\
    \varepsilon_2&:=(0,1,0,\cdots,0,0) \\
    &\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\\
    \varepsilon_n&:=(0,0,0,\cdots,0,1) \\
\end{aligned}
$$

称这组向量 $(\varepsilon_1,\varepsilon_2,\cdots,\varepsilon_n)$ 为线性空间 $\mathbb F^n$ 的**标准基**, 它们构成的向量组线性无关. 

#### Part C: 线性等价与向量组的秩

我们看到, 根据线性相关引理, 一个线性相关的向量组必有某个向量可被其前面的向量线性表示. 因此, 在某种程度上, 这个向量是“多余”的, 我们自然想要将其“去掉”. 为严格地表达这种想法, 下引入一些概念. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(线性等价)</strong>

设 $V$ 为域 $\mathbb F$ 上的一个线性空间, 而 $L_n:=(v_1,v_2,\cdots,v_n)$ 与 $G_m:=(w_1,w_2,\cdots,w_m)$ 是其中的两组向量. 若 $L_n$ 的任何向量都能被 $G_m$ 线性表示, 且 $G_m$ 的任何向量也都能被 $L_n$ 线性表示, 则称这两个向量组是**线性等价**的, 记作 $L_n\sim G_m$. 

</blockquote>

**例** 向量组 $(v)$ 与 $(v,2v,3v,1145141919810v)$ 是线性等价的. 任意向量组和自身的任一个全排列是线性等价的. 

值得指出的是, 采用线性“等价”一词是合适的, 因为线性等价也满足自反性, 对称性与传递性, 证明留作练习. 

下给出本小节的主要概念. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(极大线性无关部分组)</strong>

设 $V$ 为域 $\mathbb F$ 上的一个线性空间, 给定其中的一个向量组 $L_n:=(v_1,v_2,\cdots,v_n)$, 如果它与自身的一个线性无关的部分组

$$L_r:=(v_{i_1},v_{i_2},\cdots,v_{i_r})(1\le i_1\le i_2\le\cdots \le i_r\le s)$$

线性等价, 则称向量组 $L_r$ 为向量组 $L_n$ 的**极大线性无关部分组**. 

</blockquote>

由这个概念的名字可以看到, “部分”说明 $\{L_r\}\subseteq\{L_n\}$, “线性无关”说明 $L_r$ 是线性无关的, 而“极大”说明不可能再将某一个 $\{L_n\}$ 中的元素加入 $L_r$ 中却不破坏其线性无关性, 因为新加入的元素必然能被 $L_r$ 线性表示. 

自然, 我们关心所谓的“极大线性无关部分组”是否对所有的向量组均存在？因此, 有如下被称为**筛选法**的命题. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(筛选法)</strong>

设 $V$ 为域 $\mathbb F$ 上的一个线性空间, 给定其中的一个非零向量组 $L_n:=(v_1,v_2,\cdots,v_n)$，置 $G_{k}:=(v_k)$, 其中 $v_k$ 是 $L_n$ 中第一个不为 $\textbf 0$ 的向量. 我们进行如下筛选：令 $r$ 依次取值为 $k+1,\cdots,n$

- 若 $(G_{r-1},v_r)$ 线性无关, 令 $G_r:=(G_{r-1},v_r)$；
- 否则, 令 $G_r:=G_{r-1}$. 

则 $G_n$ 就是 $L_b$ 的一个极大线性无关部分组. 

</blockquote>

<details class="custom-details">
    <summary class="custom-summary">证明</summary>

由定义易见 $A_s\ne \varnothing$ 当且仅当 $L_n$ 不为零向量组. 这时, $A_1,A_2,\cdots,A_s$ 均是线性无关的, 现只要证 $A_s$ 与 $L_n$ 线性等价, 又因为 $A_s\subseteq L_n$, 只要证 $L_n$ 中的每个向量都能被 $A_s$ 线性表示. 

事实上, 对 $v_r\in L_n(r=2,3,\cdots,s)$, 有

- 若 $v_r\in A_s$, 其显然可被 $A_s$ 线性表示；
- 若 $v_r\notin A_s$, 根据定义, 这是因为 $A_{r-1}\cup (v_r\}$ 线性相关, 故 $v_r$ 可被 $A_{r-1}\subseteq A_s$ 线性表示. 

对 $v_1$, $v_1\notin A_s$ 当且仅当它为零向量, 零向量自然可被 $A_s$ 线性表示. <p align="right" > $\square$ </p>

</details>

筛选法向我们保证了, 除了零向量组, 任何向量组都有极大线性无关部分组, 这个方法也可以用于求极大线性无关部分组~~不过不怎么推荐，要解一堆方程~~. 

另外, 特别规定 $()$ 线性无关, 即 $()$ 是零向量组的极大线性无关部分组. 

**使用例** 给定向量组 $(v_1,v_2,v_3,v_4,v_5)$, 其中

$$
\begin{aligned}
    &v_1=(1,0,0), & & v_1=(0,1,0), \\
    &v_3=(0,0,1), & & v_4=(1,1,1), \\
    &v_5=(1,1,0),
\end{aligned}
$$

我们发现, $(v_1,v_2,v_3)$ 是它的极大线性无关部分组, 但 $(v_1,v_3,v_4)$ 也是它的极大线性无关部分组. 

可见, 一个向量组的极大线性无关部分组并不是唯一的. 这不免令我们担心：同一个向量组的不同极大线性无关部分组, 它们的长度是否相等呢？下通过证明几个命题来给出肯定的答复. ~~如果相等，那“极大”这个名字就可以改为“最大”了, 所以不这样命名的原因难道是防止剧透？~~

先证明一个著名的引理——替换引理, 这是一个在线性代数中非常重要的定理. 

<blockquote class="quote-style-2"><strong style="color: #28a745;">定理(替换引理, Steinitz)</strong>

设 $V$ 为数域 $K$ 上的一个非零维线性空间, 给定其中的两个向量组 $L_n:=(v_1,v_2,\cdots,v_n)$ 与 $G_m:=(w_1,w_2,\cdots,w_m)$. 若 $L_n$ 线性无关, 且 $v_1,v_2,\cdots,L_n$ 均能被 $G_m$ 线性表示, 则

- $n\le m$. 特别地, $n=m$ 是 $G_m$ 线性无关的充分不必要条件；
- 存在 $G_m$ 中的 $s$ 个向量 $w_{i_1},w_{i_2},\cdots,w_{i_s}$ 使得它们被替换为 $v_1,v_2,\cdots,v_s$ 后得到的新组 $G_m'$ 与 $G_m$ 线性等价. 

</blockquote>

<details class="custom-details">
    <summary class="custom-summary">证明</summary>

**证明1** 考虑反证法, 不妨设 $n>m$, 往证 $L_n$ 线性相关, 从而推出矛盾. 

要证 $L_n$ 线性相关, 只要证向量方程

$$
\sum_{j=1}^n x_jv_j=x_1v_1+x_2v_2+\cdots+x_nL_n=\textbf 0
$$

有非零解. 

既然 $L_n$ 中的每个向量都能被 $G_m$ 线性表示, 那不妨设

$$v_k=\sum_{i=1}^m a_{ik}w_i,\qquad k=1,2,\cdots,n$$

代入上述向量方程有

$$
\sum_{j=1}^n x_jv_j=\sum_{j=1}^n x_i\sum_{i=1}^m a_{ij}w_i=\textbf 0
$$

根据有限次求和的可交换性, 按照 $w_1,w_2,\cdots,G_m$ 合并同类项即得

$$
\sum_{i=1}^m \sum_{j=1}^n a_{ij}x_iw_i=\textbf 0
$$

注意到，不难举出 $G_m$ 线性无关而符合题设的例子，因此, 试令 $w_i$ 的系数 $\displaystyle \sum_{j=1}^n a_{ij}x_j$ 全为 $0$, 即

$$\left\{\begin{matrix}
\displaystyle\sum_{j=1}^n a_{1j}x_j=a_{11}x_1+a_{12}x_2+\cdots+a_{1n}x_s=0 &\\
\displaystyle\sum_{j=1}^n a_{2j}x_i=a_{21}x_1+a_{22}x_2+\cdots+a_{2n}x_s=0 &\\
\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot& \\
\displaystyle\sum_{j=1}^n a_{mj}x_j=a_{m1}x_1+a_{m2}x_2+\cdots+a_{mn}x_n=0 &
\end{matrix}\right.$$

这是一个有 $n$ 个未知量而有 $m$ 个方程的齐次线性方程组，由 $n>m$, 其必有非零解. 

从而, 存在一组不全为 $0$ 的数令上式 $w_1,w_2,\cdots,G_m$ 的系数全为 $0$, 故原向量方程

$$
\sum_{j=1}^n x_jv_j=x_1v_1+x_2v_2+\cdots+x_n L_n=\textbf 0
$$

确有非零解, 于是 $L_n$ 线性相关, 矛盾！

命题的后半部分是容易的. 

先证 $n=m$ 蕴含 $G_m$ 线性无关. 

设 $G_m$ 的某个极大线性无关部分组的元素数量为 $m'$, 则 $m'\le m = n$, 又易见该极大线性无关部分组也能线性表示 $L_n$ 的所有元素, 根据既证的一半命题，又有 $n\le m'$, 故 $m'=n=m$, 即 $G_m$ 就是自身的一个极大线性无关部分组, 得证. 

再证 $G_m$ 线性无关并不蕴含 $n=m$, 容易举出反例, 取 $\mathbb F=\mathbb R,V=\mathbb R^2$ 时, 令

$$
L_n:=\{(0,1)\},\quad G_m:=\{(0,1),(1,0)\}
$$

显然这时 $n<m$. <p align="right" > $\square$ </p>

**证明3** 不妨设 $t\in\mathbb N_{\ge 2}$（否则 $s=t=1$ 显然成立）, 再设 $L_n$ 与 $G_m$ 中不存在相等的向量, 即 $L_n\cap G_m=\varnothing$. 

考虑对 $s=1,2,\cdots,t$ 进行归纳. 

先设 $s=1$, 此时将 $L_n$ 中的唯一一个元素 $v_1$ 放入 $G_m$ 中, 得到新向量组 $G_m\sqcup (v_1\}$, 又根据题设, $v_1$ 能被 $G_m$ 线性表示

$$
v_1 =\sum_{i=1}^t k_i\beta_i= k_1\beta_1+k_2\beta_2+\cdots+k_t\beta_t
$$

从而易见 $G_m\sqcup (v_1\} \sim G_m$. 

又因为 $L_n$ 线性无关, 则 $v_1\ne \textbf 0$, 故上式中的 $k_1,k_2,\cdots,k_n$ 不全为 $0$. 不妨记某一不为 $0$ 的项为 $k_j\beta_j$, 于是

$$
\beta_j = \frac {1}{k_j}v_1+\sum_{\substack{i=1 \\ i\ne j}}^n -\frac {k_i}{k_j}\beta_i 
$$

故只需取 $G_m':=(G_m\sqcup L_n)\backslash \{\beta\}$, $G_m'\sim G_m\sqcup L_n$, 由线性等价的传递性知 $G_m'\sim G_m$. 

下证若 $s\in \{1,2,\cdots,t-1\}$ 时原命题成立, 则对于 $s+1$ 原命题也成立. 

换言之, 对于 $V_{s+1}=(v_1,v_2,\cdots,v_{s+1}\}$ 的前 $s$ 个向量, 我们既已找到可被“替换”的 $s$ 个向量 ${\beta_1,\beta_2,\cdots,\beta_s \in G_m}$ 使得集合

$$
W:=(v_1,v_2,\cdots,v_{s},\beta_{s+1},\cdots,\beta_t\}
$$

与 $G_m$ 线性等价. 那么, 再将 $v_{s+1}$ 加入上述集合, 则新集合

$$
W\sqcup(v_{s+1}\}=(v_1,v_2,\cdots,v_{s},v_{s+1},\beta_{s+1},\cdots,\beta_t\}
$$

必是线性相关的. 否则, 它拥有 $t+1>t$ 个元素, 其中的每一个元素却都可以被 $W$ 线性表示, 这与 (1) 的结论矛盾！

则存在 $t+1$ 个数 $k_1',k_2',\cdots,k_{t+1}'$ 使得

$$
\sum_{r=1}^{s+1}k_r'v_r+\sum_{r=s+1}^{t}k_{r+1}'\beta_r=\textbf 0
$$

同样因为 $V_{s+1}$ 线性无关, 故 $t-s$ 个系数 $k_{s+2}',\cdots,k_{t+1}'$ 不全为 $0$, 同理, $W\sqcup (v_{s+1}\}$ 中也存在一个 $\beta'\in G_m$ 能够被集合 $W\sqcup (v_{s+1}\}$ 中的其他 $t$ 个元素线性表示. 

只需取 $G_m':=(W\sqcup (v_{s+1}\})\backslash \{\beta'\}$ 即证. 

综上, 当 $L_n\cap G_m=\varnothing$ 时原命题成立. 

特别地, 当 $T:=L_n\cap G_m\ne\varnothing$ 时, 只需取 $L_n\backslash T$ 与 $G_m\backslash T$ 两个不交的集合, 按照原命题进行替换得到 $(G_m\backslash T)'$, 令 $G_m':=(G_m\backslash T)'\sqcup T$ 即可. <p align="right" > $\square$ </p>

</details>

由替换引理便可得出一个重要推论. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">推论</strong>

两个相互线性等价的向量组, 它们的极大线性无关部分组长度相等. 

</blockquote>

<details class="custom-details">
    <summary class="custom-summary">证明</summary>

不妨设 $L_n$ 与 $G_m$ 为两个相互线性等价的向量组, 分别设它们的一个极大线性无关部分组为 $L_k$ 与 $G_l$, 显然 $L_k$ 与 $G_l$ 仍然线性等价, 于是

- 若 $k>l$, 由替换引理的结论（1）知 $V_k$ 线性相关, 矛盾！

- 若 $k<l$, 由替换引理的结论（1）知 $W_l$ 线性相关, 矛盾！

故只能有 $k=l$. <p align="right" > $\square$ </p>

</details>

由线性等价的自反性自然得知, 同一个向量组的不同极大线性无关部分组长度相等. 现在, 我们已经知道, 一个向量组的极大线性无关部分组是存在的, 并且其长度是唯一的, 因此可以引入以下定义. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(秩)</strong>

一个向量组的极大线性无关部分组的长度称作该向量组的**秩**(rank).

</blockquote>

显然, 零向量组的秩为 $0$；本身就线性无关的向量组的秩就是它的长度；两个相互线性等价的向量组的秩相等. 秩是线性等价下的不变量. 

本小节的最后, 给出一个看上去十分显然却非常容易令人“伪证”的命题. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(极大线性无关部分组的任意性)</strong>

设 $V$ 为数域 $K$ 上的一个非零维线性空间, $L_n$ 为 $V$ 中一个秩为 $r$ 的向量组, 则对任何 $L_n$ 的部分组 $L$, 有下述三条性质

- $L$ 线性无关；
- $L$ 的长度为 $r$；
- $L_n$ 中的任一向量都能被 $L$ 线性表示. 

若 $L$ 满足其中的任意两条, 则必满足第三条. 

</blockquote>

冰雪聪明的 Cirno 同学立刻给出了一个“证明”：

**证明** 只证 $(1)(2)\Rightarrow (3)$, 其余显然. 

反设存在一个线性无关且长度为 $r$ 的部分组 $L$ 却不能线性表示 $L_n$ 的某一个向量 $v_1$, 根据线性无关的基本性质, $(L,v_1)$ 也线性无关. 

然而 $(L,v_1)$ 的长度为 $r+1$, 这与 $L_n$ 的秩为 $r$ 矛盾！ <p align="right" > $\square$ </p>

请你指出 Cirno 的证明存在的问题, 并加以改正. 

<details class="custom-details">
    <summary class="custom-summary">“正确”的证明</summary>

$w\sqcup \{\beta\}$ 有 $r+1$ 个元素究竟如何会与 $L_n$ 的秩为 $r$ 矛盾呢？

诚然 $L_n$ 的秩为 $r$, 它的“极大线性无关部分组”只能有 $r$ 个元素, 但目前尚未说明 $w\sqcup \{\beta\}$ 就是 $L_n$ 的一个极大线性无关部分组, 从而无法造成矛盾. 

要从定义说明 $w\sqcup \{\beta\}$ 是 $L_n$ 的一个极大线性无关部分组, 只能说明 $L_n$ 的每一个元素均能被 $w\sqcup \{\beta\}$ 线性表示. 注意, 这与 Cirno 一开始想要证明的, $L_n$ 的每一个元素均能被 $w$ 线性表示是相类似的. 

所以, Cirno 的证明实质上是不完整的. 若要沿着她的思路进行证明, 则必须像这样补充下去：

注意此时已有 $r<s$, 我们记 $\beta=:\beta_1$. 

- 由 $L_n$ 的秩为 $r$, 知 $w\sqcup \{\beta_1\}$ 也不为 $L_n$ 的一个极大线性无关部分组（否则它的元素数量为 $r+1$, 矛盾）. 然而 $V\sqcup \{\beta_1\}$ 确是线性无关的, 则根据极大线性无关部分组的定义, 必存在 $\beta_2\in L_n\backslash (w\sqcup \{\beta\})$ 不能被 $V\sqcup \{\beta_1\}$ 线性表示；

- 再考察 $w\sqcup \{\beta_1,\beta_2\}$, 由 $L_n$ 的秩为 $r$, 知它也不为 $L_n$ 的一个极大线性无关部分组. 然而它也是线性无关的, 则又能找到能够加入这个集合的 $\beta_3$……

那么, 考虑 $w\sqcup \{\beta_1,\beta_2,\cdots\beta_{s-r}\}$, 这个集合已有 $r+k=s$ 个元素, 又是 $L_n$ 的子集, 这说明 $w\sqcup \{\beta_1,\beta_2,\cdots\beta_{s-r}\}=L_n$, 故整个 $L_n$ 线性无关. 但这矛盾, 因为这时 $L_n$ 自身就为其极大线性无关部分组, 但 $s>r$. 

</details>

这种证明基于 Cirno 同学的思路, 尽管它是正确的, 但不是最好的证明方式, 更为简洁直观的证明方式将会在不久后介绍. 

#### Part D: 线性空间的基与维数, 向量的坐标表示

我们知道 $\mathbb F^n$ 是线性空间的最基本例子, 而 $\mathbb F^n$ 中的向量是有序组. 习惯上, 我们称一个有序数组 $(a_1,a_2,\cdots,a_n)$ 的第 $i$ 个数 $a_i$ 为它的第 $i$ **坐标**或**分量**. 

那么, 更一般的线性空间中的向量是否也有类似的坐标表示呢？为回答这个问题, 我们须引入基的概念. ~~又来搞基了~~

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(基)</strong>

设 $V$ 为数域 $K$ 上的一个线性空间, 若 $V$ 中存在一线性无关的向量组 $(\eta_1,\eta_2,\cdots,\eta_n)$ 张成了 $V$, 则称向量组 $(\eta_1,\eta_2,\cdots,\eta_n)$ 为线性空间 $V$ 的一组**基**. 

</blockquote>

我们看到, 基是类似极大线性无关部分组的一个概念——后者能线性表示一个向量组的所有向量, 而前者能线性表示整个空间 $V$ 的所有向量. 

关于线性空间的基, 我们有如下命题. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题</strong>

设 $V$ 为数域 $K$ 上的一个线性空间, 若两向量组 $L_n:=(v_1,v_2,\cdots,v_n)$ 与 $G_m:=(w_1,w_2,\cdots,w_m)$ 均是 $V$ 的基, 则 $s=t$. 

</blockquote>

<details class="custom-details">
    <summary class="custom-summary">证明</summary>

</details>

从而, 与向量组的秩类似地, 我们可以定义线性空间的维数. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(维数)</strong>

设 $V$ 为域 $\mathbb F$ 上的一个线性空间, 若其存在一组基, 则称这组基的长度为线性空间 $V$ 的**维数**, 记作 $\dim V:=n$, 并称 $V$ 为 $\mathbb F$ 上的一个 **$n$ 维线性空间**. 

$\,$

若任取线性空间 $V$ 中的一个线性无关向量组 $L_n$, 总存在一个 $v\in V$ 不能被 $L_n$ 线性表示, 则称 $V$ 为 $\mathbb F$ 上的一个**无穷维线性空间**, 并记 $\dim V=+\infty$. 

</blockquote>

显然, $\mathbb F^n$ 作为在 $\mathbb F$ 上的线性空间, 其维数就是 $n$. 零维空间的基是空集, 自然维数是 $0$. 

值得指出的是, 线性空间的维数应当与它的基域有关. 如 $\mathbb C$ 作为 $\mathbb C$ 上的线性空间的维数是 $1$, 而作为 $\mathbb R$ 上的线性空间的维数是 $2$, 作为 $\mathbb Q$ 上的线性空间则是无穷维的. 然而, 根据上下文应当知道这个线性空间的基域, 因此它没有被包含在记号中. 

同极大线性无关部分组类似地, 有限维线性空间的基也具有任意性. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(基的任意性)</strong>

设 $V$ 为数域 $K$ 上的一个 $n$ 维线性空间（$n\in\mathbb N_+$）, 则对任何 $V$ 中的向量组 $w$, 有下述三条性质

1. $w$ 线性无关；
2. $w$ 的向量数量为 $n$；
3. $V$ 中的任一向量都能被 $w$ 线性表示. 

若 $w$ 满足其中的任意两条, 则必满足第三条. 

</blockquote>

<details class="custom-details">
    <summary class="custom-summary">证明</summary>

用替换引理. 

</details>

下面阐述所谓向量组的秩与维数的关系. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">推论</strong>

向量组的秩就是它张成空间的维数. 

</blockquote>

现在我们引入一般线性空间中向量的坐标. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(向量的坐标)</strong>

设 $V$ 为数域 $K$ 上的一个 $n(n\in\mathbb N_+)$ 维线性空间, 向量组 $L_n=(\eta_1,\eta_2,\cdots,\eta_n)$ 为 $V$ 的一组基, 则任给 $v\in V$, 存在唯一的 $(k_1,k_2,\cdots,k_n)\in K^n$ 使得

$$
v = \sum_{i=1}^n k_i\eta_i=k_1\eta_1+k_2\eta_2+k_n\eta_n
$$

则称 $(k_1,k_2,\cdots,k_n)$ 为向量 $v$ 在基 $(\eta_1,\eta_2,\cdots,\eta_n)$ 下的**坐标**, 记作 $M(v,L_n)$. 

</blockquote>

> 你可能不知道 $M(v,L_n)$ 是个什么奇奇怪怪的记号, 在矩阵一章中我们才会用到这种记号. 

自然, 对于 $\mathbb F^n$ 中的向量 $(k_1,k_2,\cdots,k_n)$, 我们常说的“坐标”就是对于标准基组 $(\varepsilon_1,\varepsilon_2,\cdots,\varepsilon_n)$ 而言的. 

引入了向量的坐标后, 我们就能证明如下重要的定理. 

<blockquote class="quote-style-2"><strong style="color: #28a745;">定理</strong>

设 $V$ 与 $V'$ 为数域 $K$ 上的两个有限维线性空间, 则 $V$ 与 $V'$ 同构当且仅当它们的维数相同. 

</blockquote>

### 子空间的和与直和

两个子空间的并是否是仍是子空间？

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(子空间的和)</strong>

设 $V$ 为数域 $K$ 上的一个线性空间, $V_1,V_2$ 为 $V$ 的子空间, 则集合

$$
V_1+V_2:=\{ v_1+v_2\in V \mid v_1\in V_1,v_2\in V_2\}
$$

称作子空间 $V_1$ 与 $V_2$ 的**和**. 

</blockquote>

从上述定义又可以看到, $V_1\cup V_2\subseteq V_1+V_2$, 从而子空间的和似乎要“大于”它们简单的并. 但必须指出, $V_1+V_2$ 又是“最小”的包含 $V_1,V_2$ 的子空间, 这里所谓最小指的是：

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(子空间的和是最小的包括它们的子空间)</strong>

设 $W$ 是 $V$ 的子空间, 又设 $V_1\subseteq W,V_2\subseteq W$, 则 $V_1+V_2\subseteq W$. 

</blockquote>

类似地, 我们也可定义多个子空间的和. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(子空间的直和)</strong>

并称 $V_1$ 与 $V_2$ **互为补空间**. 

</blockquote>

一般来说, 除了 $\{0_V\}$ 与 $V$ 本身, $V$ 的子空间之补空间不是唯一的. 

类似地, 我们也可定义多个子空间的直和. 

这里, 贸然使用 $V_1\oplus V_2\oplus \cdots \oplus L_n$ 表示 $n$ 个子空间的直和或许不是一个好决定, 这可能会让人觉得, 只要这 $n$ 个空间两两之间的和都是直和就可以了. 

<反例>

因此, 更提倡使用 $\displaystyle \bigoplus_{i=1}^n V_i$ 来表示 $n$ 个子空间的直和. 事实上. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(直和的条件)</strong>

- 必要条件
- 充要条件

</blockquote>

子空间之和维数公式. 

子空间（线性空间）与（子集）集合之对比. 

## 线性映射

目前介绍的内容已足够我们用较为传统的方法引入矩阵的秩并给出线性方程组理论课题的完满解答了，但我们并不想操之过急：矩阵的概念固然脱胎于线性方程组，但其理论价值远不止于解线性方程组而已，其蕴含的深刻观点也远不止表出线性方程组的系数而已. 

### 线性映射及其表示矩阵

#### Part A: 线性映射空间 $\mathcal L(V,W)$

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(线性映射)</strong>

设 $K$ 为一个数域, $V$ 与 $W$ 为 $K$ 上的线性空间, 若映射 $T\colon V\to W$ 满足

- （可加性）
- （齐次性/可乘性）

则称 $T$ 为一个 $V$ 到 $W$ 的**线性映射**(linear map), 并记全体 $V$ 到 $W$ 的线性映射的集合为 $\mathcal L(V,W)$. 

</blockquote>

易见, 线性映射是两个线性空间之间的同态映射, 它保持了不同空间各自的加法与数乘运算. 

<details class="custom-details">
    <summary class="custom-summary">一些线性映射的例子</summary>

（3）后向位移映射. 设

$$
T\colon \mathbb R^\mathbb N\to \mathbb R^\mathbb N,(x_1,x_2,\cdots)\mapsto (x_2,x_3,\cdots)
$$

则 $T\in\mathcal L(\mathbb R^\mathbb N)$. 

> $L(V)$ 是 $L(V,V)$ 的简写. 

</details>

下给出线性映射引理, 它是证明本章许多重要命题的工具. 

<blockquote class="quote-style-2"><strong style="color: #28a745;">定理(线性映射引理)</strong>

设 $K$ 为一个数域, $V$ 与 $W$ 为 $K$ 上的线性空间, 而 $(v_1,v_2,\cdots,v_m)$ 为 $V$ 的一组基, 则任给定 $(w_1,w_2,\cdots,w_m)\in W^m$, 都存在唯一的 $T\in\mathcal L(V,W)$ 使得

$$
T(v_k)=w_k,\forall k\in \{1,2,\cdots,m\}
$$

</blockquote>

<details class="custom-details">
    <summary class="custom-summary">证明</summary>

我们不妨直接构造符合条件的映射. 

</details>

由上述引理, 我们看到, 对于有限维线性空间 $V$, 只要确定了 $V$ 的某一组基在线性映射 $T$ 下的去向, 就唯一确定了这个线性映射. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(线性映射的空间)</strong>

设 $K$ 为一个数域, $V$ 与 $W$ 为 $K$ 上的线性空间, 则 $\mathcal L(V,W)$ 也为 $K$ 上的线性空间, 其中的加法与数乘定义如下：

$$(S+T)(x):=S(x)+T(x)$$

$$(k\cdot S)(x):= k\cdot S(x)$$

</blockquote>

我们看到, 线性映射的集合 $\mathcal L(V,W)$ 也是线性空间（然而, $W^V$ 却未必是）. 另外, 我们也不难求出 $\mathcal L(V,W)$ 的维数. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(线性映射的空间的维数公式)</strong>

设 $\mathbb F$ 为一个域, $V$ 与 $W$ 为 $\mathbb F$ 上的线性空间, 则 $\mathcal L(V,W)$ 有限维当且仅当 $V,W$ 均有限维, 且

$$\dim \mathcal L(V,W)=\dim V\dim W. $$

</blockquote>

不仅如此, 在 $\mathcal L(V,W)$ 上还能定义“乘法”. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(线性映射的乘法)</strong>

</blockquote>

> 看似是“乘法”, 其实不过是我们早就熟悉了的映射的复合. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(线性映射的运算法则)</strong>

- （乘法结合律）
- （乘法对加法的分配律）

</blockquote>

显然, 线性映射的乘法没有交换律和消去律, 因此 $\mathcal L(V)$ 连同其上的加法与乘法构成环, 但也仅仅构成环. 

#### Part B: 线性映射基本定理

本节的主要目的是介绍线性映射基本定理. 纵观数学历史, 能被冠以“基本”(fundamental)二字的定理往往在对应领域占有举足轻重的地位, 如代数学基本定理、微积分基本定理. 故而本章非常重要. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(零空间)</strong>

设 $K$ 为一个数域, $V$ 与 $W$ 为 $K$ 上的线性空间, 而 $T\in\mathcal L(V,W)$, 则单点集 $\{0_W\}$ 在 $T$ 下的逆像 $T^{-1}(\{0_W\})$ 称作线性映射 $T$ 的**零空间**或**核**(kernel), 记作 $\ker(T)$ 或 $\ker T$. 

</blockquote>

请自行验证, $\ker(T)$ 是 $V$ 的子空间. 

零空间是重要的, 它反映了那些在 $T$ 下被映为零向量的向量. 正如介绍直和与线性无关时那样, 研究零向量的行为往往能带给我们启发. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(线性映射为单射的等价刻画)</strong>

设 $K$ 为一个数域, $V$ 与 $W$ 为 $K$ 上的线性空间, 而 $T\in\mathcal L(V,W)$, 则 $T$ 为单射的充分必要条件是 $\ker(T)=\{0_V\}$. 

</blockquote>

类似地, 请自行验证, $\mathrm{ran}(T)$ 则是 $W$ 的子空间, 下给出重要的线性映射基本定理. 

<blockquote class="quote-style-2"><strong style="color: #28a745;">定理(线性映射基本定理)</strong>

设 $K$ 为一个数域, $V$ 与 $W$ 为 $K$ 上的线性空间, 其中 $V$ 为有限维的, 而 $T\in\mathcal L(V,W)$, 则有

$$\dim V =\dim \ker(T)+\dim \mathrm{ran}(T). $$

</blockquote>

<details class="custom-details">
    <summary class="custom-summary">证明</summary>

不妨设 $V$ 与 $\ker(T)$ 与 $\mathrm{ran}(T)$ 均不为零维空间, 这些情形平凡, 留作练习. 

考虑 $\ker(T)$ 在 $V$ 下的补空间. 取 $\ker(T)$ 的一组基 $(v_1,v_2,\cdots,v_n)$ 扩充为 $V$ 的一组基 $(v_1,v_2,\cdots,L_n,w_1,w_2,\cdots,w_m)$, 现断言 $\mathrm{span}((w_1,w_2,\cdots,w_m))$ 在 $T$ 下的像是 $\mathrm{ran}(T)$. 

要证明此事, 只要证 $\mathrm{span}((T(w_1),T(w_2),\cdots,T(G_m)))=\mathrm{ran}(T)$. 这是显然的, 因为任取 $T(v)\in\mathrm{ran}(T)$, 根据 $(v_1,v_2,\cdots,L_n,w_1,w_2,\cdots,w_m)$ 为 $V$ 的一组基, 那么

$$
v=\sum_{i=1}^n k_iv_i+\sum_{j=1}^m t_jw_j
$$

故 $\displaystyle T(v) = T(\sum_{i=1}^n k_iv_i+\sum_{j=1}^m t_jw_j)=\sum_{j=1}^m t_jT(w_j)$. 

再证向量组 $T(w_1),T(w_2),\cdots,T(G_m)$ 线性无关, 从而构成 $\mathrm{ran}(T)$ 的一组基. 令

$$
\sum_{i=1}^m t_jT(w_j) = 0_W
$$

则 $\displaystyle T(\sum_{i=1}^m t_jw_j)=0_W$, 这表明 $\displaystyle\sum_{i=1}^m t_jw_j\in\ker(T)$, 这与 $(v_1,v_2,\cdots,L_n,w_1,w_2,\cdots,w_m)$ 线性无关矛盾！

</details>

<details class="custom-details">
    <summary class="custom-summary">思考：线性变换的零空间与值域之和是线性空间本身吗？</summary>

考虑直和的维数公式, 对于有限维线性空间 $V$, 若 $V=U\oplus W$, 则

$$
\dim V=\dim U +\dim W
$$

对于某个有限维线性空间 $V$ 内的变换 $T\in\mathcal L(V)$, 根据线性映射基本定理有

$$
\dim V=\dim \ker(T) +\dim \mathrm{ran}(T)
$$

但若认为有 $V=\ker(T)\oplus\mathrm{ran}(T)$ 就太想当然了, $\ker(T)\cap\mathrm{ran}(T)$ 未必等于 $\{0_V\}$, 即二者之和未必是直和. 即使二者的和是直和, 也未必得到 $V$. 

提示：考虑微分映射, 或参见一习题

设 $P\in \mathcal L(V),P^2=P$，求证 $V=\ker(P)\oplus\mathrm{ran}(P)$. 

</details>

由此得许多重要推论. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题</strong>

设 $V,W$ 为数域 $K$ 上的非零线性空间, $T\in\mathcal L(V,W)$ 我们有：

1. （**映到更高维空间的线性映射不满**）若 $\dim V<\dim W$, 则 $T$ 不为（$V$ 到 $W$）的满射. 注意, 是否为满射取决于陪域的选择. 

2. （**映到更低维空间的线性映射不单**）若 $\dim V>\dim W$, 则 $T$ 不为单射. 

3. （映到同维空间的线性映射, 单射与满射互相蕴含）若 $\dim V=\dim W<+\infty$, 则 $T$ 为单射的充分必要条件是 $T$ 为满射. 

</blockquote>

<details class="custom-details">
    <summary class="custom-summary">证明</summary>

均只需运用线性映射基本定理, 即

$$\dim V =\dim \ker(T)+\dim \mathrm{ran}(T)$$

$\dim \mathrm{ran}(T) \le \dim V <\dim W$, 故映到更高维空间的线性映射不满. 

$\dim \ker(T)=\dim V-\dim \mathrm{ran}(T) \ge \max \{0,\dim V-\dim W\}$, 故映到更低维空间的线性映射不单. 

$\dim V=\dim W<+\infty$, 则 $\dim \ker(T)=0\iff \dim \mathrm{ran}(T)=\dim W$, 故映到同维空间的线性映射, 单射与满射互相蕴含. 

</details>

不难看到（？）, 维数相同的线性空间同构. 今后, 我们不妨在思考时将有限维线性空间视作 $\mathbb F^n$, 这样既直观, 又不失一般性. 

根据上述推论, 我们还能从另一个角度直观地理解前备知识中提到的“未知量个数多于方程数的齐次线性方程组必有非零解”. 

<details class="custom-details">
    <summary class="custom-summary">如何理解？</summary>

考虑数域 $K$ 上的线性方程组如下

$$\left\{\begin{matrix}
a_{11}x_1+a_{12}x_2+\cdots+a_{1n}x_n=b_1 &\\
a_{12}x_1+a_{22}x_2+\cdots+a_{2n}x_n=b_2 &\\
\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot& \\
a_{m1}x_1+a_{m2}x_2+\cdots+a_{mn}x_n=b_m &
\end{matrix}\right.$$

并考虑一个 $K^n$ 到 $K^m$ 的线性映射（$k=1,2,\cdots,n$, $\varepsilon_k$ 为第 $k$ 坐标向量）

$$T\colon K^n\to K^m,\varepsilon_k\mapsto (a_{1k},a_{2k},\cdots,a_{mk})$$

则, 寻找这个线性方程组的解向量集合, 就是在寻找向量 $(b_1,b_2,\cdots,b_m)$ 在 $T$ 下的原像集. 对于齐次线性方程组, $(b_1,b_2,\cdots,b_m)$ 就为零向量, 则当 $n>m$ 时, 该线性映射不为单射, 即零空间不为单点集, 故存在 $(x_1,x_2,\cdots,x_n)\ne 0_n$ 使得

$$T((x_1,x_2,\cdots,x_n))=0_m$$

即未知量个数多于方程数的齐次线性方程必组有非零解. 

</details>

#### Part C: 线性映射的表示矩阵与矩阵空间 $M_{m,n}(K)$

由线性映射引理, 我们已经看到, 对于线性映射 $T\in\mathcal L(V,W)$, 假若 $V$ 有限维, 那么只需确定 $V$ 的一组基 $(v_1,v_2,\cdots,v_n)$ 在 $T$ 下的去向, 就唯一确定了这个线性映射. 那么, 假若 $W$ 也是有限维的, 取一组基为 $(\beta_1,\beta_2,\cdots,\beta_m)$, 我们记

$$
T(v_j)=\sum_{i=1}^m a_{ij}\beta_j,\qquad j=1,2,\cdots,n
$$

不妨将这 $mn$ 个数以第一下标为列号, 第二下标为行号, 排成一个 $m\times n$ 的矩阵, 即

$$\begin{bmatrix}
 a_{11} & a_{12} & \cdots & a_{1n}\\
 a_{21} & a_{22} & \cdots & a_{2n}\\
 \vdots & \vdots & & \vdots\\
 a_{m1} & a_{m2} & \cdots & a_{mn}\\
\end{bmatrix}$$

可见, 在 $V$ 与 $W$ 的基已确定的情况下, $K$ 上的一个 $m\times n$ 矩阵就与 $\mathcal L(V,W)$ 中的一个线性映射一一对应. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(线性映射的表示矩阵)</strong>

设 $V,W$ 为数域 $K$ 上的非零维有限维线性空间, $T\in\mathcal L(V,W)$, 而 $L_n=(v_1,v_2,\cdots,v_n)$ 与 $G_m=(\beta_1,\beta_2,\cdots,\beta_m)$ 分别为 $V$ 与 $W$ 的一组基, 记

$$
T(v_j)=\sum_{i=1}^m a_{ij}\beta_j,\qquad j=1,2,\cdots,n
$$

则称矩阵

$$\begin{bmatrix}
 a_{11} & a_{12} & \cdots & a_{1n}\\
 a_{21} & a_{22} & \cdots & a_{2n}\\
 \vdots & \vdots & & \vdots\\
 a_{m1} & a_{m2} & \cdots & a_{mn}\\
\end{bmatrix}$$

为线性映射 $T$ 关于基 $L_n,G_m$ 的**表示矩阵**, 记作 $M(T,L_n,G_m)$. 

</blockquote>

若上下文已明确了线性空间 $V$ 与 $W$ 之基的选取, 则可简记作 $M(T)$. 对于 Euclid 空间, 若不加说明, 默认取标准基. 

<details class="custom-details">
    <summary class="custom-summary">例子</summary>

设 $V$ 是 $n$ 维线性空间, 而 $W$ 是 $m$ 维线性空间. 在下面的讨论中, 总假设选取 $L_n$ 为 $V$ 的一组基, 并选取 $G_m$ 为 $W$ 的一组基. 

（1）无论 $L_n$ 与 $G_m$ 为何, 零映射 $0_{\mathcal L(V,W)}$ 的表示矩阵 $M(0_{\mathcal L(V,W)},L_n,G_m)$ 都是全零的 $m\times n$ 矩阵, 称之为**零矩阵**. 考虑到这一点, 我们总是用 $O$ 表示零矩阵, 并且如无必要不标注它的尺寸. 

（2）暂缺. 

以下两例假设 $V=W$（从而 $n=m$）, 即研究线性变换的表示矩阵. 

（3）假设 $L_n=G_m$, 即不考虑为同一个线性空间 $V$ 选取不同的基的情况. 那么, 无论 $L_n$ 为何, $V$ 上的恒等算子 $I_V$ 的表示矩阵 $M(I_V,L_n,L_n)$ 都具有如下的形式（未写出部分全为 $0$）

$$\displaystyle E_n:= \mathrm{diag}(1,1,\cdots,1)= \begin{bmatrix}
  1 & & & \\
  & 1 & & \\
  & &\ddots & \\
  & & & 1\\
\end{bmatrix}$$

称这样的 $n$ 阶方阵为 **$n$ 阶单位矩阵**, 记作 $E_n$. 如果从上下文能明确它的尺寸, 也可简记作 $E$. 

（3）假设 $L_n\ne G_m$. 那么, $V$ 上的恒等算子 $I_V$ 的表示矩阵 $M(I_V,L_n,G_m)\ne E_n$. 

例如, 取基域 $\mathbb F=\mathbb R$, 取 $V=\mathbb R^2,L_n=((1,0),(0,1)),G_m=((2,4),(1,3))$, 计算可得

$$M(I_{\mathbb R^2},((1,0),(0,1)),((2,4),(1,3)))=\begin{bmatrix}
 \displaystyle\frac 32 & \displaystyle-\frac 12\\
 -2 & 1
\end{bmatrix}$$

在[后面](#基变换与相似)会着重讨论此事. 

</details>

我们看到, 对于同一数域 $K$ 上的非零维有限维线性空间 $V$ 与 $W$, 若已选定了它们各自的一组基 $(v_1,v_2,\cdots,v_n)$ 与 $(\beta_1,\beta_2,\cdots,\beta_m)$, 则 $\mathcal L(V,W)$ 中的线性映射与 $M_{m\times n} (K)$ 中的矩阵一一对应. 那么, 自然存在一个想法：**根据 $\mathcal L(V,W)$ 中线性映射的运算, 定义 $M_{m\times n} (K)$ 中矩阵的运算, 使得 $M_{m\times n} (K)$ 成为一个与 $\mathcal L(V,W)$ 同构的线性空间**. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(矩阵加法与数乘)</strong>

设 $A,B\in\mathcal M_{m\times n}(K)$, 则

</blockquote>

下面的命题解释了这样定义的动机. 这说明矩阵的加法与数乘并不是什么新的东西. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(矩阵运算与线性映射运算的关系)</strong>

</blockquote>

请自行验证, $M_{m\times n} (K)$ 连同先前定义的加法和数乘, 已构成了 $K$ 上的一个线性空间. 因此, 我们可以说, 矩阵是一种特殊的向量. 

回忆先前列向量的定义, 我们又可以说, 列向量是一种特殊的矩阵（多行一列矩阵）. 于是, 我们有如下定义. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(行向量与列向量)</strong>

设 $A=(a_{ij})_{m\times n}\in M_{m\times n} (K)$, 记

$$A_{k,\cdot}:= [a_{k1},a_{k2},\cdots,a_{kn}](\in M_{1\times n})$$

为矩阵 $A$ 的第 $k$ **行向量**, 简称第 $k$**行**. 并称向量组

$$(A_{1,\cdot},A_{2,\cdot},\cdots,A_{m,\cdot})$$

为矩阵 $A$ 的**行向量组**；

$\,$

类似地, 记

$$A_{\cdot,r}:= \begin{bmatrix}
a_{1r}\\a_{2r}\\\vdots\\ a_{mr}
\end{bmatrix}(\in K^m)$$

为矩阵 $A$ 的第 $r$ **列向量**, 简称第 $r$ **列**. 并称向量组

$$(A_{\cdot,1},A_{\cdot,2},\cdots,A_{\cdot,m})$$

为矩阵 $A$ 的**列向量组**. 

</blockquote>

上述定义引进了一种看待矩阵的新观点. 值得指出的是, 这种观点实际上就是分块矩阵中的按行（列）分块. 

#### Part D: 矩阵乘法

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(矩阵乘法)</strong>

设 $K$ 为一个数域, $A\in M_{m\times n}(K),B\in M_{n\times s}$, 则称 $K$ 上一个 $m\times s$ 的矩阵 $C$ 为矩阵 $A$ 与矩阵 $B$ 的乘积, 其中 $C$ 的第 $i$ 行第 $j$ 列元素 $c_{ij}$ 定义为

$$
c_{ij}:=\sum_{k=1}^n a_{ik}b_{kj},\qquad i=1,2,\cdots,m,j=1,2,\cdots,s
$$

并记 $C=:A\times B$.  

</blockquote>

上述定义乍看之下必定令人感到困惑, 我们须对这样定义的动机作一个合理的解释. 

<details class="custom-details">
    <summary class="custom-summary">说明</summary>

与先前定义的加法和数乘类似地, 考虑有限维线性空间 $U,V,W$, 它们各自取定了一组基 $u_s,L_n,G_m$, 并有线性映射 $T\in\mathcal L(U,V),S\in\mathcal L(V,W)$, 我们期望找到一种恰当的定义方式, 使得在上述三组基下, 有

$$M(ST,u_s,G_m)=M(S,L_n,G_m)M(T,u_s,L_n)$$

<计算暂略>

</details>

现在, 只需验证按上述定义的矩阵乘法能满足我们的希望. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题</strong>

设 $T\in\mathcal L(U,V),S\in\mathcal L(V,W)$, 它们各自取定了一组基 $u_s,L_n,G_m$. 则 

$$M(ST,u_s,G_m)=M(S,L_n,G_m)M(T,u_s,L_n). $$ 

</blockquote>

矩阵运算满足如下性质. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(矩阵运算的性质)</strong>

设 $A,B,C$ 是数域 $K$ 上的矩阵, 下面的每一条中总假设它们之间可以进行矩阵乘法：

- （矩阵乘法结合律）$A(BC)=(AB)C$; 
- （矩阵乘法对加法的分配律）$A(B+C)=AB+AC,(A+B)C=AC+BC$; 
- （矩阵乘法与数乘的“结合律”）任给 $k\in K$, $k(AB)=(kA)B$; 
- （矩阵乘法与转置的关系）任给 $k\in K$, $(A+B)^T=A^T+B^T,(kA)^T=kA^T,(AB)^T=B^TA^T$. 

</blockquote>

值得注意的是：矩阵乘法没有交换律和消去律, 两个非零矩阵作乘法可能得到零矩阵. 

<details class="custom-details">
    <summary class="custom-summary">例子</summary>

考虑这样一个 $n$ 阶方阵（未写出的元素均为 $0$）：

$$J=\begin{bmatrix}
 0 & 1 &  &  & \\
  & 0 & 1 &  & \\
  &  & \ddots & \ddots & \\
  &  &  & \ddots & 1\\
  &  &  &  & 0
\end{bmatrix}$$

不难验证, $J$ 左乘一个任意的 $n$ 行矩阵, 所得的结果都是将后者的全体向上移动一行；相应地, $J$ 右乘一个任意的 $n$ 列矩阵, 所得的结果都是将后者的全体向右移动一列. 

于是

$$J^n = J^{n-1}\times J = O$$

换言之, $J$ 自乘 $n$ 次后得到零矩阵, 这样的矩阵又叫做**幂零矩阵**. 幂零矩阵的存在说明非零矩阵相乘可能得到零矩阵. 

</details>

引入矩阵乘法之后, 我们便能够引入一个意义非凡的观点：将**线性映射对向量的作用**与**矩阵与有序组的乘法**相互转化. 具体地说：

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(与矩阵相乘映射)</strong>

设 $A\in M_{m\times n}(K)$, 则映射

$$f_A\colon K^n\to K^m, X\mapsto AX$$

亦即

$$f_A\colon K^n\to K^m, \begin{bmatrix}
x_1 \\
x_2 \\
\vdots \\
x_n
\end{bmatrix} \mapsto \begin{bmatrix}
\displaystyle \sum_{i=1}^n a_{1i}x_i \\
\displaystyle \sum_{i=1}^n a_{2i}x_i \\
\vdots \\
\displaystyle \sum_{i=1}^n a_{mi}x_i
\end{bmatrix}$$

称作**与矩阵 $A$ 相乘映射**. 

</blockquote>

不难验证, $f_A\in\mathcal L(K^n,K^m)$, 且满足 $M(f_A)=A$（在标准基下）. 这样, $AX=f_A(X)$. 今后, 我们会非常经常借助该映射研究矩阵的性质. 

同样的, 我们也可以将线性映射对向量的作用看成矩阵与有序组的乘法, 这是由于下述命题. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(线性映射的矩阵乘法表示)</strong>

$$M(T(v),G_m)=M(T,L_n,G_m)M(v,L_n)$$

</blockquote>

> 记号 $M(v,L_n)$ 代表向量 $v$ 在基 $L_n$ 下的坐标, 即一个 $n$ 元有序组, 一个 $n\times 1$ 矩阵. 

既然与矩阵相乘映射是线性映射, 那么, 上述命题指出了：可将线性映射 $T$ 与 $\mathcal L(K^n,K^m)$ 中的与 $M(T)$ 相乘映射看作是等同的. 

<details class="custom-details">
    <summary class="custom-summary">矩阵乘法的重要例子</summary>

（1）单位矩阵 $E_n$ 左乘一个 $n\times s$ 矩阵 $A$ 得到 $A$ 本身, 右乘一个 $m\times n$ 矩阵 $B$ 亦然. 

当然可以依照矩阵乘法的定义验算, 不过这难免繁琐. 不妨令

$$f_A\colon K^s\to K^n, X\mapsto AX$$

则 $A$ 是 $f_A$ 在标准基下的表示矩阵. 又因为 $E_n$ 是 $K^n$ 上的恒等算子 $I_{n}$ 在标准基下的表示矩阵, 则

$$M(I_{n} f_A) = M(I_{n})M(f_A) $$

等号左边等于 $M(f_A)$, 即 $A$, 而右边则等于 $EA$, 得证. 

</details>

### 分块矩阵

读者可能已经感到, 矩阵运算, 尤其是矩阵乘法, 是一种相当复杂的代数运算；而线性映射的复合固然易于理解, 但难于落实到具体的计算. 

因此, 本节介绍一种非常有用的方法：矩阵分块法. 它不仅丰富了矩阵的表示方式, 更引入了许多看矩阵运算的新观点. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(分块矩阵)</strong>

</blockquote>



<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(分块矩阵的乘法)</strong>

</blockquote>

为使上述观点具体化, 现在引入一些常用的分块法. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(矩阵乘法的行列分块视角)</strong>

设 $A\in M_{m\times n}(K),B\in M_{n\times s}(K)$, 则

- 将 $A$ 按行分块, 将 $B$ 按列分块, 则据分块矩阵的乘法有

$$A\times B=\begin{bmatrix}
A_{1,\cdot} \\
A_{2,\cdot} \\
\vdots \\
A_{m,\cdot}
\end{bmatrix}
\times
\begin{bmatrix}
 B_{\cdot,1} & B_{\cdot,2} & \cdots &
  B_{\cdot,s}\end{bmatrix}=\begin{bmatrix}
 A_{1,\cdot}B_{\cdot,1} & A_{1,\cdot}B_{\cdot,2} & \cdots & A_{1,\cdot}B_{\cdot,s}\\
 A_{2,\cdot}B_{\cdot,1} & A_{2,\cdot}B_{\cdot,2} & \cdots & A_{2,\cdot}B_{\cdot,s}\\
 \vdots & \vdots &  & \vdots\\
 A_{m,\cdot}B_{\cdot,1} & A_{m,\cdot}B_{\cdot,2} & \cdots & A_{m,\cdot}B_{\cdot,s}\\
\end{bmatrix}$$

换言之, 乘积矩阵的元素等于左行乘以右列. 

- 将整个 $A$ 视作一块, 将 $B$ 按列分块, 则据分块矩阵的乘法有

$$A\times B=A\times
\begin{bmatrix}
 B_{\cdot,1} & B_{\cdot,2} & \cdots &
  B_{\cdot,s}\end{bmatrix}=\begin{bmatrix}
 AB_{\cdot,1} & AB_{\cdot,2} & \cdots &
  AB_{\cdot,s}\end{bmatrix}$$

换言之, 乘积矩阵的列等于左矩阵乘以右列. 

- 另一方面, 将 $A$ 按行分块, 将整个 $B$ 视作一块, 也能得到对偶的结论

$$A\times B=\begin{bmatrix}
A_{1,\cdot} \\
A_{2,\cdot} \\
\vdots \\
A_{m,\cdot}
\end{bmatrix}\times B=\begin{bmatrix}
A_{1,\cdot}B \\
A_{2,\cdot}B \\
\vdots \\
A_{m,\cdot}B
\end{bmatrix}$$

换言之, 乘积矩阵的行等于左行乘以右矩阵. 

- 仅将 $A$ 按列分块, 则据分块矩阵的乘法有

$$
\begin{aligned}
 A\times B & = \begin{bmatrix}
 A_{\cdot,1} & A_{\cdot,2} & \cdots &
 A_{\cdot,n}\end{bmatrix}
\begin{bmatrix}
 b_{11} & b_{12} & \cdots & b_{1s}\\
 b_{21} & b_{22} & \cdots & b_{2s}\\
 \vdots & \vdots &  & \vdots \\
 b_{n1} & b_{n2} & \cdots & b_{ns}\\
\end{bmatrix} \\
     &=\begin{bmatrix} \displaystyle \sum_{k=1}^n b_{k1}A_{\cdot,k} & \displaystyle \sum_{k=1}^n b_{k2}A_{\cdot,k} & \cdots &  \displaystyle \sum_{k=1}^n b_{ks}A_{\cdot,k}\end{bmatrix}
\end{aligned}
$$

换言之, 乘积矩阵的列是左矩阵各列的线性组合, 系数来自于右矩阵的对应列. 

- 另一方面, 仅将 $B$ 按行分块, 也能得到对偶的结论

$$\begin{aligned}
 A\times B & = \begin{bmatrix}
 a_{11} & b_{12} & \cdots & b_{1n}\\
 a_{21} & b_{22} & \cdots & b_{2n}\\
 \vdots & \vdots &  & \vdots \\
 a_{m1} & b_{m2} & \cdots & b_{mn}\\
\end{bmatrix}
\times
\begin{bmatrix}
B_{1,\cdot} \\
B_{2,\cdot} \\
\vdots \\
B_{n,\cdot}
\end{bmatrix} \\
     &=\begin{bmatrix}
\displaystyle \sum_{k=1}^n a_{1k}B_{k,\cdot} \\
\displaystyle \sum_{k=1}^n a_{2k}B_{k,\cdot} \\
\vdots \\
\displaystyle \sum_{k=1}^n a_{mk}B_{k,\cdot}
\end{bmatrix}
\end{aligned}$$

换言之, 乘积矩阵的行是右矩阵各行的线性组合, 系数来自于左矩阵的对应行. 

</blockquote>

为什么不考虑将左边的按列分块, 右边的按行分块？请自行尝试, 看看是否能得到新的观点. 

<details class="custom-details">
    <summary class="custom-summary">实际上……</summary>

将 $A$ 按行分块, 将 $B$ 按列分块, 则

$$A\times B = \begin{bmatrix}
 A_{\cdot,1} & A_{\cdot,2} & \cdots &
 A_{\cdot,n}\end{bmatrix}
\times
\begin{bmatrix}
B_{1,\cdot} \\
B_{2,\cdot} \\
\vdots \\
B_{n,\cdot}
\end{bmatrix}=\sum_{k=1}^nA_{\cdot,k}B_{k,\cdot}$$

得到的是一个 $1\times 1$ 的求和式, 求和项 $A_{\cdot,k}B_{k,\cdot}$ 是个 $n\times s$ 的矩阵——下标看着是不是很熟悉？若将其展开, 就看到

$$A_{,\cdot k}B_{k,\cdot}=\begin{bmatrix}
a_{1k}b_{k1}  & a_{1k}b_{k2} & \cdots & a_{1k}b_{ks}\\
a_{2k}b_{k1}  & a_{2k}b_{k2} & \cdots & a_{2k}b_{ks}\\
 \vdots & \vdots &  & \vdots \\
a_{mk}b_{k1}  & a_{mk}b_{k2} & \cdots & a_{mk}b_{ks}\\
\end{bmatrix}$$

再求和, 得

$$A\times B =\begin{bmatrix}
\displaystyle \sum_{i=1}^n a_{1k}b_{k1} & \displaystyle \sum_{i=1}^na_{1k}b_{k2} & \cdots & \displaystyle \sum_{i=1}^na_{1k}b_{ks}\\
\displaystyle \sum_{i=1}^na_{2k}b_{k1}  & \displaystyle \sum_{i=1}^na_{2k}b_{k2} & \cdots & \displaystyle \sum_{i=1}^na_{2k}b_{ks}\\
 \vdots & \vdots &  & \vdots \\
\displaystyle \sum_{i=1}^na_{mk}b_{k1}  & \displaystyle \sum_{i=1}^na_{mk}b_{k2} & \cdots & \displaystyle \sum_{i=1}^na_{mk}b_{ks}\\
\end{bmatrix}$$

我们就回到了矩阵乘法的定义式. 因此, 这种分块没有带来新的观点. 

</details>

值得注意的是, 我们引入矩阵分块的观点主要是为了简化问题. 因此, 下主要考虑分块为 $2\times 2$ 矩阵的情况. 

下给出一些例子. 

（1）$M_{n}(K)$ 是 $K$ 上的一个线性空间, 其标准基包含的矩阵是

$$E_{ij}=$$

用 $E_{ij}$ 左乘一个 $n$ 行矩阵, 其结果是将后者的第 $i$ 行替换为第 $j$ 行, 其余位置变为零. 相应地, 用 $E_{ij}$ 右乘一个 $n$ 列矩阵, 其结果是将后者的第 $j$ 列替换为第 $i$ 列, 其余位置变为零. 

分块矩阵中有类似的结论, 但对应位置上的小块从 $1$ 变为了单位矩阵 $E$. 

（2）**对角矩阵**, 常记作 $\mathrm{diag}(\lambda_1,\lambda_2,\cdots,\lambda_n)$. 

用对角矩阵 $\mathrm{diag}(\lambda_1,\lambda_2,\cdots,\lambda_n)$ 左乘一个 $n$ 行矩阵, 其结果是将后者的 $n$ 行分别乘 $\lambda$ 倍. 

分块矩阵中有类似的结论, 相应的矩阵称作**准对角矩阵**. 

（3）**初等矩阵**. 

**分块初等矩阵**. （倍乘变为乘可逆矩阵, 而倍加矩阵乘的矩阵只需尺寸合适）


### 矩阵的零度、秩与可逆性

在本节中, 我们先通过矩阵的行列分解证明行秩等于列秩, ~~再介绍初等变换办法. ~~

#### Part A: 转置矩阵与对偶

下一小节将介绍矩阵的乘法, 为此我们先作一些准备工作, 引入转置矩阵的概念. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(转置矩阵)</strong>

</blockquote>

矩阵行与列的地位不是对等的, 但却有许多类似的性质, 这些类似的形式皆可藉由转置矩阵来描述. 故而, 下补充一些有关对偶(dual)的内容, 方便理解转置矩阵的意义. 

先引入对偶空间的定义. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(对偶空间与线性泛函)</strong>

设 $V$ 是域 $\mathbb F$ 上的线性空间, 则称线性空间 $\mathcal L(V,\mathbb F)$ 为 $V$ 的**对偶空间**(dual space), 记作 $V'$, 并称 $V'$ 中的元素为 $V$ 上的**线性泛函**. 

</blockquote>

> $\mathbb F$ 当然是 $\mathbb F$ 上的线性空间（一维的）. 

泛函是一类特殊的线性映射, 它将线性空间中的向量映为基域中的标量. 

<details class="custom-details">
    <summary class="custom-summary">线性泛函的例子</summary>

下面的函数是 $\mathbb R^3$ 上的线性泛函

$$T \colon \mathbb R^3 \to \mathbb R,(x,y,z)\mapsto 3x+5y-z$$

而**范数**则不是一种线性泛函（由于需要满足次可加性, 亦即三角不等式）. 例如, 在 $\mathbb R^3$ 上, 我们通常采用的范数是

$$||\cdot|| \colon \mathbb R^3 \to \mathbb R, (x,y,z)\mapsto || (x,y,z) ||:= \sqrt{x^2+y^2+z^2}. $$

它满足齐次性, 但不满足可加性. 

</details>

称两个对象是对偶的, 往往表明其中一者拥有的性质, 另一者也有相应的体现. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(线性空间与其对偶的维数相等)</strong>

</blockquote>

<details class="custom-details">
    <summary class="custom-summary">证明</summary>

这是根据线性映射空间维数的公式, 自然 $\mathbb F$ 是 $\mathbb F$ 上的一维空间, 因此

$$\dim V'= \dim \mathcal L(V,\mathbb F) = \dim V \cdot \dim \mathbb F =\dim V$$. 

</details>

下面的命题体现了 $V$ 的每一组基都在 $V'$ 中有相应的对偶基存在. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(对偶基的存在性)</strong>

设 $V$ 的一组基为 $v_1,v_2,\cdots,L_n$, 记

$$\varphi_k \colon V\to\mathbb F,\varphi_k(a_1v_1+a_2v_2+\cdots+a_nL_n) = a_k,\qquad k=1,2,\cdots,n$$

则 $(\varphi_1,\varphi_2,\cdots,\varphi_n)$ 是 $V'$ 的一组基. 

</blockquote>

> 不难看出, 每个 $\varphi_k$ 都将向量映成了它的第 $k$ 分量. 

<details class="custom-details">
    <summary class="custom-summary">证明</summary>

易见 $(\varphi_1,\varphi_2,\cdots,\varphi_n)$ 线性无关. 不妨设一组标量将这组泛函表示为零映射, 即

$$k_1\varphi_1+k_2\varphi_2+\cdots+k_n\varphi_n = 0_{V'}$$

则

$$k_1a_1+k_2a_2+\cdots + k_na_n = 0 ,\forall (a_1,a_2,\cdots,a_n)\in \mathbb F^n$$

取 $(1,0,\cdots,0)$ 易见 $k_1=1$, 其余位置同理. 显然, 只有让 $k_1,k_2,\cdots,k_n$ 均为 $0$ 才有上式成立. 

亦不难证明 $(\varphi_1,\varphi_2,\cdots,\varphi_n)$ 能线性表示 $V'$ 中全体线性映射. 

</details>

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(对偶基)</strong>

**对偶基**(dual basis). 

</blockquote>

相应地 $\mathcal L(V,W)$ 中的每一个线性映射实际上都对应于一个 $V'$ 中的线性映射. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(对偶映射)</strong>

设 $T\in\mathcal L(V,W)$, 则映射

$$T'\colon W'\to V', \varphi \mapsto T'(\varphi):=\varphi T$$

称作线性映射 $T$ 的**对偶映射**. 

</blockquote>

> 想起了一个笑话, 譬如蓄意将 $f(x)$ 写成 $x(f)$, 并声称这是合理的对偶表达（）

~~同样是一个不习惯省略线性映射括号的理由, 要不然上述定义就像 $T'\varphi=\varphi T$. ~~

我们必须花些篇幅来说明这个定义是什么玩意. 

<暂略>

优美的命题. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(线性映射在任一组基下的表示矩阵与其对偶映射在对偶基下的表示矩阵互为转置)</strong>

</blockquote>

#### Part B: 矩阵的行列分解

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(行秩与列秩)</strong>

设 $A\in M_{m\times n}(K)$, 则 $A$ 的列向量组在 $M_{m\times 1}(K)$ 中张成的空间称作 $A$ 的**列空间**. $A$ 的列空间的维数, 亦即列向量组的秩, 称作 $A$ 的**列秩**. 

$\,$

相应地, $A$ 的行向量组在 $M_{1\times n}(K)$ 中张成的空间称作 $A$ 的**行空间**. $A$ 的行空间的维数, 亦即行向量组的秩, 称作 $A$ 的**行秩**. 

</blockquote>

由定义立即看到, $A$ 的行秩与列秩均应小于 $\min \{m,n\}$. 并且, 对于列秩, 我们应有一个直观的认识. 

设 $A\in M_{m\times n}(K)$, 并设

$$f_A\colon K^n\to K^m, X\mapsto AX$$

则 $f_A$ 将 $K^n$ 中的 $n$ 个标准基映为 $n$ 个列向量, 故 $\mathrm{ran}(f_A)$ 就是 $A$ 的列空间. 换言之, $A$ 的列秩等于 $\dim \mathrm{ran}(f_A)$. 

而 $A$ 的行秩就是 $A^T$ 的列秩, 根据对偶的性质, 二者似应相等. 

事实上, 我们即将通过所谓矩阵的行列分解来证明, 任何矩阵的行秩都等于列秩. 

<blockquote class="quote-style-2"><strong style="color: #28a745;">定理(矩阵的行列分解, $CR$ 分解)</strong>

设 $A\in M_{m\times n}(K)$ 为非零矩阵, 则存在 $C\in M_{m\times r}(K)$ 以及 $R\in M_{r\times n}(K)$ 使得 $A=CR$. 其中, $c\in\mathbb N_+$ 是 $A$ 的列秩. 

</blockquote>

<details class="custom-details">
    <summary class="custom-summary">证明</summary>

设 $A$ 的列向量组的一个极大线性无关部分组为 $(A_{\cdot,i_1},A_{\cdot,i_2},\cdots,A_{\cdot,i_r})$, 令该组按顺序排成一个矩阵 $C$, 则 $C\in M_{m\times r}(K)$. 

由定义, $A$ 的每个列都是这些列的线性组合, 不妨设出该线性组合的系数, 即

$$A_{\cdot,k} = a_{1k}A_{\cdot,i_1}+a_{2k}A_{\cdot,i_2}+\cdots + a_{rk}A_{\cdot,i_r},\quad k=1,2,\cdots,n$$

现在, 将 $(a_{1k},a_{2k},\cdots,a_{rk})$ 作为第 $k$ 列, 排成一个共 $n$ 列 $r$ 行的矩阵, 即为所求的 $R$. 这是因为当 $C$ 与 $R$ 相乘时, 乘积矩阵的第 $k$ 列是 $C$ 各列的线性组合, 而线性组合的系数来源于 $R$ 的第 $k$ 列. 

</details>

> 按理说, $CR$ 分解的两个字母分别对应 column 与 row, 似乎应该叫列行分解才对.

一般来说, 所谓矩阵分解, 就是把矩阵化成一系列简单矩阵的运算结果的过程. 行列分解是我们接触的第一种矩阵分解, 今后我们还将认识更多的矩阵分解方式, 如 $LU$ 分解、正交分解（$QR$ 分解）及特征值分解（$SVD$ 分解）. 

我们也可以把矩阵分解若干矩阵的和. 例如, 对任意方阵 A, 都有 $\displaystyle A= \frac {A+A^T}{2}+ \frac {A- A^T}{2}$, 而 $\displaystyle \frac {A+A^T}{2}$ 是对称矩阵, $\displaystyle \frac {A-A^T}{2}$ 是反对称矩阵, 这对我们把握 $A$ 的某些性质有一定帮助. 

上述证明也向我们展示了作 $CR$ 分解的办法：将 $A$ 的列向量组的一个极大线性无关部分组提出并排成矩阵 $C$ 即可. 注意, 由于极大线性无关部分组的选取未必是唯一的, 矩阵的 $CR$ 分解办法也未必是唯一的. 

$CR$ 分解向我们展示了一个重要的结论. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">推论</strong>

矩阵的行秩等于列秩. 

</blockquote>

<details class="custom-details">
    <summary class="custom-summary">证明</summary>

对零矩阵显然成立. 设 $A\in M_{m\times n}(K)$ 是一个非零矩阵, $c\in\mathbb N_+$ 为 $A$ 的列秩, 并设 $A=CR$ 是一种行列分解. 

根据矩阵乘法, $A$ 的各行是 $R$ 行向量组的线性组合, 系数来自 $C$ 的对应行. 换言之, $A$ 的行向量组可被 $R$ 的行向量组线性表出, 而 $R$ 共有 $c$ 行, 由替换定理, $c\ge A$ 的行秩. 

另一方面, 又可以证明 $A$ 的行秩 $\ge c$, 只需对 $A^T$ 作 $CR$ 分解即可. 

</details>

故而, 我们有理由给出这样的定义. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(秩)</strong>

矩阵 $A$ 的列秩称作矩阵 $A$ 的**秩**, 记作 $\mathrm{rank}(A)$. 

</blockquote>

下面的命题一定程度上刻画了矩阵秩的本质. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(矩阵的秩是以其为表示矩阵的线性映射值域的维数)</strong>



</blockquote>

零度与秩公式——矩阵形式的“线性映射基本定理”。

下一节我们将引入矩阵的初等变换, 从而证明这个命题. 

现在, 我们先证明一些重要的不等式. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(矩阵的秩与矩阵运算的不等式)</strong>

- $\mathrm{rank}(A+B)\le \mathrm{rank}(A)+\mathrm{rank}(B)$; 

- $\mathrm{rank}(A)=k\mathrm{rank}(A)$; 

又设 $A\in M_{m\times n}(K),B\in M_{n\times s}(K)$, 则

- $\mathrm{rank}(AB)\le \min \{\mathrm{rank}(A),\mathrm{rank}(B)\}$; 
- $\mathrm{rank}(AB)\ge \mathrm{rank}(A)+\mathrm{rank}(B)-n$. 

</blockquote>

<details class="custom-details">
    <summary class="custom-summary">证明</summary>

</details>

#### Part C: 线性方程组的理论课题

#### 矩阵的逆

尽管矩阵只有乘法没有除法, 但部分矩阵可以求逆. 我们知道, 一个映射可逆当且仅当它是双射, 而出发于有限维线性空间的双射必然以一个相同维数的线性空间为值域（由线性映射基本定理）, 因此, 我们仅仅对方阵来谈论逆. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题</strong>

设 $A\in M_{n\times n}(K)$, 若存在 $B\in M_{n\times n}(K)$ 使得 $BA=E$ 且 $AB=E$, 则这样的 $B$ 是唯一的. 

</blockquote>

<details class="custom-details">
    <summary class="custom-summary">证明</summary>

设还存在一个 $C\in M_{n\times n}(K)$, 则 $$BA=E\implies BAC=EC\implies BE=EC\iff B=C. $$

</details>

上述命题引导我们作此定义. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(逆矩阵)</strong>

设 $A\in M_{n\times n}(K)$, 若存在 $B\in M_{n\times n}(K)$ 使得 $BA=E$ 且 $AB=E$, 则称 $A$ 是**可逆**的, $B$ 为 $A$ 的**逆矩阵**, 记 $B=:A^{-1}$. 

</blockquote>

> 自然, $A=(A^{-1})^{-1}$. 

下面的命题再次深刻地揭示了线性映射与矩阵的联系, 同时又给“可逆”起了个更好听的名字. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题</strong>

$n$ 阶方阵 $A$ 可逆当且仅当 $\mathrm{rank}(A)=n$.  

</blockquote>

一般地, 我们称 满足 $\mathrm{rank}(A)=n$ 的 $n$ 阶方阵 $A$ 为**满秩**的. 因此, 上述命题又可简记为“方阵可逆当且仅当满秩”. 

<details class="custom-details">
    <summary class="custom-summary">证明</summary>

在线性映射的观点下显然. 

设 $A$ 可逆, 令 $A$ 与 $A^-1$ 分别表示 $T\in \mathcal L(K^n)$ 与 $S\in \mathcal L(K^n)$ 关于标准基的表示矩阵, 则由 $A^{-1}A=AA^{-1}=E$ 知

$$ST=TS=I$$

因为单位矩阵 $E$ 在定义域与值域均选取同一组基时, 是恒等映射的表示矩阵. 

故 $T$ 可逆, 而 $S=T^{-1}$. 这时, $\mathrm{ran}(T)$ 就是 $A$ 的列空间, 故 $n=\mathrm{ran}(T)=\mathrm{rank}(A)$. 

设 $n=\mathrm{rank}(A)$, 则在标准基下对应的线性映射 $T$ 可逆, 取其逆映射在标准基下对应的矩阵即可. 

</details>

<details class="custom-details">
    <summary class="custom-summary">可逆矩阵之例</summary>

（1）**上三角矩阵**与**下三角矩阵**必可逆. 

（2）**严格对角占优矩阵**必可逆. 具体地说, 若 $n$ 阶方阵 $A=(a_{ij})_{n\times n}$ 满足

$$|a_{ii}|\ge \sum_{\substack{j=1\\j\ne i}}^{n}|a_{ij}|,\forall i\in \{1,2,\cdots,n\}$$

则称 $A$ 对角占优. 若上述 $n$ 个不等号都是严格的, 则称 $A$ 严格对角占优. 

反设 $A$ 不可逆, 则 $\mathrm{rank}(A)<n$, 即存在一组不全为零的 $k_1,k_2,\cdots,k_n\in K$ 使得

$$\sum_{i=1}^n k_iA_{i,\cdot}=O_{1\times n}$$

即

$$\sum_{i=1}^n k_ia_{ij}=0,j=1,2,\cdots,n$$

由于 $k_1,k_2,\cdots k_n$ 不全为零, 则将其中的最大者 记为 $k_s$, 有 $k_s\ne 0$, 故

$$
a_{sj}=-\sum_{\substack {i=1\\ i\ne s}}^n \frac{k_i}{k_s}a_{ij},j=1,2,\cdots,n
$$

取 $j=s$, 则

$$
a_{ss}=-\sum_{\substack {i=1\\ i\ne s}}^n \frac{k_i}{k_s}a_{is}
$$

于是

$$
\begin{aligned}
    |a_{ss}| &=  |\sum_{\substack {i=1\\ i\ne s}}^n \frac{k_i}{k_s}a_{is}| \\
    &\le \sum_{\substack {i=1\\ i\ne s}}^n |\frac{k_i}{k_s}a_{is}| \\
    &\le \sum_{\substack {i=1\\ i\ne s}}^n |a_{is}|\\
    &<|a_{ss}|
\end{aligned}
$$

矛盾！上式的第一个不等号来自三角不等式, 第二个不等号来自 $\displaystyle |\frac{k_i}{k_s}|\le 1$, 第三个不等号来自严格对角占优的定义. 

（3）上述证明连用了三次不等式, 似乎是一个很弱的结果, 能否再加强一些呢？答案是肯定的, 但目前我们不太好介绍, 只能举例说明弱对角占优矩阵未必可逆. 

</details>

<blockquote class="quote-style-3"><strong style="color: #dc3545;">推论</strong>

设 $A,B\in M_{n\times n}(K)$, 则 $AB=E$ 当且仅当 $BA=E$. 故 $A$ 可逆当且仅当存在 $B$ 使得 $AB=E$ 或 $BA=E$. 

</blockquote>

<details class="custom-details">
    <summary class="custom-summary">证明</summary>

只证 $AB=E \implies BA=E$, 反之亦然. 令 $A,B$ 分别是 $T,S\in\mathcal L(K^n)$ 关于标准基的矩阵, 则 $ST=I$. 下证 $S$ 与 $T$ 均为双射. 

$\mathrm{ran}(S) \supseteq \mathrm{ran}(ST)=\mathrm{ran}(I)=K^n$, 故 $\mathrm{ran}(S)=K^n$, $S$ 是满射, 从而是双射. 

$T=S^{-1}I=S^{-1}$, 故而也是双射. 于是 $\mathrm{rank}(S)=\mathrm{rank}(T)=n$, 二者皆可逆, 故 $B=A^{-1}$, $BA=E$ 得证. 

根据秩的不等式也可解, 因为

$$
\mathrm{rank}(AB)=n\le \min \{\mathrm{rank}(A),\mathrm{rank}(B)\}
$$

而 $\mathrm{rank}(A)\le n,\mathrm{rank}(B)\le n$, 故 $\mathrm{rank}(A)=\mathrm{rank}(B)=n$. 

</details>

#### 矩阵的求逆

矩阵求逆与解线性方程组的关系. 

矩阵求逆的一般方法是 Gauss-Jordan 消元法, 它同时也是求解线性方程组的办法. 

下介绍分块矩阵的求逆. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(分块矩阵的求逆)</strong>

若 $A$ 与 $D-CA^{-1}B$ 均可逆, 则 $M=\begin{bmatrix}
 A & B \\
 C & D
\end{bmatrix}$ 也可逆, 且

$$M^{-1}=$$

</blockquote>

上式中的 $D-CA^{-1}B$ 称作 $A$ 关于 $M$ 的 **Schur 补**. 

## 线性映射在不同基下的表示矩阵

上一节的讨论中, 我们一般固定了 $V$ 与 $W$ 之基的选取, 从而将 $\mathcal L(V,W)$ 中的线性映射与矩阵等同起来看. 

回忆先前的例子, 我们看到, 同一个线性映射在不同基下的表示矩阵一般不同. 因此, 本节我们着重研究同一线性映射在不同基下的表示矩阵有何关系. 

### 基变换与矩阵相似

同一向量在不同基下的坐标也不同, 我们来研究采取基变换时向量的坐标变换公式. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(过渡矩阵)</strong>

设 $V$ 是数域 $K$ 上的线性空间, 而 $L_n,w_n$ 是 $V$ 的两组基, 则 $M(I_V,L_n,G_m)$ 称作由基 $w_n$ 变换到基 $L_n$ 的**过渡矩阵**. 

</blockquote>

你也许在想, 为什么 $M(I_V,L_n,G_m)$ 中两组基的顺序与“由基 $w_n$ 变换到基 $L_n$”中的顺序相反, 这不是“倒行逆施”吗？别急, 我们稍后解释. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(过渡矩阵的基本性质)</strong>

设 $V$ 是数域 $K$ 上的线性空间, 则

- 任取 $V$ 的两组基 $L_n,w_n$, 都有 $M(I_V,L_n,G_m)$ 可逆, 且 $M(I_V,L_n,G_m)^{-1}=M(I_V,G_m,L_n)$；
- 任取 $A\in M_n(K)$, 若 $A$ 可逆, 则存在 $V$ 的两组基 $L_n,w_n$ 使得 $A=M(I_V,L_n,w_n)$. 

</blockquote>

上述命题同时给出了矩阵可逆的另一等价刻画, 即一个方阵可逆当且仅当它是两组基之间的过渡矩阵. 

<blockquote class="quote-style-2"><strong style="color: #28a745;">定理(坐标变换公式)</strong>

设 $V$ 是数域 $K$ 上的线性空间, 而 $L_n,w_n$ 是 $V$ 的两组基, 则对任一 $v\in V$, 若其在 $L_n$ 下的坐标是 $X$, 而在 $w_n$ 下的坐标是 $Y$, 则有

$$Y=TX. $$

其中 $T$ 是基 $L_n$ 变换到 $w_n$ 的过渡矩阵, 即 $T=M(I_V,w_n,L_n)$. 

</blockquote>

如果充分理解了矩阵乘法与上述性质, 那么如下的基变换公式其实是显然的. 

<blockquote class="quote-style-2"><strong style="color: #28a745;">定理(基变换公式)</strong>

设 $V$ 是数域 $K$ 上的线性空间, 而 $L_n,w_n$ 是 $V$ 的两组基, 则对任一 $T\in \mathcal L(V)$, 记

$$A=M(T,L_n,L_n),B=M(T,w_n,w_n)$$

则

$$B=P^{-1}AP$$

其中 $P$ 是由基 $L_n$ 变换到基 $w_n$ 的**过渡矩阵**. 

</blockquote>

<details class="custom-details">
    <summary class="custom-summary">证明</summary>

根据矩阵乘法的定义与恒等算子的性质

$$\begin{aligned}
    P^{-1}AP & = M(I_V,L_n,w_n)M(T,L_n,L_n)M(I_V,w_n,L_n) \\
    & = M(I_V,L_n,w_n)M(T,w_n,L_n) \\
    & = M(I_V,w_n,w_n)=B
\end{aligned}$$

</details>

从上述证明过程中也能看到, **左乘过渡矩阵的逆, 变换值域的基; 右乘过渡矩阵, 变换定义域的基**. 

上述基变换公式引导我们作此定义. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(矩阵相似)</strong>

称两个方阵 $A$ 与 $B$ 是相似的, 当且仅当存在可逆矩阵 $P$ 使得 $B=P^{-1}AP$. 

</blockquote>

请自行验证, 矩阵相似是等价关系, 从而每个线性算子唯一确定了一个相似类, 但一个相似类可能对应多个线性算子. 

自然产生一个问题：对于 $V$ 上的线性算子 $T$, 能否从它表示矩阵的相似类中选取一个最为简单的矩阵作为代表元呢？此即所谓**相似标准形**问题, 在[特征值与特征向量](#特征值与特征向量)一章中, 我们将会研究这一问题. 下给出该问题的一个实际应用以体现其价值. 

<details class="custom-details">
    <summary class="custom-summary">例子</summary>

<人口流动模型>

</details>

### 矩阵相抵

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(矩阵相抵)</strong>

称两个矩阵 $A\in M_{m\times n}(K)$ 与 $B\in M_{m\times n}(K)$ 是相抵的, 当且仅当存在可逆矩阵 $P\in M_{m\times m}(K)$ 与 $Q\in M_{n\times n}(K)$ 使得 $B=PAQ$. 

矩阵相抵是解线性方程组的办法. 

</blockquote>

<details class="custom-details">
    <summary class="custom-summary">利用相抵标准形解决特定的相似标准形问题</summary>

</details>

>[!Question] 设 $A^2=E$, 求证 $A$ 

## 线性方程组的理论课题

经典代数学有两大课题：一元高次代数方程, 与多元一次代数方程组. 一元方程又叫作线性方程, 故后者也叫作线性方程组. 如今, 代数学的两门基础课程：抽象代数与线性代数, 则分别建立在对此二者的研究上. 

前面铺垫了许多线性代数的知识, 就是在为一次性**完满地**解决线性方程组的理论课题作铺垫. 

### 线性方程组的基本概念与可解性

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(齐次线性方程组)</strong>

数域 $K$ 上的**齐次线性方程组**是具有如下形式的方程组：

$$\left\{\begin{matrix}
 a_{11}x_1+a_{12}x_2+\cdots+a_{1n}x_n=0 &\\
 a_{21}x_1+a_{22}x_2+\cdots+a_{2n}x_n=0 &\\
 \cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot& \\
 a_{m1}x_1+a_{m2}x_2+\cdots+a_{mn}x_n=0 &
\end{matrix}\right.$$

其中 $a_{ij}\in K$. 

$\,$

该方程组的解 $(x_1,x_2,\cdots,x_n)\in K^n$ 称作它的**解向量**, 而矩阵 $A=[a_{ij}]$ 称作它的**系数矩阵**. 

</blockquote>

易见, 解上述齐次线性方程的问题, 又有如下三种等价的描述. 

1. 解向量方程 $$A_{\cdot,1}x_1+A_{\cdot,2}x_2+\cdots+A_{\cdot,n}x_n=0$$

其中 $A_{\cdot,i}$ 是系数矩阵 $A$ 的第 $i$ 列. 

2. 解矩阵方程 $AX=0$, 其中 $X$ 是解向量, $A$ 是系数矩阵. 注意这里等号右边的 $0$ 代表 $O_{m\times 1}$. 

3. 求线性映射

$$f_A\colon K^n \to K^m, X\mapsto AX$$

的零空间 $\ker(f_A)$. 

正如第一章提到的那样, 研究零向量的行为往往能带给我们启发, 对齐次线性方程组的研究也将会启发我们解非齐次线性方程组. 

不难看出, 全体解向量的集合应是 $K^n$ 的子空间. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(解空间与基础解系)</strong>

数域 $K$ 上的齐次线性方程组 $AX=0$ 全体解向量构成的集合是 $K^n$ 的子空间, 称作它的**解空间**, 子空间的一组基称作它的**基础解系**. 

</blockquote>

由线性映射基本定理, 立即得到齐次线性方程组的可解性. 

<blockquote class="quote-style-2"><strong style="color: #28a745;">定理</strong>

数域 $K$ 上的齐次线性方程组的基础解系存在, 包含 $n-\mathrm{rank}(A)$ 个解向量, 其中 $A$ 为其系数矩阵. 

</blockquote>

接着考虑非齐次线性方程组的情况. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(非齐次线性方程组)</strong>

数域 $K$ 上的**非齐次线性方程组**是具有如下形式的方程组：

$$\left\{\begin{matrix}
 a_{11}x_1+a_{12}x_2+\cdots+a_{1n}x_n=b_1 &\\
 a_{21}x_1+a_{22}x_2+\cdots+a_{2n}x_n=b_2 &\\
 \cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot\cdot& \\
 a_{m1}x_1+a_{m2}x_2+\cdots+a_{mn}x_n=b_m &
\end{matrix}\right.$$

其中 $a_{ij}\in K$, $B=(b_1,b_2,\cdots,b_m)\ne O_{m\times 1}$. 

$\,$

该方程组的解 $(x_1,x_2,\cdots,x_n)\in K^n$ 称作它的**解向量**, 矩阵 $A=[a_{ij}]$ 称作它的**系数矩阵**, 而矩阵 $\begin{bmatrix}
 A & B
\end{bmatrix}$ 称作它的**增广矩阵**, 记作 $\bar A$. 

</blockquote>

易见, 解上述非齐次线性方程的问题, 也有如下三种等价的描述. 

1. 解向量方程 $$A_{\cdot,1}x_1+A_{\cdot,2}x_2+\cdots+A_{\cdot,n}x_n=B$$

其中 $A_{\cdot,i}$ 是系数矩阵 $A$ 的第 $i$ 列. 

2. 解矩阵方程 $AX=B$, 其中 $X$ 是解向量, $A$ 是系数矩阵. 

3. 求 $B$ 在线性映射

$$f_A\colon K^n \to K^m, X\mapsto AX$$

下的逆像 $f_A^{-1}(B)$. 

尽管 $f_A^{-1}(B)$ 不再是 $K^n$ 的子空间, 但它可以看作 $\ker(f_A)$ 的一个平移, 具体地说, 如果找到了一个 $X_0\in f_A^{-1}(B)$, 那么

$$f_A^{-1}(B) = X_0 + \ker(f_A)= \{X_0+X\mid X\in \ker(f_A)\}$$

为此, 我们有如下定义. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(特解与导出方程组)</strong>

数域 $K$ 上的非齐次线性方程组 $AX=B$ 任意一个解向量称作它的**特解**, 而齐次线性方程组 $AX=0$ 称作它的**导出方程组**. 

</blockquote>

我们知道, 导出方程组的基础解系存在, 故只要确定存在一个特解, 就能断言非齐次线性方程组的解集存在. 为此, 我们有如下的判别定理. 

<blockquote class="quote-style-2"><strong style="color: #28a745;">定理(判别定理)</strong>

非齐次线性方程组有解的充分必要条件是 $r(A)=r(\bar A)$. 

</blockquote>

### 矩阵消元法

前已讨论过线性方程组的可解性, 得出的结论是：齐次线性方程组的基础解系存在；非齐次线性方程组的特解存在的充分必要条件是 $r(A)=r(\bar A)$, 其解集是导出方程组的解空间在特解上的平移. 

本小节重点讨论如何将线性方程组的解找出, 为此, 我们先从线性方程组的同解变换入手. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(矩阵的初等行变换)</strong>

设 $A\in M_{m\times n} (K)$, 则下述三种变换称作矩阵 $A$ 的初等行变换：

- （交换变换）交换 $A$ 的 $i,j$ 两行；
- （倍乘变换）将 $A$ 的第 $i$ 行变为 $k$ 倍, 其中 $k\in K^*$；
- （倍加变换）将 $A$ 的第 $i$ 行加上第 $j$ 行的 $k$ 倍, 其中 $k\in K$. 

</blockquote>

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(初等行变换是同解变换)</strong>

</blockquote>

上述命题当然可以通过计算证明, 但我们愿意引入另一种观点来看待初等行变换, 并同样说明此事, 故而直接计算的工作留给读者. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(初等行变换是左乘初等矩阵)</strong>

</blockquote>

初等矩阵 $P$ 是可逆的, 故变换前的方程 $AX=B$ 与变换后的方程 $PAX=PB$ 等价, 自然同解. 

现在, 看看对矩阵不断进行初等行变换会发生什么. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(行阶梯形)</strong>

</blockquote>

矩阵的行阶梯形与它左相抵, 其可以由上述 Gauss 消元法求出. 得到行阶梯形后, 我们便可以用**回代法**求解. 

Gauss 消元法已经完成了, 下面的步骤来自 Jordan. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(行简化阶梯形)</strong>

</blockquote>

行简化阶梯形存在且唯一, 其可以由上述 Gauss-Jordan 消元法求出. 得到行简化阶梯形后, 我们便可以直接求解. 

### 相抵标准形

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(标准形)</strong>

形如 的矩阵被称作标准形. 

</blockquote>

上述讨论已指明了相抵标准形的存在性. 

### 矩阵求逆

### 用矩阵乘法看待 Gauss 消元法：矩阵的 LU 分解

# 内积空间与正交性

## 内积与范数

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(内积)</strong>

设 $V$ 是数域 $K$ 上的一个线性空间, 若函数

$$
⟨\cdot ⟩ \colon V\times V \to K , (u,v)\mapsto ⟨u,v⟩
$$

满足如下四条性质：

- （**正性**）$⟨v,v⟩\in \mathbb R_{\ge 0},\forall v\in V$；
- （**定性**）$⟨v,v⟩=0\iff v=0_V,\forall v\in V$；
- （**共轭对称性**）$⟨u,v⟩=\overline{⟨v,u⟩},\forall u,v\in V$；
- （第一个位置上的**线性性**）$$⟨u+v,w⟩=⟨u,w⟩+⟨v,w⟩,\forall u,v,w\in V$$
$$⟨ku,v⟩=k⟨u,v⟩,\forall u,v\in V,\forall k\in K. $$

则称函数 $⟨\cdot⟩$ 是 $V$ 上的一个**内积**, 并称 $(V,⟨\cdot⟩)$ 为一个**内积空间**. 

</blockquote>

由第一个位置上的线性性与共轭对称性不难推知, 内积在第二个位置上也具有可加性, 但不具有齐次性, 仅具有共轭齐次性. 

故而, 实向量空间上的内积是双线性泛函, 而当 $K\not \subseteq\mathbb R$ 时则未必. 

<details class="custom-details">
    <summary class="custom-summary">为什么不将内积空间定义成双线性泛函？</summary>

双线性、正定性与对称性同时满足的函数在复内积空间上找不到. 复内积空间又称作酉空间, 我们会在很后面才开始细致研究它, 事实上下一节的许多结论都是在实内积空间上的. 

</details>

<details class="custom-details">
    <summary class="custom-summary">内积空间的例子</summary>

（1）$\mathbb R^n$ 上的 **Euclid 内积**定义为

$$ ((a_1,\cdots,a_n),(b_1,\cdots,b_n)) \mapsto a_1b_1+\cdots+a_nb_n$$

此即我们熟悉的向量点积. 这使得 Euclid 空间成为内积空间, 一般而言我们在 Euclid 空间上总是采取此种内积. 

</details>

每种内积都可诱导出一种范数, 我们先给出范数的定义. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(范数)</strong>

- （**正性**）
- （**定性**）
- （**绝对齐次性**）
- （**次可加性**, 或称**三角不等式**）

**范数**(norm), **赋范线性空间**. 

</blockquote>

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(内积空间上的范数)</strong>

设 $(V,⟨\cdot⟩)$ 为数域 $K$ 上的内积空间, 则函数

$$||\cdot||\colon V\to K , v\mapsto ||v||:=\sqrt{⟨v,v⟩}. $$

是 $V$ 上的一个范数. 

</blockquote>

<details class="custom-details">
    <summary class="custom-summary">证明</summary>

</details>

一般而言, 在内积空间上, 我们采取内积诱导出的范数. 

不难注意到, 内积是点积的推广, 范数是长度的推广, 而解析几何中向量之间还有夹角这一属性. 推广夹角到一般的内积空间中, 则需要下述的著名不等式. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(Cauchy-Schwarz 不等式)</strong>

$$|⟨u,v⟩|\le ||u||\cdot||v||$$

</blockquote>

<details class="custom-details">
    <summary class="custom-summary">Cauchy-Schwarz 不等式之例</summary>

Cauchy-Schwarz 不等式在不同的内积下有许多不同的形式. 

</details>

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(夹角与正交)</strong>

向量 $u$ 与 $v$ 的**夹角**定义为

$$\theta_{u,v}:= \arccos \frac{⟨u,v⟩}{||u||\cdot ||v||}$$

$\displaystyle \theta_{u,v}=\frac \pi 2$ 时, 亦即 $⟨u,v⟩=0$ 时, 称 $u$ 与 $v$ 是**正交**的. 

</blockquote>

接着推广一些我们熟悉的命题. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(勾股定理)</strong>

设 $V$ 为数域 $K$ 上的内积空间, 则对 $u,v\in V$, 若 $⟨u,v⟩=0$, 则 $||u^2||+||v^2||=||u+v||^2$. 

</blockquote>

<details class="custom-details">
    <summary class="custom-summary">证明</summary>

稍加计算即可得到, 因内积之双线性, 有

$$ \begin{aligned}
    ||u+v||^2 & =⟨u+v,u+v⟩ \\
    & = ⟨u,u+v⟩+⟨v,u+v⟩ \\ 
    & = ⟨u,u⟩+⟨u,v⟩+⟨v,u⟩+⟨v,v⟩ \\
    & = ⟨u,u⟩+⟨v,v⟩ \\
    & = ||u||^2+||v||^2
\end{aligned}.$$

</details>

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(正交分解)</strong>

</blockquote>


## 标准正交基与 Gram-Schmidt 过程

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(正交向量组)</strong>

正交向量组中的向量非零且两两正交. 

</blockquote>

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(正交向量组线性无关)</strong>

</blockquote>

<details class="custom-details">
    <summary class="custom-summary">证明</summary>

据线性相关性引理, 反设正交向量组中的一向量 $v$ 可被前面的向量线性表示, 即

$$v=\sum_{i=1}^n k_iv_i$$

两边同与 $v$ 作内积, 据内积之双线性有

$$
⟨v,v⟩=\sum_{i=1}^n k_i⟨v_i,v⟩=0
$$

故由正定性 $v=0_V$, 与正交向量组的定义矛盾！

</details>

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(正交基与标准正交基)</strong>

</blockquote>

标准, 也即规范, 亦即单位. 

不难看到, 欧氏空间（取内积为 Euclid 内积）中的标准基就是一组标准正交基. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(有限维内积空间必有正交基)</strong>

</blockquote>

<details class="custom-details">
    <summary class="custom-summary">证明</summary>

运用归纳法. $\dim V=1$ 时命题显然成立, 设 $\dim V=n$ 时命题成立, 对于 $\dim V= n+1$ 的情形, 取 $V$ 的 $n$ 维子空间 $U$, 据归纳假设, $U$ 存在一组正交基 $(u_1,u_2,\cdots,u_n)$, 只需找到一 $v\in V$ 使得 $⟨v,u_i⟩=0,i=1,2,\cdots,n$ 即可. 

为此, 设 $(u_1,u_2,\cdots,u_n)$ 可扩充为 $V$ 的一组基 $(u_1,u_2,\cdots,u_n,u_{n+1})$, 注意 $u_{n+1}$ 未必就是所求的 $v$, 如下图：

<暂缺, $\mathbb R^3$ 的特例>

但, 我们设

$$ v= \sum_{i=1}^{n+1} k_{i}u_{i}$$

两边同与 $u_1,u_2,\cdots,u_n$ 作内积, 得

$$ 0 = k_i||u_i||^2 + k_{n+1}⟨u_{n+1},u_i⟩,i=1,2,\cdots,n$$

故

$$k_i = -\frac{⟨u_{n+1},u_i⟩}{||u_i||^2}k_{n+1},i=1,2,\cdots,n$$

上式中 $u_{n+1},u_i$ 均为定值, 故而只需任取 $k_{n+1}\in K^*$ 即有所求的 $v$. 

</details>

我们也不难将基扩张定理推广到正交的情形, 利用替换引理易证. 

<blockquote class="quote-style-2"><strong style="color: #28a745;">定理(正交基扩张定理)</strong>

设 $V$ 为数域 $K$ 上的有限维内积空间, 又设 $U$ 是 $V$ 的子空间, 则 $U$ 的任一组正交基 $(u_1,\cdots,u_m)$ 都可以扩充为 $V$ 的一组正交基 $(u_1,\cdots,u_m,w_1,\cdots,w_n)$. 

</blockquote>

不难看到, $\mathrm{span}(w_1,\cdots,w_n)$ 作为 $U$ 的补空间, 其中的向量均与 $U$ 中的任一向量正交, 据此引出如下定义. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(正交补)</strong>

设 $V$ 为数域 $K$ 上的有限维内积空间, 又设 $U$ 是 $V$ 的子空间, 则称集合

$$W:=\{v\in V \mid ⟨u,v⟩=0,\forall u\in U\}$$

为 $U$ 的**正交补**, 记作 $U^\perp := W$. 

</blockquote>

你应自行验证, 上述正交基扩充定理中的 $\mathrm{span}(w_1,\cdots,w_n)$ 包含了全体与 $U$ 中任一向量正交的向量, 从而就是 $U^\perp$, 此即一种求取正交补的办法. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(正交补的基本性质)</strong>

设 $V$ 为数域 $K$ 上的有限维内积空间, 又设 $U$ 是 $V$ 的子空间, 则

- $U^\perp$ 是 $V$ 的子空间；
- $U\oplus U^\perp = V$, 故 $U^\perp$ 又称作 $U$ 的正交补空间；
- $(U^\perp)^\perp =U$. 

</blockquote>

> 均显然. 

<推广的正交分解与分量、勾股定理与 Bessel 不等式>

我们已经看到标准正交基是如此便利, 然而该如何找到它们呢？下述命题给出了将内积空间的任意一组基转化为标准正交基的办法. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(Gram-Schmidt 过程)</strong>

设 $(v_1,v_2,\cdots,v_n)$ 是一组基, 记 $q_1:=v_1$, 归纳地定义 $q_r$ 如下：

$$q_r := v_r - \sum_{k=1}^{r-1}\frac{⟨v_r,q_k⟩}{||q_k||^2}q_k$$

则 $(q_1,q_2,\cdots,q_n)$ 是正交向量组. 令

$$\tilde q_r:= \frac{q_r}{||q_r||}$$

即得一组标准正交基 $(\tilde q_1,\tilde q_2,\cdots,\tilde q_n)$. 

</blockquote>

从直观上看, 上述过程将 $v_r$ 变为 $q_r$ 的办法就是将 $v_r$ 在 $q_1,q_2,\cdots,q_{r-1}$ 方向上的投影全部减掉. 

## 正交矩阵与 QR 分解

对于 $n$ 维内积空间 $V$, 将一组标准正交基的坐标作为列向量排成的矩阵 $Q$ 将满足 $Q^TQ=E$, 这引导我们作此定义. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(正交矩阵)</strong>

$n$ 阶方阵 $Q$ 是正交的, 当且仅当 $Q^TQ=E_n$. 

</blockquote>

注意到逆矩阵相关的命题, 对于正交矩阵 $Q$, 必有 $Q^{-1}=Q^T$. 

## 最优化问题？

# 行列式

由于 Cramer 法则能有效地解决方程数目与未知量数目相同的方程组的问题, 在很长一段时间内, 行列式及其计算都是线性代数研究的主题. 

## 引子：积分学中的“有向面积”与“有向体积”

<补充见下>

## ？

### 行列式函数的定义与性质

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(行列式函数)</strong>

设函数

$$f \colon M_n(K)\to K , [v_1,v_2,\cdots,L_n]\mapsto f ([v_1,v_2,\cdots,L_n])$$

- （**列线性**）$$\lambda f([\cdots,v_i,\cdots])+\mu f([\cdots,\beta_i,\cdots])=f([\cdots,\lambda v_i+\mu\beta_i,\cdots])$$；
- （**反对称**）
- （**归一化条件**）$f(E_n)=1$. 

则称 $f$ 是 $M_n(K)$ 上的一个**行列式函数**. 

</blockquote>

我们先假定存在这样的行列式函数, 并研究若行列式函数存在则应有何种性质. 下一节中再通过所谓行列式完全展开来说明其确实存在. 

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(行列式函数的基本性质)</strong>

1. （不可逆矩阵行列式为零）若 $A$ 不可逆，亦即 $\mathrm{rank}(A)<n$，则 $\det(A)=0$;  
2. （唯一性）$M_n(K)$ 上唯一的行列式函数记作 $\det_n$, 然而时时也省略下标写作 $\det$；
3. （保乘法）$\det(AB)=\det(A)\det(B)$. 

</blockquote>

> 提示：先考虑行列式函数在初等矩阵处的值。

<details class="custom-details">
    <summary class="custom-summary">证明</summary>

</details>

根据反对称性，交换矩阵两列，行列式函数的值取负号，故 $f(P(i,j))=-1$；根据列线性，将一列乘以 $k(k\in K^*)$，行列式函数的值乘以 $k$，故 $f(P(k\dot i)=k)$；根据列线性与反对称性，知倍乘矩阵行列式为 $1$。

**证明1** 设 $\det(A)=0$

**证明2** 反设 $n\in\mathbb N_+$ 且 $M_n(K)$ 上存在两个函数 $f$ 与 $g$ 均为行列式函数，只要证对任何 $A\in M_n(K)$ 都有 $f(A)=g(A)$. 

若 $A$ 不满秩，根据（1）有 $f(A)=g(A)=0$. 若 $A$ 满秩，设 $A=P1_P2_\cdots P_n$

据 $QR$ 分解可知, $\det(A)=\det(Q)\det(R)$, 正交矩阵 $Q$ 满足 $Q^TQ=E$ 故 $\det(Q)=\pm 1$, 而对角线非负值上三角矩阵 $R$ 满足 $\det(R)\ge 0$. 故 $\det(Q)$ 表达的就是所谓“有向面积/体积”的“向”, 而 $\det(R)=|\det(A)|$ 是所谓“有向面积/体积”的“积”. 

### 行列式函数的存在性

行列式的展开(Laplace)

异乘变零？

下面的结果来自 Leibniz. 

<blockquote class="quote-style-2"><strong style="color: #28a745;">定理(行列式完全展开)</strong>

$$\det(A)=\displaystyle \sum_{\sigma\in\mathrm S(n)}(-1)^{\mathrm{sgn}(\sigma)}\prod_{k=1}^n a_{k\sigma_k}$$

</blockquote>

上式仅依赖于矩阵 $A$, 这说明行列式函数确实是存在的. 据行列式函数的唯一性, 事实上也有

$$\displaystyle \sum_{\sigma\in\mathrm S(n)}(-1)^{\mathrm{sgn}(\sigma)}\prod_{k=1}^n a_{k\sigma_k}=\det(A)=\displaystyle \sum_{\sigma\in\mathrm S(n)}(-1)^{\mathrm{sgn}(\sigma)}\prod_{k=1}^n a_{\sigma_kk}$$

### *算子的行列式（不依赖基）

### 分块矩阵的行列式

## 行列式的应用

### Cramer 法则

矩阵消元法太慢了.jpg

对于无需求基础解系的情况, 即 $n=r$, 利用行列式可快速求特解. 

<blockquote class="quote-style-2"><strong style="color: #28a745;">定理(Cramer 法则)</strong>

</blockquote>

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(伴随矩阵)</strong>

</blockquote>

# 多项式（鸽）


<blockquote class="quote-style-2"><strong style="color: #28a745;">定理(Vieta 定理, 根与系数的关系)</strong>

设数域 $K$ 上的一元 $n$ 次代数方程 $\displaystyle \sum_{r=0}^n a_rx^r=0(a_n\ne 0,n\in\mathbb N_+)$ 在 $\mathbb C$ 上的 $n$ 个根分别为 $x_1,x_2,\cdots x_n$, 则

$$
\frac {a_{n-r}}{a_n}=(-1)^{r}\sum_{1\le i_1<i_2<\cdots<i_r\le n}\prod_{k=1}^ra_{i_k}
$$

特别地, 当 $n=2$ 时有（中学生熟知的）一元二次方程的韦达定理：

$$
-\frac {a_1}{a_2}=x_1+x_2,\quad\frac {a_0}{a_2}=x_1x_2
$$

</blockquote>

<blockquote class="quote-style-2"><strong style="color: #28a745;">定理(代数学基本定理)</strong>

</blockquote>

# 特征值与特征向量

在[线性映射与矩阵](#线性映射与矩阵)一章中, 我们宽泛地研究了一般的线性映射．本章我们主要研究线性变换（或称线性算子, 本章中简称算子）, 即一个线性空间到其本身的线性映射, 以及相关的特征值理论．

回顾先前出现过的引子. 设甲乙两地最初分别拥有 $x_1,x_2$ 人口. 每年, 甲地 $40\%$ 的原住民迁移至乙地, 而乙地 $10\%$ 的原住民迁移至甲地, 用映射表示如下

$$T\colon \mathbb R^2\to\mathbb R^2, (x_1,x_2)\mapsto (0.6x_1+0.1x_2,0.4x_1+0.9x_2)$$

那么, 向量值序列 $\displaystyle a_n:= T^n(x_1,x_2)$ 的极限 $\displaystyle \lim_{n\to\infty} a_n$ 是否存在？若存在, 如何求出？

注意到，若存在 $\mathbb R^2$ 的一组基 $v_1,v_2$ 满足 $T(v_i)=\lambda_i v$，那么，根据线性映射的性质，有

$$
\begin{aligned}
    T(k_1v_1+k_2v_2) &= k_1\lambda_1v_1)+k_2\lambda_2v_2  \\
    T^2(k_1v_1+k_2v_2) & = k_1\lambda_1^2v_1+k_2\lambda_2^2v_2 \\
    & \cdots \\
    T^n(k_1v_1+k_2v_2) & = k_1\lambda_1^nv_1+k_2\lambda_2^nv_2 \\
\end{aligned}
$$

由于 $(v_1,v_2)$ 是一组基，$k_1v_1+k_2v_2$ 可以取遍 $\mathbb R^2$ 中的所有向量，那么，我们得知了 $a_n$ 的紧凑形式，其极限行为也尽在掌握了。

现在, 考虑满足 $T(v_i)=\lambda_i v_i$ 的 $v\in \mathbb R^2(v\ne (0,0))$ 与 $\lambda_i \in \mathbb R$, 符合该条件的向量 $v_1,v_2$ 称作算子 $T$ 的**特征向量**。不难解出：

$\lambda_1 =1$, $v_1=(4,1)$; $\lambda_2 = 0.5$, $v_2=(1,-1)$. 

设 $(x_1,x_2)=k_1v_1+k_2v_2$，解得 $\displaystyle k_1=\frac {x_1+x_2}{5},k_2=\frac {x_1-4x_2}{5}$，故

$$
a_n=T^n(x_1,x_2)=\frac {x_1+x_2}{5}(4,1)+\frac {1}{2^n}\cdot \frac {x_1-4x_2}{5}(1,-1)
$$

不难得出 $\displaystyle \lim_{n\to\infty} a_n =(\frac {4x_1+4x_2}{5},\frac {x_1+x_2}{5})$. 

现在，我们更换一种视角来看待这个问题. 

我们知道 $T$ 在标准基 $((1,0),(0,1))$ 下的表示矩阵是 $M(T)=\begin{bmatrix}
 0.6 & 0.1\\
 0.4 &0.9
\end{bmatrix}$, 故上述极限又等于 $\displaystyle \lim_{n\to\infty} \begin{bmatrix}
 0.6 & 0.1\\
 0.4 &0.9
\end{bmatrix}^n \begin{bmatrix}
 x_1\\
 x_2 
\end{bmatrix}$. 那么, 只需想办法计算 $(M(T))^n$. 回忆先前提及的相似，若能找到一个易于计算幂次的 $\Lambda$，使得

$$M(T)=P^{-1}\Lambda P$$

换言之，找到一个与 $M(T)$ 相似的 $\Lambda$, 那么 $(M(T))^n=P^{-1}\Lambda^n P $. 

能否找到一组恰当的基 $(v_1,v_2)$, 使得 $\Lambda = M(T,(v_1,v_2))$ 是一个较为容易计算幂的矩阵呢？这样, 根据基变换公式

$$M(T,\eta_2)=P^{-1}M(T,(v_1,v_2))P$$

其中 $P=M(T,(v_1,v_2),\eta_2)$ 是标准基到 $(v_1,v_2)$ 的过渡矩阵. 这样, $\displaystyle\lim_{n\to\infty} a_n$ 就可以写作

$$
\lim_{n\to\infty} P^{-1} \Lambda^n P\begin{bmatrix}
 x_1\\
 x_2 
\end{bmatrix}
$$

现在, 考虑满足 $T(v)=\lambda v$ 的 $v\in V(v\ne 0_V)$ 与 $\lambda \in K$, 不难解出：

$\lambda_1 =1$, 对应的 $v_1= \begin{bmatrix}
 4\\
 1 
\end{bmatrix}$；

$\lambda_2 = 0.5$, 对应的 $v_2 = \begin{bmatrix}
 1\\
 -1 
\end{bmatrix}$.

易见 $(v_1,v_2)$ 线性无关, 而 $T(v_i)=\lambda_i v_i(i=1,2)$, 故在这组基下 $(v_1,v_2)$ 有 $M(T,(v_1,v_2))=\begin{bmatrix}
 1 & 0\\
 0 & 0.5 
\end{bmatrix}$. 这是一个对角矩阵, 作 $n$ 次幂只需将对角线上元素均作 $n$ 次幂即可, 即为所求的 $\Lambda$. 又不难求出过渡矩阵 $\displaystyle P= \begin{bmatrix}
 \displaystyle \frac 15 & \displaystyle \frac 15\\
 \displaystyle \frac 15 & \displaystyle -\frac 45 
\end{bmatrix}$, 于是

$$\lim_{n\to\infty}a_n = \begin{bmatrix}
 4 & \displaystyle 1\\
 1 & \displaystyle -1
\end{bmatrix}\begin{bmatrix}
 1 & 0\\
 0 & \displaystyle \frac 1{2^n} 
\end{bmatrix}\begin{bmatrix}
 \displaystyle \frac 15 & \displaystyle \frac 15\\
 \displaystyle \frac 15 & \displaystyle -\frac 45 
\end{bmatrix}\begin{bmatrix}
 x_1\\
 x_2 
\end{bmatrix}$$

计算可得 $\displaystyle \lim_{n\to\infty} a_n = \begin{bmatrix}
 \displaystyle \frac {4x_1+4x_2}{5}\\
 \displaystyle \frac {x_1+x_2}{5}
\end{bmatrix}$, 即最终甲地的人口将趋于总人口的 $80\%$, 而乙地的人口将趋于总人口的 $20\%$. 

## 基本概念

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(算子的特征值与特征向量)</strong>

设 $V$ 是数域 $K$ 上的一个线性空间, 设 $T\in \mathcal L(V)$, 若存在 $\lambda \in K$ 与 $v\in V^*$ 满足 $T(v)=\lambda v$, 则称 $\lambda$ 为算子 $T$ 的一个**特征值**, 并称 $v$ 为属于特征值 $\lambda$ 的一个**特征向量**, 又称序对 $(\lambda,v)$ 称作算子 $T$ 的一个**特征对**. 

</blockquote>

> $V^*$ 表示线性空间 $V$ 去掉零向量, 即 $V\backslash \{0_V\}$. 

由上述定义立刻知道, 特征值与特征向量之间是一对多的关系：一个特征向量只能属于一个特征值, 但一个特征值却能对应多个特征向量. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(特征子空间)</strong>

设 $V$ 是数域 $K$ 上的一个线性空间, 设 $T\in \mathcal L(V)$, 对任一 $\lambda \in K$, 定义

$$V_\lambda := \{ v \in V \mid T(v)=\lambda v\}$$

不难验证 $V_\lambda$ 为 $V$ 的子空间, 且 $\lambda$ 为 $T$ 的特征值当且仅当 $V_\lambda\ne \{0_V\}$. 此时称 $V_\lambda$ 为算子 $T$ 关于特征值 $\lambda$ 的**特征子空间**. 

</blockquote>

因此, 我们说“$v$ 是属于特征值 $\lambda$ 的特征向量”, 实际上是在说 $v\in V_\lambda$. 

我们知道, 在有限维线性空间上, 对线性映射所作的计算都可以在取定了基之后落实到矩阵的运算上来. 对于算子 $T\in\mathcal L(V)$, 为求其特征值, 我们可以为 $V$ 指定一组基 $L_n$, 并求矩阵 $M(T,L_n,L_n)$, 由

$$M(T(v),L_n)=M(T,L_n,L_n)M(v,L_n)$$

若 $T(v)=\lambda v$, 代入上式, 则

$$
\lambda M(v,L_n)=M(T,L_n,L_n)M(v,L_n)
$$

故而, 只要找到那样的 $M(v,L_n)\in K^n$ 与 $\lambda\in K$ 满足 $\lambda M(v,L_n)=M(T,L_n,L_n)M(v,L_n)$, 就找到了特征值 $\lambda$ 与属于它的特征向量 $L_n$. 为此, 有如下定义. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(矩阵的特征值和特征向量)</strong>

$A\in M_n(K)$，若存在 $X\in K^n$ 使得 $AX=\lambda X$，则称。

</blockquote>

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(特征值与特征向量是联系算子与矩阵的桥梁)</strong>

设 $K$ 是一个数域，$V$ 是 $K$ 上的有限非零维线性空间，又设算子 $T\in\mathcal L(V)$ 与矩阵 $A\in M_n(K)$ 满足在 $V$ 的一组基 $L_n=(v_1,v_2,\cdots,v_n)$ 下有 $M(T,L_n)=A$. 那么, 

- 若 $(\lambda,v)$ 是 $T$ 的特征对，则 $(\lambda,M(v,L_n))$ 也是 $A$ 的特征对；
- 若 $(\lambda,X)$ 是 $A$ 的特征对，其中 $X=(x_1,x_2,\cdots,x_n)$，则 $(\lambda,\displaystyle \sum_{i=1}^n x_iv_i)$ 也是 $T$ 的特征对. 

</blockquote>

因此, 特征值与特征向量是联系算子与矩阵的桥梁——一方面, 同一个相似等价类中的矩阵的特征值与特征向量相同, 因为它们是同一个算子在不同基下的表示矩阵；另一方面, 不同的算子的特征值与特征向量相同, 说明它们在不同基下存在相同的表示矩阵. 

若算子 $T\in \mathcal L(V)$ 存在特征值 $\lambda$, 则 $\lambda I_V-T$ 不为单射. 当 $V$ 是有限维线性空间时, 这表明 $T$ 不为双射. 故 $\lambda I_V-T$ 在任一组基下的矩阵都不可逆, 亦即

$$\det (\lambda E_n - M(T)) =0$$

其中 $n=\dim V$. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(特征多项式)</strong>

设 $A\in M_n(K)$, 则

$$p_A(\lambda)= \det (\lambda E_n - A)$$

称作矩阵 $A$ 的**特征多项式**. 显然, $A$ 的特征值就是特征多项式在 $K$ 上的根. 

</blockquote>

不难知道，矩阵的特征多项式是相似不变量。

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(相似矩阵具有相同的特征多项式)</strong>

</blockquote>

从而，我们可以定义算子 $T$ 的特征多项式为其在任一组基下的矩阵 $M(T)$ 的特征多项式。

下面展示了一些求算子特征值的例子. 

<details class="custom-details">
    <summary class="custom-summary">求取特征值的例子</summary>

以下假设 $K$ 为数域. 

（1）考虑算子 $T\in \mathcal L(K^2)$ 满足 $T((x,y))=(-y,x)$. 

$T$ 在标准基下的矩阵为 $\begin{bmatrix}
 0 & 1\\
 -1 & 0
\end{bmatrix}$, 容易求得特征多项式 $p(\lambda)=\lambda^2+1$, 解得 $\lambda = \pm \mathrm i$. 

实际上, 若 $K=\mathbb R$, 上述算子即我们熟悉的**旋转变换**, 显然 $\mathbb R^2$ 平面上的任一向量旋转 $\displaystyle \frac \pi 2$ 后都不会与自身共线. 

（2）上、下三角矩阵的特征值是主对角线上的元素. 

（3）考虑矩阵 $A=\begin{bmatrix}
 -7 & -5 & 5 \\
 -2 & 3 &-2 \\
 -10 & 10 & -8 \\
\end{bmatrix}$

</details>

下面的命题给出了任一方阵特征多项式的系数特征。

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(特征多项式的系数特征)</strong>

$A\in M_n(K)$ 的特征多项式

$$\displaystyle p(\lambda)= \sum_{i=0}^n a_i\lambda^i$$

满足 $a_0=(-1)^n\det (A), a_{n-1}=-\mathrm{tr}(A),a_n=1$. 

</blockquote>

<details class="custom-details">
    <summary class="custom-summary">证明</summary>

设 $A=\begin{bmatrix}
 a_{11} & a_{12} & \cdots &  a_{1n}\\
 a_{21} & a_{12} & \cdots & a_{2n} \\
 \vdots & \vdots &  & \vdots \\
 a_{n1} & a_{n2} & \cdots & a_{nn}
\end{bmatrix}$, 则

$$
p_A(\lambda)= \det(\begin{bmatrix}
 \lambda-a_{11} & -a_{12} & \cdots &  -a_{1n}\\
 -a_{21} & \lambda-a_{12} & \cdots & -a_{2n} \\
 \vdots & \vdots &  & \vdots \\
 -a_{n1} & -a_{n2} & \cdots & \lambda-a_{nn}
\end{bmatrix})
$$

由行列式的完全展开式知，$\lambda^n$ 与 $\lambda^{n-1}$ 只能来自完全展开中的 $\displaystyle \prod_{i=1}^n (\lambda - a_{ii})$ 项，易见 $a_n=1$，而 $a_{n-1}=-\mathrm{tr}(A)$. 

另一方面，令 $\lambda=0$，得 $a_0 = \det(-A)$，即 $a_0=(-1)^n\det(A)$. 

</details>

<blockquote class="quote-style-3"><strong style="color: #dc3545;">推论</strong>

迹是特征值的和，行列式是特征值的积（计重数）. 

有限维线性空间上的算子可逆，当且仅当零不是它的特征值。

</blockquote>

上述推论由 Vieta 定理易证。

>不知道放哪的小寄巧？$A$ 是矩阵，$x$ 是序对，$Ax$ 的共轭等于 $A$ 的共轭乘 $x$ 的共轭. 


<blockquote class="quote-style-2"><strong style="color: #28a745;">定理(Gershgorin 圆盘定理)</strong>

设 $K$ 是一个数域, $A\in M_n(K)$. 集合

$$S_i=\{ z\in K \mid |z-a_{ii}|\le \sum_{\substack {j=1\\ j\ne i}}^n |a_{ij}| \}$$

称作一个 Gershgorin 圆盘. 则对于 $A$ 的特征值 $\lambda$, 有 $\displaystyle \lambda \in \bigcup_{i=1}^n S_i$. 

</blockquote>

> 当 $K=\mathbb C$ 时, 上述的 $S_i$ 是一个闭圆盘. 

讲真，我并不知道这定理有什么用，但两本教材都介绍了（且不给例题），还是写进来吧.jpg 

事实上 Gershgorin 圆盘定理的一个应用是证明严格对角占优矩阵可逆，但……除此之外它真的有用吗（）

<details class="custom-details">
    <summary class="custom-summary">证明</summary>

根据上述定理，严格对角占优矩阵不可能以零为特征值，从而必定可逆. 

</details>

</blockquote>

## 可对角化算子

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(可对角化算子)</strong>

若算子 $T\in\mathcal L(V)$ 在某组基下的矩阵是对角矩阵，则称算子 $T$ **可对角化**. 

</blockquote>

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(可对角化矩阵与谱分解)</strong>

若矩阵 $A$ 相似于某个对角矩阵 $\Lambda$，亦即 $A=P^{-1}\Lambda P$，则称 $P$ 把 $A$ 对角化，并称上式为矩阵 $A$ 的**谱分解**。

</blockquote>

本章之初的讨论已经指明了，要实现对角化，或者说，谱分解，其关键是找到由特征向量构成的一组基。因此，下述定理其实是显而易见的。

<blockquote class="quote-style-2"><strong style="color: #28a745;">定理(可对角化的充要条件)</strong>



</blockquote>

根据上述定理，我们立刻提出一个可对角化的充分条件。

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(特征子空间的和是直和)</strong>

换言之，属于不同特征值的特征向量线性无关. 

</blockquote>

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(线性空间能被写成特征子空间的直和等价于算子可对角化)</strong>

对复向量空间 $V$，$T$ 可对角化当且仅当

$$\bigoplus_{\lambda\in K} V_\lambda= \bigoplus_{i\in 1}^k V_{\lambda_i}=V$$

若 $V$ 有限维, 则又等价于

$$\sum_{i=1}^k\dim V_{\lambda_i}=\dim V$$

</blockquote>

<details class="custom-details">
    <summary class="custom-summary">证明</summary>

证法一：反设 $(v_1,v_2,\cdots,v_n)$ 线性相关, 根据特征向量不为零向量知 $n\ge 2$, 设

$$
k_1v_1+k_2v_2+\cdots+k_nL_n=0_V
$$

由线性相关的定义, 存在一个 $r\in \{1,2,\cdots,n\}$ 使得 $k_r\ne 0$, 于是

$$
k_rv_r= - \sum_{\substack{i=1 \\ i\ne r}}^n k_iv_i
$$

两边同时以线性映射 $T-\lambda_r I_V$ 作用, 得

$$
(T-\lambda_r I_V)(k_rv_r)= - (T-\lambda_r I_V)(\sum_{\substack{i=1 \\ i\ne r}}^n k_iv_i)
$$

由于 $T(v_i)=\lambda_i v_i$, 上式等价于

$$
0_V = \sum_{\substack{i=1 \\ i\ne r}}^n k_i(\lambda_r-\lambda_i)v_i
$$

注意, 特征向量 $v_i\ne 0$, 而根据题设, $\lambda_r-\lambda_i \ne 0$, 而这 $n-1$ 个 $k_i$ 也不能全为 $0$（否则 $k_rv_r=0_V$, 与 $v_r$ 为特征向量矛盾！）. 换言之, 这组长度为 $n-1$ 特征向量的线性相关, 即若原命题当 $n\in\mathbb N_{\ge 2}$ 时不成立, 必然对 $n-1\in\mathbb N_+$ 也不成立, 这与自然数的良序性矛盾. 

证法二：坐标化. 换言之，取一组基 $(v_1,v_2,\cdots,v_n)$，记 $A$ 是 $T$ 在这组基下的矩阵, 又设 $v_1,v_2,\cdots,L_n$ 在这组基下的坐标为 $X_1,X_2,\cdots,X_n\in M_n(K)$，设

$$\sum_{k=1}^n r_kX_k=0$$

上式两边左乘矩阵 $A$，直到重复 $n-1$ 次，可得


$$\left\{\begin{array}{rcr}
\displaystyle\sum_{k=1}^n r_kX_k =& r_1X_1+r_2X_2+\cdots+r_nX_n&=O_{n\times 1}\\
\displaystyle A\times\sum_{k=1}^n r_kX_k =& \lambda_1r_1X_1+\lambda_2r_2X_2+\cdots+\lambda_nr_nX_n&=O_{n\times 1}\\
\displaystyle A^{n-1}\times\sum_{k=1}^n r_kX_k =& \lambda_1^{n-1}r_1X_1+\lambda_2^{n-1}r_2X_2+\cdots+\lambda_n^{n-1}r_nX_n&=O_{n\times 1}\\
\end{array}\right.$$

用分块矩阵的视角看待矩阵乘法，可将上式转化为

$$\begin{bmatrix}
 r_1X_1 & r_2X_2 & \cdots & r_nX_n
\end{bmatrix} \times \begin{bmatrix}
 1 & \lambda_1 & \cdots & \lambda_1^{n-1}\\
 1 & \lambda_2 & \cdots & \lambda_2^{n-1}\\
 1 & \vdots &  & \vdots\\
 1 & \lambda_n & \cdots & \lambda_n^{n-1}
\end{bmatrix}=O_{n\times n}$$

由于 $\lambda_1,\lambda_2,\cdots,\lambda_n$ 互异，故右边的 Vandermonde 矩阵可逆，得 $r_iX_i=O_{n\times 1}$ 对 $i=1,2,\cdots,n$ 都成立，而 $X_i\ne O_{n\times 1}$，故只能有 $r_i=0$，得证。

</details>

<blockquote class="quote-style-3"><strong style="color: #dc3545;">推论</strong>

具有 $\dim V$ 个互异的特征值是可对角化的充分条件。

</blockquote>

那些没有 $\dim V$ 个互异特征值的算子，也有可能可对角化。

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(代数重数与几何重数)</strong>

设 $p_A(\lambda)$ 可因式分解为 $\displaystyle \prod_{i=1}^k (\lambda - \lambda_{n_i})^{m_i}$，则 $m_i$ 称作特征值 $\lambda_{n_i}$ 的**代数重数**. 

而 $d_i:=\dim \ker (\lambda_{n_i} I-T)$ 称作特征值 $\lambda_{n_i}$ 的**几何重数**. 

</blockquote>

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(几何重数不大于代数重数)</strong>

</blockquote>

由于 $\displaystyle \sum_{i=1}^k m_i = n$，而 $d_i\le m_i$，故若 $\displaystyle \sum_{i=1}^k d_i=n$, 必有 $d_i=m_i$ 对 $i=1,2,\cdots,k$ 均成立，不妨给予定义。

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(半单特征值与亏损特征值)</strong>

</blockquote>

立得下述命题。

<blockquote class="quote-style-3"><strong style="color: #dc3545;">命题(可对角化当且仅当特征值都半单)</strong>

</blockquote>

<details class="custom-details">
    <summary class="custom-summary">证明</summary>



</details>

## Jordan 标准形


<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(零化多项式)</strong>

若多项式 $p$ 满足 $p(T)=0$（代表零算子），称 $p$ 为算子 $T$ 的零化多项式。零化多项式的根是 $T$ 的特征值. 

</blockquote>

## 可交换算子

$AB$ 与 $BA$ 不一定相等，但它们的特征多项式相等. 也即 $\det(\lambda I- AB)=\det(\lambda I-BA)$. 

## 不变子空间

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(不变子空间)</strong>

设 $V$ 为数域 $K$ 上的一个非零维线性空间, $T\in\mathcal L(V)$, 对于 $V$ 的一个子空间 $U$, 若 $T(U)\subseteq U$, 则称 $U$ 为算子 $T$ 的一个**不变子空间**. 

</blockquote>

由定义不难发现, $\{0_V\}$ 与 $V$ 为任何 $T\in\mathcal L(V)$ 的不变子空间. 此外, 对给定的算子 $T$, $\ker(T)$ 与 $\mathrm{ran}(T)$ 也为其不变子空间. 

我们先研究最简单的不变子空间, 即一维不变子空间. 因为任何有限维的不变子空间都可以分解为多个一维不变子空间的直和. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(特征值与特征向量)</strong>

设 $V$ 为数域 $K$ 上的一个非零维线性空间, $T\in\mathcal L(V)$, 若存在 $v\in V$ 且 $v\ne 0_V$ 与 $\lambda\in K$ 使得 $T(v)=\lambda v$, 则称 $v$ 为算子 $T$ 的一个**特征向量**, 并称 $\lambda\in K$ 为 $T$ 的一个**特征值**. 

</blockquote>

不难发现, 只要找到了 $T$ 的一个特征向量 $v$, 则 $\mathrm{span}(v)$ 即为 $T$ 的一个一维不变子空间. 相应地, 只要找到了 $T$ 的一个一维不变子空间 $U$, 则它的基（只需任取其中一个非零向量）就是 $T$ 的一个特征向量. 因此, 下述命题是显而易见的. 

PRO

设 $V$ 为数域 $K$ 上的一个非零维线性空间, $T\in\mathcal L(V)$,.00 则 $T$ 有不变子空间的充分必要条件是 $T$ 有特征值. 

</blockquote>

<details class="custom-details">
    <summary class="custom-summary">求取特征值的例子</summary>

设 $K$ 为数域, $T\in \mathcal L(K^2)$ 满足 $T((x,y))=(-y,x)$. 问 $T$ 是否有特征值？若有, 将其求出. 

假设 $T$ 有特征值 $\lambda$, 则有 $\left\{
    \begin{aligned}
    &\lambda x=-y \\
    &\lambda y=x
    \end{aligned}
\right.$. 

相乘得 $\lambda^2 xy=-xy$, 易见 $xy\ne 0$, 故 $\lambda = \pm i$ 为 $\lambda$ 是特征值的必要条件. 因此, 当 $i\notin K$ 时, $T$ 无特征值. 

当 $i\in K$ 时, 不难证明 $\pm i$ 均为 $T$ 特征值. 

</details>

值得说明的是, 每个特征向量对应着一个一维不变子空间, 并对应着一个特征值. 但同一个特征值却可以对应多个特征向量, 甚至对应一组线性无关的特征向量, 考虑恒等映射即知. 

不过, 我们有如下命题阐释特征值与特征向量的联系. 

PRO(不同特征值对应的特征向量构成的组线性无关)</strong>

设 $T\in\mathcal L(V)$ 存在 $n$ 个特征值 $\lambda_1,\lambda_2,\cdots \lambda_n$, 设 $v_k\in V$ 为一个对应着特征值 $\lambda_k$ 的一个特征向量 $(k=1,2,\cdots n)$, 则向量组 $(v_1,v_2,\cdots,v_n)$ 线性无关. 

</blockquote>

<details class="custom-details">
    <summary class="custom-summary">证明</summary>

反设 $(v_1,v_2,\cdots,v_n)$ 线性相关, 根据特征向量不为零向量知 $n\ge 2$, 设

$$
k_1v_1+k_2v_2+\cdots+k_nL_n=0_V
$$

由线性相关的定义, 存在一个 $r\in \{1,2,\cdots,n\}$ 使得 $k_r\ne 0$, 于是

$$
k_rv_r= - \sum_{\substack{i=1 \\ i\ne r}}^n k_iv_i
$$

两边同时以线性映射 $T-\lambda_r I_V$ 作用, 得

$$
(T-\lambda_r I_V)(k_rv_r)= - (T-\lambda_r I_V)(\sum_{\substack{i=1 \\ i\ne r}}^n k_iv_i)
$$

由于 $T(v_i)=\lambda_i v_i$, 上式等价于

$$
0_V = \sum_{\substack{i=1 \\ i\ne r}}^n k_i(\lambda_r-\lambda_i)v_i
$$

注意, 特征向量 $v_i\ne 0$, 而根据题设, $\lambda_r-\lambda_i \ne 0$, 而这 $n-1$ 个 $k_i$ 也不能全为 $0$（否则 $k_rv_r=0_V$, 与 $v_r$ 为特征向量矛盾！）. 换言之, 这组长度为 $n-1$ 的线性相关, 即若原命题当 $n\in\mathbb N_{\ge 2}$ 时不成立, 必然对 $n-1\in\mathbb N_+$ 也不成立, 这与自然数的良序性矛盾. 

</details>

由此可得一个推论. 

PRO

有限维线性空间上的算子, 特征值数不超过该空间的维数. 

</blockquote>

## 最小多项式

先定义算子的多项式. 

<略>

PRO

设 $T\in\mathcal L(V)$, 而 $p\in P(K)$, 则 $p(T)$ 的零空间与值域均为 $T$ 的不变子空间. 

</blockquote>

THEO(特征值的存在性)</strong>

</blockquote>

> 注意, 对于有限维实向量空间, 可能存在无特征值的算子, 上一节中已经举出了这样的例子（二维实平面中的旋转变换）. 

<blockquote class="quote-style-1"><strong style="color: #007BFF;">定义(最小多项式)</strong>

</blockquote>

