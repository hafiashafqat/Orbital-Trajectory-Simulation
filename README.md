# Orbital-Trajectory-Simulation
Simulated a two-body orbital motion system to evaluate accuracy differences between 1st-order Euler's method and 4th/5th-order adaptive RK45 numerical integration.

**Dataset**: Synthetically generated state vectors using Newton's Law of Universal Gravitation ($GM = 1000.0$)

**Status**: Complete

---

## Research Question

**How does adaptive RK45 integration resolve energy conservation errors and trajectory drift found in Euler's method during curved orbital motion?**

This project compares two fundamental numerical integration approaches for solving the gravitational two-body problem, analyzing their stability, accuracy, and computational efficiency.

---

## Key Findings

### 1. Euler's Method Limitations 
- Fixed step-size Euler's method fails on curved orbital paths
- Causes non-physical energy gains and outward spiral trajectories
- Accumulates truncation errors over multiple orbital periods
- Results in orbit decay rather than stable motion

### 2. RK45 Superior Precision 
- Combining 4 slope evaluations ($k_1, k_2, k_3, k_4$) with weighted average:
  $$y_{n+1} = y_n + \frac{dt}{6}(k_1 + 2k_2 + 2k_3 + k_4)$$
- Maintains precise, stable elliptical orbits
- Preserves energy conservation across simulation
- 4th/5th-order accuracy vs 1st-order Euler

### 3. Adaptive Efficiency 
- RK45 automatically reduces time steps ($dt$) near perigee (high gravity gradients)
- Increases time steps at apogee for optimal computational speed
- Balances accuracy and efficiency without manual tuning
- Adaptive step control provides optimal solver performance

### 4. Visualization Quality 
- Dense sampling ($t_{eval} = 1000$ points) provides smooth plotting
- Preserves underlying physics solver efficiency
- Professional trajectory plots show orbit stability
- Phase-space diagrams confirm energy conservation

---

## Technologies Used

| Technology | Purpose |
|-----------|---------|
| **Python 3.x** | Scientific computing language |
| **NumPy** | Vector mathematics & state-space operations |
| **SciPy** (`solve_ivp`) | RK45 numerical integration |
| **Matplotlib** | 2D trajectory & phase-space visualization |
| **Physics** | Newton's Laws & orbital mechanics |

---

## Project Files

- `orbit_simulation.ipynb` - Complete Python notebook with physics derivations & plots
- `README.md` - This documentation file

---

## Simulation Parameters

| Parameter | Value | Description |
|-----------|-------|-------------|
| **Initial Position** | $[x, y] = [10.0, 0.0]$ | Starting point in orbital plane |
| **Initial Velocity** | $[v_x, v_y] = [0.0, 5.0]$ | Tangential velocity for circular orbit |
| **Gravitational Constant** | $GM = 1000.0$ | Central body strength |
| **Time Span** | $t = 0$ to $t = 10$ seconds | Total simulation duration |
| **Plotting Resolution** | $n_{eval} = 1000$ points | Dense sampling for smooth visualization |

---

## How to View

**Click `orbit_simulation.ipynb` above** to see:
- Complete mathematical derivations
- Python implementation with comments
- Step-by-step comparison plots
- Energy conservation analysis
- Professional trajectory visualizations

All visualizations render directly in GitHub (no downloads needed)!

---

## Skills Demonstrated

**Numerical Integration** - Euler vs RK45 methods  
**Orbital Mechanics** - Gravitational physics & trajectories  
**Python Scientific Computing** - NumPy, SciPy, Matplotlib  
**Data Visualization** - Professional scientific plots  
**Mathematical Modeling** - Differential equations & state-space representation  
**Physics Understanding** - Energy conservation & orbital dynamics  
**Algorithm Comparison** - Performance analysis & trade-offs  

---

## Mathematical Foundation

### Two-Body Gravitational Problem

The acceleration of a satellite due to central body gravity:

$$\vec{a} = -\frac{GM}{r^2} \hat{r} = -\frac{GM}{r^3} \vec{r}$$

Where:
- $GM$ = gravitational parameter
- $r = \sqrt{x^2 + y^2}$ = distance from center
- $\vec{r} = [x, y]$ = position vector

### State Vector Formulation

Convert to first-order ODE system:

$$\frac{d}{dt}\begin{bmatrix} x \\ y \\ v_x \\ v_y \end{bmatrix} = \begin{bmatrix} v_x \\ v_y \\ -\frac{GM \cdot x}{(x^2+y^2)^{3/2}} \\ -\frac{GM \cdot y}{(x^2+y^2)^{3/2}} \end{bmatrix}$$

This is the form solved by both Euler and RK45 methods.

---

## Physics Insights

### Why RK45 Wins for Orbital Mechanics

1. **Error Order**: RK45 is O(dt^5) vs Euler's O(dt)
   - 4-5 orders of magnitude more accurate!

2. **Stability Region**: RK45's stability domain covers crucial orbital regimes
   - Euler struggles with the rapid changes at perigee

3. **Energy Conservation**: Implicit handling maintains physical validity
   - Euler accumulates non-conservative energy errors

4. **Adaptive Control**: Automatically respects local dynamics
   - No manual step-size tuning needed

---

## Learning Outcomes

- Why higher-order methods matter in orbital mechanics
- How Runge-Kutta methods work mathematically
- Adaptive step control and error estimation
- Real-world differences between methods
- How to implement scientific solvers in Python

---

## Applications

This comparison is relevant to:
**Satellite Tracking** - Accurate long-term orbit prediction  
**Astrophysics** - N-body simulations  
**Mission Planning** - Trajectory optimization  
**Research Computing** - Numerical methods validation  
**Scientific Software** - Solver selection criteria  

---

## Related Concepts

- **Runge-Kutta Methods** - Family of higher-order integrators
- **Adaptive Mesh Refinement** - Dynamic step-size control
- **Energy Conservation** - Symplectic integrators & Hamiltonian systems
- **Orbital Elements** - Classical orbital mechanics
- **Stability Analysis** - Method comparison & testing

---

## Code Highlights

Notebook includes:
1. **Physics Setup** - Defining the gravitational system
2. **Euler Implementation** - Basic numerical integration
3. **RK45 Implementation** - Using SciPy's `solve_ivp`
4. **Comparison Plots** - Side-by-side trajectory visualization
5. **Error Analysis** - Energy conservation metrics
6. **Phase Space** - Velocity vs position plots

---

This project shows:
- **Deep Understanding** of numerical methods (not just using libraries blindly)
- **Physics Knowledge** (orbital mechanics, energy conservation)
- **Scientific Rigor** (comparing approaches, analyzing errors)
- **Practical Skills** (Python scientific computing)
- **Communication** (clear visualization & documentation)

**Employers in aerospace, research, or scientific computing will be impressed!** 🚀

---

## Project Summary

| Aspect | Details |
|--------|---------|
| **Domain** | Orbital Mechanics & Numerical Methods |
| **Methods** | Euler's Method vs RK45 |
| **Language** | Python |
| **Complexity** | Advanced (physics + numerical analysis) |
| **Status** | Complete & Professional |
| **Visualization** | Trajectory plots & phase-space analysis |

---
**Completed**: August 2026 

---
