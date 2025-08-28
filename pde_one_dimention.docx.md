**Task 1**

First let’s approximate the following one-dimensional pde :

$$u\_{xx}= κ⋅u⋅c\left(x\right) , x\in \left[0 , 1\right]$$

Where:

$u :$ the concentration of some type of cell

$κ :$ some constant

$c\left(x\right) :$ the concentration of some nutrient

* We have assumed zero dependence of u w.r.t time so we have eliminated the partial derivative w.r.t time $\left(u\_{t}=0\right)$
* Assume $k=1 $for simplicity
* Also assume that $c\left(x\right)=\sin(\left(-x^{2}\right))$

Consider zero-Newman boundary condition on the left boundary $\left(x=0\right)$:

$$\frac{du}{dx}\_{x=0}=0$$

And Dirichlet BC at the right boundary $\left(x=1\right)$ :

$$u\left(x=1\right)=1$$

We want to obtain an approximate solutioin of the pde $u : \left[0, 1\right] ⟼ R $with physics informed neural networks (PINNs).

To do so, we approximate the underlying solution with a feedforward neural network with tunable parameters $θ$ :

$$u\_{θ}\left(x\right)≈u\left(x\right)$$

We define the residuals:

1.Interior residual (Pde):

$$r\_{int,θ}\left(x\right)≔u\_{xx,θ}\left(x\right)-u\_{θ}\left(x\right)⋅\sin(\left(-x^{2}\right))$$

2.Spatial boundary residuals:

$$r\_{sb,θ}\left(x=0\right)≔u\_{x,θ}-u\_{b}\left(0\right)$$

$$r\_{sb,θ}\left(x=1\right)≔u\_{θ}-u\_{b}\left(1\right)$$

We define the following training sets:

$$S\_{int}=\left\{x\_{n}\right\}, n\in \left(1, N\_{int}\right)$$

Compute the loss functions

$$L\_{int}\left(θ\right)=\frac{1}{N\_{int}}\sum\_{i=1}^{N\_{int}}r\_{int,θ}^{2}\left(x\_{n}\right), L\_{sb}\left(θ\right)=r\_{sb,x=0}^{2}+r\_{sb,x=1}^{2}$$

$$ $$

Solve the following minimization problem:

$$θ^{\*}=argmin\_{θ}\left(L\_{int}\left(θ\right)+L\_{sb}\left(θ\right)\right)$$