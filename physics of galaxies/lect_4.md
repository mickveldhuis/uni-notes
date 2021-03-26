# Lecture 4: The Cosmic Distance Scale

## Groups of distance measures

We can roughly distinguish between two groups of distance measures.

### Absolute methods
- Distances can be determined quite directly.
- Typically involve geometric measurements.
- Typically used for nearby sources, i.e. sources within the Milky Way.

### Relative methods
- Typically used for larger distances.
- Often refers to a standard candle.


## Primary Methods: Distances within the Milky-Way

### Stellar Parallax

1 pc is the distance to some object (measured with respect to the earth being at a distance of 1 AU from the sun) such that the distance sun-earth subtends 1 arcsec.

$$d=\frac{1}{\varpi}$$

where $\varpi$ is the observed parallax in arcsec.

$$(m-M)_0\equiv 5\log_{10}\bigg(\frac{0.1\ [\text{arsec}]}{\varpi}\bigg)$$

### Secular Parallax

Instead of using the Earth's motion around the sun, one uses the motion of the sun around nearby stars. The mean proper motion of the stars $d\theta/dt$, which has a mean component proportional to $\sin\theta$ and if the slope of this line is $\mu$ then the distance $D$ is given (in parsec) by $D=4.16/\mu$, where $\mu$ is given in arcsec per year.

### Gravitational Lensing

Typically one would use a cluster of galaxies ($z\approx[0,1]$) which would function as a lens. Due to the mass of the object, light passing it will bend. The distance can be worked out from the light delay $t_{\text{lens}}^{(i)}$ due to the longer path (as a consequence of not reaching us directly). 

### The Sunyaev-Zeldovich Method

Galaxy clusters are gravitationally bound, between those galaxies we have the intracluster medium (lots of gas). As CMB photons pass through the cluster they will increase in energy (the Sunyaev-Zeldovich effect), and you know the normal characteristic energy of the CMB, such that you can determine the distance (to the cluster). In the expression for $D$, $\sigma_T$ is the collision cross-section, $F$ the flux, $\tau_s$ the optical (scattering) depth, and $T$ the electron temperature in the intracluster medium.

$$
D=\frac{\tau_s}{\theta n_e\sigma_T}=\frac{1.78\cdot 10^{-40}\tau_s^2\theta T^{1/2}}{24\sigma_T^2F}
$$

where

$$\tau_s=2\sigma_TRn_e$$

and if the cluster is spherical $R=D\theta$.

## Relative Methods (secondary/tertiary methods)

The general idea is to measure something that doesn't vary with the distance, e.g. a galaxy (i.e. flux specific phenomenon). Relate the velocity or period to the luminosity using local object, using $F=L/4\pi d^2$ we can work out the distance or we use the distance modulus.

### Stellar main sequence fitting

One can calibrate the main sequence in terms of parallax in terms of magnitude and color. Then compare the apparent magnitude to other clusters and determine the distance.

$$m_\text{cluster}-M_\text{ref}=5\log(d)-5+A$$

where $A$ is the extincition, i.e. dust will have the effect of yielding a lower flux than its true flux.

> In general main sequence fitting compares the location of the main sequence for the cluster stars placed on the HR Diagram where apparent magnitude is used as the y-axis variable to the location of the main sequence for nearby stars whose distances are well-known from parallax where absolute magnitude is used on the y-axis. Any difference in position between the main sequences must be due to the distance of the cluster. The vertical position of the cluster main sequence is adjusted that it lines up with the main sequence of the nearby stars. The amount of vertical adjustment gives the distance modulus which in turn gives the distance.

### Variable stars

Variable stars vary periodically in luminosity (due to pulsations in their interiors). For instance Cepheids (young, quite luminous, with relatively long periods).

### Time-delay methods

Typically applied to supernovae. A supernova explosion at time t is seen at position $A$. At some time later, $t_0$, light from the supernova is seen at
position $B$, and at an even later time, $t_1$, exactly the
same signal is seen at position $C$. Using this information one can write

$$
t_B-t_A=\frac{r(1-\sin i)}{c}\\[1em]
t_C-t_A=\frac{r(1+\sin i)}{c}
$$

and determine the distance.

### Standard candles

Standard candles are anything that has a predictable brightness. Using Cepheids is very useful for nearby galaxies, we can measure the distance out to ~30 Mpc this way. We can determine the apparent magnitude by measuring the pulsation for several periods and using the period-luminosity relation determine the distance modulus.

### Supernovae as distance estimators

Type I supernovae involve a white dwarf that is part of a binary system. Type II supernovae involve very massive stars at the ends of their lives. Because supernovae are such energetic events, one can observe them at great distances. They are only useful as distance indicators if it is possible to calibrate them, i.e. to relate their observed brightness profile to absolute magnitudes. Type I supernovae are very uniform and easy to calibrate, more so than type II.

### Globular cluster LF

The number of globular clusters per unit magnitude in a galaxy has a Gaussian form, with a well defined peak (of the Gaussian) at turnover magnitude $M_0=-6.5$. This turnover magnitude is a standard candle that can work out o ~50 Mpc.

### The Tully-Fisher relation

The (linear) relation between absolute magnitude (or luminosity) and the rotational velocity in spiral galaxies. By comparing the intrinsic brightness with the apparent magnitude (which you measure), one can calculate its distance.

### The Hubble Law

For the fast majority of objects we use the Hubble Law $v=H_0d$ (where $H_0\approx 100h$ km/s/Mpc is the Hubble Constant, currently we use $h=0.69$ to parameterize the Hubble constant).
