## 距离, 拉格朗日乘子, 以及SVM

SVM的核心是要最大化support vector到分类平面的距离.


## 点到超平面的距离

高维空间一点$X'$ 到平面$WX+b=0$的距离可以表示为求解如下约束问题:

1. $\min \frac{1}{2} \left \| X - X' \right \|^2  \ s.t. \ W X + b=0$

这实际上是一个等式约束的二次规划问题, 可以用拉格朗日乘子法求解:

2. $\min f(X) = \frac{1}{2} \left \| X - X' \right \|^2  + \lambda (W X + b)$

3. $\frac{\partial f}{\partial X} = (X - X') + \lambda W = 0$

4. $\frac{\partial f}{\partial \lambda} = W X + b = 0$

注意公式3实际上是向量表示, 将X解出, 带入到公式4, 可得:

5. $W(X'-\lambda W)+b=0 \Rightarrow \lambda = \frac{WX'+b}{\left \| W \right \|^2}$

将公式5代入到公式3可得:

6. $X - X' = \frac{WX'+b}{\left \| W \right \|^2} W$

注意公式6也是向量表示, 公式6两边平方开个根号即是距离(这里为了简便省掉根号,
直接计算距离的平方):

7. $\left \| X - X' \right \| = \frac{(WX'+B)^2}{\|W\|^2}$
