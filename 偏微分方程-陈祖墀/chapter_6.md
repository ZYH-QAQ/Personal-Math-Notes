### 6.2 Laplace算子的特征值问题（p182）
**（p182）** 在Sobolev空间$H_0^1(\Omega)$中，取如下范数：
$$
\Vert u\Vert_{H_0^1}^2 = \int_{\Omega}|Du|^2dx
$$
这个范数和$H_0^1(\Omega)$中标准的内积导出的范数是等价的。后者是：
$$
\Vert u\Vert_{H_0^1}^2 = \int_{\Omega}\left[cu^2+|Du|^2\right]dx
$$
两者的等价性由Friedrichs不等式得到。则定义泛函$Q[u]$和$J[u]$：
$$
Q[u]:=\Vert u\Vert_{H_0^1}^2 ,\ 
J[u] = \frac{Q[u]}{\Vert u\Vert_2^2}
$$
其中$\Vert \cdot\Vert_2^2$表示$L^2$范数。
**（p183）** Theorem 6.2.1证明的第一步要证$Q[u]$的极小化序列$\{u_k\}$收敛到$u\in L^2(\Omega)$。由于$\{\Vert u_k\Vert_{H_0^1}\}$有界，因此$\{u_k\}$是$L^2(\Omega)$中的列紧序列——这一步在书上没有讲清楚是怎么来的。在*Evans PDE*的p271给出了这个定理的证明。定理如下：

**Rellich-Kondrachov Compactness Theorem:** 若 $U$ 为有界开集，且 $\partial U$ 是 $C_1$ 的。假设 $1\leq p<n$ ，则对任意 $q$ 满足 $1\leq q<p^*$ （$p^*$ 为 $p$ 的Sobolev Conjecture，即 $\frac{1}{p^*}=\frac{1}{p}-\frac{1}{n}$），都有：
$$
W^{1,p}(U)\subset\subset L^q(U)
$$

其中$C_1$的定义为（*Evans PDE* p626 Appendix C）：

$U\subset \mathbb{R}^n$ 是一个有界开集，称 $\partial U$ 是 $C_k$ 的当任意 $x^0\in \partial U$，均存在 $r>0$ 和一个 $C^k$ 连续的函数 $\gamma \in C^k:\mathbb{R}^{n-1}\to\mathbb{R}$ ，使得在适当的坐标系变换和交换坐标轴序号下，满足：
$$
U\cap B(x^0,r)=\{ x\in B(x^0,r)|x_n>\gamma(x_1,x_2,\dots,x_{n-1}) \}
$$
这个定义的意义可以这样考虑。对于一个开集，若经过某些连续映射，使得其边界可以像平面一样，那么就可以轻易用平面的“一侧”来描述开集中的点。这里也是一样，$x_n>\gamma(x_1,x_2,\dots,x_{n-1})$其实就是在描述在一个平面一侧的点的集合。

而 $W^{k,p}$ 表示所有在 $L^p$ 内，且具有 $k$ 阶弱微商的函数的集合。$\subset\subset$ 代表紧嵌入（compactly embedded），若 $X\subset\subset Y$ ，即：
$$
\Vert x\Vert_Y \leq C\Vert x\Vert_X \ \ (x\in X) \ \ \ \text{对于某常数 $C$}
$$
且任意 $X$ 中的有界序列都是 $Y$ 中的准紧集。

由此，显然 $H^1_0\subset H^1 = W^{1,2}\subset\subset L^2 \ \ (n\geq 3)$。注意！书上讨论的Laplace算子的特征值问题，只针对 $n\geq 3$ 的情况。

**（p183）** Theorem 6.2.1证明思路（$K_1$ 为 $H^1_0(\Omega)\subset L^2(\Omega)$ 中的非零元。$K_1'$ 为 $H^1_0(\Omega)$ 中按照 $L^2$范数的单位球面）：
1. 根据 $\lambda_1$ 的定义，找到 $H^1_0(\Omega)$ 中的序列 $\{u_k\}\subset K_1'$（$\{u_k\}$ 是 $Q[u]$ 的极小化序列的子列 ）在 $L^2(\Omega)$ 中收敛到某一 $u$。

2. 已有 $u_k\to u$ 在 $L^2(\Omega)$ 中成立，然后证明 $\{u_k\}$ 是 $H^1_0(\Omega)$ 中的柯西列。由于 $H^1_0(\Omega)$ 是Hilbert空间，即完备，因此由极限的唯一性， $u_k\to u$ 在 $H^1_0(\Omega)$ 中成立。

3. 
$$
\begin{aligned}
\lambda_1&=\lim_{k\to\infty}Q[u_k]\ \ \ \ \ \text{极小化序列的子列}\\
&=Q[u]\ \ \ \ \ \text{$Q[u]$ 是范数，因此是连续函数，$H^1_0(\Omega)$ 中的序列极限拿到里面}\\
&=\frac{Q[u]}{\Vert u\Vert_2^2}\ \ \ \ \ \text{$\Vert \cdot \Vert_2^2$ 连续，$L^2(\Omega)$ 中的序列极限使 $\Vert u \Vert_2^2=\lim_{k\to\infty}\Vert u_k \Vert_2^2=1$}\\
&=J[u]\\
&=\inf_{v\in{K_1}}J[v]\ \ \ \ \ \text{$\lambda_1$ 的定义}
\end{aligned}
$$
即 $J[v]$ 的下确界在 $H^1_0(\Omega)$ 中是可达的。

4. 由于 $J[v]$ 在 $v=u$ 极小，对任意 $0\neq v\in H_0^1(\Omega)$ 有：
$$
\frac{dJ[u+tv]}{dt}=0
$$
变形后得到 $-\Delta$ 的（广义）特征值的定义式。这就证明了 $\lambda_1=\inf_{v\in{K_1}}J[v]$ 是 $-\Delta$ 的特征值。

5. 最后证明是最小特征值。通过特征值的定义式易得。

**（p184）** Theorem 6.2.2 $-\Delta$ 的（广义）特征值组成无穷序列：
$$
0<\lambda_1\leq \lambda_2\leq \cdots \leq \lambda_m\leq \cdots
$$
对应的特征函数为：
$$
u_1,u_2,\cdots,u_m,\cdots
$$
满足 $\Vert u_k\Vert_2=1,\ k=1,2,\cdots$

其主要证明思路如下：

1. 使用数学归纳法，在Theorem 6.2.1给出 $\lambda_1$ 以及对应的特征函数 $u_1$ 的情况下，要求出 $\lambda_2$ 和 $u_2$。

首先从 $H^1_0(\Omega)$ 中剔除掉 $u_1$ 的影响，从而寻找新的主特征值 $\lambda_2$（由于特征值重数可能>1，有可能与 $\lambda_1$ 相同）。因此设置 $V_1={\rm{span}}\{u_1\}\subset L^2(\Omega)$，其在 $L^2(\Omega)$ 中的正交补空间为 $V_1^\bot$。那么，对应于Theorem 6.2.1证明中的 $K_1$ 和 $K_1'$，令：
$$
\begin{aligned}
&K_2=\{v\vert 0\neq H_0^1(\Omega)\cap V_1^\bot\},\\
&K_2'=\{v\vert v\in K_2, \Vert v\Vert_2=1\}.
\end{aligned}
$$
则 $K_2$ 便是我们需要的排除了 $u_1$ 的影响的空间，这一操作是通过正交补实现的。

2. 照搬Theorem 6.2.1的证明方法，可以找到 $u_2\in K_2,\ \Vert u_2\Vert_2=1$ 和 $\lambda_2$ 使：
$$
\int_\Omega {\rm{D}}u_2\cdot {\rm{D}}v \ dx = \lambda_2\int_\Omega u_2v\ dx = 0 \ \ \ \forall v\in K_2
$$
3. 根据上步的结论以及正交分解的性质，可以证明 $\forall v\in H_0^1$， 均有：
$$
\int_\Omega {\rm{D}}u_2\cdot {\rm{D}}v \ dx = \lambda_2\int_\Omega u_2v\ dx\ \ \ \forall v\in H_0^1
$$
即 $\lambda_2$ 为特征值，$u_2$ 为特征函数，且显然有 $\lambda_2\geq\lambda_1$。同样的，$\lambda_2$ 也是 $\lambda_1$ 以外最小的特征值了，不存在特征值在 $\lambda_1$ 和 $\lambda_2$ 之间。

4. 再证已有 $m-1$ 个特征值 $0<\lambda_1\leq \lambda_2\leq \cdots \leq \lambda_{m-1}$ 、其特征函数为 $u_1,u_2,\cdots,u_{m-1}$ 的情况下，要找到 $\lambda_m$ 和 $u_m$。

同样先定义：
$$
\begin{aligned}
&K_m=\{v\vert 0\neq H_0^1(\Omega)\cap V_{m-1}^\bot\},\\
&K_m'=\{v\vert v\in K_m, \Vert v\Vert_2=1\}.
\end{aligned}
$$
则可以找到特征值 $\lambda_m$ 和特征函数 $u_m\in K_m,\ \Vert u_m\Vert_2=1$，即满足：
$$
\int_\Omega {\rm{D}}u_m\cdot {\rm{D}}v \ dx = \lambda_m\int_\Omega u_m v\ dx\ \ \ \forall v\in H_0^1
$$
且 $\lambda_m\geq \lambda_{m-1}$。

可以看到，新的特征函数总是属于此前所有特征函数张成的子空间的正交补（对 $L^2(\Omega)$ 而言的），这可以说明不同特征值对应的特征函数在 $L^2(\Omega)$ 中正交。

**（p187）** Theorem 6.2.7 对应同一特征值的特征函数组成的空间是有限维的。证明思路为：用反证法，假设对于某特征值 $\lambda$ ，有无限个线性无关的特征函数 $\{w_k\}$。

将 $\{w_k\}$ 在 $L^2$ 中进行史密斯正交化，形成 $L^2$ 中的标准正交系，则由特征函数的定义：
$$
\Vert w_k\Vert_{H_0^1}^2=\int_{\Omega}|{\rm{D}}u_m|^2 \ dx = \lambda \int_{\Omega}|u_m|^2 \ dx = \lambda \Vert w_k\Vert_{2}^2 = \lambda
$$
因此 $\{w_k\}$ 是 $H_0^1(\Omega)$ 中的有界序列，因此是 $L^2(\Omega)$ 中的准紧集。这意味着有 $L^2(\Omega)$ 中的收敛子列，这和 $\{w_k\}$ 在 $L^2$ 中是标准正交系矛盾。

**（p188）** Theorem 6.2.8 $-\Delta$ 的特征函数列构成了 $H_0^1(\Omega)$ 的规范正交基，即 $\{u_k\}$ 张成子空间的闭包等于 $H_0^1(\Omega)$ ，其中 $\{u_k\}$ 对应了不同的特征值。证明思路如下：

规范正交基等价于完备正交系，在Hilbert空间的情况下等价于完全的正交系。用反证法，若不是完全的，则存在 $v\in H_0^1(\Omega)$ 使得 $(v,u_k)_{H_0^1}=0,\ v\neq 0, k=1,2,\cdots$。此时有：
$$
0=(v,u_k)_{H_0^1}=\lambda_k (v,u_k)_{2}, \  \lambda_k>0
$$
即 $(v,u_k)_{2}=0, k=1,2,\cdots$，即对 $\forall k>0$ ，$v\in V_{k-1}^\bot$。

因此 $\lambda_k\leq \frac{Q[v]}{\Vert v\Vert_2^2}$。 当 $k\to\infty$ 时，左边趋于无穷（Theorem 6.2.6），而右边为常数，矛盾。**这个证明的关键在于 $\lambda_k\to\infty$**

*注意，拉普拉斯算子 $-\Delta$ 是自伴算子，因此其特征值一定是实数。可以考虑将 $u$ 推广至复数域，即复值函数？*