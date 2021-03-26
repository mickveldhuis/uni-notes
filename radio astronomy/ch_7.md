# 7. Continuum Emission Mechanisms

## Overview 

- Thermal emission: the thermal motions (due to $T>0\ \text{K}$ ) of particles results in the emission of thermal radiation. Such as,
  - Black body emission, e.g. the moon, quiet Sun, planets
  - Grey body emission, e.g. heated dust
  - Free-free emission, thermal bremsstrahlung from ionized hydrogen clouds
- Non-thermal emission: charged particles are accelerated in magnetic fields to produce synchrotron radiation (independent of the temperature). E.g. accelerated within radio jets from black holes or shocked acceleration by expanding SN remnants.

Spectral energy distributions allow us to study the broad band emission such that we can determine whether the source is thermal or non-thermal. Furthermore, they allow us to study the physical conditions within the sources (density, temperature, magnetic fields, star-formation, energetics).

Note that for instance synchrotron radiation goes as $S_\nu\propto\nu^{-0.7}$, free-free emission goes as $S_\nu\propto\nu^{-0.1}$, and dust goes up according to a (modified) black body spectrum.

## Emission from Heated Dust

Dust grains mainly consist of silicate and graphite (carbon) material, of non-spherical shape. They are intermixed with (molecular) hydrogen clouds and therefore trace the molecular hydrogen used for star formation.

The UV radiation from young stars is absorbed by the dust and re-radiated at FIR wavelengths (at a much lower temperature). As structures have a variety of temperatures, the dust is not perfectly non-reflective and there is a variation of the dust opacity with frequency, therefore, we use a modified black body (grey-body) spectrum.

From radiative transfer we find that the spectrum is defined by,

$$S_\nu=(1-e^{-\tau_D})B_\nu(T)\Delta\Omega$$

Note that at mm/sub-mm wavelengths the medium can be considered optically thin ($\tau_D\ll 1$). Furthermore, the optical depth is not constant,

$$\tau_D=\bigg(\frac{\nu}{\nu_0}\bigg)^\beta$$

where $\nu_0$ is the frequency when $\tau_D=1$ and $\beta$ is the emissivity. Or in terms of the opacity,

$$\kappa_\nu=\kappa_0\bigg(\frac{\nu}{\nu_0}\bigg)^\beta$$

Such that we find that the spectrum is defined by,

$$S_\nu=\frac{2h}{c^2}\frac{\Delta\Omega}{\nu_0^\beta}\frac{\nu^{3+\beta}}{e^{h\nu/kT}-1}$$

Typical values are $\beta=1\ \text{to}\ 2$ and a dust temperature of $T=1\ \text{to}\ 2\ \text{K}$. 

As the dust is heated by young stars the luminosity of the dust is directly related to the star-formation rate of the galaxy, such that,

$$\text{SFR}\,[\text{M}_\odot/\text{yr}]=1.71\times 10^{10}\,L_\text{IR}\,[L_\odot]$$

where $L_\text{IR}$ is the integrated IR luminosity.

## Free-Free Emissions (Breaking Radiation)

Free-free radiation is related to star formation. And it is produced by free electrons in an ionised plasma (HII regions) scattering off ions without being captured (they remain free).

The free electrons are attracted by the positive ions, therefore will endure an electro-static acceleration, which produces pulses of radiation. As derived in week 2 the power of this radiation is given by Lamor's formula,

$$P=\frac{2}{3}\frac{q^2a^2}{c^3}$$

where $a$ is the tangential (perpendicular) acceleration, whose magnitude is determined from Coulomb's law.

The energy of an emitted photon is much smaller than the energy of an electron. Therefore, the deflection of the electron is very small, we can consider it to (almost) remain a straight line.

During the interaction, the electron is accelerated in the radial and tangential directions to its almost straight path, such that respectivelly,

$$F_{||}=\frac{Ze^2}{b^2}\sin\psi\cos^2\psi$$

and,

$$F_{\perp}=\frac{Ze^2}{b^2}\cos^3\psi$$

where $b$ is the impact parameter (the distance of closest approach). 

The tangential component of the acceleration is roughly Gaussian, which produces a short pulse that dominates radio wavelengths. The radial component is somewhat sinusoidal, containing both acceleration and deceleration, dominating IR wavelengths.

Only considering the radial component, we find that the power is,

$$P=\frac{2}{3}\frac{Z^2e^6}{m_e^2c^3}\bigg(\frac{\cos^3\psi}{b^2}\bigg)^2$$

The total energy radiated is therefore given by $W=\int P\,dt$, which gives,

$$W=\frac{\pi}{4}\frac{Z^2e^6}{m_e^2c^3b^4}\frac{1}{v}$$

Which is the total energy radiated by a charge $e$ if it moves in the field of an ion with a charge $Ze$. The energy is emitted in a single pulse of duration $\tau\approx b/v$, called the interaction time. The frequency of such an emission is,

$$\nu=\frac{1}{2\pi\tau}$$

which is the frequency over which the power spectrum is approximately flat.

The total energy radiated per unit frequency is,

$$W_\nu=\frac{\pi^2}{2}\frac{Z^2e^6}{m_e^2c^3}\frac{1}{b^2v^2}$$

To determine the free-free radiation from an HII cloud, we need to determine the distribution of velocities and its dependence on the electron temperature $T_e$. For which we assume that the velocities are distributed according to a non-relativistic Maxwellian distribution. And the distribution of impact parameters and its dependence on the electron and ion number densities $N_e$ and $N_i$.

The number of electron-ion encounters per unit volume is given by,

$$N(v,b)\,dv\,db=\big[2\pi\,db\big]\big[vf(v)\,dv]N_eN_i$$

Therefore the emission coefficient is given by,

$$\epsilon_\nu=\frac{\pi^2 Z^2e^6 N_eN_i}{4c^3m_e^2}\bigg(\frac{2m_e}{\pi k T}\bigg)^{1/2}\ln\bigg[\frac{b_\text{max}}{b_\text{min}}\bigg]$$

Such that,

$$I_\nu=\int\epsilon_\nu\,ds\propto\int N_e^2T^{-1/2}\,ds$$

assuming that the hydrogen plasma is optically thin, which means that $N_e=N_i$. The observed $I_\nu$ will also depend on the absorption within the HII region, which is, by Kirchoff's law, given by,

$$\kappa_\nu=\frac{\epsilon_\nu c^2}{2kT\nu^2}=\frac{1}{\nu^2 T^{3/2}}\bigg[\frac{Z^2e^6}{c}N_eN_i\frac{1}{\sqrt{2\pi(m_ek)^3}}\bigg]\frac{\pi^2}{4}\ln\bigg[\frac{b_\text{max}}{b_\text{min}}\bigg]$$

note $b_\text{min}$ has a quantum mechanical limit from the uncertainty principle, and $b_\text{max}$ has the limit where a significant amount of power at some relevant radio frequency can be generated. Such that, approximately,

$$b_\text{min}=\frac{\hbar}{m_e v}$$

and,

$$b_\text{max}=\frac{v}{2\pi \nu}$$

Given that $b_\text{min}$ is a function of frequency, the natural log is weakly related on the frequency, leading to,

$$\kappa_\nu\propto\nu^{-2.1}$$

And the optical depth along the line-of-sight is given by,

$$\tau_\nu\propto\int\frac{N_e^2}{\nu^{2.1}T^{3/2}}\,ds$$

Such that in the optically thick regine,

$$S_\nu\propto\nu^2$$

consistent with a black body. However, in the optically thin regime we find,

$$S_\nu\propto\nu^{-0.1}$$

creating a very flat spectrum. 

In a more involved treatment, considering the proper Gaunt factor, gives the following optical depth,

$$\tau_\nu\approx3.28\times10^{-7}\bigg(\frac{T_e}{10^4}\bigg)^{-1.35}\bigg(\frac{\nu}{\text{GHz}}\bigg)^{-2.1}\bigg(\frac{\text{EM}}{\text{pc}\,\text{cm}^{-6}}\bigg)$$

where EM is the emission measure,

$$\frac{\text{EM}}{\text{pc}\,\text{cm}^{-6}}=\int_\text{los}\bigg(\frac{N_e}{\text{cm}^{-3}}\bigg)^2d\bigg(\frac{s}{\text{pc}}\bigg)$$

Note that measurements of the flux-density as a function of frequency can be used to determine the optical depth (and hence the electron number density), which can be used to infer the level of star formation from the number of ionising photons from young stars.

## Synchrotron Emission

This consists of charged particles that can be accelerated by magnetic fields, to produce magneto-bremsstrahlung radiation (defined by the particle's velocity). We can consider three regimes,

1. Gyro radiation: $v\ll c$
2. Cyclotron radiation: $v < c$
3. Synchotron radiation: $v\approx c$

### Gyro Radiation

Consider particles in a circular orbit with radius $R$, perpendicular to the $B$-field. We can define the gyro frequency,

$$\omega_G=\frac{eB}{m_e c}$$

We generally (not impossible) do not see gyro-radiation at radio wavelengths because its too weak.

Synchrotron emissions are produced by cosmic rays (electrons and protons) with extremely high energies. Such that we need special relativity to describe the behaviour of the radiation.

The inertial mass of ultrarelativistic particles is higher (for an electron $m=\gamma m_e$). Thus their orbital frequency is larger. 

$$\omega_B=\frac{\omega_G}{\gamma}$$

where the Lorentz factor is defined as,

$$\gamma\equiv\frac{1}{\sqrt{1-\beta^2}},\ \beta \equiv \frac{v}{c}$$

The power of synchrotron radiation is given by,

$$P=2\sigma_T\beta^2\gamma^2 c U_B\sin^2\alpha$$

where $\beta=v/c$, $\gamma$ is the Lorentz factor, $U_B=B^2/8\pi$ the magnetic energy density, and $\sigma_T$ is the Thompson cross-section. 

Note that the power radiated by synchrotron radiation is strongly dependent on the magnetic field $B$ and the velocity $v$ of the accelerated particle. Synchrotron radiation is much more powerful than cyclotron radiation due to the relativistic velocities of the electrons, i.e. $P_\text{sync}\propto\gamma^2\beta^2$. The average power emitted by an electron over its lifetime ($10^3$ to $10^6$ years), is given by,

$$\langle P\rangle = \frac{4}{3}\sigma_T\beta^2\gamma^2 c U_B$$

We can define the synchrotron lifetime of the emitting electron as the ratio of the energy of the electron divided by the power,

$$t_\text{lifetime}=\frac{\gamma m_e c^2}{\langle P\rangle}\approx 16.4\ \text{years}\ \frac{1}{\gamma}\bigg[\frac{1\ \text{Gauss}}{B^2}\bigg]$$

So electrons with higher $\gamma$ and/or stronger $B$-field will lose their energy faster. Note that an old source will have a lot of low energy electrons and a young source will have a lot of high energy electrons.

The power pattern of the radiation is also changed by relativistic effects, the electrons appear to catch up with their own emission, called relativistic beaming.

The observed synchrotron power spectrum is the Fourier transform of the time series of the pulses. This power spectrum is almost continuous,

$$P(\nu)=\frac{\sqrt{3} e^3 B \sin\alpha}{mc^2}\bigg(\frac{\nu}{\nu_c}\bigg)\int_{\nu/\nu_c}^\infty K_{5/3}(\eta)\,d\eta$$

where the critical frequency is $\nu_c=3\gamma^2\nu_G\sin\alpha/2$. The see that most of the energy is radiated around the critical frequency.

The spectrum of a synchrotron source is the superposition of the spectrum of the individual electrons. The ensemble of electrons is thought to have a power-law electron energy distribution (i.e. a non-thermal process),

$$N(E)\,dE\approx KE^{-\delta}\,dE$$

where $N(E)$ is the number density of electrons. The spectral energy distribution of synchrotron emission is given by,

$$S_\nu\propto\nu^\alpha$$

where,

$$\alpha=\frac{1-\delta}{2}$$

and we used that,

$$\epsilon_\nu\propto B^{(\delta+1)/2}\nu^{(1-\delta)/2}$$

Note that the synchrotron spectrum of a power-law energy distribution is itself a power-law. The spectral index $\alpha$ is given by,

$$\alpha=\frac{\log(S_{\nu_2}/S_{\nu_1})}{\log(\nu_2/\nu_1)}$$

From this index we can ascertain the coefficient $\delta$ in the energy distribution of electrons. From a spectrum of the synchrotron radiation we find that we can determine an age for the electron distribution and the energetics.

The synchrotron spectrum will have a $\nu^{2.5}$ dependence at low frequencies (optically thick regime), then at higher frequencies it will go as $\nu^{-0.7}$ (optically thin), and thus is dominated by the power-law energy distribution of electrons. At even larger frequencies we see _synchrotron cooling_, where the spectrum drops off, relatively steep, due to higher energy (i.e. higher frequency) electrons radiating away their energy first. 

There is also the _low-energy cut-off_ in the electron energy distribution, due to the spectrum of individual electrons ($S_\nu\propto\nu^{1/3}$).

If the energy distribution of the electrons is Maxwellian, then [_synchrotron self-absorption_](http://www-astro.physics.ox.ac.uk/~astroc1/Lectures_files/lecture5-2011.pdf) will prevent the brightness temperature of the synchrotron radiation from exceeding the kinetic temperature of the emitting electrons. In an relativistic plasma the effective temperature is $T_e\propto\nu^{1/2}B^{-1/2}$, and thus in the optically thick regime $T_b=T_e$, and the flux density will go as $\nu^{5/2}$. Even if the ensemble has a nonthermal energy distribution. Thus at low frequencies the spectrum of a synchrotron self-absorbed. Which is independent of the slope of the electron-energy spectrum! Such that at the turn-over we can estimate,

$$\bigg(\frac{B}{\text{Gauss}}\bigg)\approx 1.4\times 10^{12}\bigg(\frac{\nu}{\text{Hz}}\bigg)\bigg(\frac{T_b}{\text{K}}\bigg)^{-2}$$

Continuum from normal galaxies is dominated by a combination of, free-free emission from HII regions and synchrotron radiation from cosmic ray (CR)-electrons, mainly accelerated in SNRs of massive stars. For these sources the galactic $B$-field is generally of the order of 5-100 micro Gauss. 

The synchrotron emission is related to the supernovae remnant rate, which is directly related to the star-formation rate via the _FIR-Radio correlation_,

$$q_\text{IR}=\log_10\bigg(\frac{L_\text{IR}}{\big[3.75\times 10^{12}\ \text{Hz}\big]L_{1.4\ \text{GHz}}}\bigg)$$

This quantity $q$ is typically of the order $q=2.4\pm 0.25\ \text{dex}$.
