# 5. Radiometers

## Basics

Recall that the noise temperature is defined as,

$$T_N=\frac{P_\nu}{k}$$

And the system temperature is equivalent to the total noise power from all sources referenced to the input of an ideal receiver connected to the output of a radio telescope.

$$P_\text{sys}=\sum_i P_i$$

and

$$T_\text{sys}=\sum_i T_i$$

These components $T_i$ include noise from the CMB, the target source, the atmosphere, losses at the receiver, the injected calibration system, and the receiver as a whole. Often the source is the smallest and the receiver noise dominates.

These receivers generate noise equivalent to a circuit consisting of an ideal noiseless receiver whose input is a resistor of temperature $T_\text{rec}$.

## Band Limited Noise

Band limited noise is due to the voltage at the output of a radio telescope, which is the sum of noise voltages from many independent random contributions. The central limit theorem states that the amplitude distribution tends to a Gaussian.

The *Nyqvist-Shannon sampling theorem* states that any signal (even if we just consider noise) of limited bandwidth $\Delta\nu$ and duration $\tau$ can be represented by a minimum of $2N$ independent samples.

## A Simple Total-Power Radiometer

This measures the time-averaged power of the input noise in some well-defined RF (radio frequency) range,

$$\bigg[\ \nu_\text{RN}-\frac{\Delta \nu_\text{RN}}{2},\ \ \nu_\text{RN}+\frac{\Delta \nu_\text{RN}}{2}\bigg]$$

where $\Delta_\text{RF}$ is the receiver bandwidth. 

The simplest radiometer consists of four stages in series:

1. An ideal lossless bandpass filter that passed input noise only in the desired frequency range. Now the voltages are no longer random. It now resembles a sine wave of frequency $\sim \nu_\text{RF}$, whose amplitude fluctuates on time scales $\Delta\tau\approx\Delta\nu_\text{RF}^{-1}$. Note that $\Delta\nu_\text{RF}<\nu_\text{RF}$.
2. An ideal *square-law detector* whose output voltage is proportional to the square of its input voltage. Suppose $V_\text{in}\approx\cos(2\pi\nu_\text{RF}t)$, the output is $V_\text{out}\propto\cos^2(2\pi\nu_\text{RF}t)$, those mean is the average power of the input signal.
3. An integrator, which smoothes out the rapidly fluctuating detector output. It is a rapidly varying component at frequencies $2\nu_\text{RF}$. Any unwanted rapid variations can be suppressed by taking the arithmetic mean of the detected envelope over some timescale, integrating or averaging the detector output.
4. An recording device, such as a voltmeter to measure and record the smoothed voltage.

## The Radiometer Equation

Our ability to measure a signal is dependent on the noise properties of our complete system. The variations are estimated by,

1. In a time interval $\tau$ there are a minimum $N=2\Delta\nu\tau$ independent samples of the total noise power $T_\text{sys}$.
2. The uncertainty in the noise power is about $\sqrt{2} T_\text{sys}$.
3. The rms error in the average of $N\gg 1$ independent samples is reduced by the factor $\sqrt{N}$.

Such that the rms uncertainty in kelvin is given by,

$$\sigma_T\approx \frac{T_\text{sys}}{\sqrt{\Delta\nu_\text{RF}\tau}}$$

Typically the system temperature is significantly larger than the source temperature. Therefore we need the rms uncertainty in the system temperature to be as low as possible. We could, for instance, increase the observing bandwidth, observe longer, or decrease the receiver temperature.

The SNR of our target source is,

$$\frac{S}{N}=\frac{T_\text{source}}{\sigma_T}$$

The rms uncertainty can be expressed in terms of the system equivalent flux density (SEFD),

$$\text{SEFD}=\frac{2k T_\text{sys}}{A_e}$$

to obtain the rms uncertainty in Jansky. It is a good way to compar ethe sensitivity of telescopes because it takes both the receiver system and the effective area into account.

In terms of flux density the ideal radiometer equation is,

$$\sigma_{S_\nu}=\frac{2k T_\text{sys}}{A_e\sqrt{\tau\Delta\nu}}=\frac{\text{SEFD}}{\sqrt{\tau\Delta\nu}}$$

## Coherent Total Power Radiometers

Typical coherent receivers preserve phase information. Most practical radiometers systems are heterodyne receivers. In which a mixer (after an amplifier) multiplies the RF signal by a sine wave of a frequency $\nu_\text{LO}$ of the Local Oscillator.

1. Amplifiers: increase the signal before further processing. They need to have low internal noise, large fractional bandwidths ($\Delta\nu/\nu$), linearity, gain stability. The amplifier gain is the ratio between the input and output power,
    $$G=\frac{P_\text{out}}{P_\text{in}}$$
    Typically we need amplification of an order $\sim 100\,\text{dB}$, most often multiple amplifiers are used. Such that the total gain is given by,
    $$G=\prod_iG_i$$
    Note that each of these amplifiers add (temperature) noise to the system,
    $$T_\text{eq}=T_1+\frac{T_2}{G_1}+\frac{T_3}{G_1G_2}+\dots$$
    So, given that the gains are generally large, the noise is dominated by the first amplifier. Note that lossy devices (mixers and filters) have $G<1$. Therefore, they are often proceeded with another amplifier.
2. Mixers: change (typically lower) the frequency of the received emission. This is useful to (1) avoid feedback of amplified signals back into the ront end, (2) choose a frequency which is easier to deal with, considering the amplifiers/digitizers. The process mixes the RF signal with the sine wave from the Local Oscillator, producing a (known) phase shift. This adds a small amount of noise, but the signal is at a new intermediate frequency (IF), $\nu_\text{IF}=\nu_\text{RF}\nu_\text{LO}$. The upper IF and higher harmonics can be removed using a low pass filter, leaving only the lower IF. Such that we can split the spectral window into multiple IFs.
3. Filters: limit the frequencies passing through the system, or change the phase of the input. Some examples are
    - A band pass filter: allow frequencies between two frequencies.
    - A low pass filter: only allow frequencies below some frequency.
    - A high pass filter: only allow frequencies above some frequency.
    - A band stop filter: eliminate frequencies between two frequencies.
    - An all pass filter: allows all frequencies, but shifts the phase.
4. Digitalization: an *analog-to-digital (A/D) converter* converts the analog input into a digital output. I.e. convert voltages to bits. Note that this conversion results in some loss of the signal. However, a 2-bit system already allows for 90% of the signal to be reconstructed. The number of bits used to describe the analog input needs to be as low as possible, without loss of information. E.g. LOFAR uses 16-bits, JVLA uses 3 and 8-bits. The sampling must satisfy the Nyqvist-Shannon theorem.

## Receiver Calibration

Measuring the receiver temperature is needed to determine the noise power scale at the receiver input. For coherent receiver systems, this requires the noise temperature increment $\Delta T$ at the receiver input to be related to the receiver output power ($\Delta z$).

This is done by connecting two or more known power sources, typically matched resistive loads of known temperature to the system. The receiver input is related to the receiver output ($z$) via the receiver gain $G$,

$$z_L=(T_L+T_R)G$$

and

$$Z_H=(T_H+T_R)G$$

giving

$$T_R=\frac{T_H-T_Ly}{y-1}$$

where $T_R$ is the receiver temperature and,

$$y=\frac{z_H}{z_L}$$

This calibration method assumes that the receiver is a linear power measuring device. And we assume that the gain is close to constant in time.

## Limitations to the Radiometer Equation

1. Gain instability: the ratio of the input to the output power (i.e. the gain) might fluctuate over time due to changes in the system. If the gain changes by some amount $\Delta G$, 
    $$\frac{\Delta T}{T_a+T_\text{rec}}=\frac{\Delta G}{G}$$
    The variations due to noise and gain changes are random processes, therefore,
    $$\sigma_\text{total}^2=\sigma_\text{noise}^2+\sigma_G^2$$
    Such that we obtain a practical total-power radiometer equation,
    $$\sigma_T\approx T_\text{sys}\bigg[\frac{1}{\Delta_\text{RF}\tau}+\bigg(\frac{\Delta G}{G}\bigg)^2\bigg]^{1/2}$$
    Astronomical signals are typically $10^{-4}$ of the total system temperature. Therefore, we need to make sure that the gain variations are similarly small. To that extent we need to calibrate very often.
2. Atmospheric fluctuations: fluctuations in atmospheric emission also add to the noise in the output of a simple receiver. This effect (i.e. the fluctuations in receiver gain and atm. emission) can be minimized by observing two parts of the sky by two different feeds. There's a switch which switches between which of the two feeds is used. This is called [Dicke Switching](http://www.radiosky.com/dicke.html). The disadvantage of this method is that, to reach the same noise level, observations take twice as long. Because half of the time is spent off-source.
3. Source confusion: single-dish telescopes have large collecting areas, but relatively poor angular resolution at long wavelengths. Sky-brightness fluctuations caused by faint sources that enter the beam are called *confusion*. We consider the rms confusion $\sigma_c$ for specifying the width of the confusion distribution. The confusion noise can be minimized by decreasing the angular resolution.
4. Baseline ripples: for spectral line observations, the signal from the receiver and bright sources will get reflected between the receiver and reflector, which could cause ripples (a standing wave) in the frequency response of the radio telescope. We can minimize the effects of the ripple by shifting the focus by $\pm\lambda/8$, observing a calibrator source and dividing out the ripple, and/or use an offset gregorian reflector (as there is essentially no ability for standing waves to form between the receiver and reflector).

## Multi-beam Systems

We can include multiple single pixel receivers. This is useful to:

1. Increase the effective field-of-view of the telescope. Each feed samples a different portion of the sky, with the same solid angle. useful for surveys with large telescopes.
2. Can help with calibration, since multiple feeds see a different part of the sky.

## Incoherent Receivers

Incoherent receivers don't maintain the phase information. An example is a bolometer, mainly used at mm and sub-mm wavelengths due to heterodyne receivers being comparatively expensive.

### Bolometer radiometers

These use the varying resistance $R$ of a material as a function of temperature $T$, to measure the intensity of the incoming radiation. They are broadband ($\sim 100$ GHz) systems, due to the thermal effect being nearly independent on the frequency.

Essentially, the radiation from our source $P_0$ will change the temperature $\Delta T$ of a material coupled to a heat sink of temperature $T_0$. From energy balance, we can relate the thermal capacitance $C$ and thermal conductance $G$ via,

$$C\frac{d\Delta T}{dt}+G\Delta T=P$$

For a steady flow,

$$\Delta T=\frac{P}{G}$$

If the power source is switches off, then the temperature after some time is,

$$\Delta T=\frac{P}{G}\exp\bigg(-\frac{t}{\tau}\bigg)$$

where $\tau=C/G$ is the thermal time constant. Generally,

$$P=P_0\exp(i2\pi\nu t)$$

Such that,

$$\Delta T=\frac{P_0\exp(i2\pi\nu t)}{G(1+i2\pi\nu\tau)}$$

The noise is dominated by the photon noise from te incoming radiation. We define the noise equivalent power (NEP): the power required to fall on the detector in order to raise the output by an amount equal to the rms of the detector. Given that we know that $\Omega A=\lambda^2$, including the emissivity $\epsilon$ of the background radiation:

$$\text{NEP}_\text{ph}=2\epsilon k T_\text{bg}\sqrt{\Delta\nu}$$
