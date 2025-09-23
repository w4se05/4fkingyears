# I. Def:

Given 2 vector $\vec{u}$ and $\vec{v}$ (in $R^{2}, R^3$)
Given $\alpha\in R$
1. We define $\alpha.\vec{u}$ in a vector sit in its direction that is the SAME  if $\alpha\geq_{}0$ or OPPOSITE if $\alpha<0$ as $\vec{ u}$
2. Parallelogram rule
3. Props of Vectors:
- $\vec{u}+\vec{v}=\vec{v}+\vec{u}$ (commutative)
- $\vec{u}+(\vec{v}+\vec{w})=(\vec{u}+\vec{v})+\vec{w}$ (associative)
- $\alpha.(\vec{u}+\vec{v})=\alpha\vec{u}+\alpha\vec{v}$ (distributive)
- $(\alpha+\beta).\vec{u}=\alpha.\vec{u}+\beta.\vec{u}$
- If A $\equiv$ B, $\vec{AB}=0$ (vector zero)
- $\vec{AB}=-\vec{BA}$
4. In $\mathbb{R}^2$, $e_{1}=(1,0),e_{2}=(0,1)$, then any $\vec{u}=x.e_{1}+y.e_{2}$, x and y are called the coordinates of $\vec{u}$

# II. Construct a Vector out of 2 points

Given $A(x_{a},y_a)$ and $B(x_{b},y_{b})$
Then$$\vec{ AB } =(x_{b}-x_{a},y_{b}-y_{a}) $$
# III. Dot Product
Given $\vec{ u}, \vec{v} \in \mathbb{R}^2$ ($\mathbb{R}^n$). If $\vec{u}=(x_{u},y_{u})$ and $\vec{v}=(x_{v},y_{v})$ , then the dot product of $\vec{u}$ and $\vec{v}$, denoted $\vec{u}. \vec{v}$ is defined:$$\vec u. \vec v=x_u.x_{v}+y_{u}.y_{v}$$
The 2 vectors $\vec{ u}, \vec{v}$ are orthogonal when the angle of them is 90 degree, meaning that their dot product = 0
Besides, there is another way to calculate dot product$$\vec{u}.\vec{v}=|\vec{u}|.|\vec{v}|.\cos(\vec{u},\vec{v})$$
From that we have:$$\cos(\vec{u},\vec{v})=\frac{\vec{u}.\vec{v}}{|\vec{u}|.|\vec{v}|}$$
With $|\vec{u}|=\sqrt{ x_{u}^2+y_{u}^2 }$ 
In general, $\vec{u}=(x_{1},x_{2},\dots,x_{n})$, $\vec{v}=(y_{1},y_{2},\dots,y_{n})$ 
$$|\vec{u}|=\sqrt{ x_{1}^2+x_{2}^2+\dots+x_{n}^2 }$$ and
$$\vec{u}.\vec{v}=x_{1}y_{1}+x_{2}y_{2}+\dots+x_{n}y_{n}$$
## Props of Dot Product:

- $\vec{u}.\vec{v}=\vec{v}.\vec{u}$
- $\vec{u}.(\vec{v}+\vec{w})=\vec{u}.\vec{v}+\vec{u}.\vec{w}$
- $(\alpha.\vec{u}).\vec{v}=\alpha.(\vec{u}.\vec{v})$

According to Pythagoras Theorem, given $\vec{u},\vec{v} \in R$

$$|\vec{u}+\vec{v}|=|\vec{u}-\vec{v}|\implies \vec u.\vec{v}=0$$

Consequently, if $\vec{u}.\vec{v}=0$, then $|\vec{u}+\vec{v}|^2=|\vec{u}|^2+|\vec{v}|^2$

# IV. Area of the Parallelogram in $R^2$ (Determinant)

Given $\vec{u}$ and $\vec{v}$ $\in R^2$ and $ABCD$ is the parallelogram spanned by those 2 vectors
$S_{ABCD}=2.S_{ABC}=2.\frac{1}{2}\vec{|AB|}.\vec{|AC|}.\sin(\vec{AB},\vec{AC})$
Supposing that:
- $\vec{AB}=(x_{1},y_{1})$
- $\vec{AC}=(x_{2},y_{2})$
and $\sin(\vec{AB},\vec{AC})=\sqrt{ 1-\cos^2(\vec{AB},\vec{AC}) }$
$\implies \sqrt{ (x_{1}^2+y_{1}^2).(x_{2}^2+y_{2}^{2})-\frac{(x_{1}^2+y_{1}^2).(x_{2}^2+y_{2}^{2}).(x_{1}x_{2}+y_{1}y_{2})^2}{(x_{1}^2+y_{1}^2).(x_{2}^2+y_{2}^{2})}}$

=$\sqrt{ (x_{1}^2+y_{1}^2).(x_{2}^2+y_{2}^{2})-(x_{1}x_{2}+y_{1}y_{2})^2}$

After reducing blah blah blah we have:

$\implies \sqrt{  x_{1}^2y_{2}^2+x_{2}^2y_{1}^2-2x_{1}x_{2}y_{1}y_{2}}=\sqrt{(x_{1}y_{2}-x_{2}y_{1})^2 }$$\implies|x_{1}y_{2}-x_{2}y_{1}|$

This is the DETERMINANT

[HOP IN YOUTUBE AND WATCH THIS SHIT ](https://www.youtube.com/watch?v=Ip3X9LOh2dk)

