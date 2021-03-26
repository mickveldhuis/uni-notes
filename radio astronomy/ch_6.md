# 6. Inferferometers

## Basics

Each of the telescopes part of the interferometer has a resolution of $\theta\approx \lambda/D$. The combined resolution of the entire interferometer is,

$$\theta\approx\frac{\lambda}{B}$$

which is obtained by correlating the signals from different telescopes to effectively increase the diameter of a single telescope to an arbitrarily large distance $B$ called the baseline length.

Pros:
- High angular resolution, down to (less than) 1 mas.
- Better sensitivity, due to the collecting area being $N\times\pi D^2/4$, where $N$ is the number of telescopes.
- Large field-of-field in the case of phased array feeds. 

Cons:
- Field-of-field is limited by the _fov_ of the individual telescopes.

## Young's Double Slit Experiment

If we consider a plane wave passing through a slit a fringe pattern is created due to constructive and destructive interference. 

Constructive interference fringes occur when the path difference is an integer number of wavelength (i.e. the waves add in phase),

$$d\sin\theta=n\lambda$$

Similarly, for destructive interference,

$$d\sin\theta=(n+1/2)\lambda$$

When the distance $y$ between the slits is much smaller than the distance to where the pattern is formed $L$ the maxima are located at,

$$y_c=\frac{n\lambda L}{d}$$

and

$$y_d=\frac{(n+1/2)\lambda L}{d}$$

The spacing between successive fringes is,

$$\Delta y=\frac{\lambda L}{d}$$

or rather $\theta\approx\lambda/D$ in terms of the angular distance.

## A Simple Two-Element Interferometer

A two element interferometer is similar to Young's double slit experiment. The radiation to antenna 1 travels an extra distance $\mathbf{b}\cdot\hat{\mathbf{s}}=b\cos\theta$, where $\mathbf{b}$ is the baseline length.

Expressed in a geometric delay we have,

$$\tau_g=\frac{\mathbf{b}\cdot\hat{\mathbf{s}}}{c}$$

Which is the time delay in the signal at antenna 1. The combined output signal is the time-averaged multiplied voltage of the two telescopes. Note that we average over a time much larger than the inverse of the frequency of the voltage, $\Delta t\gg (2\omega)^{-1}$, such that we obtain the following response (output voltage),

$$R=\langle V_1V_2\rangle=\frac{V^2}{2}\cos(\omega\tau_g)$$

where $\omega$ is the frequency of the voltage, which is related to the observing frequency. The sinusoidal variations we call fringes, such that we can define the fringe phase $\phi=\omega\tau_g=b\cos\theta/c$. Differentiating the phase w.r.t. to the angle to the source is,

$$\frac{d\phi}{d\theta}=\frac{2\pi b\sin\theta}{\lambda}$$

The fringe period $\Delta\phi=2\pi$, corresponds to an angular change of $\Delta\theta=\lambda/b\sin\theta$. Thus, for large $b$, interferometers can measure very accurately the positions of sources.

For sources much larger than the adjacent positive and negative fringes will cancel out. E.g. the CMB is everywhere and therefore the signal will completely cancel (approximately). Small baselines are needed for extended sources and conversely large baselines are necessary for compact sources.

## Extended Sources

A spatailly incoherent extended source with sky brightness $I_\nu(\hat{\mathbf{s}})$ near frequency $\nu=\omega/2\pi$ can be considered as the sum of independent point sources. The response is then,

$$R_C=\int I_\nu(\hat{\mathbf{s}})\cos(2\pi\mathbf{b}\cdot\hat{\mathbf{s}}/\lambda)\,d\Omega$$

The output from the correlator also contains a complex part,

$$R_s=\int I_\nu(\hat{\mathbf{s}})\sin(2\pi\mathbf{b}\cdot\hat{\mathbf{s}}/\lambda)\,d\Omega$$

This allows us to define the (complex) visibility:

$$V=r_c-iR_s=Ae^{-i\phi},\ \ A=\sqrt{R_c^2+R_2^2}, \ \ \phi=\arctan(R_s/R_c)$$

The amplitude contains information about the brightness of the object. The phase contains information about the position of the source in the sky.

For a two element interferometer the response in terms of the visibility is given by,

$$V_\nu=\int I_\nu(\hat{\mathbf{s}})\exp(2\pi\mathbf{b}\cdot\hat{\mathbf{s}}/\lambda)\,d\Omega$$

## The General Response of an Interferometer

We define a set of coordinates, the $l, m, n$-coordinates. $l$ is east-west, $m$ is north-south, $n$ is up-down, and note that the source is located in the $\hat{\mathbf{s}}$ direction.

Or we define the $(u,v,w)$-plane. Where $u$ is east-west, $w$ is up-down, and $v$ is north-south. These are defined as,

$$\frac{\mathbf{b}}{\lambda}=(u, v, w)$$

and

$$\mathbf{s}=(l, m, \sqrt{1-l^2-m^2})$$

Such that we can describe the visibility as,

$$V_\nu(u,v,w)=\int \frac{I_\nu(l,m)}{\sqrt{1-l^2-m^2}}\exp\big[-i2\pi(ul+vm+wn)\big]\,dl\,dm$$

In case $w=0$,

$$V_\nu(u,v,w)=\int \frac{I_\nu(l,m)}{\sqrt{1-l^2-m^2}}\exp\big[-i2\pi(ul+vm)\big]\,dl\,dm$$

So the response of an interferometer is the inverse Fourier transform of the (apparent) sky brightness distribution.

## The Visibility Function

Each visibility samples a discrete point in the Fourier plane, giving information about the amount of power on some projected angular size on the sky.

To make images of the sky that are closest to the true surface brightness distribution we need a completely (well) samples $(u,v)$-plane.

To obtain a better sampling of the [Fourier plane](https://web.njit.edu/~gary/728/Lecture6.html),

1. Add more antennas: increase the number of baselines by $N(N-1)$
2. Add more frequencies: the $(u,v)$-coordinates are a function of the wavelength, using more frequency channels, the radial sampling will be increased.
3. Add more time: each visibility coordinate is dependent on the projected baseline length $b$. As the Earth rotates, $b$ changes and a different part of the $(u,v)$-plane is sampled.

Aperture synthesis uses the Earth's rotation to change the projected baseline length, to increase the sampling.

Note that the amplitude and phase of the visibilities as a function of baseline length and are dependent on the structure of the source.

- A point source has a constant visibility amplitude and if the source is offset from the center it will be constantly varying over time.
- A Gaussian source has a decreasing amplitude and constantly varying phase.

## The Delay Beam

Consider the effect of increasing the integration time and the bandwidth of our observation (to increase the SNR and the sampling of the $(u,v)$-plane). For a constant source brightness, we find that the brightness function over a bandwidth $\Delta \nu$ is,

$$V=\int I_\nu(\hat{\mathbf{s}})\text{sinc}(\Delta \nu\tau_g)\exp(-i2\pi\nu_c\tau_g)\,d\Omega$$

We can consider 3 beams:

1. Primary beam: due to the power pattern of the individual antennas of the baselines.
2. Synthesised beam: due to the sinusoidal response of the two antennas of the baseline.
3. Delay beam: due to the attenuation produced by the finite bandwidth of the observation.

The effect of the delay beam can be corrected for by defined a delay/phase center. It can be defined by adding a phase shift in the correlation, or by introducing an extra path length in the cable connecting the antennas, this is the compensating delay $\tau_0\approx\tau_g$. 

The time that the incoming waves can be considered coherent for (i.e. have known phase) is the coherence time, $\tau=1/\Delta\nu$.

We find that the delay beam can only be compensated for in a single direction, so that theta angular radius of the usable _FoV_ $\Delta\theta$, is determined by the variation in the geometric delay $\tau_g$. We find that,

$$\Delta\theta\Delta\nu\ll\theta_s\nu$$

where $\Delta\theta$ is the angular off-set from the phase centre, $\Delta\nu$ is the visibility bandwidth, $\theta_s$ is the synthesised beam width, and $\nu$ is the observing frequency. This causes smearing for wide-field images, which we can solve by,

1. splitting the bandwidth into many smaller channels. But, this increases the data volume.
2. Shift the phase centre is post-processing, and average the result after the fact.

The smearing leads to the objects being stretched in the sky surface brightness plane and a lowering of the measured surface brightness. It will be radially stretched in the $uv$-plane.

Furthermore, the correlator requires an averaging time sufficiently short such that the Earth's rotation will not move the source by more than the synthesised beam width in the interferometer frame. Otherwise this will lead to time smearing. This will tangential broadening of the source in the $uv$-plane.

$$\Delta\theta\Delta t\ll\theta_s\times 1.37 \times 10^4\ \text{s}$$

## Point Source Sensitivity

We can compute the sensitivity using the radiometer equation, including the number of antennas used,

$$\sigma_{I_\nu}=\frac{\text{SEFD}}{\sqrt{N(N-1)\Delta\nu_\text{RF}\tau}}$$

in terms of the SEFD. In terms of the system temperature,

$$\sigma_{S_\nu}=\frac{2kT_\text{sys}}{A_\text{eff}\sqrt{N(N-1)\Delta\nu_\text{RF}\tau}}$$

Note that the practical sensitivity of a real interferometer is also affected by the efficiency of the correlator, with an efficiency around $\sim 0.89$. 

## Extended Source Sensitivity

An interferometer is sensitive to structure on some angular-scale, which is given in terms of the surface brightness. The surface brightness sensitivity of an interferometer is much worse than a single dish with the same effective area because the beam solid angle is much smaller, by a factor $(D/b)^2$.

The sensitivity (in terms of $T_b$) is expressed as,

$$\sigma_{T_b}=\bigg(\frac{\sigma_{S_\nu}}{\Omega_A}\bigg)\frac{\lambda^2}{2k}$$

The synthesised beams produced by interferometers are typically Gaussian in shape, so the beam solid angle is given by,

$$\Omega_A=\frac{\pi\theta_S^2}{4\ln 2}$$

## Aperture Arrays

In the same way that an interferometer works, the receiving elements are added together by taking into account the delay due to the waves arriving at different times, from different directions.

1. Low costs
2. Better effective area at low (radio) frequencies
3. Large field-of-view and flexible electronic beam forming
4. With a very high (angular) resolution

It is simply an array of dipoles, which can function as an interferometer. Having a very narrow beam, allowing for very strong directional sensitivity, contrary to a single dipole.

To change the pointing we add an artificial delay to the output before combining the individual voltages. We can add multiple artificial delays, such that we can look at different parts of the sky at the same time.

We generally place the antennas in an aperture arrays at different distances from one another to have each sample at a different baseline, such that none of them observe the exact same part of the Fourier plane.

## Focal Plane Arrays

These are phased array feeds, where the receivers are off-set in the focal plane of the telescope such that they see slightly different parts of the sky.

1. Can provide a much larger field-of-view
2. Still limited by the mechanics of the telescope
3. Combining different beams results in a uniform response to the sky

