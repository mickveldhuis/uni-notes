# Lecture 11: Gravitational Lensing

Background reading:

- [Meneghetti Notes](http://www.ita.uni-heidelberg.de/~jmerten/misc/meneghetti_lensing.pdf)
- [Notes on Gravitational Lensing in astronomy](https://arxiv.org/abs/astro-ph/9812021)
- [Differences between types of gravitational lensing](http://w.astro.berkeley.edu/~jcohn/lens.html)

## History

Using general relativity we could in 1919 calculate the (angle of) deflection of the light by a star we have

$$\alpha=\frac{4GM}{c^2}\frac{1}{\xi}$$

## Two regimes of gravitational lensing

Note: magnifications preserves surface brightness:

$$\mu=\frac{A_\text{obs}}{A_\text{int}}$$

### Strong regime

You have the creation of multiple images, gravitational arcs are visible, and you have high magnifications (10-100 times the intrinsic luminosity). Due to very *good* alignment.

### Weak regime

Small distortion of the images of (the) galaxies.

## Lens equation

The lens equation is given by:

$$\beta D_\text{OS}=\alpha(\theta) D_\text{LS}=\theta D_\text{OS}$$

where $\beta$ is he real position on the source plane, $\alpha$  and $\theta$ are related to the observed position on the lens plane. Note $\alpha$, the deflection angle, depends on the *lens* mass distribution and on the observed position. We can write

$$\beta=\theta-\alpha(\theta)\frac{D_\text{LS}}{D_\text{OS}}$$

### The deflection angle

For a point mass, assuming a weak gravitational field, the deflection angle of a  point mass is given by:

$$\vec{\alpha}=\frac{4GM}{c^2}\frac{\vec{\xi}}{\xi^2}$$

For an extended lens we have

$$\vec{\alpha(\vec{\xi})}=\frac{4G}{c^2}\int d^2\xi '\int dz \rho(\vec{\xi '}, z)\frac{\vec{\xi}-\vec{\xi '}}{|\vec{\xi}-\vec{\xi '}|^2}$$

define the projected mass density profile (considering no perturbers along the LOS)

$$\Sigma(\xi ')=\int dz \rho(\vec{\xi '}, z)$$

Such that

$$\vec{\alpha}(\vec{\theta})=\vec{\alpha}(D_{OL}\vec{\theta})\frac{D_{LS}}{D_{OS}}$$

### Magnification

In gravitational lensing the surface brightness is conserved. The magnification is given by the ratio between the observed and intrinsic fluxes,

$$\mu=\frac{d\Omega_\text{obs}}{d\Omega_\text{int}}$$

We decompose the magnification in an isotropic and traceless part, the isotropic part just magnifies the object whereas the traceless part (which is defined by the shear $\gamma$) distorts the image. We find

$$\mu=\frac{1}{(1-\kappa)^2-\gamma^2}$$

note that $\kappa$ is the dimensionless projected mass distribution, named convergence. It is defined as the projected mass density profile at $D_{OL}\vec{\theta}$ divided by the critical density. We have a tangential and radial magnification

$$\mu_t = \frac{1}{1-\kappa-\gamma}$$

and 

$$\mu_r = \frac{1}{1-\kappa+\gamma}$$

Every time you cross a caustic from *outside* an extra two degrees of multiplicity will be visible. So inside the first but outside the second caustic we have three (multiple) images.

## Time delay

The lens equation can be rewritten as

$$\nabla(\delta t)=0, \ \ \delta t = t - t_0$$

The time delay is the difference between the actual arrival time and the arrival time with no deflector. It defines a plane and the multiple images are formed in the stationary points. It can also be used to probe the Hubble constant

$$t_1-t_2\propto F(\psi)/H_0$$

where $F$ depends on the lens potential, which is a projection of the 3D gravitational potential.

## Point mass model #1
This is an antisymmetric case, all vectors have the same direction, so we can reduce to one dimension. The magnification is given by:

$$\mu=\bigg[1-\bigg(\frac{\theta_E}{\theta}\bigg)^4\bigg]^{-1}$$

where

$$\theta_E^2\equiv\frac{4GM}{c^2}\frac{D_\text{LS}}{D_\text{OL}D_\text{OS}}$$

is called the Einstein radius. The Einstein radius defines the Einstein ring, which is a special case of gravitational lensing, caused by the exact alignment of the source, lens, and observer. This results in symmetry around the lens, causing a ring-like structure.

## Axisymmetric mass distribution model #2

The deflection angle depends on the mass enclosed inside the image position. This way we can compute the mass of for instance a galaxy within an Einstein ring of a certain size $\theta_E$:

$$M(<\theta_E)=1.1\cdot10^{14}M_\odot\bigg(\frac{}{}\bigg)$$

## Lens model #3

The singular isothermal sphere, assuming that the matter behaves as an ideal gas and thermal and hydrostatic equilibrium.

$$\rho(r)=\frac{\sigma_v}{2\pi G r^2}$$

where $\sigma_v$ is the central velocity dispersion.

## Microlensing

Point mass lenses are good approximations for stars. Note microlensing implies very small deflection angles $\alpha<0.01\ \text{arcsec}$ that we cannot resolve. So we mainly see a boost in luminosity and not really any change in the observed image.

## Lenses with elliptical symmetry

We go from radial coordinates to elliptical coordinates.

$$\kappa(x)\rightarrow\kappa(x_e)$$

where

$$x_e=\sqrt{\frac{x^2}{1-e}+y^2(1-e)},\ \ e=1-\frac{b}{a}$$

If we have multiple components, i.e. a cluster of galaxies:

$$\kappa(\vec{x})=\sum\kappa_i(\vec{x})$$

Where each galaxy member is described as a singular isothermal sphere and the dark matter extended component by an elliptical mass distribution NFW or a cored IS. Lenses with elliptical symmetry can produce most of the observed configurations of multiple images. But still very simplistic for real systems.

## Weak lensing regime

At larger distances from the core, lensing weakly distorts the background galaxies. You can measure the mass of galaxy clusters at large radii by stacking the signal of several single galaxies to obtain an average profile. One can for instance measure the shear, which had some orientation w.r.t. to the center of the cluster.

## Real world lenses

Systems with Einstein rings are are, we use multiple images or distortion to measure the mass distribution of galaxies. The mass distribution is never axisymmetric, so we at least have to consider elliptical symmetry and substructures. So we study the mass distribution of clusters and galaxies by using multiple images.
