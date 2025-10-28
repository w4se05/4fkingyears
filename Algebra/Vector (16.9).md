## 🧩 Definition — Vector
Given two vectors $\vec{u}$ and $\vec{v}$ (in $\mathbb{R}^2$ or $\mathbb{R}^3$) and a scalar $\alpha \in \mathbb{R}$:

1. $\alpha \vec{u}$ is a vector in the **same direction** as $\vec{u}$ if $\alpha \ge 0$, or in the **opposite direction** if $\alpha < 0$.
2. **Parallelogram Rule** — The sum of $\vec{u}$ and $\vec{v}$ is represented by the diagonal of the parallelogram formed by them.
3. **Properties of Vectors:**
   - $\vec{u}+\vec{v}=\vec{v}+\vec{u}$  (Commutative)
   - $\vec{u}+(\vec{v}+\vec{w})=(\vec{u}+\vec{v})+\vec{w}$  (Associative)
   - $\alpha(\vec{u}+\vec{v})=\alpha\vec{u}+\alpha\vec{v}$  (Distributive)
   - $(\alpha+\beta)\vec{u}=\alpha\vec{u}+\beta\vec{u}$
   - If $A \equiv B$, then $\vec{AB}=0$  (Zero vector)
   - $\vec{AB}=-\vec{BA}$

In $\mathbb{R}^2$:  
$e_{1}=(1,0)$, $e_{2}=(0,1)$, then any $\vec{u}=x e_{1}+y e_{2}$.  
Here, $x$ and $y$ are called the **coordinates** of $\vec{u}$.

---

## 🧮 Constructing a Vector from Two Points
Given points $A(x_{a},y_{a})$ and $B(x_{b},y_{b})$,  

$$\vec{AB} = (x_{b}-x_{a},\, y_{b}-y_{a})$$

---

## ⚫ Dot Product
Given $\vec{u}, \vec{v} \in \mathbb{R}^2$ (or $\mathbb{R}^n$), where  
$\vec{u}=(x_{u},y_{u})$, $\vec{v}=(x_{v},y_{v})$,

then the **dot product** is defined as:  
$$\vec{u}\cdot\vec{v} = x_{u}x_{v} + y_{u}y_{v}$$

Two vectors $\vec{u}$ and $\vec{v}$ are **orthogonal** if the angle between them is $90^\circ$,  
that is, if $\vec{u}\cdot\vec{v} = 0$.

Alternatively:  
$$\vec{u}\cdot\vec{v} = |\vec{u}|\,|\vec{v}|\,\cos(\theta)$$  

Thus,  
$$\cos(\theta) = \frac{\vec{u}\cdot\vec{v}}{|\vec{u}|\,|\vec{v}|}$$  

where $|\vec{u}| = \sqrt{x_{u}^2 + y_{u}^2}$.

In general, if  
$\vec{u} = (x_{1},x_{2},\dots,x_{n})$ and $\vec{v} = (y_{1},y_{2},\dots,y_{n})$,  

then:  
$$|\vec{u}| = \sqrt{x_{1}^2 + x_{2}^2 + \dots + x_{n}^2}$$  
$$\vec{u}\cdot\vec{v} = x_{1}y_{1} + x_{2}y_{2} + \dots + x_{n}y_{n}$$

---

## ⚙️ Properties of the Dot Product
- $\vec{u}\cdot\vec{v} = \vec{v}\cdot\vec{u}$
- $\vec{u}\cdot(\vec{v}+\vec{w}) = \vec{u}\cdot\vec{v} + \vec{u}\cdot\vec{w}$
- $(\alpha\vec{u})\cdot\vec{v} = \alpha(\vec{u}\cdot\vec{v})$

According to the **Pythagorean Theorem**, for $\vec{u},\vec{v} \in \mathbb{R}^n$:

$$|\vec{u}+\vec{v}|=|\vec{u}-\vec{v}|\implies \vec{u}\cdot\vec{v}=0$$

Consequently, if $\vec{u}\cdot\vec{v}=0$, then:  
$$|\vec{u}+\vec{v}|^2 = |\vec{u}|^2 + |\vec{v}|^2$$

---

## 🧱 Area of a Parallelogram in $\mathbb{R}^2$ (Determinant)
Given $\vec{u}$ and $\vec{v}$ in $\mathbb{R}^2$, and a parallelogram $ABCD$ spanned by them:  

$$S_{ABCD} = 2S_{ABC} = 2\cdot\frac{1}{2}|\vec{AB}||\vec{AC}|\sin(\theta)$$  

Let:
- $\vec{AB} = (x_{1},y_{1})$
- $\vec{AC} = (x_{2},y_{2})$
- $\sin(\theta) = \sqrt{1 - \cos^2(\theta)}$

Then:  
$$S = \sqrt{(x_{1}^2+y_{1}^2)(x_{2}^2+y_{2}^2) - (x_{1}x_{2}+y_{1}y_{2})^2}$$  

Simplifying:  
$$S = \sqrt{(x_{1}y_{2} - x_{2}y_{1})^2} = |x_{1}y_{2} - x_{2}y_{1}|$$  

This expression represents the **determinant**, i.e., the **area** of the parallelogram.

🎥 [Watch this concept explained visually](https://www.youtube.com/watch?v=Ip3X9LOh2dk)
