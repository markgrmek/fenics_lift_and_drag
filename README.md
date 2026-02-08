# Lift and Drag Calculation of Fluid Flow Around a Static Cylinder

## Running the code
These project file is **designed to be run in Google Colab**, which ensures compatibility and avoids dependency issues.

## Project information
The code solves the incompressible Navier Stokes Equation:

$\dot{u} + \nabla u \cdot u - \nu \Delta u + \nabla p = f, \qquad \nabla \cdot u = 0$

with constant velocity boundary condtition on the left, top and bottom domain boundary, zero pressure boundary condition on the right domain boundary and zero velocity boundary condition on the cylinder.

![Boundary conditions sketch](BCs.png)

The solution is obtained via the Chorins' method, which is preformed in 3 steps:

1. Step - ignore the pressure and momentum equation and calculate the tentative velocity $u^\star$:

  $\langle\left(u_h^\star - u_h^{n-1}\right)/\Delta t_n, v \rangle + \langle\nabla u_h^{n-1} \cdot u_h^{n-1},v \rangle + \langle \nu \nabla u_h^n, \nabla v\rangle = \langle f, v \rangle$
  
2.  Step - pressure correction step:

  $\langle \nabla p^n, \nabla q \rangle = - \langle \nabla \cdot u_h^\star, q \rangle / \Delta t_n$

3.  Step - velocity correction step:

   $\langle u_h^n,c \rangle = \langle u_h^\star,v \rangle - \Delta t_n \langle \Delta p^n, v \rangle$
