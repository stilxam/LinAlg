<center><h1> Linear Algebra Notes </h1>
<u>Maxwell Litsios-Hilbert</u> </center>

## 1.1 Linear Maps
### Definition (Linear map):
A map $A: V \rightarrow W$ is called *linear* if for all $x, y \in V$  and for all $\alpha, \beta \in \mathbb{R}$.
$$ A(\alpha x + \beta y)= \alpha A x + \beta A y$$


### Definition (Composition):
Suppose $A: V \rightarrow W$ and $B: U \rightarrow V$ are linear maps.
Then the *composition*  $A \circ B = AB: U \rightarrow W$

$$A \circ B = A(B(u)), \forall{u} \in U$$ 

### Definition (Null Space):
Let $A : V \rightarrow W$ be a linear map.
$$ N := \{v \in V | A(v)=0\}$$
$N$ is called the *null space* or *kernal* of $A$

### Definition (Range):
Let $A : V \rightarrow W$ be a linear map.
$$ R := \{A(v) \in W | v \in V\}$$
$R$ is called the *range* of $A$ it can also be denoted $A(V)$.


### Theorem (Injectivity, Surjectivity and Bijectivity of a Linear Map):
1. $N = \{0\} \iff A$ is injective
2. $R = W \iff A$ is surjective
3. Let $b \in R$. Then there is a vector $p$ s.t. $A(p) = b$, we say that p is a particular solution of the vector equation $A(x) = b$. All solutions of the vector equation $A(x) = b$ are given by the set
$$ p + N = \{p + n | n \in N\} $$
This set is called a **coset**.

### Theorem (Existence and Uniqueness of L.M. with Prescribed Values on Basis):
Let $V$ and $W$ be vector spaces, $\{a_1, ..., a_n\} a basis for $V$ and $\{w_1, ..., w_n\}$ an n-tuple vector in $W$. Then, there exists a unique linear map $A: V \rightarrow W$ s.t. $A(a_i) = w_i $ for $i = 1, ..., n$.

### Theorem (Range of a L.M. by its Basis):
Consider $A: V \rightarrow W$ with $V = <a_1, ... , a_n>$ then $R= <A(a_1), ..., A(a_n)>$.


### Theorem (Dimensions):
Let $A : V \rightarrow W$ be a linear map with $dim(V) < \infty$.
Then :

$$ dim(V) = dim(N) + dim(R)$$

### Theorem (Invertability w.r.t. Dimensions):
Let $A : V \rightarrow W$ be a linear map with $dim(V) < \infty$.
$A^{-1}$ exists $\iff dim(V) = dim(W) \land N = \{0\}$



## 1.2 Matrices of Linear Maps I
In this section, we study linear maps $\mathbb{K}^n \rightarrow \mathbb{K}^m$, where $\mathbb{K} = \mathbb{R}, \mathbb{Q}$ or $\mathbb{C}$ or even more exotic fields. We will use matrices to describe such maps.

### Theorem (Matrix Representation for Linear Maps):
Every linear map $A : \mathbb{K}^n \rightarrow \mathbb{K}^m$ is determined by an $m \times n$ matrix $A$ whose columns are $Ae_1, ..., Ae_n$. The image of the vector $x$ under $A$ can be computed as the matrix product $A(x)$.

### Definition (Matrix of the Linear Map):
The matrix $A$ is called the _matrix of the linear map_ $A$.


### Algorithm (Computing the matrix):
A linear map $A: \mathbb{K}^n \rightarrow \mathbb{K}^m$ is uniquely determined by the images of a basis $a_1, ..., a_n$ for $\mathbb{K}^n$. If $e_1, ..., e_n$ is the basis, then we may just write the matrix using the theorem "Existence and Uniqueness of L.M. with Prescribed Values on Basis". However, if we start with another basis, we must employ the following computations.
Let $A$ be a linear map and consider the two ordered pairs of row-vectors, LHS is a vector in $\mathbb{K}^n$, RHS is its image in $\mathbb{K}^m$,
$$ (a, A(a))$$
$$ (b, A(b))$$
Since a is linear
$$(a+b, A(a)+ A(b))$$
$$(\alpha a, \alpha A(a))$$
#### Example:
$$ A(− 1, 0, 1) = (− 4, 2, 4), A(1, 1, 0) = (1, − 1, − 1), A(0, 1, 2) = (− 5, 4, 4)$$
$$ 
\begin{pmatrix} 
-1 &0&1 &|& -4 & 2 & 4\\
1 & 1&0&|&1 & -1 & -1\\ 
0 & 1 & 2  &|& -5 & 4 & 4
\end{pmatrix}
$$
$$RReF$$
$$
\begin{pmatrix} 
1 & 0 & 0 &|& 2 & 1 & -3 \\
0 & 1 & 0 &|& -1 & -2 & 2 \\ 
0 & 0 & 1 &|& -2 & 3 & 1
\end{pmatrix}
$$
$$(I^T, (A(I))^T)$$

Now we have in our rows on the LHS the standard basis of vectors $e_1, e_2, e_3$ and on the RHS their image. i.e. the matrix A.

### Theorem (Matrix Composition):
Let $A, B$ be two matrices s.t. $AB$ exists, and let $A$ and $B$ be the corresponding linear maps.
Then, $AB$ is the matrix of the product map $\mathfrak{AB}$.

### Theorem (Matrix of Sum and Scalar Multiples):
Let $A, B$ be two matrices of the same size and let $\mathfrak{A} , \mathfrak{B}$ be the corresponding linear maps.
Then, $A+B$ is the matrix of the sum $\mathfrak{A+B}$ and for every scalar $\alpha$, the matrix of the linear map $\alpha A$ is $\mathfrak{\alpha A}$.

### Theorem (Matrix of the Inverse):
let $A: \mathbb{K}^n \rightarrow \mathbb{K}^m$  be a linear map with matrix $A$. Then the map $\mathfrak{A}$ has an inverse iff the matrix $A$ has an inverse.
If $\mathfrak{A}$ has an inverse, then $\mathfrak{A}^{-1}$ is equal to $A^{-1}$.


## 1.3 Matrices of Linear Maps II
- Effect on the coordinates of a vector when changing basis
- Description of linear maps using matrices depending on choice of basis
- Change of basis

### Coordinates:
In an $n$-dimensional vector space $V$, we choose a basis $\alpha = \{a_1, ..., a_n\}$.
Every vector $x \in V$ can now be expressed as a linear combination of the basis vectors.
$$ x = x_1 a_1 + ... + x_n a_n$$
The numbers $x_1, ..., x_n$ are the coordinates of $x$ w.r.t. the basis $\alpha$, and $(x_1, ..., x_n)$ is the coordinate vector of $x$ w.r.t. basis $\alpha$.
#### Property:
If we choose a basis $\alpha$ in an $n$-dimensional vector space $V$, then the map sending each vector $x$ to its coordinates w.r.t. this basis is an invertible linear map from $V$ to $\mathbb{K}^n$.
We will usually denote this map also by $\alpha$. This shouldn't lead to confusion : $\alpha (x)$ is the coordinate vector of the vector $x \in V$ w.r.t. the basis $\alpha$.

### Change of basis:
Consider an $n$-dimensional vector space $V$ and choose for $V$ two bases:
$$ \alpha = \{a_1, ..., a_n\}, \beta = \{b_1, ..., b_n\}$$
So now with every $x \in V$, there are two sets of coordinates: 
- $\alpha (x)$ w.r.t. the basis $\alpha$
- $\beta (x)$ w.r.t. the basis $\beta$

### Definition (Coordinate Transformation / Map):
Let $\alpha$ and $\beta$ be bases of an $n$-dimensional vector space $V$.
The linear map $\beta \alpha ^{-1}: \mathbb{K}^n \rightarrow \mathbb{K}^n$ is called the *coordinate transformation (map)* from $\alpha$ to $\beta$

### Theorem (Transition Matrix):
Let $\alpha$ and $\beta$ $n$-dimensional vector space $V$ and let $_{\beta} S_\alpha$ be the matrix of $\beta \alpha^{-1}$. If $x$ is the $\alpha$-coordinate vector of a vector $v \in V$, then the $\beta$-coordinate vector of $v$ is equal to $_{\beta} S_{\alpha} x$.

### Definition (Transition Matrix):
The matrix $_{\beta} S_{\alpha} x$ is called the transition matrix of the basis $\alpha$ to the basis $\beta$
It is of course also possible to change from $\beta \rightarrow \alpha$ coordinates.
This is done through $_{\alpha} S_{\beta} x$. 
$$_{\alpha} S_{\beta}  \circ_{\beta} S_{\alpha} = I$$
$$_{\alpha} S_{\beta}  = _{\beta} S_{\alpha}^{-1} $$


### Matrix of a Linear map:
We now discuss how to describe a linear map between two finite dimensional vector spaces using a matrix.
Let $V$ and $W$ be the aforementioned vector spaces over a field $\mathbb{K}$.
Consider a linear map $A : V \rightarrow W$ .
Let $\alpha$ be a basis for $V$ s.t. for $v \in V$, $\alpha (v) \in \mathbb{K}^n$
Let $\beta$ be a basis for $W$ s.t. for $w \in W$, $\beta (w) \in \mathbb{K}^m$
$$\beta A \alpha^{-1}: \mathbb K^{n} \rightarrow \mathbb K ^{m}$$

### Theorem (Effect of Change of basis):
Let V be a finitely dimensional space.
Let it have the bases $\alpha$ and $\beta$ 
Let $A$ be a linear map such that $A: V \rightarrow V$
$$A_{\beta} = ._{\beta}S_{\alpha} A_\alpha ._\alpha S_\beta$$
$$\beta A \beta^{-1} = (\beta \alpha^{-1}) (\alpha A \alpha ^{-1})(\alpha \beta^{-1})$$


## 1.4 Eigenvalues and Eigenvectors

### Definition  (Diagonal Form):
A square matrix has a *diagonal* form if $\forall{i,j | i\ne j }, a_{ij} = 0$ 
This builds the following theorem
### Theorem (Diagonalization of eigenvalues w.r.t. basis of eigenvectors):
Let $A :V \rightarrow V$ be a linear map with $\alpha = \{a_1, ..., a_n\}$ as a basis.
The matrix $A_{\alpha}$ must have the form 
$$A_\alpha = 
\begin{pmatrix}
\lambda_{1}& 0 & ... & 0 \\
0 &  \lambda_{2} & ... & 0 \\
... & ... & ... &0 \\
0 &  ... & 0 & \lambda_n 

\end{pmatrix}
\iff A a_i = \lambda_i a_i
$$
### Alternative Characterization:
Let $A: V \rightarrow V$ be a linear map, $A_\alpha$  is in diagonal form $\iff$ $\alpha$ is a basis of eigenvectors.

### Definition (Eigenvector and Eigenvalue):
Let $A : V \rightarrow V$ be a linear map.
A vector $v \ne 0$ is called eigenvector of $A$ with *eigenvalue* $\lambda$ if $A v = \lambda v$

### Definition (Eigenspace):
Consider $A : V \rightarrow V$.  For every $\lambda$ let $E_\lambda = N(A-\lambda I )$ 
We call $E_\lambda$ the eigenspace of $A$ for $\lambda$

### Theorem:
$\lambda$ is an eigenvalue $\iff \det{(A-\lambda I)} = 0$ and the associated $\alpha$-coordinates of the corresponding eigenvectors are the solutions different from the zero solution of the following system :
$$
\begin{pmatrix}
a_{11} & a_{12} & ... & a_{1n} \\
a_{21} & a_{22} & ... & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{n1} & a_{n2} & ... & a_{nn} \\
\end{pmatrix}
\begin{pmatrix}
v_1 \\
v_2 \\
\vdots\\
v_n \\
\end{pmatrix}
=
\begin{pmatrix}
0\\
0\\
\vdots\\
0
\end{pmatrix}

$$
### Definition (Characteristic Polynomial)

Let $A : V \rightarrow V$ be a linear map.
let $A_\alpha$ be the matrix A w.r.t. the basis $\alpha$.
Then, $\det (A - \lambda I) =0$ is called the **characteristic equation** of A. The LHS of the equation is called the *characteristic polynomial* of $A$
#### Note: Characteristic Equation is Independent From Basis.
##### Proof:
$$ \det(A_\beta - \lambda I) = \det( ._{\beta} S _{\alpha}  A_\alpha ._{\alpha}S_\beta - \lambda _{\beta} S _{\alpha}  I_\alpha ._{\alpha}S_\beta  )$$ $$
 = \det(_{\beta} S _{\alpha}(A_\alpha - \lambda I)_{\alpha}S_\beta) 
$$ $$
= \det(_{\beta} S _{\alpha})\det(A_\alpha - \lambda I)\det(_{\alpha}S_\beta)$$
$$\det(_{\beta} S _{\alpha}) = (\det(_{\alpha} S _{\beta}))^{-1} $$
$$\therefore \det(A_\beta - \lambda I) = \det(A_\alpha -\lambda )$$

### Definition (Matrix Trace):
The sum of the diagonal elements of a square matrix is called its trace
let $A \in \mathbb K ^{n \times n}$
$$tr(A) = \sum_{i=1}^{n}{a_{ii}}$$
### Theorem (Trace is Invariant Through Change of Basis):
Let $A$ be a linear map s.t. $A: V \rightarrow V, dim(V) <\infty$ 
for every $\alpha$, $tr(A_{\alpha})$ is the same

## 1.5 Invariant Subspaces

## 2.1 Orthogonal Maps

## 2.2 Symmetric Maps

## 3.1 LU-decomposition

## 3.2 Singular Value Decomposition

## 3.3 Jordan NF

## 4. Systems of Differential Equations


