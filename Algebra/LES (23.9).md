>[!Definition] Linear Equation
>A **linear equation in n variables** $x_{1},x_{2},\dots, x_{n}$ in an equation satisfying $a_{1}x_{1}+a_{2}x_{2}+\dots +a_{n}x_{n}=b$ (1)
>
>We have:   $\begin{split}
&a_{1},a_{2},\dots ,a_{n} \in R \text{ called } \textbf{coefficient} \text{ of (1)}\\&b\in R \text{ is called }\textbf{the right hand side} \text{ of (1)}
\end{split}$

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
\end{pmatrix}\text{is called the coefficient matrix for (2)}$$
And the matrix (A|b)
>$$A=\begin{pmatrix}
a_{11} & a_{12} & \dots & a_{1n} &|&b_{1} \\
a_{21} & a_{22} & \dots & a_{2n} &|&b_{2}\\
. \\
. \\
a_{m_{1}} & a_{m_{2}}& \dots &a_{m_{n}} &|&b_{m}
\end{pmatrix}\text{is called the augmented 
matrix for (2)}$$



>[!Definition] Row Echelon Form And Gaussian Elimination
>The REF (A$^*$|b$^*$) of a LES should look like this
>$$A=\begin{pmatrix}
a_{11} & a_{12}&a_{13} & \dots & a_{1n} &|&b_{1} \\
0 & a_{22} &a_{23}& \dots & a_{2n} &|&b_{2}\\
0 & 0& a_{33} & \dots & a_{3n} &|&b_{3}\\
. \\
. \\ 
0 & 0&0& \dots &a_{m_{n}} &|&b_{m}
\end{pmatrix}$$
and all the coefficient $a_{ij}, i=j$, sequentially become the leading entry (pivot) as we transforming the LES in order to make all the coefficient of the variables below the pivot in the same column become 0. At the final equation, all the variables whose the coefficient is not the pivot are called free variable, meaning that it can take any values and the pivot's value must be dependent on them.
>
**TL;DR**
The matrix is a row echelon form if satisfies:
> 1. All zero rows are at the bottom of the matrix
> 2. For each non-zero row, we call the left most non-zero the pivot. All entries below the pivot of a column are zero
> 3. All pivots are ordered from the top to the bottom & from the left to the right, i.e the pivot of a row is in a col. to the right of the pivot of the row above it
> 4. All variables which are not the pivot at the final equations are regarded free variables. The pivot variable must be dependent on them
> 
> After transforming the LES to the row echelon form, we use back substitution to solve dependent variables in terms of free variables form bottom to the top. This method is called **Gaussian Elimination**. 
> 
> **Note:** 
> - (A|b) is inconsistent if A* has a zero but the corresponding right hand side is non-zero
> - The number of free variables is the level of dimension of the solution set

>[!Definition] Gaussian - Jordan Elimination Method
>$$(A|b)\xrightarrow{\text{GE}}(A^*|b^*)\xrightarrow[\text{from the bottom to the top}]{\text{E}}(\text{A**|b**})$$
>
>$A^\text{**}$ row echelon form so that all entries below and above the pivot are 0s and all pivot are 1s. This is called **Reduced Echelon Form**
>
>This method help us to simplify (idk) the procedure of calculating the solution set


