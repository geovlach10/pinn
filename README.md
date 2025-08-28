# pinn
- **Task 1** : solve the PDE u_xx(x) + k * u(x) * c(x), x ε [0,1], c(x) = sin(-x^2), k = ct (k = 1, for simplicity)  
- **Task 2** : solve the PDE u_xx(x, t) + k * u(x, t) * c(x), x, t ε [0,1] and c(x) = sin(-x^2)

  
**next steps :**
- create a pyhton function which solves the PDE with Newton-Raphson.
- evaluate the model using L2-norm.
- add weights to each term of the loss_func, as described in the following paper < link >.
- change the colocation point generator function in < follder name > goal : add more collocation points where the loss is bigger???
