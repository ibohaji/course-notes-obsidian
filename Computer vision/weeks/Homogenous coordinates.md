---
week: "1"
---



---
Homogenous coordinates: Add an extra coordinate to the system, be it 2D or 3D. e.g. we use three real numbers to represent a 2D coordinate and four to represent a 3D coordinate. 

The added coordinate represents a scaling vector, represented by the vector $\begin{bmatrix} sx\\sy\\ s \end{bmatrix}$ , such that the coordinate point (3,2) can be represented by homogenous coordinate by a whole range of length three vectors, e.g. 


$$
\Huge
\begin{bmatrix} 3 \\ 2 \\ 1 \end{bmatrix} = \begin{bmatrix} 1\cdot 3 \\ 1\cdot2 \\ 1 \end{bmatrix}, \begin{bmatrix} 6 \\ 4 \\ 2 \end{bmatrix} = \begin{bmatrix} 2\cdot3 \\ 2\cdot 2 \\ 2 \end{bmatrix}, \begin{bmatrix} -6 \\ -4 \\ -2 \end{bmatrix} = \begin{bmatrix} -2\cdot 3 \\ -2\cdot2 \\ -2 \end{bmatrix}
$$

The same holds for 3D coordinates 

$$
\Huge
\begin{bmatrix} sx \\ sy \\ sz \\ s \end{bmatrix}
$$


## Lines 

Consider the following (x,y) points located on a line, expressed by the following equation, given a,b,c: 


$$ 
\Huge
0 = ax+by+c.
$$

multiplying both sides of this equation by a scalar s we achieve

$$
\Huge
0 = sax + sby+sc = \begin{bmatrix} a \\ b \\ c \end{bmatrix}^T \begin{bmatrix} sx \\ sy \\ s \end{bmatrix} = l^T q ,
$$
where l and q are vectors, and q is the possible 2D points on the line, represented in homogenous coordinates. A similar thing holds in 3D given by the equation $$\Huge 0 = ax+by+cz+d \implies   0=sax+sby+scz+sd

$$

