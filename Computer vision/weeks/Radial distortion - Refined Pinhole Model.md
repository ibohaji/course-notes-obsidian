---
week: "2"
related: "[[Pinhole Camera model]]"
---

---

This is an effect that typically increases with the field of view of the lens and with a lowering of the lens cost.  

We define distorted projection coordinate, $p^d$ = $[sx^d,sy^d,s]^T$ , and the corrected projection coordinate, $p^c = [sx^c,sy^c,s]^T$ , such that the transformation form 3D world coordinates $Q_i$ to 2d image coordinates $q_i$ is given by : 

$$ 
\Huge 

p_i^d = A_p [R \space \space t] \space Q_i 

\newline




$$
$$ \Huge 
\left[ \begin{array}{c} x_i^c \\ y_i^c \\ \end{array} \right] = \left[ \begin{array}{c} x_i^d \\ y_i^d \\ \end{array} \right] (1 + \Delta(r_i)) , 
$$
$$
\Huge q_i = A_q p_i^c 
$$
where $\Delta(r_i)$ is the radial distortion, which is a function of the radius 
$$ 
\Huge 
r_i = \sqrt{{(x_i^d)}^2 + {(y_i^d)}^2}
$$
Here, A has been split into $A_p$ and $A_q$ , where 

$$\Huge 

A_p = \begin{bmatrix}
f & 0 & 0 \\
0 & f & 0 \\
0 & 0 & 1 \\
\end{bmatrix}, \tag{1.29}



A_q = \begin{bmatrix}
1 & \beta & \Delta x \\
0 & \alpha & \Delta y \\
0 & 0 & 1 \\
\end{bmatrix}


$$
Much of the computations is done in standard inhomogeneous coordinates


$$ \Delta(R_i) = k_3r^2 + k_5r^4+k_7r^6+...,
$$


## Easier way 



$$\Huge p_d = K \Pi^-1(dist(\Pi([R|t]Q)]))$$

Where $\Pi$ Maps from homogenous to inhomogeneous coordinates


