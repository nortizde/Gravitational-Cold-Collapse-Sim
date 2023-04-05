# Gravitational Cold Collapse Simulation - Computational Physics 20/21 Final Project
This repo contains my final project for the Introduction to Computational Physics class with Professor Hy Trac for the academic year 20/21 at Carnegie Mellon University. 

## 1) N-body Simulations
N-body simulations are used to solve the dynamics of a system of particles, commonly known as the many-body problem. Particles that interact with one another through a force can be solved analytically for a low number of bodies. 
A simple binary star system can be solved analytically with Newtons equations and is a common exercise for high school physics students. Upon adding another body, say a planet, the exercise becomes quite more difficult. If we 
wanted to study a system of millions of bodies, an anlytical approach is simply not feasible. This is where N-body algorithms have helped progress out understanding of complex many-body systems. 

## 1.1) Particle Mesh (PM) Method
In this project, I use a particle mesh (PM) method. A typical approach woould be to use a particle-particle (PP) method, where  the net force on a given particle is calculated by directly summing the pairwise force from all of its neighbors. 
In the PM method, particles are mapped onto a "mesh" and Poisson's equation for gravity is solved using Fast Fourier Transforms (FFT). The benefit of the PM method is that it is O(N*logN), where as the PP method is O(N^2), making a faster, but less accurate method.

## 2) Approach
Considering a system of N particles with fixed mass m, for each particle we evolve its position x and velocity v using Newton's equations:

  $\frac{\mathrm{d} \mathbf{x}}{\mathrm{d} t} = \mathbf{v}\$
  
  $\frac{\mathrm{d} \mathbf{v}}{\mathrm{d} t} = \mathbf{a}\$
  
  Newton's 2nd law gives us a relation between the force per unit mass and the gravitational potential:
  
  $\mathbf{f} = - \nabla \Phi$
  
  Using Poisson's equation we can then relate the gravitational potential $\Phi (\mathbf{x})$ to the density field $\rho (\mathbf{x})$:
  
  $\nabla^{2} \Phi (\mathbf{x}) = 4 \pi G \rho (\mathbf{x})$
  
  whose general solution is a convolution. The efficiency of the PM method is from solving Poisson's equation in Fourier space given by:
  
  $\Phi (\mathbf{k}) = \rho (\mathbf{k}) w(k)$, 
  
  where the transformed kernel $w(k)$ is:
  
  $w(k) = - \frac{4 \pi G}{k^2}$
  
  ## 2.1) Density field
  
  ## 2.2) Gravity
  
  ## 3) Cold gravitational collapse and initial conditions
  
  ## 4) Results
