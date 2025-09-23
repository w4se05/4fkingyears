>[!Definition] Linear Equation
>A **linear equation in n variables** $x_{1},x_{2},\dots, x_{n}$ in an equation satisfying $a_{1}x_{1}+a_{2}x_{2}+\dots +a_{n}x_{n}=b$ (1)
>We have:   $a_{1},a_{2},\dots ,a_{n} \in R$ called coefficient of (1)
>		$b\in R$ is called the right hand side of (1)

>[!Definition] Linear Equation System
>A system of $m$ linear equations in $n$ variables is called **a linear equation
>system** (LES)
>$$
\left\{
\begin{array}{l}
a_{11}x_{1}+a_{12}x_{2}+\dots+a_{1n}x_{n}=b_{1} \\ 
a_{21}x_{1}+a_{22}x_{2}+\dots+a_{2n}x_{n}=b_{2} \\ \dots  \\\dots
\\
a_{m_{1}}x_{1}+am_{2}x_{2}+\dots+a_{m_{n}}x_{n}=b_{m}
\end{array}
\right.(2)$$
$a_{ij}\in R, 
\begin{split}
&i=1,2,\dots m \\ 
&j=1,2,\dots ,n
\end{split}$ are called coefficients of (2) and $b_{1},b_{2},\dots,b_{m}$ are the right hand sides

>[!Definition] Solution Set of a LES
>A solution to (2) is assignment variables $x_{1},x_{2},\dots,x_{n}$ to real numbers $s_{1},s_{2},\dots,s_{n}$ so that all equations of (2) are satistifed
>We write that solution in a vector form
>$$
\begin{pmatrix}
x_{1} \\
x_{2} \\
. \\
. \\
. \\ 
x_{n}
\end{pmatrix}=
>\begin{pmatrix}
s_{1} \\
s_{2} \\
. \\
. \\
. \\ 
s_{n}
\end{pmatrix}
$$

>[!Definition] Consistency of a LES
>(2) is called consistent if it has at least 1 solution, otherwise, it's called inconsistent

>[!Definition] Equivelance of 2 LESs
>2 LESs are called equivalent if they have the same solution set
>**Note**: There are 3 elementary operations unchanging the solution set
>- Multiplying an equation by a non-zero number
>- Adding a multiple equation to another equation
>- Interchanging two equations

>[!Definition]  Coefficient matrix of a LES
>Given a LES
>$$
\left\{
\begin{array}{l}
a_{11}x_{1}+a_{12}x_{2}+\dots+a_{1n}x_{n}=b_{1} \\ 
a_{21}x_{1}+a_{22}x_{2}+\dots+a_{2n}x_{n}=b_{2} \\ \dots  \\\dots
\\
a_{m_{1}}x_{1}+am_{2}x_{2}+\dots+a_{m_{n}}x_{n}=b_{m}
\end{array}
\right.(2)$$ 
>The matrix
>$$A=\begin{pmatrix}
a_{11} & a_{12} & \dots & a_{1n} \\
a_{21} & a_{22} & \dots & a_{2n} \\
. \\
. \\
a_{m_{1}} & a_{m_{2}}& \dots &a_{m_{n}} 
\end{pmatrix}$$
is called the coefficient matrix for (2)
And the matrix (A|B)
>$$A=\begin{pmatrix}
a_{11} & a_{12} & \dots & a_{1n} &|&b_{1} \\
a_{21} & a_{22} & \dots & a_{2n} &|&b_{2}\\
. \\
. \\
a_{m_{1}} & a_{m_{2}}& \dots &a_{m_{n}} &|&b_{m}
\end{pmatrix}$$
is called the augmented matrix for (2)







