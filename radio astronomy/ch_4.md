# 4. Dish Telescopes & Horn Antennas

## Basics

We use parabolic reflectors at short wavelengths, for which it must have a collecting area $>\lambda^2/4\pi$ of an isotropic antenna. It provides a much larger angular resolution, and much more directive.

Most radio telescopes use large reflectors to collect and focus power onto simple feed antennas connected to receivers.

## The Focal Length

Plane wave fronts from a distant source arrive perpendicular to the $z$-axis. From a wavefront at height $h$ above the vertex, the ray path lengths at all radial offsets $r$ down to the reflector and up tot the focal point at $z=f$ must be the same to remain in phase. Which gives us the requirement that,

$$z=\frac{r^2}{4f}$$

The focal length is related to the diameter of the reflector, by the ratio $f/D$. If this is too high, the support structure is too large. If its too small the field of view becomes limited. Typically, $f/D\approx 0.4$.

Parabolic reflectors are useful because,

1. The effective area can approach the geometric area.
2. Simpler than an array of dipoles.
3. Feed antenna can be *swapped out* to observe over a wide range of frequencies. Note that as the frequency goes up the feed horn size goes down.

## The Far-Field Distance

We can consider spherical waves emitted from a certain distance as plane waves. 

$$R_\text{ff}\approx \frac{2D^2}{\lambda}$$

Unless the distance is larger than $R$, path-length errors will introduce significant phase errors in the waves coming from the off-axis component of our reflector, reducing the effective area and the antenna power pattern.

## The Aperture Illumination Pattern

An aperture is the opening which all rays pass. For a paraboloidal reflector of diameter $D$, the aperture is a plane circle with diameter $D$. 

In determining the power gain as a function of position for a circular aperture, we assume,

1. A 1D aperture of width $D$ and $R\gg R_\text{ff}$.
2. Consider a current density $J(x,t)=J(x)\exp(-i\omega t)$ for $-D/2\le x\le D/2$ and zero otherwise. Note that, the radiation between two points separated by x on the aperture, will travel an extra distance $\Delta r=x\sin\theta$.

For a receiving antenna, the electric field pattern is $f(\ell)$ and the electric field illuminating the aperture is $g(u)$,

$$f(\ell)=\int_\text{aperture}g(u)\exp(-i2\pi\ell u)\,du$$

In the far-field limit, the electric field pattern is the Fourier transform of the electric field illuminating the aperture. 

### Uniform illumination

The normalised electric field pattern of a uniformly illuminated 1D aperture of width $D$ at wavelength $\lambda$. Note $g(u)=\text{constant}$ and $-D/2\lambda<u<D/2\lambda$. So we consider a unit rectangle of size $D=\lambda$, so $\Pi(u)=1$ and $-1/2<u<1/2$ and its zero outside those bounds. We find the pattern,

$$f(\ell)=\frac{\sin(\pi\ell)}{\pi\ell}=\text{sinc}(\ell)$$

where $\ell=\sin\theta$. Using the similarity theorem for Fourier transforms: $f(1/a)/|a|$ is the FT of $g(au)$ for $a\not=0$. Then,


$$f(\ell)\propto\text{sinc}(\ell D/\lambda)$$

And for large apertures ($D/\lambda$) $\ell\approx\theta$, i.e. $f(\ell)\propto\text{sinc}(\theta D/\lambda)$. And the power pattern scales as,

$$P(\ell)\propto \text{sinc}^2\bigg(\frac{\ell D}{\lambda}\bigg)^2$$

### Normalised power spectrum

Such that the normalised power pattern, $P_n(\ell)$, for a 1D uniformly illuminated aperture is,

$$P_n(\ell)=\text{sinc}^2\bigg(\frac{\theta D}{\lambda}\bigg)^2$$

The central peak of the power pattern between the first minima is called the main beam. The smaller secondary peaks are called side-lobes. These minima are for,

$$\frac{\pi\theta D}{\lambda}=n\pi$$

The first minimum is for $n=1$. Such that we can define the zero-power bream width,

$$\theta_\text{ZPBW}=\frac{2\lambda}{D}$$

Which is the angular size of the main beam. However, we generally use the half-power beam width as the definition for the main beam,

$$\theta_\text{HPBW}\approx\frac{0.89\lambda}{D}$$

The angular size for which the half of the power is received, assuming full illumination. This is the width of the point spread function. And is defined as the resolution of a telescope.

More generally, the HPBW is given by,

$$\theta_\text{HPBW}\approx\frac{k\lambda}{D}$$

where $k$ is dependent on the illumination pattern.

### 2D apertures

We now consider a 2D rectangular aperture. The field pattern in 2D is,

$$f(\ell,m)\propto\iint g(u,v)\exp(-i 2\pi(\ell u+mv))\,du\,dv$$

where $v=y/lambda$, $m=\sin\theta_y$, and similarly for $u$ and $\ell$. The electric field pattern will therefore be,

$$f(\ell,m)\propto \text{sinc}\bigg(\frac{\ell D_x}{\lambda}\bigg)\,\text{sinc}\bigg(\frac{m D_y}{\lambda}\bigg)$$

With a normalised power pattern like,

$$P_n(\ell,m)=\text{sinc}^2\bigg(\frac{\ell D_x}{\lambda}\bigg)\,\text{sinc}^2\bigg(\frac{m D_y}{\lambda}\bigg)$$

We can determine the peak power gain $G_0$ in any direction,

$$G_0=\frac{4\pi D_x D_y}{\lambda^2}\propto A_\text{geom}=D_x D_y$$

Such that the power gain is,

$$G=G_0\text{sinc}^2\bigg(\frac{\theta_x D_x}{\lambda}\bigg)\,\text{sinc}^2\bigg(\frac{\theta_y D_y}{\lambda}\bigg)$$

From the definition of the maximum effective collecting area we find that the largest effective area is the geometric area of the telescope. And $A_e$ is independent of the wavelength.

An ideal illuminated aperture has an (aperture) efficiency $\eta_A=1$, given the definition,

$$\eta_A\equiv \frac{\max(A_e)}{A_\text{geom}}$$

If we want to achieve the maximum angular resolution be look for a narrow main beam width in an illumination pattern. To limit the side-lobe structure we want for instance a Gaussian current grading, which has minimal/none side-lobe structure.

## The Aperture Efficiency 

Not all of the aperture is used for observation. Such that the aperture efficiency is smaller than unity. This also affects the angular resolution and side-lobe structure. Note we define $\eta_A=\eta_\text{sp}\eta_t\eta_b\eta_s$,

- $\eta_\text{sp}$: feed spillover; radiation from the feed falls outside the antenna.
- $\eta_t$: feed illumination taper; outer parts of the antenna are illuminated less than the centre. For instance, in case of a Gaussian illumination pattern the beam width is about 35% larger. Which reduces the aperture efficiency by about 30%. It does also reduce the spillover and reduces the first side-lobe level by an order of magnitude.
- $\eta_b$: aperture blockage, for instance by the receiver system. This term is defined as, 
  $$\eta_b=\bigg(1-\frac{\text{effective blocked area}}{\text{total area}}\bigg)^2$$
- $\eta_s$: surface errors; random errors on the parabolic shape introduce phase changes. Caused by manufacturing errors, thermal changes across the antenna, deformation due to gravity, or strong winds. The surface efficiency is given by the Ruze equation, in terms of the rms of the surface error fluctuations,
  $$\eta_s=\exp\bigg[-\bigg(\frac{4\pi\sigma}{\lambda}\bigg)^2\bigg]$$

## Antenna Mount & Feed Position

- Equatorial mount: the mount is aligned with the polar axis. Rotation of polar axis set the RA. DEC axis moves to set the DEC. 
  - Pros: beam does not rotate over time, better tracking accuracy. 
  - Cons: higher cost, poorer gravity performance, non-intersecting axis.
- Alt-Az mount: two moving axes that are fixed relative to the Earth.
  - Pros: lower cost, better gravity performance.
  - Cons: beam rotates over time.
