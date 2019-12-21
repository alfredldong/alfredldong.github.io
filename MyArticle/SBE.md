<head>
    <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
    <script type="text/x-mathjax-config">
        MathJax.Hub.Config({
            tex2jax: {
            skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
            inlineMath: [['$','$']]
            }
        });
    </script>
</head>

**1 Basic Concept**

非平衡格林函数方法
格林函数方法则能够比较详细的考量某一相互作用，并可通过Feynman图将起主要作用的微扰项包含在理论框架中，因此该方法适用于处理各种散射机制的问题。

密度矩阵方法（半导体Bloch方程）
密度矩阵中的一组微分方程能够很好得求得系统的时间演变，它适用于计算相位弛豫时间较长的情形。
密度矩阵方法同其它量子力学方法一样，与具体表象无关。各种物理量包括电流密度、电子极化、光子数等都可以通过密度矩阵来表示。在密度矩阵中，其对角元描述半导体中载流子占据数，而非对角元描述的是电子极化。而这些量通常表示为两个产生湮灭算符乘积的期望。

在对受激半导体的光偶极跃迁的研究中，密度矩阵理论就是一个非常适用的方法，但是由于电子一空穴等离子体的振荡和复合，电子和空穴已然不能以一种纯态描述，而是呈现出一种混合态，而且为了更切合实际的半导体性质，还必须考虑等离子体之间的库仑作用。因此，精确描述系统态矢几乎是不可能的。而在理论研究中，载流子分布$n_{ek}$和带间极化强度$P_k$所组成的动量耦合方程通常由海森堡方程和多体哈密顿来推导得出。然而，由于库仑多体相互作用包含了四个产生和湮灭算符，会导致更高阶的密度矩阵，从而得到一系列非闭合的互相耦合的微分方程组，一般情况下没有确定解。因此，在计算时必须对其进行截断而取近似。随机相位近似RPA方法即使包含库仑作用的最低阶近似，此方法将一个四算符期望值分解为两个二算符期望值的乘积。如此获得的方程称为Hartree-Fork方程，如果继续超越RPA近似，则进入更高的层次，可包含等离子屏蔽和更高阶的相关性，由此即可得半导体Bloch方程。

电偶极近似

$$
V_{a b}=\int \psi_{a}(r)(-e \boldsymbol{E} \cdot \boldsymbol{r}) \psi_{b}(r) \mathrm{d}^{3} r=-e \boldsymbol{r}_{\mathrm{d}}\cdot \boldsymbol{E} =- \boldsymbol{p} \cdot \boldsymbol{E}
$$

非极性原子或分子没有固有偶极矩

$$
V_{a a}=V_{b b}=0
$$

$$
V=\left(\begin{array}{cc}
{0} & {V_{a b}} \\ 
{V_{b a}} & {0}
\end{array}\right)
$$

电偶极矩

$$
e \boldsymbol{r}
=\left(\begin{array}{cc}
{0} & {e r_{a b}} \\ 
{e r_{b a}} & {0}
\end{array}\right)
$$

$$
\langle e \boldsymbol{r}\rangle
=\mathrm{tr}(\boldsymbol{\rho} e\boldsymbol{r})
=e(\rho_{a b} r_{b a}+\rho_{b a} r_{a b})
$$

$\rho_{a a}=c_{a}^{*} c_{a}$: 原子在上能级几率

$\rho_{b b}=c_{b}^{*} c_{b}$: 原子在下能级几率

$\rho_{a b}=c_{b}^{*} c_{a}=\rho_{b a}^{*}$: 正比于复数电偶极矩

带间极化强度

通常，半导体具有一个导带以及数个价带，这些能带形状并不对称而且具有不同的极值。在研究半导体问题时，所采用的最简单的模型即为二能带模型，即只考虑一个价带和一个导带，而且这两个能带为抛物带，在半导体大多数性质的探索中，这一近似已足够说明其基本性质，而且其它完全填充的能带通常也并不对我们所感兴趣频域的光跃迁产生贡献。在以下的讨论中，我们也仅只考虑二能级抛物带结构。在这一情形下，由于抛物带结构，光跃迁均为直接带隙跃迁，因此，我们也只需要考虑带隙附近的一个极小的区域内的跃迁情形。
在半导体性质中，极化强度$P$是一个极为重要的物理量，它与半导体吸收率和折射率密切相关。在微观理论描述中，极化强度$P$定义为单位体积的电偶极矩$er$, 并可依能态分解表示为$P=d_{c v} \sum p_{k}$，其中$p_k$即为光诱导产生的相干的导带电子和价带空穴之间的极化强度，$d_{c v}$为带间偶极矩阵元。

极化强度$P(t)$即带间偶极矩的期望值之和:

$$
P(t)=\sum_{\sigma} \int d^{3} r\left\langle\hat{\psi}_{\sigma}^{\dagger}(r, t) e r \hat{\psi}_{\sigma}(r, t)\right\rangle=\sum_{\sigma} \int d^{3} r \mathrm{Tr}\left(\rho_{0} \hat{\psi}_{\sigma}^{\dagger} e r \hat{\psi}_{\sigma}\right)
$$

式中，$\rho_0$是密度算子，表示场到达前的系统的初始状态。$\hat{\psi}_{\sigma}$为电场算子，

$$
\hat{\psi}_{\sigma}(r, t)=\sum_{\lambda} \sum_{k} a_{\lambda, k, \sigma}(t) \phi_{\lambda, k, \sigma}(r)
$$

其中，$\phi_{\lambda, k, \sigma}(r)$为半导体中一个电子的单粒子本征值，它对应于带序号为$\lambda$，动量为$k$、自旋为$\sigma$的态。$a_{\lambda, k, \sigma}(t)$ 为湮灭算符。因此，带入可得

$$
P(t)=\sum_{\sigma} \sum_{\lambda, \lambda^{\prime}} \sum_{ k, k^{\prime}}\left\langle a_{\lambda, k, \sigma}^{\dagger}(t) a_{\lambda^{\prime}, k^{\prime}, \sigma}(t)\right\rangle \int d^{3} r \phi_{\lambda, k, \sigma}^{\dagger}(r) e r \phi_{\lambda, k^{\prime}, \sigma}(r)
$$

可将偶极矩阵元写为

$$
\int d^{3} r \phi_{\lambda, k, \sigma}^{\dagger}(r) e r \phi_{\lambda^{\prime}, k^{\prime}, \sigma}(r)=\delta_{k k^{\prime}} d_{\lambda \lambda^{\prime}}
$$
对于$\lambda \neq \lambda^{\prime}$，

$$
P(t)=\sum_{\sigma} \sum_{\lambda, \lambda^{\lambda} k, k^{\prime}}\left\langle a_{\lambda, k, \sigma}^{\dagger}(t) a_{\lambda^{\prime}, k, \sigma}(t)\right\rangle d_{\lambda, \lambda^{\prime}}=\sum_{\sigma} \sum_{\lambda, \lambda^{\prime}} \sum_{k, k^{\prime}} P_{\lambda \lambda^{\prime}, k, \sigma} d_{\lambda, \lambda^{\prime}}
$$

其中，定义了带间极化强度

$$
P_{\lambda \lambda^{\prime}, \boldsymbol{\sigma}}(t)=\left\langle a_{\lambda, k, \sigma}^{\dagger}(t) a_{\lambda^{\prime}, k, \sigma}(t)\right\rangle
$$

在二能级近似条件下，即只考虑导带和价带间的情形，令$\lambda=v, \quad \lambda^{\prime}=c$，并假定自旋已包含至动量算符$k$，省略自旋标号，上式可变为

$$
P_{c v, k}(t)=\left\langle a_{v, k}^{\dagger} a_{c, k}(t)\right\rangle
$$

这个量表示的是约化密度矩阵的非对角元素，在不包含固有偶极矩的平衡系统中，这些非对角元素为零，因此，极化强度也为零。但在光场作用下，能带间会发生跃迁，这样就使得带间极化强度存在且为一个有限值。

**2 Semiconductor Bloch Equation**

**2.1. Two - band model**

microscopic interband polarization between conduction band and valence band

$$
i \frac{\partial}{\partial t} p_{k}=\left(\varepsilon_{c}(k)-\varepsilon_{v}(k)-i \frac{1}{T_{2}}\right) p_{k}+\left(f_{k}^{c}-f_{k}^{v}\right) d(k) E(t)+i E(t) \nabla_{k} p_{k}
$$

the populations of the lowest conduction band and the highest valence band

$$
\frac{\partial}{\partial t} f_{k}^{c(v)}=-2 \mathrm{Im}\left[d(k) E(t) p_{k}^{*}\right]+E(t) \nabla_{k} f_{k}^{c(v)}
$$

where $d(k)$ is the dipole element,and $E(t)$ is the temporal laser field. $T_2$ is the dephasing time. $\epsilon_c(k)$ and $\epsilon_v(k)$ are k-dependent energy bands of the lowest conduction band and the highest valence band

$$
J(t)=\sum_{\lambda} \int_{B Z} e v_{k}^{\lambda} f_{k}^{\lambda}(t) d k
$$

$$
P(t)=\int_{B Z}\left[d(k) p_{k}(t)+c.c.\right] d k
$$

$$
\Omega(\boldsymbol{K}, t)=\boldsymbol{F}(t) \boldsymbol{d}[\boldsymbol{K}+\boldsymbol{A}(t)]
$$

$$
S(\boldsymbol{K}, t)=\int_{-\infty}^{t} \varepsilon_{g}\left[\boldsymbol{K}+\boldsymbol{A}\left(t^{\prime}\right)\right] d t^{\prime}
$$

$$
\dot{\pi}(\boldsymbol{K}, t)=-\frac{\pi(\boldsymbol{K}, t)}{T_{2}}-i \Omega(\boldsymbol{K}, t) w(\boldsymbol{K}, t) e^{-i S(\boldsymbol{K}, t)}
$$

$$
\dot{n}_{m}(\boldsymbol{K}, t)=i s_{m} \Omega^{*}(\boldsymbol{K}, t) \pi(\boldsymbol{K}, t) e^{i S(\boldsymbol{K}, t)}+c.c.
$$

$$
\boldsymbol{j}_{r a}(t)=\sum_{m=c, v} \int_{\overline{B Z}} \boldsymbol{v}_{m}[\boldsymbol{K}+\boldsymbol{A}(t)] n_{m}(\boldsymbol{K}, t) d^{3} \boldsymbol{K}
$$

$$
\boldsymbol{j}_{e r}(t)=\frac{d}{d t} \int_{\overline{B Z}} \boldsymbol{d}[\boldsymbol{K}+\boldsymbol{A}(t)] \pi(\boldsymbol{K}, t) e^{i s(\boldsymbol{K}, t)} d^{3} \boldsymbol{K}+c.c.
$$

**2.2 Three band model**

以上是两带的半导体布洛赫方程，为了考虑更高的导带对高次谐波谱的影响，需要把式子推广到三带模型，即一条价带和两条导带。

三带模型的半导体布洛赫方程为

$$
\dot{n}_{m}=i \sum_{m^{\prime} \neq m} \Omega_{m m^{\prime}} \pi_{m m^{\prime}} e^{i S_{m m^{\prime}}}+c . c .
$$

$$
\dot{\pi}_{m m^{\prime}}=-\frac{\pi_{m m^{\prime}}}{T_{2}}+i \Omega_{m m^{n}}^{*}(K, t)\left(n_{m}-n_{m^{\prime}}\right) e^{-i S_{m m}}
+i \sum_{m^{\prime \prime} \in\left\{m, m^{\prime}\right\}}\left(\Omega_{m^{\prime} m^{\prime \prime}} \pi_{m m^{\prime \prime}} e^{i S_{m^{\prime} m^{\prime \prime}}}-\Omega_{m m^{\prime \prime}}^{*} \pi_{m^{\prime} m^{\prime \prime}}^{*} e^{-i S_{m m^{n}}}\right)
$$

其中对于电子的布局数作了限制，即需要满足条件$\sum_{m} n_{m}=1$。

其他量的定义和前面一致，其中考虑了更多带之间的相互耦合。

**2.3. Multi - band model**

**4 SBE Proved by Second Quantization**

$$
\mathcal{H}=\mathcal{H}_{e l}+\mathcal{H}_{l}
$$

电子部分，包括动能项和库仑作用项

$$
\mathcal{H}_{e l}
=\sum_{\boldsymbol{k}}\left(E_{c, k} a_{c, \boldsymbol{k}}^{\dagger} a_{c, \boldsymbol{k}}+E_{v, k} a_{v, \boldsymbol{k}}^{\dagger} a_{v, \boldsymbol{k}}\right)
+\frac{1}{2} \sum_{\boldsymbol{k}, \boldsymbol{k}^{\prime}, \boldsymbol{q} \neq \boldsymbol{0}} V_{q}\left(a_{c, \boldsymbol{k}+\boldsymbol{q}}^{\dagger} a_{c, \boldsymbol{k}^{\prime}-\boldsymbol{q}}^{\dagger} a_{c, \boldsymbol{k}^{\prime}} a_{c, \boldsymbol{k}}
+a_{v, \boldsymbol{k}+\boldsymbol{q}}^{\dagger} a_{v, \boldsymbol{k}^{\prime}-\boldsymbol{q}}^{\dagger} a_{v, \boldsymbol{k}^{\prime}} a_{v, \boldsymbol{k}}
+2 a_{c, \boldsymbol{k}+\boldsymbol{q}}^{\dagger} a_{v, \boldsymbol{k}^{\prime}-\boldsymbol{q}}^{\dagger} a_{v, \boldsymbol{k}^{\prime}} a_{c, \boldsymbol{k}}\right)
$$

此式中，考虑到各个带之间相对较大的能隙，只包含了使各带满足粒子数守恒的库仑作用，而不包括诸如一对电子空穴湮灭产生两个电子的带间库仑过程。

电子与光场$\xi(t)$耦合带间偶极子

$$
\mathcal{H}_{l}=-\sum_{k} \xi(t)\left(a_{c, k}^{\dagger} a_{v, k} d_{c, v}(k)+h . c .\right)
$$

带间偶极矩

$$
d_{c, v}(\boldsymbol{k}) \propto\langle c, \boldsymbol{k}|\hat{\boldsymbol{p}}| v, \boldsymbol{k}\rangle
$$

Transformation to electron-hole representation

$$
\beta_{-\boldsymbol{k}}^{\dagger}=a_{v, \boldsymbol{k}}
$$

$$
\alpha_{\boldsymbol{k}}^{\dagger}=a_{c, \boldsymbol{k}}^{\dagger}
$$

电子-空穴描述哈密顿量

$$
H
=\sum_{k}\left(E_{c, k} \alpha_{k}^{\dagger} \alpha_{k}+E_{v, k} \beta_{-k}^{\dagger} \beta_{-k}\right)
+\frac{1}{2} \sum_{k, k^{\prime}, q \neq 0} V_{q}\left(\alpha_{k+q}^{\dagger} \alpha_{k^{\prime}-q}^{\dagger} \alpha_{k^{\prime}} \alpha_{k}+\beta_{k+q}^{\dagger} \beta_{k^{\prime}-q}^{\dagger} \beta_{k} \beta_{k^{\prime}}-2 \alpha_{k+q}^{\dagger} \beta_{k^{\prime}-q}^{\dagger} \alpha_{k} \beta_{k^{\prime}}\right)
-\sum_{k} \xi(t)\left(d_{c, v} \alpha_{k}^{\dagger} \beta_{-k}+h . c .\right)
$$

电子-空穴单粒子动能

$$
E_{e, k}=E_{c, k}=\hbar \varepsilon_{e, k}
$$

$$
E_{h, k}=-E_{v, k}+\sum_{q \neq 0} V_{q}=\hbar \varepsilon_{h, k}
$$

空穴的动能包括库仑交换能量$-\sum V_{q} n_{v, k-q}$，对于满导带，$n_{v,|k-q|}=1$


低强度带间跃迁能为：

$$
\Delta E_{k}=E_{c, k}-E_{v, k}+\sum_{q \neq 0} V_{q}
$$

电子、空穴分布函数以及带间极化强度可定义如下：

$$
n_{e, k}(t)=\left\langle\alpha_{k}^{\dagger} \alpha_{k}\right\rangle
$$

$$
n_{h, k}(t)=\left\langle\beta_{-k}^{\dagger} \beta_{-k}\right\rangle
$$

$$
p_{k}(t)=\left\langle\beta_{-k} \alpha_{k}\right\rangle
$$

海森堡运动方程

$$
i \hbar \frac{\partial}{\partial t} A(t)=[A(t), H]
$$

综上得到

$$
\hbar\left[i \frac{d}{d t}-\left(\varepsilon_{e, k}+\varepsilon_{h, k}\right)\right] p_{k}
=\left(n_{e, k}+n_{h, k}-1\right) d_{c, v} \xi(t)
+\sum_{k q \neq 0} V_{q}(\left\langle\alpha_{k^{\prime}+q}^{\dagger} \beta_{-k+q} \alpha_{k^{\prime}} \alpha_{k}\right\rangle-\left\langle\beta_{k^{\prime}+q}^{\dagger} \beta_{-k+q} \beta_{k^{\prime}} \alpha_{k}\right\rangle)+\left\langle\beta_{-k} \alpha_{k^{\prime}-q}^{q} \alpha_{k^{\prime}} \alpha_{k-q}\right\rangle-\left\langle\beta_{-k} \beta_{k^{\prime}-q}^{\dagger} \beta_{k^{\prime}} \alpha_{k-q}\right\rangle)
$$

$$
\hbar \frac{\partial}{\partial t} n_{e, k}
=-2 \mathrm{Im}\left[d_{c v} \xi(t) p_{k}^{*}\right]
+i \sum_{k^{\prime}, q \neq 0} V_{q}(\left\langle\alpha_{k}^{\dagger} \alpha_{k^{\prime}-q}^{\dagger} \alpha_{k-q} \alpha_{k^{\prime}}\right\rangle-\left\langle\alpha_{k+q}^{\dagger} \alpha_{k^{\prime}-q}^{\dagger} \alpha_{k} \alpha_{k^{\prime}}\right\rangle+\left\langle\alpha_{k}^{\dagger} \alpha_{k-q} \beta_{k^{\prime}-q}^{\dagger} \beta_{k^{\prime}}\right\rangle-\left\langle\alpha_{k+q}^{\dagger} \alpha_{k} \beta_{k^{\prime}-q}^{\dagger} \beta_{k^{\prime}}\right\rangle)
$$

$$
\hbar \frac{\partial}{\partial t} n_{h, k}
=-2 \mathrm{Im}\left[d_{c v} \xi(t) p_{k}^{*}\right]
+i \sum_{k^{\prime}, q \neq 0} V_{q}(\left\langle\beta_{-k}^{\dagger} \beta_{k^{\prime}-q}^{\dagger} \beta_{-k-q} \beta_{k^{\prime}}\right\rangle-\left\langle\beta_{-k+q}^{\dagger} \beta_{k^{\prime}-q}^{\dagger} \beta_{-k} \beta_{k^{\prime}}\right\rangle+\left\langle\alpha_{k^{\prime}+q}^{\dagger} \alpha_{k^{\prime}} \beta_{-k}^{\dagger} \beta_{-k+q}\right\rangle-\left\langle\alpha_{k^{\prime}+q}^{\dagger} \alpha_{k^{\prime}} \beta_{-k-q}^{\dagger} \beta_{-k}\right\rangle)
$$

在上述方程组中，上式的右边项$\left(n_{e, k}+n_{h, k}-1\right) d_{c, v} \xi(t)$描述了一个重要的多体效应：相位填充效应（PSF），或者也称为泡利阻塞，即随着等离子体密度的增大，泡利阻塞因子$\left(n_{e, k}+n_{h, k}-1\right)$将会降低振荡强度。

上式中有许多四算子项，它们所描述的正是载流子之间的库仑作用所产生的效应。如果摒弃这些四算子项，方程就会退化为描述自由电子跃迁的光学布洛赫方程。

对于四算子式的计算，显然二算子项的动态是与四算子项相关的，而若继续计算四算子项的动态时，就会发现它又与六算子项相关，以此类推，我们会得到一个无限级次的方程，求解基本不可能。因此，我们必须采用一定的方法，在一定的级次截断，从而得到一个封闭的方程组在此，我们所采用的方法是直接四算子式子期望值分解为相关的二算子期望值，即将其依密度和带间极化强度进行因式分解，忽略更高阶的相关作用，但是保留了密度和极化强度之间的耦合作用。这即使随机相位近似(RPA)。以项$\left\langle\alpha_{k^{\prime}+q}^{\dagger} \beta_{-k+q} \alpha_{k^{\prime}} \alpha_{k}\right\rangle$为例，可将其分解为$n_{e, k}$与$p_{k-q}$两项，并加上未分解余项

$$
\left\langle\alpha_{k^{\prime}+q}^{\dagger} \beta_{-k+q} \alpha_{k^{\prime}} \alpha_{k}\right\rangle=\left\langle\alpha_{k^{\prime}+q}^{\dagger} \alpha_{k}\right\rangle\left\langle\beta_{-k+q} \alpha_{k^{\prime}}\right\rangle \delta_{k^{\prime}+q, k}
$$

$$
\frac{\partial}{\partial t}\langle A\rangle=\frac{\partial}{\partial t}\langle A\rangle_{H F}+\frac{\partial}{\partial t}\left.\langle A\rangle\right|_{\text {scatt}}
$$

$$
\frac{\partial}{\partial t} p_{k}=-i\left(e_{e, k}+e_{h, k}\right) p_{k}-\frac{i}{\hbar}\left(n_{e, k}+n_{h, k}-1\right)\left[d_{c v} \xi(t)+\sum_{q \neq k} V_{|k-q|} p_{q}\right]+\frac{\partial}{\partial t}\left.p_{k}\right|_{scatt}
$$

$$
\frac{\partial}{\partial t} n_{e, k}=-\frac{2}{\hbar} \mathrm{Im}\left\{\left[d_{c v} \xi(t)+\sum_{q \neq k} V_{|k-q|} p_{q}\right] p_{k}^{*}\right\}+\frac{\partial}{\partial t}\left.n_{e, k}\right|_{\text {scatt}}
$$

$$
\frac{\partial}{\partial t} n_{h, k}=-\frac{2}{\hbar} \mathrm{Im}\left\{\left[d_{c v} \xi(t)+\sum_{q \neq k} V_{|k-q|} p_{q}\right] p_{k}^{*}\right\}+\frac{\partial}{\partial t}\left.n_{h, k}\right|_{scatt}
$$

$$
\hbar e_{i, k}=\hbar \varepsilon_{i, k}+\sum_{e x c, i}(k)=\hbar \varepsilon_{i, k}-\sum_{q} V_{|k-q|} n_{i, k}, i=e, h
$$

$$
\omega_{R, k}=\frac{1}{\hbar}\left[d_{c v} \xi(t)+\sum_{q \neq k} V_{|k-q|} p_{q}\right]
$$

$$
\frac{\partial}{\partial t} p_{k}=-i\left(e_{e, k}+e_{h, k}\right) p_{k}-i\left(n_{e, k}+n_{h, k}-1\right) \omega_{R, k}+\frac{\partial}{\partial t}\left.p_{k}\right|_{\text {scatt}}
$$

$$
\frac{\partial}{\partial t} n_{e, k}=-2 \mathrm{Im}\left(\omega_{R, k} p_{k}^{*}\right)+\frac{\partial}{\partial t}\left.n_{e, k}\right|_{\text {scatt}}
$$

$$
\frac{\partial}{\partial t} n_{h, k}=-2 \mathrm{Im}\left(\omega_{R, k} p_{k}^{*}\right)+\frac{\partial}{\partial t}\left.n_{h, k}\right|_{\text { scatt }}
$$


**等离子体屏蔽效应**

在电子等离子体系统中，一个极其重要的多体作用就是等离子体屏蔽效应。等离子体在经过集体激励之后，屏蔽效应会影响半导体的介电常数，并最终降低库仑势的影响，也因此成为库仑屏蔽作用。

在实空间，裸库仑势为：

$$
V(r)=\frac{e^{2}}{4 \pi \varepsilon r}
$$

通过傅立叶变换，可得到2D系统中库仑势在$k$空间的表达式

$$
V(q)=\frac{e^{2}}{2 \varepsilon A} \cdot \frac{1}{q}
$$

式中A为2D系统的面积·
而考虑屏蔽效应后的库仑势，即屏蔽库仑势可表示为：

$$
V_{s}(q)=\frac{V_{q}}{\varepsilon(q, \omega)}
$$

分析可知，在2D系统中：

$$
\frac{1}{\varepsilon(q, \omega)}=1-\frac{\omega_{p l}^{2}(q)}{\omega^{2}(q)}
$$

$$
\omega_{p l}^{2}(q)=\frac{n e^{2}}{2 \varepsilon m} q
$$

$$
\omega^{2}(q)=\omega_{p l}^{2}(q)\left(1+\frac{q}{\kappa}\right)+v_{q}^{2}
$$
