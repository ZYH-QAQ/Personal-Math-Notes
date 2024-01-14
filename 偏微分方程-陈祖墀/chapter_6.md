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