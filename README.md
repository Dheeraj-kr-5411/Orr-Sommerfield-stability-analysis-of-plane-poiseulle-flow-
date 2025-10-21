Orr-Sommerfield-stability-analysis-of-plane-poiseulle-flow-

compute the neutral stability curve and find the critical reynolds number for laminar channel flow.
Neutral Stability Analysis of Plane Poiseuille Flow (Orr–Sommerfeld Equation)

 Objective:
This project investigates the *stability of Plane Poiseuille flow* (laminar channel flow) using the *Orr–Sommerfeld equation*.  
The goal is to determine the *neutral stability curve* and estimate the *critical Reynolds number (Reₚ)* for transition from laminar to unstable flow.
 Background Theory:

Plane Poiseuille Flow
Plane Poiseuille flow is the steady laminar motion of a viscous fluid between two parallel plates driven by a pressure gradient.  
The dimensionless velocity profile is:
U(y) = 1 - y^2,  y belongs [-1, 1]

Orr–Sommerfeld Equation

(U - c)(D^2 - \alpha^2)\phi - U''\phi = \frac{1}{i\alpha Re}(D^2 - \alpha^2)^2\phi
where:
(U(y)) -Mean velocity profile 
(c = c_r + i c_i) - Complex wave speed (real part = phase speed, imaginary part = growth rate) 
(alpha) - Streamwise wavenumber 
Re- Reynolds number 
D = d/dy
Boundary Conditions:
phi(pm1) = 0,phi'(pm1) = 0

#Numerical Method
Discretization: Chebyshev collocation method (spectral accuracy).
Eigenvalue formulation:
  
L phi = c M phi
where (L) and (M) are matrix operators derived from the Orr–Sommerfeld equation.
Solution: Solve generalized eigenvalue problem using scipy.linalg.eig.

#Algorithm Steps
1. Generate Chebyshev differentiation matrix \(D\) and collocation points \(y_i\).
2. Compute \(D^2, D^4\), and form matrices for \(L\) and \(M\).
3. Impose boundary conditions (\(\phi = \phi' = 0\)).
4. Loop over range of Reynolds numbers (Re) and wavenumbers (α).
5. For each pair \((α, Re)\), compute eigenvalues \(c\).
6. Extract the *maximum imaginary part* of \(c\) → determines growth/decay.
7. Plot growth rate vs Re* and *neutral stability curve (α–Re plane)

