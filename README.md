# 2D Hard-Sphere Molecular Dynamics

This simulation models $N$ particles moving in a 2D box, undergoing elastic collisions with each other and the walls. It approximates the **Boltzmann collision term** deterministically.

## 1. Boltzmann Equation

The time evolution of the single-particle distribution function $f(\mathbf{r},\mathbf{v},t)$:

$$
\frac{\partial f}{\partial t} + \mathbf{v} \cdot \nabla_\mathbf{r} f + \mathbf{F} \cdot \nabla_\mathbf{v} f = \left(\frac{\partial f}{\partial t}\right)_{\rm coll}.
$$

This is a **deterministic, discrete-particle approximation** of the Boltzmann collision term. Over time, the particle velocity distribution evolves similarly to the predictions of the Boltzmann equation.

## 2. Variable phase transition

By varying the temperature, a fluid consisting of hard spheres exhibits a phase change.

The standard potential for pairs or particles is the Lennard-Jones potential (12-6 potential):

$$V_{\mathrm{LJ}}(r)
=
4 \, \varepsilon
\left[
\left(\frac{\sigma}{r}\right)^{12}
-
\left(\frac{\sigma}{r}\right)^{6}
\right].$$

In this project we used a simpler potential of the form:

$$V(r)=
\begin{cases}
\infty, & r < 2 r_0 \\
-\varepsilon \left( 7 r - \frac{r^2}{4 r_0} \right) + C, & 2 r_0 \le r < 4 r_0 \\
0, & r \ge 4 r_0
\end{cases}.$$
