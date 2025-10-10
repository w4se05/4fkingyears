>[!Definition] Infinite Series
>Given a sequence {$a_{n}$}, the expression 
>$$\displaystyle\sum^\infty_{n=1}a_{n}=a_{1}+a_{2}+a_{3}+\dots$$
>is called an **Infinite Series**
>
>Whose the **Partial Sum** is
>$$s_{n}=\displaystyle\sum^n_{k={1}}a_{k}$$

>[!Convergence]
>If the sequence {$s_{n}$} has a finite limit $s$, then $$\displaystyle\sum^\infty_{n=1}a_{n}=s$$
>and the series is **Convergent**.
> Otherwise, the series is **Divergent**
> 
> **Note:** The way con/divergence works in series is a lil diff from the sequence. If a series converges, we know that we can calculate its sum, otherwise, we cannot
> Check the lecture slides for further example
> 

>[!Definition] Algebra of Convergent Series
>1. Suppose $\sum a_{n}$ and $\sum b_{n}$ are convergent series. Then:
> $$\sum(a_{n}\pm b_{n})=\sum a_{n}\pm \sum b_{n}$$
> 2. For any constant $c$, $\sum ca_{n}=c\sum a_{n}$
>    
>**Theorem:**
> If *$\sum a_{n}$ converges*, then *$a_{n}\to 0$*
> 
> Let $s_{n}=a_{1}+a_{2}+\dots+a_{n}$ be the partial sum. If $\sum a_{n}$ converges, then $s_{n}\to S$ for some finite S.
> 
> Consequently, if *$\lim_{ n \to \infty }a_{n}\neq 0$* then the series *diverges*
> 
>**NOTE: THIS IS AN ONE-WAY THEOREM, THERE IS NO OTHER WAY BACK**
> 
> **Proof:**
> $$a_{n}=s_{n}-s_{n-1}$$
> Since $s_{n}\to S$ and $s_{n-1}\to S$, we have
> $$a_{n}=s_{n}-s_{n-1}\to S-S=0$$

>[!Definition] Comparison Test (Squeeze Theorem Rep 1:1)
>*Suppose* $0\leq a_{n}\leq b_{n}$
>- If *$\sum b_{n}$ converges*, then *$\sum a_{n}$ also converges*
>- If *$\sum a_{n}$ diverges*, then *$\sum b_{n}$ also diverges*

>[!Definition] p-Series Test
>*The series*
>$$\displaystyle\sum^\infty_{n=1}\frac{1}{n^P}$$
>- **converges** if $p>1$ 
>- **diverges** if $p\leq{1}$

>[!Definition] Limit Comparison Test
>If $a_{n},b_{n}>0$ and
>$$\lim_{ n \to \infty } \frac{a_{n}}{b_{n}}=c,\quad 0<c<\infty$$
>then $\sum a_{n}$ and $b_{n}$ *either both converge or both diverge*
>- If *c=0* and *$\sum b_{n}$ converges*, then *$\sum a_{n}$ converges as well*
>- If *$c=\infty$*, and *$\sum b_{n}$ diverges*, then *$\sum a_{n}$ diverges as well*

>[!Definition] Ratio Test
>For $\sum a_{n}$, let 
>$$L=\lim_{ n \to \infty }\left|\frac{a_{n+1}}{a_{n}}\right|$$
>- If $L<1$, the series *converges absolutely *
>- If $L>1$ or $L=\infty$, the series *diverges*
>- If $L=1$, the test *is inconclusive*
 
>[!Definition] Root Test
>For $\sum a_{n}$, let
>$$L=\lim_{ n \to \infty } \sqrt[n]{|a_{n}| } $$
>- If $L<1$, the series *converges absolutely*
>- If $L>1$ or $L=\infty$, the series *diverges*
>- If $L=1$, the test *is inconclusive*

>[!Definition] Leibniz Criterion
>Consider *$\sum(-1)^{n-1}b_{n}$* with *$b_{n}\geq{0}$*. If
> $$b_{n+1} \leq b_{n} \text{ (decreasing) and } \lim_{ n \to \infty }b_{n}=0$$
> then the series *converges*

>[!Definition] Absolute/Conditional Convergence
>A series $\sum a_{n}$ is *absolutely convergent* if
>$$\sum|a_{n}|\text{ converges}$$
>A series $\sum a_{n}$ is *conditionally convergent* if
>$$\sum a_{n}\text{ converges, but }\sum|a_{n}| \text{ diverges}$$
>
>**Remark:**
>- *Absolutely Convergent* $\implies$ series also converges
>- *Conditionally convergent* $\implies$ series converges, but not absolutely
>
>

