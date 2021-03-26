# Chapter 4

## Sampling, Statistics, and Systematic Errors

Sampling is obtaining a data set through repeated measurements of a variable under fixed operating conditions.

The statistical error is the (unknown) difference between the retained value and the true value:

$$x'=\bar{x}\pm u_{\bar{x}}\ (P\%)$$

where from left to right we have the true value, the most probable estimate, the uncertainty interval of the estimated value $\bar{x}$, and the probability level $P$.

Uncertainties are numbers that quantify the possible range of the effects of the errors. Systematic errors do not vary with repeated measurements and do not affect the statistics of the measurement.

## Histogram

A graphical way of grouping data is different ranges (bins), the height shows how many data points fall in the range. 

The total number of measurements $N$ is the sum of all the data in the bins,

$$N=\sum_{j=1}^K n_j$$

where $n_j$ is the number of times that a measured value assumes a value within a certain interval. Note we can convert a histogram to a frequency distribution via $f_j=n_j/N$. Note that the area under a frequency distribution (what we could consider as the PDF) is 100%, i.e. $\sum_j f_j=1$.

The interval number $K$ (i.e. answering the question: _how many bins should one use?_) is given by,

$$K=1.87(N-1)^{2/5}+1$$

For large $N$, we can use $K\approx \sqrt{N}$.

## Standard probability Distributions

- The normal distribution,
    $$p(x)=\frac{1}{\sqrt{2\pi\sigma^2}}\exp\bigg[-\frac{1}{2}\bigg(\frac{x-x'}{\sigma}\bigg)^2\bigg]$$
    where $x'$ is the true value, $x$ the measured value, and $\sigma^2$ the true variance of $x$. 68.26% of the data falls within $1\sigma$, 95.45% within $2\sigma$, and 99.73% within $3\sigma$.
- The Poisson distribution, for random events in time, describing observing $x$ events in time $t$, 
  $$p(x)=\frac{e^{-\lambda}\lambda^x}{x!}$$ 
  where $\lambda$ is given by $x'$.
- The binomial distribution, which described the number of occurrences, $n$, of a particular outcome during $N$ independent tests, each having the same probability $P$,
  $$p(n)=\bigg[\frac{N!}{(N-n)!n!}P^n(1-P)^{N-n}\bigg]$$

Given a PDF $p(x)$, the true value is given by,

$$x'=\int_{-\infty}^\infty xp(x)\,dx$$

and the true variance $\sigma^2$ is given by,

$$\sigma^2=\int_{-\infty}^\infty (x-x')^2p(x)\,dx$$

for a continuous variable $x$. For discrete data,

$$x'=\lim_{N\rightarrow\infty}\frac{1}{N}\sum_i x_i$$

and

$$\sigma^2=\lim_{N\rightarrow\infty}\frac{1}{N}\sum_i (x_i-x')^2$$

## Population Statistics

We consider the data to be normally distributed. The probability that we find a certain value on a certain interval is given by,

$$P(x'-\delta x\le x \le x'+\delta x)=\int_{x'-\delta x}^{x'+\delta x} p(x)\,dx$$

We define a transformation $\beta=(x-x')/\sigma$, with which we define the statistic $z_1$,

$$z_1=\frac{x_1-x'}{\sigma}$$

Such that we write,

$$P(-z_1\le \beta\le z_1)=\frac{1}{\sqrt{2\pi}}\int_{-z_1}^{z_1}e^{-\beta^2/2}\,d\beta=2\text{erf}(z_1)$$

Using these definitions we find that the probability that some $i$th measured value of $x$ will have a value $x'\pm z_1\times\text{something}$ is $2P(z_1)\times 100\%$. Which is written as,

$$x_i=x'\pm z_1\sigma\ \ (P\%)$$

## Finite-sized Datasets Statistics

Suppose we have $N$ measurements $x_i$, the sample mean is then given by,

$$\bar{x}=\frac{1}{N}\sum x_i$$

and the sample variance is given by,

$$s_x^2=\frac{1}{N-1}\sum(x_i-\bar{x})^2$$

For a normal distribution we can state that,

$$x_i=\bar{x}\pm t_{\nu,P}s_x\ \ (P\%)$$

where $t_{\nu,P}$ is a coverage factor (replacing the $z$-statistic) for finite length datasets and $\nu=N-1$ is the degrees of freedom in the sample variance (the $-1$ coming from the sample means). Note that the degrees of freedom is defined as the number of data points minus the number of previously determined statistical estimator (it indicates the number of independent values that can vary in an analysis without breaking any constraints). The $t$ variable is defined as,

$$t=\frac{\bar{x}-x'}{s_{\bar x}}$$

where $s_{\bar{x}}=s_x/\sqrt{N}$ is the standard deviation of the means. Which provides a measure of how well a measured mean value from a small sample size represents the true mean of the entire population. Such that we find that the range of possible values of the mean is given by 

$$x'=\bar{x}\pm t_{\nu,P}s_{\bar{x}}\ \ (P\%)$$

where $P$ is some probability level and $t_{\nu,P}s_{\bar{x}}$ is the confidence interval about the mean value with coverage factor $t$.

## Pooled Data

Suppose we have $N$ measurements of a large population under fixed conditions, and we duplicate this process $M$ times. Then the sample mean and variance will be slightly different each time.

## Hypothesis Testing

A hypothesis is a statement that something is believed true. A hypothesis test uses the tools of statistics to test it. E.g. we want to test whether a measured sample mean is a reasonable proxy for the population mean comparing information of the observed scatter in the data set against the assumed distribution of the population. Then, the null hypothesis is expressed as $H_0 ~:~ x=x_0$.

### Definition of a hypothesis test

1. Establish the null hypothesis.
2. Assign a level of significance, $\alpha$, to determine the critical values; this sets the rejection region. 
3. Calculate the observed value of the test statistic. 
4. Compare the observed test statistic to the critical values. If the observed statistic is in the rejection region, reject the null hypothesis; otherwise, do not reject.

### $z$-test

The $z$-test can be used when the population variance $\sigma^2$ is known. As test statistic we use the $z$-variable with $x'=x_0$,

$$z_0=\frac{\bar{x}-x_0}{\sigma/\sqrt{N}}$$

This statistic is evaluated against critical values of $z$ at a desired level of significance, $\alpha$, where $P(z)=1-\alpha$. For a two-tailed test the acceptance region is defined by $P(-z_{\alpha/2}\le z\le z_{\alpha/2})$, for one-tailed tests we use $P(-z_\alpha\le z_0)$ or $P(z_0\le z_\alpha)$. We then reject the null hypothesis if the value lies outside the acceptance region. Most often we find $\alpha=0.05$ is adequate.

### $t$-test

Similar to the $z$-test, but now we don't know the population variance and therefore we use the $t$-variable.

### $p$-value

The $p$-value reports the probability that the difference between two tested values is due only to random chance. It is the observed level of significance. A very small $p$-value indicates that effects other than random chance are influencing the variations in a sampling. To calculate the $p$-value, assume that the null hypothesis is true and compute the observed level of significance corresponding to the test statistic. If this p-value is less than $\alpha$, we reject $H_0$, otherwise we do not reject $H_0$.


## Chi-squared Distribution

The $\chi^2$-distribution defines the distribution of the sample standard deviation for many datasets, each with $N$ data points. For the normal distribution $\chi^2=\nu s_x^2/\sigma^2$, where $\nu=N-1$. We can use this distribution to test how well the sample variance estimates the population variance.

We define $P(\chi_\alpha^2)=1-\alpha$ and by computing $\chi^2$ given the available information and a $\chi_\alpha^2$ table we find the precision interval.

### Goodness-of-fit test

To test how well a set of measurements follow an assumed distribution function. To do this we apply the $\chi^2$-test, which would provide a measure of the discrepancy between the measured variation of a dataset and that due to chance as predicted by the density function.

Construct a histogram of $K$ intervals a from a dataset of $N$ measurements. The number of data points in each $j$th interval is $n_j$. Calculate the degrees of freedom in the variance for the dataset, $\nu=N-m$, where $m$ is the number of restrictions imposed. Lastly, estimate the number of occurrences $n_j'$ to be expected from the distribution function.

$$\chi^2=\frac{\sum_j(n_j-n_j')^2}{n_j'}$$

for $j=1,2,\dots,K$. The better a dataset fits the proposed distribution the lower the $\chi^2$ value, ideally it approaches unity. Too large a value will imply a rather dubious fit. Similarly, a value much smaller than unity is also not desirable. These problems might be due to too small error bars or measurement errors.

## Regression Analysis

Regression analysis can be used to establish a functional relationship between the dependent and independent variable. Generally assuming that the variation found in the measured variable is normally distributed.

### Least-Squares Regression

We want to fit an $m$th order polynomial, 

$$y_c=a_0+a_1 x +\dots+a_m x^m$$

for $m\le n-1$, where $n$ is the number of different values of the independent variables included in the analysis. In LS fitting we attempt to minimize the squared deviation,

$$D=\sum_{i=1}^N(y_i-y_{c_i})^2$$

The standard deviation, considering the pairs $(x_i,y_i)$, is given by,

$$s_{yx}=\sqrt{\frac{\sum(y_i-y_{c,i})^2}{\nu}}$$

where $\nu=N-(m+1)$. Note $s_{yx}$ is called the standard error of the fit, which is related to how closely a polynomial fits the data. Generally, the best order of polynomial fit to apply is one that makes logical physical sense. The confidence interval of a fit is defined (and approximated) as,

$$y_c\pm t_{\nu,P}\frac{s_{yx}}{\sqrt{N}}$$

This confidence interval is also called the *Scheffe band*.

### Correlation

We can define the correlation coefficient $r$, which provides a measure of the association between $x$ and $y$ as predicted by the form of the curve fit equation. Perfect correlation is marked by $r=\pm 1$, for $\pm0.9\le r\le \pm 1$ the fit can still be considered reliable.

The coefficient of determination $r^2$, indicates how well the variance in $y$ is account for by the fit.

## Outlier Detection/Rejection

Outliers may be the result of simple measurement glitches, such as a random spike in operating condition, or may reflect a more fundamental problem with test variable controls. If outliers are removed from a data
set, the statistics are recomputed using the remaining data.

We can detect outliers using Chauvenet's criterion, which identifies outliers having less than a $1/2N$ probability to occur. Consider the test statistic $z_0=|x_i-\bar{x}|/s_x$, then the data point is an outlier if,

$$1-2P(z_0)<\frac{1}{2N}$$

## The Number of Required Measurements

To find how many measurements $N$ are required to reduce the estimated value for random error in the sample mean to an acceptable level. We find,

$$N\approx\bigg(\frac{t_{\nu,P}s_x}{d}\bigg)^2\ \ (P\%)$$

where $d$ is the precision value, defined as,

$$d=\frac{t_{\nu,P}s_x}{\sqrt{N}}$$

## Monte Carlo Simulations / Methods

Monte Carlo experiments are a broad class of computational algorithms that rely on repeated random sampling to obtain numerical results. Using randomness to solve deterministic problems. 

These methods are mainly used for optimization, numerical integration, and generating samples from a PDF. In physics, e.g. simulating systems with many coupled degrees of freedom.

Consider a result $R$, a function of variables $x$ and $y$ (drawn from $p(x)$ and $p(y)$). Each iteration we randomly draw values $x_i$ and $y_i$, and compute $R_i$. After $\sim 10^5$ iterations be result approaches the true distribution of $R$. We generally continue until the standard deviation of $R$ converges to an asymptotic value, within for instance 1-5%.

The uncertainty of Monte Carlo results depends on the number of _histories_ (samples) $N$, with the error scaling as $1/\sqrt{N}$.
