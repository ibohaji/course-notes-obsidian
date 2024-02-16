---
aliases: 
tags:
  - scale-space-theory
  - blob-detection
  - image-analysis
  - computer-vision
  - multi-class-representation
  - Lindberg
---
---

# Scale-space 

Scale invariant detection, detection of images independently of the scale, i.e. using criteria that are independent from the scale. 

- The computation is done by representing image features at all scales at once.
- Gaussian scale-space.
	- smoothing by Gaussian filter.


#### Gaussian scale-space L 
$$
\Huge
L(x, y; t) = \Sigma_\gamma^\gamma \Sigma_\delta^\delta I(x-\gamma,y-\delta) g(\delta,\gamma;t)
$$

where g: $R^2 \times R_+ \to R$  is the 2d Gaussian kernel. 

$$
\large
g(x,y;t) = \frac{1}{2\pi t} \exp\left(-\frac{x^2+y^2}{2t}\right)
$$

























--- 
