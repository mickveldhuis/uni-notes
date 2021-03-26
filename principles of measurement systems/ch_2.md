# Chapter 2

## Signal analysis

We can consider multiple types of signals:

- Analog signal: a signal continuous in time. Any value within the operating range is available.
- Discrete (time) signals: information about the magnitude of the signal is available only at discrete points in time.
- Digital signal: signals only exist at discrete values in time. The magnitude is also discrete (i.e. the magnitude is quantized).

An Analog-to-Digital (ADC or A/D) is a solid-state device that converts an analog voltage signal to a binary number representation. Note, however, that the ADC has a limited resolution. The range of voltages creates the quantization levels and establishes the range. The quantization assigns a single number to represent a range of magnitudes of an analog signal.

We can classify signals as either static or dynamic, i.e. not varying with time or varying with time. Often a signal is periodic. A steady periodic signal repeats in regular intervals in time. Simple periodic functions contain only a single frequency and amplitude, whereas complex periodic signals contain a multitude of frequencies and amplitudes.

### Mean & RMS Values

The mean $\bar{y}$ describes the DC component of the signal, and is defined as,

$$\bar{y}=\frac{1}{t_2-t_1}\int_{t_1}^{t_2}y(t)\,dt$$

The RMS value of a signal on the other hand tells something about the AC component of the signal, it is defined as

$$y_\text{rms}^2=\frac{1}{t_2-t_1}\int_{t_1}^{t_2}y(t)^2\,dt$$

or for a discrete signal as,

$$y_\text{rms}^2=\frac{1}{N}\sum_{i}y_i^2$$


By [analogy](https://www.raeng.org.uk/publications/other/8-rms), concerning currents and voltages:

> The RMS value is the effective value of a varying voltage or current. It is the equivalent steady DC value which gives the same effect. For example, a lamp connected to a 6V RMS AC supply will shine with the same brightness when connected to a steady 6V DC supply.

### Periodic Signals

A periodic function is a function $y(t+T)=y(t)$ for some value $T$. A general form of such signals is,

$$y=A\cos\omega t+B\sin\omega t$$

which is a signal with period $T=2\pi/\omega=1/f$ and frequency $f=\omega/2\pi$. We can convert this to either a sine or cosine function,

$$y=C\sin(\omega t+\phi^*)$$

or

$$y=C\cos(\omega t-\phi)$$

where 

$$C^2=A^2+B^2,\ \ \phi=\arctan(B/A) \ \ \text{and}\ \ \phi^*=\arctan(A/B)$$

## Fourier Series

If we consider periodic functions, i.e. $y(t+T)=y(t)$, we can represent them as a sum of sines and cosines. 

$$y(t)=A_0+\sum_{n=1}^{\infty}\bigg[A_n\cos n\omega t+B_n\sin n\omega t\bigg]
$$

Note that the terms corresponding to $n=1$ are related to the fundamental frequency. The others ($n=2, 3, 4,\dots$) are called harmonics.

The coefficients are given by

$$A_0=\frac{1}{T}\int_{-T/2}^{T/2}y(t)\, dt, \ \ A_n=\frac{2}{T}\int_{-T/2}^{T/2}y(t)\cos n\omega t\, dt, \ \ B_n=\frac{2}{T}\int_{-T/2}^{T/2}y(t)\sin n\omega t\, dt$$

Which, similarly as for the lone sine and cosine terms can be written solely in terms of cosine or sine terms, but with an added phase term. Note, also, that if the function we consider if even, i.e. $f(-t)=f(t)$, then $B_n=0$ for all $n$. Conversely, if we consider an odd function, i.e. $f(-t)=-f(t)$, then $A_n=0$.

## Fourier Transform

In the limit that $T\rightarrow\infty$, the sum becomes an integral, and we obtain the so-called Fourier transform:

$$Y(\omega)=\int_{-\infty}^\infty y(t)e^{-i\omega t}\,dt$$

or rather in terms of the (cyclical) frequency $f$, using the substitution $\omega=2\pi f$. We consider the Fourier transform as a decomposition of $y(t)$ into amplitude versus frequency information. Conversely, we have the inverse Fourier transform,

$$y(t)=\int_{-\infty}^\infty Y(\omega)e^{i\omega t}\,dt$$

Note, $Y(f)$ can be thought of as having a magnitude and a phase:

$$Y(f)=|Y(f)|e^{i\phi(f)}=A(f)-iB(f)$$

where 

$$|Y(f)|=\sqrt{\Re[Y(f)]^2+\Im[Y(f)]^2}\ \ \text{and}\ \ \phi(f)=\arctan\frac{\Im[Y(f)]}{\Re[Y(f)]}$$

The amplitude expressed in frequency,

$$C(f)=\sqrt{A(f)^2+B(f)^2}$$

is called the amplitude spectrum. And 

$$\phi(f)=\arctan\frac{B(f)}{A(f)}$$

is called the phase spectrum.

## Discrete Fourier Transform

Generally the signal is sampled $N$ times every $\delta t$ seconds. Such that measurements are represented as $y(t)\rightarrow\{y(r\delta t)\}$, for $r=0,1,\dots, N-1$. And instead of a continuous Fourier transform, we would perform a discrete Fourier transform, defined as,

$$Y(f_k)=\frac{2}{N}\sum_{r=0}^{N-1}y(r\delta t)e^{-i 2\pi r k / N}$$

where $f_k=k\delta f$ (for $k=0, 1, 2, \dots, N/2-1$) and $\delta f=1/N\delta t$ is the frequency resolution. For instance, at $f=0\ \text{Hz}$, when $k=0$, 

$$Y(f_0)=\frac{1}{N}\sum_{r=0}^{N-1}y(r\delta t)$$

Only for $k=0$ we use $1/N$, which yields the DC value at 0 Hz. Note that this is the so-called half-transform, yielding $N/2$ discrete values of the Fourier transform.
