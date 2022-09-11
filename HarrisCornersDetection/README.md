### This project we implement Harris Corners Detectors

#### steps 

1. The first step is to convert it into a grayscale image, which will enhance the processing speed.

2. Compute image gradients $I_{x}(x,y)$ and $I_{y}(x,y)$ .

3. Compute products of the derivatives  $I_{x^2}(x,y) = I_{x}(x,y)\times I_{x}(x,y)$ , $I_{xy}(x,y) = I_{x}(x,y)\times I_{y}(x,y)$ , $I_{y^2}(x,y) = I_{y}(x,y)\times I_{y}(x,y)$.

4. Filtering the product with the Gaussian filter. 
5. Define at each pixel ${\displaystyle M(x,y) ={\underset {(x,y)\in W}{\sum }}{\begin{bmatrix}I_{x}^{2}&I_{x}I_{y}\\I_{x}I_{y}&I_{y}^{2}\end{bmatrix}}={\begin{bmatrix}{\underset {(x,y)\in W}{\sum }}I_{x}^{2}&{\underset {(x,y)\in W}{\sum }}I_{x}I_{y}\\{\underset {(x,y)\in W}{\sum }}I_{x}I_{y}&{\underset {(x,y)\in W}{\sum }}I_{y}^{2}\end{bmatrix}}}$
6. Compute the response of the detector at each pixel. $$R(i,j)=\mathtt{det}(M)-K\cdot[\mathtt{trace}(M)]^2$$ $$K = 0.06$$ 
7. Threshold on value of R and perform non-maxima suppression.
