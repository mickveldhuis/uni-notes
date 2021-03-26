# Chapter 3

## Measurement System Modeling

We consider an input signal $F(t)$ and a measurement system operation with initial conditions $y(0)$, which produces an output $y(t)$.

A general model consists of an $n$th-order linear ordinary differential equation in terms of a general output signal represented by $y(t)$ and subjected to a general input, represented by the forcing function $F(t)$.

$$a_n\frac{d^n y}{dt^n}+\dots+a_0 y=F(t)$$

where 

$$F(t)=b_m\frac{d^m x}{dt^m}+\dots+a_0 x$$

The coefficients represent the physical system parameters, with generally $m\le n$.

## Zero-order Systems

Zero-order systems are represented by,

$$a_0y=F(t)$$

I.e. the output and forcing function are linearly related,

$$y(t)=KF(t)\ \ \text{where}\ K=\frac{1}{a_0}$$

Noting that $K$ is the static sensitivity, or rather the steady gain of the system. It is the slope of the static calibration curve, i.e. $K=dy/dx|_x$.

In practical scenarios, the zero-order system concept is used to model non-time-dependent measurement system responses to static inputs. It models appropriately any system during a static calibration.

When dynamic inputs are involved, the zero-order model is only valid at static equilibrium.

## First-order Systems

First-order systems are modeled by,

$$a_1\dot{y}+a_0y=F(t)$$

These could, for instance, be measurement systems that contain storage elements, they do not respond instantaneously to changes in input. We generally write the differential equation in terms of a time constant and static gain,

$$\tau\dot{y}+y=KF(t)$$

where $\tau=a_1/a_0$ and $K=1/a_0$.

### Step function input

The step function is defined to be zero ($AU(t)=0$) below some time $t<0$ and for $t\ge 0$, $AU(t)=A$. A step function describes a sudden change in the input signal. 

If we consider $y(0)=0$, i.e. zero initial conditions, and the force function $F(t)=AU(t)$, we can solve the differential equation to obtain:

$$y(t)=KA+(y_0-KA)e^{-t/\tau}$$

where the first term describes the steady-state response and the latter the transient response. The steady-state response is such that for $t\rightarrow\infty$, $y(t)\rightarrow KA$.

### Error fraction

The error fraction of the output signal is defined as $\Gamma(t)$,

$$\Gamma(t)=\frac{y(t)-y_\infty}{y_0-y_\infty}$$

Which for a step input is,

$$\Gamma(t)=e^{-t/\tau}$$

It decreases from a value of 1 and approaches a value of 0 with increasing $t/\tau$. A 100% error fraction implies that the system has responded 0% to the input. So an error fraction of 0% implies that the system has responded fully to the input change. 

We can also define the _rise time_, as the moment that the system has responded to 90% of the input, i.e. $\Gamma(t)=0.1$.

### The time constant

The time constant $\tau$ is a measure of how quickly a first-order measurement system responds to a change in input. A smaller time constant implies a shorter time between the application of the input and the full response.

This constant can be determined from the relation $\ln\Gamma=-t/\tau$, i.e. in plotting $\ln\Gamma$ as a function of the time $t$, with slope $-1/\tau$.

### Periodic input signals

When periodic inputs are applied to the first-order system, the input signal frequency has an important influence on measuring the system time response and it affects the output signal.

We consider an input $F(t)=A\sin(\omega t)$,

$$\tau\dot{y}+y=KA\sin(\omega t)$$

The general solution is,

$$y(t)=Ce^{-t/\tau}+\frac{KA}{\sqrt{1+(\omega \tau)^2}}\sin\big[\omega t - \arctan(\omega \tau)\big]$$

The left most term is the transient periodic response and the second term is the steady periodic response. So when $t\rightarrow\infty$,

$$y(t)\rightarrow \frac{KA}{\sqrt{1+(\omega \tau)^2}}\sin\big[\omega t - \arctan(\omega \tau)\big]$$

Note that the output frequency is the same as the input frequency, however, the output amplitude now depends on the input signal. We define,

$$B(\omega)=\frac{KA}{\sqrt{1+(\omega \tau)^2}}$$

and

$$\phi(\omega)=- \arctan(\omega \tau)$$

Such that the solution can be written as,

$$y(t)=Ce^{-t/\tau}+B(\omega)\sin\big[\omega t + \phi(\omega)\big]$$


Furthermore, we can define a time delay related to the phase shift, $\beta=\phi/\omega$. Note that $\beta$ is generally negative, indicating a delay between the output and input. In this manner we can discuss the frequency response of the output response. 

The magnitude ratio $M(\omega)$ is the defined as the ratio between the output and input signal,

$$M(\omega)=\frac{B}{KA}=\frac{1}{\sqrt{1+(\omega \tau)^2}}$$

When the magnitude ratio is one, the phase approaches zero and time delay as approaches zero as well. Conversely, if $\omega\tau$ is larger, the amplitude is small and the time delay is large as well.

Note that we also define a _frequency bandwidth_, the frequency band over which,

$$M(\omega)\ge 0.707$$

or in decibels,

$$-3\ \text{dB}\le M(\omega)\le 0\ \text{dB}$$

We define the dynamic error,

$$\delta(\omega)=M(\omega)-1$$

It is a measure of the inability of a system to adequately reconstruct the amplitude of the input signal for a particular input frequency. To minimize the dynamic error we try to obtain a magnitude ratio close to unity. However, this is essentially not possible in reality. The frequency response of a measurement system is found physically by a dynamic calibration.

## Second-order Systems

Examples of 2nd order systems include systems with some acceleration, for instance in case of a pressure inducer, present in e.g. microphones.

The system is modeled by,

$$a_2\ddot{y}+a_1\dot{y}+a_0y=F(t)$$

where the parameters are physical parameters describing the system. Note that we define the parameters,

$$\omega_n=\sqrt{\frac{a_0}{a_2}}$$

the natural frequency and the damping ratio (damping is the property of the system that enables it to dissipate energy internally),

$$\zeta=\frac{a_1}{2\sqrt{a_0a_2}}$$

and the static sensitivity,

$$K=\frac{1}{\omega_0}$$

Such that the differential equation can be written as,

$$\frac{1}{\omega_n^2}\ddot{y}+\frac{2\zeta}{\omega_n}\dot{y}+y=KF(t)$$

### Homogeneous solution

The solutions to the characteristic equation of the ODE is,

$$\lambda_{1,2}=-\zeta\omega_n\pm\omega_n\sqrt{\zeta^2-1}$$

Therefore, three solutions are possible:

1. Underdamped ($0\le\zeta<1$): the transient response will be oscillatory,
    $$y_h(t)=Ce^{-\zeta\omega_n t}\sin\bigg(\omega_n\sqrt{1-\zeta^2 t}+\phi\bigg)$$
2. Critically damped ($\zeta=1$): the demarcation between a oscillatory and non-oscillatory transient response,
    $$y_h(t)=C_1e^{\lambda_1 t}+C_2te^{\lambda_2 t}$$
3. Overdamped ($\zeta>1$):  the transient response will not oscillate,
    $$y_h(t)=C_1e^{\lambda_1 t}+C_2e^{\lambda_2 t}$$

**Note**: these homogeneous solutions determine the transient response of a system.

### Step function response

A step function can be applied to determine the general behaviour and speed at which the system will respond to a change in input. Therefore, considering $F(t)=AU(t)$, we obtain three solutions for an underdamped, critically damped, and an overdamped system:

$$y(t)=KA-KAe^{-\zeta\omega_n t}\bigg[\frac{\zeta}{\sqrt{1-\zeta^2}}\sin\bigg(\omega_nt\sqrt{1-\zeta^2}\bigg)+\cos\bigg(\omega_nt\sqrt{1-\zeta^2}\bigg)\bigg],$$

$$y(t)=KA-KA\big(1-\omega_n t\big)e^{-\omega_n t},$$

$$y(t)=KA-KA\bigg[\frac{\zeta+\sqrt{\zeta^2-1}}{2\sqrt{\zeta^2-1}}e^{(-\zeta+\sqrt{\zeta^2-1})\omega_n t}-\frac{\zeta-\sqrt{\zeta^2-1}}{2\sqrt{\zeta^2-1}}e^{(-\zeta-\sqrt{\zeta^2-1}) \omega_n t}\bigg]$$

where we used zero initial conditions. Note that for an underdamped system, the transient response is oscillatory. A critically damped system shows both oscillatory and non-oscillatory behaviour. In an overdamped system no oscillatory behaviour is present.

For the underdamped system we define a period $T_d$, of the oscillations of the system,

$$T_d=\frac{2\pi}{\omega_d}$$

where

$$\omega_d=\omega_n\sqrt{1-\zeta^2}$$

is called the ringing frequency (free oscillation frequency of a system's displacement from its equilibrium). Note that the ringing frequency is independent of the input signal. _(The experimental determina-
tion of the ringing frequency associated with underdamped systems is performed by applying a step
input to the second-order measurement system and measuring the response.)_

The duration of the transient response is controlled by the time constant, now defined as,

$$\tau=\frac{1}{\zeta\omega_n}$$

The system reaches the steady-state solution sooner when the time constant is smaller. 

For the second order system we can also define the rise time, to be 90% of the time necessary to reach $(KA-y_0)$. Decreasing the damping ratio reduces the rise time. Severe ringing frequencies associated with very lightly damped systems delays the time to achieve a steady value compared to systems with higher damping.

The time for a measurement system's oscillations to settle within $\pm10\%$ of the steady-state value is defined as the settling time.

### Periodic Response

The output due to a sinusoidal input $F(t)=A\sin(\omega t)$ is given by,

$$y(t)=y_h(t)+\frac{KA\sin(\omega t + \phi(\omega))}{\sqrt{\big[1-(\omega/\omega_n)^2\big]^2+\big[2\zeta\omega/\omega_n\big]^2}}$$

where 

$$\phi(\omega)=\arctan\bigg[-\frac{2\zeta\omega/\omega_n}{1-(\omega/\omega_n)^2}\bigg]$$

Note that the steady-state solution is frequency dependent and given by,

$$y_\infty=B(\omega)\sin[\omega t + \phi(\omega)]$$

We can define the magnitude ratio for a 2nd order system as,

$$M(\omega)=\frac{1}{\sqrt{\big[1-(\omega/\omega_n)^2\big]^2+\big[2\zeta\omega/\omega_n\big]^2}}$$

For an ideal system the magnitude ratio approaches unity and the phase shift goes to zero. In reality generally, the magnitude ratio tends to approach zero if the frequency increases, and the phase shift goes to $-\pi$.

For a system without damping, $\zeta=1$, which don't exist in reality, $M\rightarrow\infty$ and $\phi\rightarrow -\pi$ when $\omega\ge \omega_n$.

Peak resonance occurs in underdamped systems when the input frequency reaches the natural frequency.

$$\omega_R=\omega_n\sqrt{1-2\zeta^2}$$

Resonance behaviour results in a considerable phase shift, is very non-linear, and results in distortion of the signal. Operating at frequencies in the resonance band is confusing and could damage the system. Note that systems where $\zeta>1/\sqrt{2}$, do not resonate. When $\omega/\omega_n\ll 1$, the magnitude ratio is close to 1 and the phase shift is close to 0. So when the input frequency is much smaller than the output frequency the output frequency the signal is passed with very little alterations. This is the case for,

$$-3 \text{dB} \le M(\omega)\le 3\ \text{dB}$$

the so-called transmission bandwidth. We can also consider the filter band, for which $M(\omega)\le -3\ \text{dB}$. In this case $M\approx 0$ and $\phi\approx -\pi$. This filter band essentially removes undesirable features from a desirable product. I.e. amplitudes of the input signal corresponding to these frequencies are surpressed.

## Transfer Functions

The transfer function defined the mathematical operation that the measurement system performs on the input signal $F(t)$ to yield the response of the system. If we consider a first-order system, with input $F(t)$, initial values $y_0=y(t=0)$, being operated on by some function $G(s)$ (in Laplace space) then the Laplace transform of the system is,

$$Y(s)=\frac{KF(t)+y_0}{\tau s+1}$$

with is written as $Y(s)=G(s)[KF(s)+Q(s)]$, with $G(s)=(\tau s+1)^{-1}$ and $Q(s)$ being the initial state of the system.

We can find the system frequency response by evaluating $G(s=i\omega)$, noting that,

$$G(i\omega)=M(\omega)e^{i\phi(\omega)}$$

## Multiple-function Inputs

When using models that are linear, such as ordinary differential equations subjected to inputs that are linear in terms of the dependent variable, the principle of superposition of linear systems applies in the solution of these equations. The principle of superposition states that a
linear combination of input signals applied to a linear measurement system produces an output signal that is simply the linear addition of the separate output signals that would result if each
input term had been applied separately. Because the form of the transient response is not affected by the input function, we can focus on the steady response. In general, we can write that if the forcing function of a form,

$$F(t)=A_0+\sum_{k=1}^\infty A_k\sin\omega_k t$$

is applied to a system, then the combined steady response will have the form,

$$y_\text{ss}=KA_0+\sum_{k=1}^\infty B(\omega_k)\sin\big[\omega_k t+\phi(\omega_k)\big]$$

where $B(\omega_k)=KA_kM(\omega_k)$.

## Coupled Systems

The overall static sensitivity of a coupled system, containing $H$ interconnected devices, is given by,

$$K=K_1K_2\cdots K_H$$

similarly the overall system magnitude is the product,

$$M(\omega)=M_1(\omega)M_2(\omega)\cdots M_H(\omega)$$

with an overall phase shift of,

$$\phi(\omega)=\phi_1(\omega)+\dots+\phi_H(\omega)$$
