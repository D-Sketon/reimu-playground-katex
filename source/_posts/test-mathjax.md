---
title: 线性方程组解的结构
tags:
  - 线性代数
categories:
  - 线性代数
date: 2024-11-29 01:37:27
excerpt: 一些对于线性代数教材上，线性方程组解的结构章节的看法
---

# 线性方程组解的结构

## 齐次线性方程组解的结构

> 为何要从齐次线性方程组开始研究？
>
> ==（个人见解）齐次线性方程组具有一个已知解$\boldsymbol 0$，并且写成向量形式后能利用线性相关性的知识求解==

设齐次线性方程组
$$
\begin{equation}
\left\{
\begin{gathered}
a_{11}x_1+a_{12}x_2+\cdots+a_{1n}x_n=0\\
a_{21}x_1+a_{22}x_2+\cdots+a_{2n}x_n=0\\
\cdots\cdots\cdots\cdots\\
a_{m1}x_1+a_{m2}x_2+\cdots+a_{mn}x_n=0\\
\end{gathered}
\right.
\label{Eq.1}
\end{equation}
$$
写成矩阵形式
$$
\begin{equation}\boldsymbol{AX}=\boldsymbol{0}\label{Eq.2}\end{equation}
$$
写成向量形式
$$
\begin{equation}x_1\boldsymbol{\alpha}_1+x_2\boldsymbol{\alpha}_2+\cdots+x_n\boldsymbol{\alpha}_n=\boldsymbol0\label{Eq.3}\end{equation}
$$
记$N(\boldsymbol A)$为齐次线性方程组$\eqref{Eq.1}$的全体解向量所构成的解集合，称$N(\boldsymbol A)$的基$\boldsymbol\xi_1,\boldsymbol\xi_2,\cdots,\boldsymbol\xi_{n-r}$为方程组$\eqref{Eq.1}$的**基础解系**

**定理5.2**&emsp;齐次线性方程组$\eqref{Eq.1}$的解集合$N(\boldsymbol A)$是向量空间，并且$N(\boldsymbol A)$的维数是$n-R(\boldsymbol A)$.

> 该定理包含两个部分：==$N(\boldsymbol A)$是向量空间==；==$N(\boldsymbol A)$的维数是$n-R(\boldsymbol A)$==。
>
> ==先证明$N(\boldsymbol A)$是向量空间（通过定义），再去找它的一个基（由此可以求出它的维数）==
>
> 从书上证明过程中引发的几个问题来整理：
>
>  $Q1$. 为什么能设左上角$r$阶子式不为$0$？
>
>  $A1$. 任何矩阵都能由初等行变化变为行阶梯矩阵，对应到线性方程组上即为**方程加减和扩大缩小**，不改变其解，此时可以假定第$i$行的主元就在第$i$列（如果主元不在，则可交换两列，此时只改变的解的顺序，不改变解集的维数）~~写的都是些什么呀（唔，这个定理记住应该就行了吧）~~
> 
> $Q2$. 为什么要/能给 $x_{r+1},x_{r+2},\cdots,x_{n}$ 一组值？
>
>  $A2$. 因为此时只将 $x_1,x_2,\cdots,x_r$ 视为变量，而证明这个定理的最终方式是**找到一个基**，其实就是找到**一些线性无关的向量**，而我们要证明维数是$n-r$，所以前$r$个变量可以不重要（由$P119$推论$4.1$知，只要保证后面$n-r$个分量构成的向量组线性无关，则加上前$r$个分量也无所谓）。方程$(
>7)$的作用就是保证在这种 $x_{r+1},x_{r+2},\cdots,x_
>  {n}$ 取值之下$x_1,x_2,\cdots,x_r$存在。由此使得构造的 $\boldsymbol\xi_1,\boldsymbol\xi_2,\cdots,\boldsymbol\xi_{n-r}$ 线性无关

> $Q3$. 为什么$\boldsymbol \eta$要那样构造？
> 
> $A3$. 其实在证明**如果两个解的后$n-r$个分量相同，则前$r$个分量也相同**，最终的结论应当是 $L(
>\boldsymbol\xi_1,\boldsymbol\xi_2,\cdots,\boldsymbol\xi_{n-r})=N(\boldsymbol A)
>  $ ，一个解最后的$n-r$个分量已经确定了 $\boldsymbol\xi_1,\boldsymbol\xi_2,\cdots,\boldsymbol\xi_
>{n-r}$ 表示这个解的形式，所以最后$n-r$个分量包括了向量组 $\boldsymbol\xi_1,\boldsymbol\xi_2,\cdots,\boldsymbol\xi_
>  {n-r}$ 所有的表示，此时我们必须要让前$r$个分量能被后$n-r$个分量表示，否则结论将不成立。联想到之前的步骤：当 $x_{r+1},x_
> {r+2},\cdots,x_n$ 选定时，由$\rm Cramer$法则知 $x_1,x_2,\cdots,x_r$ 唯一，与之前的想法一致。
> 
> 相对来说，书上提到的另一种由秩证明线性相关的方式更好想到

**推论**&emsp;设$\boldsymbol A$是$m\times n$矩阵，$\boldsymbol X=(x_1, x_2, \cdots, x_n)'$，则

​    (1) $\boldsymbol{AX}=\boldsymbol0$有唯一解$\Leftrightarrow$$R(\boldsymbol A)$等于未知数个数$n\Leftrightarrow\boldsymbol
A$为列满秩矩阵

​    (2) $\boldsymbol{AX}=\boldsymbol0$有无穷多解（有非零解）$\Leftrightarrow R(\boldsymbol A)$小于未知数的个数

​    (3) 当$r=R(\boldsymbol A)<n$时，设$\boldsymbol\xi_1,\boldsymbol\xi_2,\cdots,\boldsymbol\xi_{n-r}$是$N(\boldsymbol A)
$的基，则$\boldsymbol{AX}=\boldsymbol{0}$的解空间可以表示成
$$
N(\boldsymbol A)=\{\boldsymbol X | \boldsymbol X=k_1\boldsymbol\xi_1+k_2\boldsymbol\xi_2+\cdots+k_{n-r}\boldsymbol\xi_
{n-r};k_1,k_2,\cdots,k_{n-r}\in \boldsymbol F\}
$$
方程组的通解可以表示成
$$
\boldsymbol X=k_1\boldsymbol\xi_1+k_2\boldsymbol\xi_2+\cdots+k_{n-r}\boldsymbol\xi_{n-r}
$$
当$R(\boldsymbol A)=n$时，$N(\boldsymbol A)={\boldsymbol 0}$，此时方程组没有基础解系；当$R(\boldsymbol A)<
n$时…（书上有，不想敲了…)

## 非齐次线性方程组解的结构

设有非齐次线性方程组
$$
\begin{equation}
\left\{
\begin{gathered}
a_{11}x_1+a_{12}x_2+\cdots+a_{1n}x_n=b_1\\
a_{21}x_1+a_{22}x_2+\cdots+a_{2n}x_n=b_2\\
\cdots\cdots\cdots\cdots\\
a_{m1}x_1+a_{m2}x_2+\cdots+a_{mn}x_n=b_m\\
\end{gathered}
\right.
\label{Eq.4}
\end{equation}
$$
称齐次线性方程组
$$
\begin{equation}
\left\{
\begin{gathered}
a_{11}x_1+a_{12}x_2+\cdots+a_{1n}x_n=0\\
a_{21}x_1+a_{22}x_2+\cdots+a_{2n}x_n=0\\
\cdots\cdots\cdots\cdots\\
a_{m1}x_1+a_{m2}x_2+\cdots+a_{mn}x_n=0\\
\end{gathered}
\right.
\label{Eq.5}
\end{equation}
$$
为非齐次线性方程组$\eqref{Eq.4}$的**导出组**

**定理5.3**&emsp;方程组$\eqref{Eq.4}$与方程组$\eqref{Eq.5}$的解向量满足

​	(1). 若$\boldsymbol \eta_1,\boldsymbol \eta_2$都是$\eqref{Eq.4}$的解，则$\boldsymbol\eta_1-\boldsymbol\eta_2$是$\eqref{Eq.5}$

​	(2). 若$\boldsymbol\eta$是$\eqref{Eq.4}$的解，$\boldsymbol\xi$是$\eqref{Eq.5}$的解，则$\boldsymbol X=\boldsymbol\xi+\boldsymbol\eta$还是$\eqref{Eq.4}$的解

> ​	这个定理表明，非齐次线性方程组两个解的差一定是其导出组的解，而其中一个解加上其导出组的解一定也是这个非齐次线性方程组的解，所以才会有后面推论

**推论5.3**&emsp;设$\boldsymbol A$是方程组$\eqref{Eq.4}$的系数矩阵，$\boldsymbol B$是$\eqref{Eq.4}$的增广矩阵，$n$是$\eqref{Eq.4}$的未知数个数，则

​	(1). 方程组$\eqref{Eq.4}$有唯一解$\Leftrightarrow R(\boldsymbol A)=R(\boldsymbol B)=n$

​	(2). 方程组$\eqref{Eq.4}$有无穷多解$\Leftrightarrow R(\boldsymbol A)=R(\boldsymbol B)<n$

> ​	由于方程组$\eqref{Eq.5}$有非零解，所以可以通过定理5.3(2)构建出无数个解

​	(3). 当$r=R(\boldsymbol A)=R(\boldsymbol B)<n$时，设$\boldsymbol\xi_1,\boldsymbol\xi_2,\cdots,\boldsymbol\xi_{n-r}$是方程组$\eqref{Eq.5}$的一个基础解系，$\boldsymbol\eta^*$是方程组$\eqref{Eq.4}$的一个特解，则$\eqref{Eq.4}$的通解可以表示成
$$
\boldsymbol X=\boldsymbol\eta^*+k_1\boldsymbol\xi_1+k_2\boldsymbol\xi_2+\cdots+k_{n-r}\boldsymbol\xi_{n-r}
$$

> 实际上就是**非齐次线性方程组的特解+齐次线性方程组的解**的形式
>
> 解非齐次线性方程组的一般解法即为
>
> 1. 求出其一个特解
> 2. 求出其导出组的一个基础解系，构造方法可以是定理5.2证明过程中的构造方法
> 3. 用特解和基础解系表示通解

### 课本例题里还有些东西

**例$3$**&emsp;如果$\boldsymbol\eta_1,\boldsymbol\eta_2,\cdots,\boldsymbol\eta_m$都是非齐次线性方程组$\boldsymbol{AX}=\boldsymbol\beta$的解，那么$\displaystyle\frac{\displaystyle\sum^m_{i=1}k_i\boldsymbol\eta_i}{\displaystyle\sum^{m}_{i=1}k_i}$也是$\boldsymbol{AX}=\boldsymbol\beta$的解

> 有啥用？做作业的时候你就发现了，好吧可以方便求基础解系
>
> 可以去对应一下作业里$P57-4$（注意不同人作业可能版本不同）



~ ~~哎好像这种东西没人看，下次想摆烂了（直接拍书行不行.?~~ ~
