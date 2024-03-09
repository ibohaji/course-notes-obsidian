![[Pasted image 20240209102434.png]]

# The Pinhole Camera Model Explained

## What is the Pinhole Camera Model?
- **Used in**: Computer vision and photogrammetry.
- **Goal**: Optics of 'normal' lenses mimic this model.
- **Key Idea**: Models how light passes through a tiny hole to form an image.

## How Does It Work?
- **Camera Obscura**: Basis of the pinhole camera model.
- **Setup**: Image sensor inside a box with a small pinhole.
- **Projection**: Light through the pinhole illuminates the sensor.

## Mathematical Derivation
- **Coordinate System**: Image plane aligns with xy-plane; z-axis is the viewing direction.
- **2D Representation**: 
  $$x = \frac{X}{Z}$$
  - Simplification: Image plane is unit distance from origin; camera coordinates align with global system.
- **3D Extension**: 
  $$x = \frac{X}{Z}, \quad y = \frac{Y}{Z}$$
  - Applies due to orthogonal x and y axes.

## Using[[ Homogeneous Coordinates]]
- **For 2D point** \(q\) **and 3D point** \(Q\):
  $$q_i = \frac{Q_i}{Z_i}$$
- **Transformation**:
  $$\begin{bmatrix} s_ix_i \\ s_iy_i \\ s_i \end{bmatrix} = \begin{bmatrix} X_i \\ Y_i \\ Z_i \end{bmatrix} \Rightarrow x_i = \frac{X_i}{Z_i}, \quad y_i = \frac{Y_i}{Z_i}$$
- **Incorporating Rotation and Translation**:
  $$q_i = \left[ R \quad t \right] Q_i$$

## Final Pinhole Camera Model

- **projects a 3D world point Qi onto a 2D image point (both in homogeneous representation), via:
$$
\Huge

q_i = PQ_i \space , \space P = A\space [\space R \space t\space] \space , \space A \space = \space  \left[ \begin{array}{ccc} f & f\beta & \Delta x \\ 0 & \alpha f & \Delta y \\ 0 & 0 & 1 \\ \end{array} \right] 

$$
  $$\Huge 
  q_i = A \left[ R \quad t \right] Q_i = P Q_i, \quad P = A \left[ R \quad t \right]$$

Where P is a 3 by 4 matrix.


## Camera center 

$$ \Huge 
\tilde{Q}_c = -R^Tt
$$

Where $\tilde{Q_c}$ is the inhomogeneous coordinate corresponding to $Q_c$ 




## Focal length 


The focal length, the distance from the focal point to the image plane. 

$$ 
\frac{x}{f} = \frac{X}{Z} \implies x = \frac{fX}{Z}
$$



## Properties of the Pinhole Camera Model 


## Summary
- The pinhole camera model simplifies the complex process of image formation into understandable mathematical terms, providing a foundation for further exploration in computer vision and photogrammetry.
