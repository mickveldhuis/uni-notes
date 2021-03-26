# Lecture 5: Galaxy Dynamics

## Two components of the gravitational potential

- Smooth potential: The average over a region containing many stars in a large volume.
- A deep potential well: Due to/depending on the local potential due to the stars.

## Stellar collisions

**Close encounters** are encounters that will change the orbits of stars significantly. Whereas **Weak encounters** are a rather small perturbation on the initial trajectory.

### Strong encounters

A strong encounter has happened is the change in potential energy is at least as large as the initial kinetic energy.

$$\frac{Gm^2}{r}\ge \frac{mV^2}{2}$$

which implies that

$$r\le r_s=\frac{2Gm}{v^2}$$

where $r_s$ is the strong encounter radius. The average time between collisions in a volume (in the galaxy) of a cylinder $\pi r_s^2vt$. Define $n\pi r_s^2vt_s=1$, such that a star will on average have 1 close encounter (given $n$ stars per unit volume). We find

$$t_s=4\cdot 10^{12}\ \text{yr}\,\bigg(\frac{v}{10\ \text{km/s}}\bigg)^{3}\bigg(\frac{m}{M_\odot}\bigg)^{-2}\bigg(\frac{n}{1\ \text{pc}^{-3}}\bigg)^{-1}$$

Note that strong encounters are only important in the dense cores of globular clusters.

## Distant weak encounters

The force of one star on another is so weak that the stars hardly deviate from their original paths. We consider the case of a star moving through a system of $N$ identical stars of mass $m$. We assume that the change in velocity is very small $\delta v/v<<1$, the perturbing star is stationary (this is also called the *impulse approximation*). We assume that a projectile star (mass $m$) is perturbed by a target star of mass $M>>m$. The impact parameter $b$ is the minimum distance between the two stars. The change in velocity in the smaller star is given by

$$\Delta v_\perp=\frac{2GM}{bv}$$

The faster the relative velocity, the smaller the perturbation. The (differential) number of weak encounters is equal to

$$dn_e=2\pi nvtb\,dt$$

Each of these encounters will produce a small change in velocity $dv$. The accumulation of weak encounters can be measured by the sum of $\langle\Delta v_\perp^2\rangle$.

$$\langle\Delta v_\perp^2\rangle=\frac{8\pi G^2M^2 nt}{v}\ln\bigg(\frac{b_\text{max}}{b_\text{min}}\bigg)$$

The relaxation time is the time necessary for that system to drastically change the system (i.e. lose its memory of the initial dynamics). Relaxation is the cumulative effect of individual encounters. In a relaxation time, the stellar velocity distribution randomizes.

$$t_\text{relax}=\frac{t_s}{2\ln\Lambda}$$

where $\Lambda=b_\text{max}/b_\text{min}$. This expression can be approximated by

$$t_\text{relax}=\frac{2\cdot 10^{9}\ \text{yr}}{\ln\Lambda}\,\bigg(\frac{v}{10\ \text{km/s}}\bigg)^{3}\bigg(\frac{m}{M_\odot}\bigg)^{-2}\bigg(\frac{n}{10^3\ \text{pc}^{-3}}\bigg)^{-1}$$

Often the relaxation time is in the order of the Hubble time. This implies that when calculating the motions of stars like the Sun, we can ignore pulls of individual stars, and consider them to move in the smooth potential of the entire Galaxy. 

## Motion under gravity

$$\frac{d}{dt}(m\mathbf{v})=-m\nabla\Phi(\mathbf{x})$$

where

$$\Phi(\mathbf{x})=-\sum_\alpha\frac{Gm_\alpha}{|\mathbf{x}-\mathbf{x}_\alpha|}\ \ \text{for}\ \ \mathbf{x}\not=\mathbf{x}_\alpha$$

### Poission's equation

The potential at a point $\mathbf{x}$ produced by a continuous mass distribution represented by density $\rho(\mathbf{x})$ is given by

$$\Phi(\mathbf{x})\equiv -G\int d\mathbf{x}^3\frac{\rho(\mathbf{x}')}{|\mathbf{x}'-\mathbf{x}|}$$

and if the potential is known instead of the density we have

$$\nabla^2\Phi=4\pi G \rho$$

Note that not all $\Phi$ are meaningful, only those where the mass is always positive.

### Theorem I

A body that is inside a spherical shell of matter experiences no net gravitational force from that shell.

### Theorem II

The gravitational force on a body that lies outside a closed spherical shell of matter is the same as it would be if all the shells' mass was concentrated in a point at is center. So the gravitational force within a spherical system that a
particle feels at a radius R is only due to the mass inside
that radius. 

As such, if a star moves on a circular orbit, its acceleration is given by

$$\frac{v_c^2}{r}=\frac{GM(r)}{r^2}$$

where 

$$v_c^2=\frac{GM}{r}$$

### The orbit of stars on a plane

- In a time-independent gravitational potential energy is conserved
- In a spherical potential angular momentum is conserved

### The orbits of stars in a disk galaxy

We define the position using $(R,\phi, z)$, for axisymmetric systems (i.e. systems independent of $\phi$) we write $\Phi=\Phi(R,z)$. 

## Equations of motion

$$\frac{d^2\mathbf{r}}{dt^2}=-\nabla\Phi$$

where $\mathbf{r}=R\hat{R}+z\hat{z}$.

$$\frac{d^2R}{dt^2}=-\frac{\partial\Phi}{\partial R}$$
$$\frac{d^2z}{dt^2}=-\frac{\partial\Phi}{\partial z}$$

Note that $L_z=R^2\tfrac{d\phi}{dt}=\text{constant}$. We define the effective potential

$$\Phi_\text{eff}=\Phi(R, z) + \frac{L_z^2}{2R^2}$$

The effective potential behaves like a potential energy for the star's motion in $R$ and $z$. Note that the effective potential is minimum when the radius (let's call it $R=R_g$) of the orbit is that of a circular orbit and when $z=0$.

## Epicycles

The equation of motion for stars on nearly circular orbits in the symmetry plane are given by 

$$x=x_0\cos(\kappa t+\psi)$$

and

$$z=z_0\cos(\nu t+\theta)$$

where $\nu$ is the vertical frequency $\nu^2=\partial^2\Phi_\text{eff}/\partial z^2|_{(R_g,0)}$, $\kappa$ the epicycle frequency $\kappa^2=\partial^2\Phi_\text{eff}/\partial R^2|_{(R_g,0)}$ and $x=R-R_g$.
