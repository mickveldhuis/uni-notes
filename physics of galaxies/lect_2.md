# Lecture 2: Galaxy Morphological Classification 

## Galaxy morphology

Different inclinations will influence the galaxy morphology, on top of that the morphology will also be different in different wavelength bands. 

The morphology can be influenced by, for instance, mergers. Major mergers are mergers in which the two colliding galaxies have similar mass, whereas minor mergers consist of two galaxies with vastly different masses.

### The Hubble sequence

The hubble sequence is valid up to redshifts $z\approx 1$. 

![Hubble sequence](resources/hubblefork.gif)

## Types of Galaxies

### Elliptical galaxies

Ellipticals seem featureless, typically red (and they therefore radiate mostly in the NIR) due tot the abundance of old stars, and they are the most massive galaxies.

They can also show shells, which are probably due to mergers. Some contain a bit of dust, but not much.

Some also have an active black hole, i.e. BHs that accrete matter from the dark matter halo.

### Lenticular galaxies S0/SB0

They could be an intermediate stage between ellipticals and spirals.

### Spiral galaxies

They contain a disk of stars and gas in a spiral pattern. The bulge has old stars (population II stars), whereas the disk consist also of young stars (population I stars).

Basic characteristics:
- A flat disk
- A rotating disk
- Orbits which are almost in a single plane (the random motion of stars is small, the disk)

From Sa to Sc on the Hubble sequence:
- The bulge decreases
- Fractional amount of gas increases
- Contribution of young stars increases
- More patchy disk
- The spiral arms become more open

### Irregulars

Irregulars have a lot of stars formation and are therefore quite blue, they are also relatively small. Dwarf irregulars have a lot of HI gas, which might indicate that atomic gas can lead directly to stars formation.

### Ring galaxies

Ring galaxies might be the process of (nearly) head-on collisions with smaller galaxies.

## A Quantitative Analysis of Galaxies

### Light profiles of elliptical galaxies

The surface brightness of ellipticals can be characterized by

$$\mu(r)=\mu_e+8.33\bigg[\bigg(\frac{r}{r_e}\bigg)^{1/4}-1\bigg]$$

Note that $[\mu]=\text{mag/arcsec}^2$ and $r_e$ is the effective radius, i.e. the projected radius within which one-half of the galaxies light is emitted. 

### A general light profile

A more general model is given by the 3-parameter model, the [sersic profile](http://www-star.st-and.ac.uk/~spd3/Teaching/AS3011/AS3011_5.pdf) (see [Graham](https://ned.ipac.caltech.edu/level5/March05/Graham/Graham2.html) for more detail):

$$I(r)=I_e\exp\bigg(-b_n\big[(r/r_e)^{1/n}-1\big]\bigg)$$

where $n$ is the Sersic index. $n=1$ indicates a perfect disk and $n=4$ is the Vaucouleurs profile.

### CAS classification

A non-parametric classification scheme used for $z>1$ galaxies, i.e. it does not assume a functional form.

- Asymmetry: Measures the rotation of the image, $$A=\frac{|I-R|}{I}$$ 
- Smoothness: Measures how blurred the image is, $$\frac{I-B}{I}$$
- Concentration: Measures to what extent the light is concentrated or spread out, $$C=5\log\bigg(\frac{r_{80}}{r_{20}}\bigg)$$ where $r_{80}$ and $r_{20}$ denote respectively the radii where $80\%$ and $20\%$ of the light come from. High concentration implies high $C$.
