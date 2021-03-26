# 3. Dipole Antennas

## Fundamentals

An *antenna* is a device for converting EM radiation in space into electrical currents. 

### The $E$ and $H$-fields

If we consider an antenna of length $\Delta\ell$, we find the $E$-field and induction $H$ to be,

$$H_\psi = -i\frac{I\Delta\ell}{2\lambda}\frac{\sin\theta}{r}\bigg(1-\frac{1}{ikr}\bigg)\exp\big(-i\big[\omega t - kr\big]\big)$$

$$E_\theta = -i\sqrt{\frac{\mu_0}{\epsilon_0}}\frac{I\Delta\ell}{2\lambda}\frac{\sin\theta}{r}\bigg(1-\frac{1}{ikr}+\frac{1}{(ikr)^2}\bigg)\exp\big(-i\big[\omega t - kr\big]\big)$$

Note that the radiation field dominates in the far-field limit, the induction field goes as $1/r^2$, and the static part of the $E$-field goes as $1/r^3$.

We can determine the time-averaged Poynting vector, for a constant current distibution, is,

$$\langle\mathbf{S}\rangle=\big|\operatorname{Re}\big\{\mathbf{E}\times\mathbf{H}\big\}\big|=\frac{1}{2}\sqrt{\frac{\mu_0}{\epsilon_0}}\bigg(\frac{I\Delta\ell}{2\lambda}\bigg)^2\frac{\sin^2\theta}{r^2}$$

Such that the time-averaged power is given by integrating over the Poynting flux, to this extent we find,

$$\langle P\rangle=\frac{\pi}{3c\epsilon_0}\bigg(\frac{I\Delta\ell}{\lambda}\bigg)^2$$

Now if we consider a varying current, $\langle P\rangle$ will be smaller by a factor $4$.

The length of a dipole antenna is typically half a wavelength (i.e. $\ell=\lambda/2$), because the standing wave is highest at the centre when each half of the dipole is $\lambda/4$ long.

## Radiation Resistance

For a resistor with resistance $R$, 

$$\langle P_\text{heat}\rangle=\frac{1}{2}I_0^2 R$$

For some time-varying current $I=I_0\cos\omega t$. We define that radiation resistance of an antenna as,

$$R_\text{rad}=\frac{2\langle P_\text{rad}\rangle}{I_0^2}$$

We want the radiation resistance to be high, as it is defined as the resistance at the antenna feed point that is due to EM radiation. For the short dipole ($\Delta\ell\ll\lambda$) with $I=I(t)$,

$$\langle R_\text{rad}\rangle = \frac{\pi}{6 c\epsilon_0}\bigg(\frac{\Delta\ell}{\lambda}\bigg)^2$$

Note: a larger dipole is a better receiver. The radiation resistance is related to the geometry of the antenna, the ohmic resistance related to the material of the antenna, and the impedance of free space ($Z_0=1/c\epsilon_0\approx 120\pi\ \Omega$). We can define the time-averaged input power as a combination of the radiation resistance ($R_\text{rad}$) and the resistance of the antenna ($R_\text{load}$).

$$P_\text{in}=\langle VI\rangle=\frac{V_0^2}{2(R_\text{rad}+R_\text{load})}$$

Therefore, the power transferred to the load is,

$$P_\text{load}=\langle I^2 R_\text{load}\rangle$$

Such that the power re-radiated by the antenna is,

$$P_\text{rad}=\langle I^2 R_\text{rad}\rangle$$

The maximum power transferred to the load (our antenna) is when $R_\text{rad}=R_\text{load}$, found via setting $dP_\text{load}/dR_\text{load}=0$. In this case half of the power into the system is re-radiated.

## Antenna Power Patterns

The normalized power pattern of a simple short dipole is,

$$P_n(\theta, \phi)=\frac{1}{P_\text{max}}P(\theta,\phi)$$

We define the *power gain* $G(\theta, \phi)$, the power transmitted per unit solid angle in the direction $(\theta, \phi)$ divided by the power transmitted per unit solid angle from an isotropic antenna with the same total power. We often express the gain in decibells, $G_\text{dB}=10\log_{10} G$.

For a lossless isotropic antenna, by conservation of energy, the average gain should be unity. For such an antenna the gain depends only on the angular distribution of radiation from that antenna.

The higher the gain, the narrower the radiation pattern (the directivity),

$$\Delta\Omega = \frac{4\pi}{G_\text{max}}$$

Where $\Delta\Omega$ is the solid angle over which the antenna is most sensitive.

## Effective Collecting Area

The receiving counterpart of the transmitting gain is the effective collecting area, defined as the product of the geometric area and the incident spectral power per unit area.

$$A_e\equiv \frac{P_\nu}{S_\text{(matched)}}=\eta_aA_g$$

where $\eta_a$ is the aperture efficiency and $A_g$ is the geometric area. Any antenna with a single output measures only one polarization. $E$-fields perpendicular to the antenna wires do not produce currents in the antenna. To *collect* both polarizations, a pair of crossed dipoles are needed.

Therefore,

$$S_\text{(matched)}=\frac{S_\nu}{2}$$

Recall that,

$$P_\nu=kT$$

Such that, using the R-J equation, we obtain,

$$\int_{4\pi} A_e(\theta, \phi)\,d\Omega=\lambda^2$$

Meaning the average collecting area will equal,

$$\langle A_e\rangle = \frac{\lambda^2}{4\pi}$$

Meaning the effective collecting area is independent of the antenna environment, so this is valid for any type of radiation. In case of an isotropic antenna,

$$A_e(\theta, \phi)=\langle A_e\rangle$$

Therefore, dipoles are used at long wavelengths. To get a decent collecting area of short wavelengths, we need many dipoles. 

## Reciprocity Theorems

- Strong: If a voltage is applied to the terminals of an antenna A and the current is measured at the terminals of another antenna B, then an equal current (in both amplitude and phase) will appear at the terminals of A if the same voltage is applied to B. Note that, for any antenna pair, $I_AV_A=I_BV_B$.
- Weak: The power pattern of an antenna is the same for transmitting and receiving. 
    $$G(\theta, \phi)\propto A_e(\theta,\phi)$$ 
    For an isotropic antenna we know that $G(\theta, \phi)=1$ and $A_e(\theta,\phi)=\langle A_e\rangle$, such that
    $$A_e(\theta, \phi)=\frac{\lambda^2}{4\pi}G(\theta, \phi)$$

## Antenna Temperature

The power output from a receiving antenna,

$$T_A\equiv \frac{P_\nu}{k}=\frac{A_eS_\nu}{2k}$$

for an unpolarised source. Using this measure we can calibrate the antenna and compare it to the source signal, receiver noise, or atmospheric noise. More generally,

$$T_A=\frac{A_e}{2k}\int I_\nu(\theta,\phi)\,d\Omega$$

We can also define the *beam area* $\Omega_A$, the area through which all the power radiated by the antenna would stream if $P(\theta, \phi)$ maintained its maximum value over the solid angle and is zero everywhere else. Such that the *beam solid angle* is,

$$\Omega_A\equiv\int_{4\pi}P_n(\theta,\phi)\,d\Omega$$

The power received is also a function of the power pattern, such that the true antenna temperature is,

$$T_A=\frac{A_e}{2k}\iint I_\nu(\theta,\phi)P_n(\theta,\phi)\,d\Omega$$

Where,

$$P_n(\theta,\phi)=\frac{G(\theta,\phi)}{G_\text{max}}$$

We define the following two elements of the beam:

- Main beam solid angle: the area containing the principle response out to the first zero.
    $$\Omega_{\text{MB}}=\int_\text{MB}P_n(\theta,\phi)\,d\Omega$$
    with efficiency (the so-called *main beam efficiency*),
    $$\eta_B=\frac{\Omega_\text{MB}}{\Omega_A}$$
- Side-lobes: areas outside the principle response that are non-zero.

