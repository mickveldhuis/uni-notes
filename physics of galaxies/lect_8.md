# Lecture 8: The Integrated Galaxy View

We generally study the integrated view of the galaxy, as we cannot resolve individual stellar populations for $z>0.3$. Note $z\approx 2$ is around 3 billion years ago.

## Galaxies in a blank field

If we look at high redshift ($z>0.3$) galaxies we tend to study multiple galaxies together. If we take these images containing thousands of galaxies, we estimate the redshift via a statistical treatment based on galaxy evolution.

## Galaxy physics from photometric measurements

### Galaxy photometry

The more point-like objects in your aperture are the more distant galaxies. We want to measure the light from each individual galaxy. To do so we measure the light encircled in an aperture (and subtract the background), this is done at multiple wavelengths (to measure light from different components).

### Dealing with different resolutions

Even if the resolution is the same, for instance the [PSF](http://web.ipac.caltech.edu/staff/fmasci/home/astro_refs/PSFtheory.pdf) could be different. To properly analyse these type of images one would need a theoretical model of the PSF.

### Galaxy color-magnitude diagrams

The fast majority of galaxies will lie in the so called *red sequence* (ellipticals) or *blue cloud* (mostly spirals). The green valley is a region in between the red and blue, which contains mostly stars that recently ... This is valid for $z\lessapprox1$, as at higher $z$ dust extinction will start to play a bigger role.

### SED: Spectral energy distribution

We measure the galaxy at (as many) different wavelengths (as possible). We for instance determine the AB magnitude. We can then construct various models, using among others the IMF. We construct the model assuming $z=0$, then fitting the model to the measured data we have to shift the model, thus obtaining the redshift.

Recall that the observed and emitted wavelengths are related via

$$\lambda_{\text{o}}=(z+1)\lambda_{\text{e}}$$

### SED models

Synthetic models take into account the spectra of the individual stars, isochrones (the evolution on the MS), and the IMF. We generally assume a IMF, as it is not known for the fast majority of galaxies. Then you can determine the spectrum of a galaxy assuming a single stellar population (assuming all stars were born at the same time, at very high redshift). To form models of galaxies with more complicated star formation histories we combine models of single populations born at different times. We also need to know the chemical composition and the presence of dust. Synthetic models are generally from UV to NIR. Combining all this information one would obtain the CSP (combined stellar population). 

Emperical models are ...

### Expected photometry from templates

If you want to obtain the magnitudes from the observed flux, you'd need to solve

$$f_\nu^{\text{band}}=\frac{\int_0^\infty f_\nu (\lambda)T(\lambda)\,d\lambda}{\int_0^\infty T(\lambda)\,d\lambda}$$

Note $T(\lambda)$ is the transmission profile/curve of the filter.

## Dust in galaxies

Dust was more important in the cosmic past than it is nowadays. As the star formation rates are lower now, than in the past. 

## Radio

Radio emission is due to synchrotron acceleration as a result of SNs, also an indicator of (new) star formation.

## Galaxy physics from spectroscopy

The spectra of star forming galaxies are characterized by the presence of emission lines (due to the presence of gas). 

The spectra of passive galaxies (i.e. no/negligible new star formation takes place) only have absorption lines. 

AGNs can be classified as type I or type II. Type I spectra contain very pronounced broadening of specific lines. But note that not all AGNs show these broadened lines, which might we due to the orientation of the galaxy wrt us.

### Multi-object spectroscopy

This is traditionally obtained with slits or fibres. This method could (1) be used for instance to calibrate your redshifts obtained via the photometric route (as photometry is *less expensive* than spectroscopy). (2) Provide a backbone for last scale structure studies. (3) Use it for studies of metallicities, which can only be done via spectroscopy.

### Spectral classification: BPT diagram 

These graphs plot the line ratios of various metals wrt H$\alpha$ and H$\beta$.

### Integral field spectroscopy

Various slices of the galaxy are passed through a spectrograph, constructing a data cube containing two spatial coordinates and a spectral dimension.
