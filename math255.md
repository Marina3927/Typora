### Course Description

1. Linear Systems, Matrices
2. Inverses and Transposes, Vector Spaces
3. Bases and Dimension
4. Linear Maps, Rank-Nullity Theorem
5. Matrices as Linear Maps
6. Inner product Spaces
7. Determinant
8. Functions of Several Variables, Vector-Valued Functions
9. Limits and Continuity, Partial Derivatives
10. Chain Rule, Directional Derivative, Gradient
11. Extrema in Functions of Several Variables

**Midterm Exam**

12. Double Integrals
13. Surface Area
14. Triple Integrals
15. Vector Fields
16. Line Integrals
17. The Fundamental Theorem for Line Integrals
18. Green’s Theorem
19. Curl and Divergence
20. Parametric Surfaces and Their Areas
21. Surface Integrals
22. Stokes’ Theorem
23. Divergence Theorem

**0515**

Matlab: $diag([d_1, \cdots d_n])$

**Superdiagonal matrix (upper shift)**: pop the first one out

$B_n =  \begin{pmatrix}
0&1& \dots & \dots&0\\
0&0&1 &\ddots & 0 \\ \vdots & \vdots &\dots&&1 \\ 0 & \dots &&&0\end{pmatrix}$

**Subdiagonal matrix**

$D_n$

**Cyclic matrix**: pull it out & add it back on the top

$C_n =  \begin{pmatrix}
0&1& \dots & \dots&0\\
0&0&1 &\ddots & 0 \\ \vdots & \vdots &\dots&&1 \\ 1 & \dots &&&0\end{pmatrix}$

$(A,B)\mapsto AB$

**0510**

vector $$ v=(v_1, \dots , v_n) \in \mathbb{R}^n$$

Inner product $$ \left\langle v,w \right\rangle = v^{\top}w$$

Length/norm/magnitude of vector $$ v=\sqrt{\left\langle v,v \right\rangle}=\sqrt{\sum^n_{i=1}{v_{i}^2}} $$

outer product

**RC 0518**

if $ tr(AA^T)=0 $, then $A=0$.

**0522**

$Ax=B,x=A/B$  will produce a solution anyway.

Elimination

Elementary row operations

Gaussian Elimination --> Row echelon form:

- The first non-zero element in each row, called the **leading entry**, is 1.
- Each leading entry is in a column to the right of the leading entry in the previous row.
- Rows with all zero elements, if any, are below rows having a non-zero element.

#### Gaussian Jorden Elimination

--> Reduced row echelon form (to calculate inverse):

- conditions for a row echelon form.
- The leading entry in each row is the only non-zero entry in its column.

$$
\begin{pmatrix}
1&2&1&0&2 &|&3\\
0&0&0&1&3 &|&2 \\
0&0&0&0&0 &|&*
\end{pmatrix}
\text{Argumented / extended matrix}
$$

Because $*\not=0$, no solutions.

#### Premultiplying 

= multiply from the right VS. post multiplying

$[A|I_n]->[I_n|B]$

**0523**

#### logistics difference equation

for population growth

$\frac{dP}{dt}=kP(1-\frac{P}{M})$

M: carrying capacity; P: population



