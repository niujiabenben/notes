## 微积分

**极限**

对于任意给定的正数 $\epsilon>0$, 存在正数 $\delta>0$, 使得当 $x \in (x_0-\delta, x_0) \cup(x_0,x_0+\delta)$ 时, 总有 $|f(x)-A|<\epsilon$ 成立, 则称函数 $f(x)$ 在 $x \rightarrow x_0$ 时的极限为 $A$, 记为: $\lim_{x \rightarrow x_0} f(x)=A$.

上述定义中, 将 $x$ 的范围限制在 $x \in (x_0-\delta, x_0)$, 则得到左极限: $\lim_{x \rightarrow x_0^-} f(x)=A$; 将$x$ 的范围限制在 $x \in (x_0, x_0+\delta)$, 则得到右极限: $\lim_{x \rightarrow x_0^+} f(x)=A$.

注意上述定义中, 不需要函数 $f(x)$ 在 $x_0$ 处有定义. 所取的范围为 $x_0$ 的去心邻域.

从以上的定义中可知, 函数 $f(x)$ 在点 $x_0$ 处的极限存在的充要条件是左右极限存在且相等: $\lim_{x \rightarrow x_0^-} f(x)=\lim_{x \rightarrow x_0^+} f(x)=A$.

**连续**

连续的定义是极限等于函数值: $\lim_{x \rightarrow x_0} f(x)=f(x_0)$.

这就要求函数 $f(x)$ 在 $x_0$ 处的极限存在, 且 $f(x)$ 在 $x_0$ 处有定义.

**无穷小**

若 $\lim_{x \rightarrow x_0} f(x)=0$, 我们就称 $f(x)$ 为 $x \rightarrow x_0$ 时的无穷小. 由此可知, 无穷小是变量.

若 $f(x)$ 和 $g(x)$ 均为 $x \rightarrow x_0$ 时的无穷小, 考察极限: $\lim_{x \rightarrow x_0} \frac {f(x)}{g(x)}=C$:

* 若 $C=0$, 则称 $f(x)$ 为 $g(x)$ 的高阶无穷小;
* 若 $C=\infty$, 则称 $f(x)$ 为 $g(x)$ 的低阶无穷小;
* 若 $C \ne 0$ 且 $C \ne \infty$, 则称 $f(x)$ 为 $g(x)$ 的同阶无穷小;
* 若 $C = 1$, 则称 $f(x)$ 为 $g(x)$ 的等价无穷小;

**导数**

如果函数 $f(x)$ 在 $x_0$ 的邻域内有定义, $\Delta x$ 为自变量 $x$ 在 $x_0$ 处的增量, 如果如下极限存在: $\lim_{\Delta x \rightarrow 0} \frac{f\left(x_{0}+\Delta x\right)-f\left(x_{0}\right)}{\Delta x}$, 则称 $f(x)$ 在 $x_0$ 处可导, 极限值即为 $f(x)$ 在 $x_0$ 处的导数, 记为 $f'(x_0)$.

可导必连续, 连续不必可导.

**微分**

函数 $f(x)$ 在某区间内有定义, 如果 $x_0$ 和 $x_0 + \Delta x$ 在定义域内, 且函数增量 $\Delta y=f(x_0 + \Delta x) - f(x_0)$ 可表示为 $\Delta y=A \Delta x + o(\Delta x)$, 其中 $A$ 是不依赖 $\Delta x$ 的常数, 那么称 $f(x)$ 在 $x_0$ 处是可微的, $A \Delta x$ 叫做函数 $f(x)$ 在点 $x_0$ 处的微分, 记为: $dy=A \Delta x$.

根据以上定义, 自变量 $x$ 的微分为 $dx=1*\Delta x=\Delta x$, 所以 $dy=Adx=f'(x)dx$.

由以上定义可知, 微分的几何意义是在 $x_0$ 的邻域中用切线代替函数 $f(x)$.

对于一元函数来说, 可导与可微等价.

**原函数与不定积分**

在区间 $I$ 上可导函数 $F(x)$ 的导函数为 $f(x)$, 则称 $F(x)$ 为 $f(x)$ 在区间 $I$ 上的原函数. $\int f(x)dx=F(x)+C$ 为 $f(x)$ 的不定积分.

原函数存在定理: 连续函数一定有原函数.

这个定理指出, 连续函数必定可积(不定积分意义上的), 但不一定可导(魏尔施特拉斯函数处处连续, 但处处不可导).

定积分的定义较为繁琐, 这里不写.

**偏导数**

给定函数 $z=f(x,y)$, 若 $g(x,y)=\frac{\partial^{2} z}{\partial y \partial x}$ 和 $h(x,y)=\frac{\partial^{2} z}{\partial x \partial y}$ 都连续, 则两者相等.

## 应用

**椭圆**

椭圆方程: $\frac{x^2}{a^2}+\frac{y^2}{b^2}=1$.
参数方程: $\left\{\begin{array}{l}{x=a \cos \alpha} \\ {y=b \sin \alpha}\end{array}\right.$

整个椭圆的面积为第一象限面积的4倍:

$S = 4\int_{0}^{a} ydx
   = 4\int_{\frac{\pi}{2}}^{0} bsin\alpha \ d(asin\alpha)
   = 4\int_{0}^{\frac{\pi}{2}} absin^2\alpha d\alpha
   = 2ab\int_{0}^{\frac{\pi}{2}}(1-cos2\alpha)d\alpha
   = 2ab\pi$

椭圆的周长为第一象限弧长的4倍:

$L = 4\sum \Delta s
   = 4\sum \sqrt{\Delta x^2+\Delta y^2}
   = 4\sum \sqrt{(x'd\alpha)^2 + (y'd\alpha)^2}
   = 4\sum \sqrt{x'^2+y'^2}d\alpha \\
   = 4\int_{0}^{\frac{\pi}{2}} \sqrt{a^2sin^2\alpha + b^2cos^2\alpha} d\alpha$

上式不能用初等函数来表示, 这里列出来仅仅为了展示弧微分的计算方法.

**球**

球的方程: $x_2+y_2+z^2=R^2$.
参数方程: $\left\{\begin{array}{l}{x=R \sin \varphi \cos \theta} \\ {y=R \sin \varphi \sin \theta} \\ {z=R \cos \varphi}\end{array}\right.$

面积计算方法一: 取沿纬线的切片, 设 $\theta$ 为仰角, 则该切片的半径为 $Rcos\theta$, 周长为 $2\pi Rcos\theta$, 切片侧面的高为弧微分 $d\sigma=Rd\theta$.

$S = 2\int_{0}^{\frac{\pi}{2}} 2\pi Rcos\theta \ Rd\theta = 4 \pi R^2$

面积计算方法二: 考虑半球面 $z=\sqrt{R^2-x^2-y^2}$, 其在xOy平面上的投影为 $x^2+y^2 \leq R^2$, 可以用标准的曲面积分来算.

$\frac{\partial z}{\partial x} = -x(R^2-x^2-y^2)^{-\frac{1}{2}}$

$\frac{\partial z}{\partial y} = -y(R^2-x^2-y^2)^{-\frac{1}{2}}$

$S = 2\iint_{D} \sqrt{1+(\frac{\partial z}{\partial x})^{2}+(\frac{\partial z}{\partial y})^{2}} dxdy
   = 2\iint_{D} \sqrt{\frac{R^2}{R^2-x^2-y^2}}dxdy \\
   = 2\int_{0}^{2\pi} d\theta \int_{0}^{R} \sqrt{\frac{R^2}{R^2-\rho^2}}\rho d\rho
   = 2\int_{0}^{2\pi} R^2 d\theta
   = 4\pi R^2$

这里内层积分为反常积分, 应该首先判断其收敛性, 这里为了简便略去.

体积计算方法一: 取沿纬线的切片, 设 $x$ 为切片的圆心离球心的距离, $dx$ 为切片的厚度, 则切片的半径为 $r = \sqrt{R^2-x^2}$, 切片的体积为 $\Delta V = \pi r^2dx = \pi (R^2-x^2)dx$.

$V = 2\int_{0}^{R} \pi (R^2-x^2)dx = \frac{4}{3} \pi R^3$

体积计算方法二: 考虑半球面 $z=\sqrt{R^2-x^2-y^2}$, 其在xOy平面上的投影为 $x^2+y^2 \leq R^2$, 这是一个标准的曲顶柱体, 可以用标准的二重积分.

$V = 2\iint_{D} \sqrt{R^2-x^2-y^2}dxdy
   = 2\int_{0}^{2\pi}d\theta\int_{0}^{R} \sqrt{R^2-\rho^2} \rho d \rho
   = 2\int_{0}^{2\pi} \frac{R^3}{3} d\theta
   = \frac{4}{3} \pi R^3$

这里第二步用了二重积分的极坐标变换.

#### 引力

设物体的密度为 $\rho(x,y,z)$, 所占空间区域为 $\Omega$, 取物体中的一个小体积元 $dv$, 其位置为 $P=(x,y,z)$, 质量为 $\rho dv$. 设一质量为 $m$ 质点位于 $Q=(x_0,y_0,z_0)$, 根据牛顿的万有引力定律, 体积元与质点之间的引力为:

$dF= G \frac{m\rho(x,y,z)}{r^2}dv$, 方向为 $\vec{PQ}=(x_0-x,y_0-y,z_0-z)$.

其中, $r=|\vec{PQ}|=\sqrt{(x_0-x)^2+(y_0-y)^2+(z_0-z)^2}$.

将体积元在 $\Omega$ 上积分, 然后投影到各个坐标轴上, 即得到物体对质点的引力:

$(\iiint_{\Omega}G \frac{m\rho(x,y,z)(x_0-x)}{r^3}dv, \iiint_{\Omega}G \frac{m\rho(x,y,z)(y_0-y)}{r^3}dv, \iiint_{\Omega}G \frac{m\rho(x,y,z)(z_0-z)}{r^3}dv)$

**实心球对质点的引力**

设匀质实心球密度为 $\rho_0$, 所占空间方程为 $x_2+y^2+z^2 \leq R^2$, 质点质量为 $m_0$, 位于 $(0,0,z_0)$, 由于球的对称性, 沿着 $x$ 和 $y$ 方向的引力都为0, 下面只求沿着 $z$ 方向的引力.

情况一: 质点位于实心球外部, 此时 $0<R \leq z_0$

$F_z = \iiint_{\Omega}G \frac{m_0\rho_0(z_0-z)}{\sqrt{(x^2+y^2+(z-z_0)^2)}^3}dv \\
     = m_0\rho_0\int_{-R}^{R}dz \ \iint_{x^2+y^2\leq R^2-z^2}(z_0-z)(x^2+y^2+(z-z_0)^2)^{-\frac{3}{2}}dxdy$

考虑内层的二重积分, 用极坐标系来表示, 为:

$\int_{0}^{2\pi}d\theta\int_{0}^{\sqrt{R^2-z^2}}(z_0-z)(\rho^2+(z-z_0)^2)^{-\frac{3}{2}}\rho d\rho = 2\pi (1-\frac{z_0-z}{\sqrt{-2z_0z+R^2+z_0^2}})$

将其代入原式子, 得:

$F_z = 2\pi m_0\rho_0 G \int_{R}^{-R}(1-\frac{z_0-z}{\sqrt{-2z_0z+R^2+z_0^2}})dz
     = 2\pi m_0 \rho_0 G \frac{2R^3}{3z_0^2}
     = \frac{4}{3} \pi R^3 \rho_0 \cdot \frac{Gm_0}{z_0^2}$

最后这个积分可以直接查积分表, 但是相当难算.

从结果可知, 均匀的实心球对质点的引力相当于将实心球的质量集中于球心是两质点的引力.

情况二: 质点位于实心球内部, 此时 $0<z_0 \leq R$

基本表达式和情况一一致, 内层二重积分的结果为:

$\int_{0}^{2\pi}d\theta\int_{0}^{\sqrt{R^2-z^2}}(z_0-z)(\rho^2+(z-z_0)^2)^{-\frac{3}{2}}\rho d\rho = 2\pi (\frac{z_0-z}{|z_0-z|}-\frac{z_0-z}{\sqrt{-2z_0z+R^2+z_0^2}})$

注意上式和情况一的不同: 在 $z \in [-R, R]$ 时, $z_0-z$ 符号不定.

外层积分的结果为:

$F_z = 2\pi m_0\rho_0 G \int_{-R}^{R}(\frac{z_0-z}{|z_0-z|}-\frac{z_0-z}{\sqrt{-2z_0z+R^2+z_0^2}})dz \\
     = 2\pi m_0\rho_0 G (\int_{-R}^{R}\frac{z_0-z}{|z_0-z|}dz-\int_{-R}^{R}\frac{z_0-z}{\sqrt{-2z_0z+R^2+z_0^2}}dz)$

$\int_{-R}^{R}\frac{z_0-z}{|z_0-z|}dz = \int_{-R}^{z_0}dz-\int_{z_0}^{R}dz = 2z_0$

$\int_{-R}^{R}\frac{z_0-z}{\sqrt{-2z_0z+R^2+z_0^2}}dz=\frac{4z_0}{3}$ (这里的结果和情况一不一致, 是因为 $z_0$ 和 $R$ 的大小关系变了)

$F_z = 2\pi m_0\rho_0 G (2z_0-\frac{4z_0}{3})
     = \frac{4}{3} \pi \rho_0 Gm_0z_0
     = \frac{4}{3} \pi z_0^3 \rho_0 \cdot \frac{Gm_0}{z_0}$

从结果可知, 当质点在球内部时, 比质点距离球心远的部分对引力的贡献为0.

**空心球壳对质点的引力**

设球壳的内表面方程 $x^2+y^2+z^2=R_0^2$, 外表面方程 $x^2+y^2+z^2=R_1^2$, 质点质量 $m_0$, 位置 $(0,0,z_0)$, 球壳的密度为 $\rho_0$, 与位置无关. 且有: $0 \leq z_0 \leq R_0 < R_1$. 由于球的对称性, 沿着 $x$ 和 $y$ 方向的引力都为0, 下面只求沿着 $z$ 方向的引力.

在直角坐标系中, 由于积分区域非凸, 无法用标准的三重积分的方法. 这里采用迂回的方法: 把空心球壳填实, 计算整个的实心球的引力 $F_o$, 然后减去填充部分的引力 $F_i$ 贡献即可.

注意到在计算 $F_o$ 和 $F_i$ 的过程中, 质点都位于对应球的内部, 根据上一节讨论的结果, $F_o=F_i$, 所以 $F_z=0$.
