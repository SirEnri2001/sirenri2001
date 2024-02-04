# Fluid Simulation For Computer Graphics: A Tutorial in Grid Based and Particle Based Methods

*Colin Braley & Adrian Sandu - Virginia Tech*

# Main contribution

This paper provide a introductory tutorial for people learning fluid simulation at a undergraduate level. It gives out a Navier-Stokes equation and 2 major methods, grid based and particle based, for calculating the equation.

# Outline of the major topics

Part 1 Navier-Stokes Equation

Part 2 Grid Based Simulation

1. Data Structures that defines each grid (MAC cell)
   
   Marker-and-Cell Grid technique stores different quantities (pressure & velocity of the fluid) in different locations.The advantage of MAC is it has $O(\Delta x^2)$ accuracy whilst consider the actual velocity value $u$ at the center of each cell. 

2. Timestep selection (CFL condition)
   
   CFL condition says, by each $\Delta t$ iteration, any quantity will only move $\Delta h$ distance (the length of each cell). However, in real implementations, we don't need to satisfy strictly of this condition since it'll be to slow for calculation. We usually use alternated form of CFL condition to speed up the simulation process. 

3. Advection (RK2 or Forward Euler)
   
   We use the integrator to update each quantity according its neighbors.

4. Pressure Solve (Solving linear equations that defines on Laplacian matrix of the cells)
   
   We need to satisfy both the incompressibility condition (the divergence of each cell equals 0) and boundary conditions (the surface normal velocity of the fluid equals the surface of solid it contacted).
   
   Therefore, we can defina a Laplacian matrix that track the connectivity of cells. We can also get the divergence of each cell by calculating the fluid velocity of its neighbors. By solving the linear equation, we get the pressure at every cell. 

# One thing interesting about the paper

This paper introduce a different set of methods of CFL to speed up the simulation. By using optimized method of CFL, the advection process will be faster and more robust.

# One thing I don't like about the paper

The author did not explain well the differences of Navier-Stokes equation in Euler and Lagrangian representation. For example, the left-hand side of the equation $\frac{\partial \vec{u}}{\partial t} + \vec{u}$ is a Lagrangian representation, while we have $\frac{D \vec{u}}{D t}$ in Euler representation. There are different math background of the two.

# Questions for the Authors (Two)

1. How does hybrid approach (mixed point based and grid based) works?

2. How to preserve the volumn (mass) when we adopt surface construction method in point based? 
