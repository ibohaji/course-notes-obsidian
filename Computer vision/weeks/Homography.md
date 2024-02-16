---
week: "2"
related: "[[Homogenous coordinates]]"
---


---
### What is a homography?

A  geometric transformation matrix that maps from one plane to the other, when the point of view is the same. Mathematically it can be described as 3x3 (full rank) matrix, H that maps between 2D homogenous coordinates $q_1$ and $q_2$ as follows: 
$$
\Huge 
q_1 = Hq_2$$


The inverse of a homography is also a homography 

$$ \Huge

q_2 = H^{-1}q_1 $$


## Estimating a homography 

#### Linear algorithm 

Consider the following points

$$\Huge q_{1i} = \begin{bmatrix} x_{1i} \\ y_{1i} \\ 1 \end{bmatrix} , q_{2i} = \begin{bmatrix} x_{2i} \\ y_{2i} \\ 1 \end{bmatrix}$$

And let $b_i^T$  be 
$$  b_i^T =
\begin{bmatrix}
0 & -x_{2i} & x_{2i}y_{1i} & 0 & -y_{2i} & y_{2i}y_{1i} & 0 & -1 & y_{1i} \\
x_{2i} & 0 & -x_{2i}x_{1i} & y_{2i} & 0 & -y_{2i}x_{1i} & 1 & 0 & -x_{1i} \\
-x_{2i}y_{1i} & x_{2i}x_{1i} & 0 & -y_{2i}y_{1i} & y_{2i}x_{1i} & 0 & -y_{1i} & x_{1i} & 0
\end{bmatrix}
 $$



And consider $B$ 

where $$ \Large B = \begin{bmatrix} b_1^T \\  b_2^T \\ b_3^T\\.\\.\\. b_i^T \end{bmatrix} $$

E.g. $b_i^T$ stacked into a matrix.  where each $b_i^T$ correspond to a matching pair of coordinates.


$b_i^T$ can also be calculated as the kronker product between $q_{2i}^T \otimes [q_{1i}]$ such that 

$$ \Huge 
b_i^T = q_{2i}^T \otimes \begin{bmatrix} 0 & -1 & y_{1i} \\1 & 0 & -x_{1i} \\ -y_{1i} & x_{1i} & 0 \end{bmatrix}
$$


Then the homography can be estimated by solving the following equation 

$$ \Huge 

B \cdot vec(H) = 0 

$$

with the constraint that  $$\Large ||vec(H)||^2 = 1 $$
To ensure that $vec(H)\neq 0$


The system of equations can be solved using SVD eigen decomposition as following

