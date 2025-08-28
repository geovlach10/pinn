# pinn
- **Task 1** : solve the PDE u_xx(x) + k * u(x) * c(x), x ε [0,1], c(x) = sin(-x^2), k = ct (k = 1, for simplicity) see the following [document](pde_one_dimention.docx) for more info 
- **Task 2** : solve the PDE u_xx(x, t) + k * u(x, t) * c(x), x, t ε [0,1] and c(x) = sin(-x^2)

  
**next steps :**
- create a pyhton function which solves the PDE with Newton-Raphson.
- use the Newton-Raphson solution to evaluate the model by using the L2-norm.
- I will use [this code](https://github.com/mroberto166/CAMLab-DLSCTutorials/blob/main/Pinns.ipynb) as a guide and making the appropriate changes.
    1. Add weights to each term of the loss_func, as described in the following paper [Dynamic Weight Strategy of Physics-Informed Neural Networks for the 2D Navier–Stokes Equations](https://www.mdpi.com/1099-4300/24/9/1254).
    2. Make the appropriate changes in the collocation point generator function as described in the following paper : [A comprehensive study of non-adaptive and residual-based adaptive sampling for physics-informed neural networks](https://www.sciencedirect.com/science/article/abs/pii/S0045782522006260?via%3Dihub)  
**goal** : add more collocation points where the residual is bigger.

**then:**
- Add more terms in the loss function
