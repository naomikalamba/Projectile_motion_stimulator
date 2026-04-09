#Projectile Motion Simulator (MATLAB GUI)

##  Overview
This project is a MATLAB-based application that simulates two-dimensional projectile motion. It allows users to input physical parameters such as initial velocity, launch angle, and initial height, and then visualizes the motion through graphs and computed results.

The application is built using MATLAB App Designer and demonstrates both numerical and symbolic computation.

---

##  Features
- User-friendly GUI for input parameters
- Simulation of projectile motion without air resistance
- Calculation of:
  - Time of flight
  - Maximum height
  - Horizontal range
- Graphical visualization:
  - Trajectory (Distance vs Height)
  - Velocity vs Time
  - 3D visualization of motion
- Symbolic computation of velocity using differentiation
- Polynomial curve fitting of trajectory
- Export of simulation data to Excel

---

##  Equations Used

### Horizontal Motion:
x(t) = v₀ cos(θ) · t

### Vertical Motion:
y(t) = h₀ + v₀ sin(θ) · t − (1/2)gt²

### Velocity:
v = √(vₓ² + vᵧ²)

### Maximum Height:
H = h₀ + (v₀² sin²(θ)) / (2g)

### Range:
- If h₀ = 0:
  R = (v₀² sin(2θ)) / g
- Else:
  R = final x position

---

## Project Structure

- `ProjectileTrajectory.m`  
  Calculates x, y, velocity, and time values

- `HeightAndRange.m`  
  Computes maximum height and horizontal range

- `plotProjectileGraphs.m`  
  Handles all plotting (2D and 3D graphs)

- `App (.mlapp)`  
  GUI interface built using MATLAB App Designer

---

##  GUI Functionality

The GUI allows users to:
1. Enter initial conditions (velocity, angle, height)
2. Run the simulation using a button
3. View results directly on the interface
4. Visualize graphs in real-time

---

##  Symbolic Computation

The project uses MATLAB symbolic math to derive velocity:

```matlab
syms T
y_sym = h₀ + v₀ * sind(angle) * T - 0.5 * g * T^2;
vy_sym = diff(y_sym);
