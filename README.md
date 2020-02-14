## 应用

**椭圆**

椭圆方程: $\frac{x^2}{a^2}+\frac{y^2}{b^2}=1$.
参数方程: $\left \{ \begin{array}{l}{x=a \cos \alpha} \\ {y=b \sin \alpha}\end{array} \right$

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
