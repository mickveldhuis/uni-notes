# 2. Radiation Fundamentals

## Brightness & Flux

Radiation in empty space can be considered as a stream of particles moving at the speed of light. The energy $dE$ flowing through $d\sigma$ in time $dt$ in the frequency range $\nu+d\nu$ within solid angle $d\Omega$ from an incoming ray at angle $\theta$ is,

$$dE=I_\nu\cos\theta d\sigma\, d\Omega\, dt\, d\nu$$

### Brightness

This has an associated power, $dP=I_\nu\cos\theta\,d\sigma\,d\Omega\,d\nu$. Such that we define the specific intensity as,

$$I_\nu=\frac{dP}{\cos\theta\,d\sigma\,d\Omega\,d\nu}$$

The specific intensity is conserved along any ray in empty space, meaning: the brightness is independent of distance and is the same at the source and at the detector. Furthermore,

$$I=\int_0^\infty I_\nu\,d\nu$$

is also conserved. 

### Flux

We define the *flux-density* as the spectral power received by a detector per unit projected area, i.e.

$$dS_\nu=I_\nu\cos\theta\,d\Omega$$

So for on-axis sources,

$$S_\nu=\int_\text{source} I_\nu(\theta,\phi)\,d\Omega$$

where $d\Omega=\cos\theta\,d\theta\,d\phi$. Note that $S_\nu$ is dependent on the distance to the source from the observer.

### Luminosity

Using $S_\nu$, we define the spectral luminosity,

$L_\nu=4\pi r^2 S_\nu$

Which is independent of the distance to the source. If you integrate $L_\nu$ over the whole frequency range, you obtain the *bolometric luminosity* $L_\text{bol}$.

## Radiative Transfer

### Absorption only

If we consider a source at $s=0$ and a detector at $s=s_0$, we can define the linear absorption coefficient as

$$\kappa_\nu=\frac{dp_\nu}{ds}$$

where $dp_\nu$ is the probability of a photon being absorbed in a slab of thickness $ds$. Such that

$$\frac{dI_\nu}{I_\nu}=-dp_\nu$$

If we integrate over, say, an area of space which is not empty containing some absorbing *material*, from $s_\text{in}$ to $s_\text{out}$, we obtain

$$I_\nu(s_\text{out})=I_\nu(s_\text{in})\exp(-\tau_\nu)$$

where $\tau_\nu$ is the optical depth, defined as,

$$\tau_\nu=-\int_{s_\text{out}}^{s_\text{in}}\kappa_\nu(s')\,ds'$$

If $\tau_\nu \gg 1$ the absorber is optically thick (opaque) and if $\tau_\nu\ll 1$ the absorber is optically thin (transparent). 

### Including emission

There's also a chance that a photon may be emitted within some volume $ds\,d\sigma$, which is described by $\epsilon_\nu$, the emission coefficient. Such that the radiative transfer equation (RTE) becomes,

$$\frac{dI_\nu}{ds}=-\kappa_\nu I_\nu+\epsilon_\nu$$

These coefficients are not independent, when the emitting and absorbing medium are in thermodynamic equilibrium (TE), then $I_\nu=B_\nu(T)$. In that case the LHS of the RTE becomes zero and,

$$\frac{\epsilon_\nu(T)}{\kappa_\nu(T)}=B_\nu(T$$

Which is *Kirchhoff's law* for a TE system. We also have *local thermodynamic equilibrium* (LTE), where the emitting/absorbing material is in thermal equilibrium, even if it's not in equilibrium with the radiation field. 

### The brightness temperature

From the RJ-approximation we can see that $T$ and $I_\nu$ are equivalent, such that we define a quantity called the *brightness temperature* $T_b(\nu$),

$$T_b(\nu)\equiv \frac{I_\nu c^2}{2k\nu^2}$$

$T_b$ is a practical way to specify the brightness, as radio telescopes are often calibrated by loads of known temperature. The brightness temperature of the atmosphere is given by

$$T_b=T_\text{atm}\big\{ 1 - \exp( -\tau_z \sec z ) \big\}$$

In general, the brightness temperature of radiation at position $s$, of a medium with temperature $T$ and optical depth $\tau_\nu(s)$, is given by:

$$T_b(s)=T_b(0)\exp[-\tau_\nu(s)]+T(1-\exp[-\tau_\nu(s)])$$

where the first term on the RHS is the attenuation of the original brightness by the medium and the second term is the contribution of the emission from the medium. Note  that at centimeter wavelengths, the CMB and atmosphere dominate the signal received from radio telescopes.

## Emissivity and Reflectivity

We define the *reflectivity* as the probability that an incident photon of a certain frequency is reflected, such that for an opaque body,

$$a_\nu+r_\nu=1$$

where $a_\nu$ is the absorption coefficient ($a_\nu=1$ for a back body), $r_\nu$ is the reflection coefficient. The brightness temperature of an opaque body in LTE at temperature $T$ is,

$$T_b(\nu)=a_\nu T=(1-r_\nu)T$$

Note that $a_\nu<1$ (no perfect absorbers exist), therefore $T_b<T$. And, a perfect reflector has a zero brightness temperature, i.e. it does not emit.

## Black Body Radiation

The integrated brightness (radiance) of a black body radiator at temperature $T$ is,

$$B(T)=\frac{\sigma T^4}{\pi}$$

where $\sigma$ is the Stefan-Boltzmann constant. Note that the Planck function attains a maximum at

$$\nu_\text{max}\,[\text{GHz}]=55.789 T$$

We can also define a spectral energy density,

$$u_\nu=\frac{1}{c}\int I_\nu\,d\Omega$$

Which, when $I_\nu=B_\nu$, is given by $u_\nu=4\pi B_\nu/c$. And the total radiation energy density, given by integrating over all frequencies, is, 

$$u=\frac{4\sigma T^4}{c}=\alpha T^4$$

where $\alpha=7.6\times 10^{-16}\ \text{J}/\text{m}^3/\text{K}^4$.

## Radio Waves in a Conducting Medium

A plasma consists of an ionised gas of ions and free electrons, which has no net charge. We generally consider a cold plasma, where the thermal motions of electrons are negligible.

The medium is defined by the parameters $\mu$, $\epsilon$, and $\sigma$. Recall from E&M that,

$$\nabla\times\mathbf{E}=-\frac{\partial\mathbf{B}}{\partial t}$$

and


$$\nabla\times\mathbf{B}=-\mu_0\mathbf{J}+\mu_0\epsilon_0\frac{\partial\mathbf{E}}{\partial t}$$

where $\mathbf{J}=\sigma\mathbf{E}$. Rewriting the above equations, fully, in terms of $\mathbf{E}$ and $\mathbf{B}$, we obtain the wave equation for $\mathbf{E}$,

$$\nabla^2\mathbf{E}-\mu_0\sigma\dot{\mathbf{E}}-\mu_0\epsilon_0\ddot{\mathbf{E}}=0$$

This expression reduces to,

$$k^2=\frac{\omega^2}{c^2}+i\frac{\sigma\omega}{\epsilon_0 c^2}$$

Note that $c^2=1/\mu_0\epsilon_0$. This is an expression for the dispersion, i.e. how the waves change as a function of frequency. We can define the phase velocity of the waves, i.e. the rate that any one frequency component travels through a medium, as,

$$v=\frac{\omega}{k}=\frac{c}{\sqrt{\epsilon\mu}}$$

Note, that means that we can write the wave vector as $k=\alpha+i\beta$,

$$\mathbf{E}(r,t)=\mathbf{E}_0\exp(-\beta r)\exp(-i(\omega t-\alpha r))$$

The $\exp(-\beta r)$ term will dampen the waves, in case of a conducting medium (similar to the absorbing effect discussed in optics). The conductivity in the plasma is,

$$\sigma=i\frac{n_e e^2}{m_e^2\omega}$$

which is purely imaginary. Plugging this expression into the expression for the wave vector $k$, we obtain,

$$k^2=\frac{\omega^2}{c^2}\bigg(1-\frac{n_e e^2}{\omega^2\epsilon_0 m_e}\bigg)$$

where we define the plasma frequency,

$$\omega_p^2=\frac{n_e e^2}{\epsilon_0 m_e}$$

which defined the natural resonant frequency of the oscillation of the plasma. We can also define the group velocity as the rate that the wave envelop travels through a medium as,

$$v_g=\frac{d\omega}{dk}$$

Note that the group velocity is related to the phase velocity by $v_g v_p=c^2$ and if $\omega_g=\omega$, there's no propagation of radiation through the plasma, and when $\omega > \omega_p$ the group velocity is purely imaginary and we have reflection.

Using the phase velocity we can define the refractive index,

$$n=\frac{c}{v}=\sqrt{1-\frac{\omega_p^2}{\omega^2}}$$

We can investigate the effect of the dispersive effect on the group velocity, considering a set of pulses moving with the group velocity. The time that these pulses will be delayed (due to dispersion) is given by

$$\tau_D=\int_0^L\frac{dl}{v_g}=\frac{L}{c}+\frac{e^2}{8\pi^2 cm_e\epsilon_0}\frac{1}{\nu^2}\int_0^L n_e\,dl$$

Using this expression, we can define the difference in arrival time between two different frequencies as,

$$\Delta\tau_D=\frac{e^2}{8\pi^2 cm_e\epsilon_0}\bigg(\frac{1}{\nu_1^2}-\frac{1}{\nu_2^2}\bigg)\int_0^L n_e\,dl$$

The integral we call the [*Dispersion Measure* (DM)](https://casper.ssl.berkeley.edu/astrobaki/index.php/Dispersion_measure), i.e.,

$$\text{DM}=\int_0^L n_e\,dl$$

with $n_e$ in $\text{cm}^{-3}$ and $l$ in $\text{pc}$. From DM, we see that the larger the electron density or the path length, the larger the dispersive effect is.

## Nyquist Theorem & Noise Temperature

A resistor is any electrical device that absorbs all of the electrical power applied to it. The motions of charged particles in a nonzero temperature resistor generates electrical noise (a current). This noise is almost constant in frequency, but would increase with temperature.

The power in such a resistor is dependent on the temperature and the collisional time, $P\propto T/\tau_c$. There's a high frequency cut-off, above this cut-off we have time-scales were the collision become too small for fluctuations, meaning no noise/power. Below this cut-off we have a flat response in spectral space; i.e. random white noise.

Such that for a single resistor the spectral power from rms noise fluctuations is,

$$P_\nu=kT$$

Which is independent on the resistance; it depends only on the temperature. The expression for $P_\nu$ is *Nyquists formula*.

## Radiation From An Accelerated Charge

Accelerated charged emit (non-thermal) radiation. If we consider the radial and tangential electric fields, they are related via,

$$E_\theta=E_r\frac{t\sin\theta}{c}\frac{dv}{dt}$$

where we can use that $E_r=q/r^2$ from Coulomb's law. In case there's no acceleration, then there will be a zero tangential field and hence no radiation, such that,

$$E_\theta=\frac{qa\sin\theta}{rc^2}$$

The power per unit area is defined as,

$$\mathbf{S}=\frac{c}{4\pi}\mathbf{E}\times\mathbf{H}$$

And for plane waves (in cgs units) $|\mathbf{E}| = |\mathbf{H}|$, such that

$$S=\frac{1}{4\pi}\frac{q^2a^2}{c^3}\frac{\sin^2\theta}{r^2}$$

Due to the sine squared term the radiation emitted is highly anisotropic. Such that the total power emitted in all directions is given by,

$$P=\int S\,dA=\frac{2}{3}\frac{q^2a^2}{c^3}$$

This expression for the power is called *the Larmor formula*, it describes the total power radiated by any accelerated charged particle, such as electrons and protons.

The total energy emitted is given by,

$$W=\int_{-\infty}^{\infty}P(t)\,dt=\frac{2}{3}\frac{e^2}{c^3}\int_{-\infty}^{\infty}a(t)\,dt$$
