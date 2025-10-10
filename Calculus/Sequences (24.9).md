>	[!Definition] Sequence
>A **sequence** is a list of numbers written in a definite order:
>$$a_{1},a_{2},a_{3},\dots,a_{n},\dots \equiv \{a_{n}\}$$
>$a_{1}$: first term, $a_{2}$: second term, in general $a_{n}$: n-th term
>
>Finite Sequence: has finite number of terms
>Infinite Sequence: $\{a_{n}\text{ or more complex general rule of the sequence}\}^{\infty}_{n=1}$
>
>Sequences $\neq$ Sets. Sequences take into account the order of the terms while Sets do not.
>
>Sequences can be plotted on number lines or on the coordination plane 
>
>**IT IS ALL ABOUT RECOGNIZING THE PATTERN**
>
>**Note**: Signs alternate: $(-1)^n$ or $(-1)^{n-1}$ depending on where n starts

>[! Geometric Sequence]
>$$a, ar, ar^{2},ar^3,\dots$$
>where $a\neq 0$ is the first term and $r \neq{0}$ is the common ratio. The general term is
>$$a_{n}=ar^{n-1}$$ 

>[!Arithmetic Sequence]
>$$a,a+d,a+2d,a+3d,\dots$$
>where $a$ is the first term and $d$ is the common difference. The general term is $$a_{n}=a+(n-1)d$$

>[!Definition] Limit
> A sequence $\{a_{n}\}$ has the limit L if
> $$\forall \epsilon > 0, \exists N \in \mathbb{N}: |a_{n}-L|<\epsilon, \forall_{n}>N $$
> We write $\lim_{ n \to \infty }a_{n}=L$ or $a_{n}\to L$
> 
> **$\lim_{ n \to \infty }a_{n+1}=\lim_{ n \to \infty }a_{n}=L$**
> 
> For any given constant sequence $a_{n}=C$ (for all $n \in \mathbb{N}$)
> We have: $\lim_{a_{n}}=C$
> 
> **Notation:**
> - $\lceil a \rceil$: is the smallest integer that is bigger than or equal a 
>   e.g $\lceil 0.2 \rceil=1$
> - $\lfloor a \rfloor$ is the biggest integer that is smaller than or equal a 
>   e.g $\lfloor 0.2 \rfloor=0$
> - If |r|<1, then $\lim_{ n \to \infty }r^n=0$. Ask for proof? **Go fk urself.**
> 
>**Limit Laws for $\textbf{Sequences}$**
>Given lim $a_{n}=A$ and lim $b_{n}=B$, bear in mind that $a_{n}$ and $b_{n}$ are independent and both of them are convergent
> 1. $\lim{ a_{n}\pm b_{n}}=A\pm B$
> 2. $lim(ca_{n})=cA,\; c \in \mathbb{R}$
> 3. lim$(a_{n}b_{n})=AB$
> 4. lim$\left( \frac{a_{n}}{b_{n}} \right)=\frac{A}{B},\;B\neq_{0}$
> 5. If $a_{n}<b_{n}, \forall n\geq N$, then $\lim_{ n \to \infty}a_{n}\leq \lim_{ n \to \infty }b_{n}$
> 6. $\lim_{ n \to \infty }a_{n}^p=A^p$,  if $p>0$ and $a_{n}>0$

>[!Definition] Convergence and Divergence
>- If $\lim_{ n \to \infty }a_{n}=L \in \mathbb{R}$, then the limit exists, is **unique**, and the sequence is called **convergent**. Notation: $a_{n}\to L$ as $n\to \infty$
>- If $\lim_{ n \to \infty }a_{n}=\pm \infty$, the sequence **diverges to infinity**
>- Otherwise, {$a_{n}$} is simply called **divergent**
>
>**Example:**
> - $a_{n}=\frac{1}{n}\quad\implies a_{n}\to{0}$ (convergent)
> - $a_{n}=n\quad\implies a_{n}\to +\infty$ (diverges to infinity)
> - $a_{n}=(-1)^n\quad\implies$ oscillates, no limit (divergent)
> 
> If $a_{n}\to L$ then also $a_{n+1}\to L$ by the definition of limit

>[!Definition] Boundedness
>A sequence {$a_{n}$} is **bounded** if there exists $M>0$ such that
>$$|a_{n}|\leq M, \; \forall n\in \mathbb{N}$$
>
>**Example:**
>- $a_{n}=\frac{n}{n+1}$ is bounded because $0<a_{n}<1$ for all $n$, so we can choose $M=1$
>- $a_{n}=(-1)^{n}$ is bounded because $|a_{n}|=1$ for all $n$, so we can choose $M=1$, BUT this sequence is not converge because it oscillates, not increasing nor decreasing.
>- $a_{n}=n$ is unbounded because $|a_{n}|=n\to \infty$ as $n\to \infty$, so no finite M can satisfy $|a_{n}|\leq M$

>[!Definition] Monotonicity 
>A sequence {$a_{n}$} is 
> - **increasing** if $a_{n+1}\geq a_{n}$ for all n
> - **decreasing** if $a_{n+1}\leq a_{n}$ for all n
> - **monotone** if it is increasing or decreasing
>   
**Example:**
>- $a_{n}=\frac{n}{n+1}$ is increasing because
>$$a_{n+1}-a_{n}=\frac{n+1}{n+2}-\frac{n}{n+1}=\frac{1}{(n+1)(n+2)}>0$$
>- $a_{n}=\frac{1}{n}$ is decreasing because
>$$a_{n+1}-a_{n}=\frac{1}{n+1}-\frac{1}{n}=-\frac{1}{n(n+1)}<0$$
>
>**Weirestrass Theorem**:
>$\quad$Every **bounded monotone sequence** is convergent
>
>**Example:**
> - $a_{n}=1-\frac{1}{n}$ is increasing, bounded above by 1. Thus $\lim_{ n \to \infty }a_{n}=1$
> - $a_{n}=n$ is monotone but unbounded above and thus diverges to infinity
> - $a_{n}=\sin(n)$ is bounded (between -1 and 1), but not monotone and does not converge (it oscillates irregularly)
> - $a_{n}=(-1)^n$ is bounded but divergent, because it is not monotone
>   
>**By the Monotone Convergence Theorem:**
> $$\lim_{ n \to \infty }\left( 1+\frac{1}{n} \right)^n=e $$

>[!Definition] Squeeze Theorem
>Let {$a_{n}$}, {$b_{n}$},{$c_{n}$} be sequences such that
>$$a_{n}\leq b_{n}\leq c_{n}\; \forall n\geq N$$
>*If*
>$$\lim_{ n \to \infty } a_{n}=\lim_{ n \to \infty } c_{n}=L$$
>*then*
>$$\lim_{ n \to \infty } b_{n}=L$$
>
>**Example:**
>Consider the sequence
>$$a_{n}=\frac{(-1)^n}{2\sqrt{ n }}$$
>We have
>$$-\frac{1}{2\sqrt{ n }}\leq a_{n}\leq{\frac{1}{2\sqrt{ n }}},\; \forall n\geq{1}$$
>Since
>$$\lim_{ n \to \infty } -\frac{1}{2\sqrt{ n }}=\lim_{ n \to \infty } \frac{1}{2\sqrt{ n }}=0$$
>by the **Squeeze Theorem**, we conclude that
>$$\mathbf{\lim_{ n \to \infty }a_{n}=0 }$$
>$\implies$This theorem can **ONLY** be used to define the convergent
>
>Here is why:
![[Screenshot 2025-09-25 095429.png]]
>
>Imagine {$a_{n}$} and {$c_{n}$} have different limits, then the limit of $b_{n}$ can be anywhere between them. Only when both lim($a_{n}$) and lim($b_{n}$) approach the same $L$ as the n goes to infinity can we apply this theory

>[!Definition] Another Stupid Theorems that don't even have a fking NAME
>1. Odd Even Theorem (seriously?)
> *Let {$a_{n}$} be a sequence*
> - If both the subsequences of even and odd indices converge to the same limit L, i.e
> $$\lim_{ n \to \infty } a_{2k}=L\quad and\quad \lim_{ n \to \infty } a_{2k-1}=L$$
> then the whole sequence **converges** and
> $$\lim_{ n \to \infty } a_{n}=L$$
> - If $\lim_{ k \to \infty }a_{2k} \neq \lim_{ k \to \infty }a_{2k-1}$, then the sequence {$a_{n}$} **does not converge**
>  
 $\implies$**This theorem is used to define both convergent and divergent**
>
>
>1. Absolute Value Theorem (idk)
>Let {$a_{n}$} be a real sequence. If
>$$\lim_{ n \to \infty } |a_{n}|=0,$$
>then
>$$\lim_{ n \to \infty } a_{n}=0$$ 
>
>
>2. Ratio Test
>First we compute $r=\frac{a_{n+1}}{a_{n}}$
> - If $\lim_{ n \to \infty }r>1$,$\lim_{ n \to \infty }|a_{n}|=\infty$, however, we cannot $\implies$ $a_{n} \to \infty$ as the actual sequence could:
>	+ go to $+\infty$ (e.g $a_{n}=n$)
>	+ go to $-\infty$ (e.g $a_{n}=-n$)
>	+ or oscillates with growing magnitude (e.g $a_{n}=(-1)^nn$)
> - If $\lim_{ n \to \infty }r<1$, $a_{_{n}} \to 0$. 
> - If $\lim_{ n \to \infty }r=1$, we cannot conclude anything, switch to another method pls
>   
>**Note: It is important that we need to take $\lim_{ n \to \infty }r$ to conclude**







