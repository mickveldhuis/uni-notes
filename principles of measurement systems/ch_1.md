# Chapter 1

## Basics

### Important measurement questions

- How can a measurement be devised so that the measurement provides unambiguous information we seek?
- How can a measurement system be used so that the engineer can easily interpret the measured data and be confident in their meaning?

### The measurement & measurement system

- Measurement: Act of assigning a specific value to a physical variable; the measured variable.
- Measurement system: Tool used to quantify the measured variable.

### Sensors and Transducers

A complete measurement system consists of both a sensor and a transducer.

- Sensor: the physical element to sense the variable being measured.
- Transducer: converts the sensed information into a detectable signal.

Subsequently, the *signal-conditioning stage* takes the signal from the transducer and modifies it to a desired magnitude. The *output stage* indicates or records the measured value (e.g. a display or a marked scale).

Additionally, a measurement system might include a *feedback-control stage*, which makes a decision regarding actions required to control the process.

## Experimental test plan

1. Parameter design plan: what do you want to answer, what parameters need to be measured, and which parameters influence the result?
2. System & tolerance design plan: select the equipment (i.e. what measurement device) and how accurate should the result be?
3. Data reduction design plan: How do you interpret the data, how will it answer your question, and how *good* is this solution?

## Variables

A *variable* is a physical quantity whose value influence the result. Which is either discrete or continuous in nature. There are variables that influence each other, dependent variables. And those that do not, independent variables. Furthermore, some variables are controlled, meaning they are kept fixed. *Extraneous variables* are variables that are not purposely manipulated or controlled during measurement but that do affect
the test result.

- Dependent: variable affected by changes in the value of one or more other variables. These variables are functions of independent variables.
- Independent: variable that does not influence other variables. These are generally kept constant or purposefully changed.
- Extraneous: variables that are not controlled during measurement, but do affect the result.

## Randomization

Refers to test strategies that apply the changes in independent variables in some random order. This is to neutralize effects that may not be accounted for in the test plan and therefore attempts to reduce or eliminate bias as much as possible.

### Noise & interference

*Noise* is the random variation in the volume of the measured signal, which increases data scatter. And, *interference* (an extraneous signal) imposes an undesirable/false trend on the measured signal. 

## Repetition & Replication

- Repetition: Repeated measurements of the same variable during any single test run or on a single batch. With the goal of improving the estimate of a measured variable.
- Replication: intended duplication of a set of measurements or a test. With the goal of quantifying the variation in the measured variable as it occurs between duplicate tests under similar conditions.

## Calibration

Calibration applies a known input value to a measurement system for the purpose of observing the system output value. These known values are called standards. 

### Static calibration

An input is applied to the system under calibration, and the output is recorded. The input value does not vary with time or space. Or an average is used.

We record a functional relationship between the input and output, this correlation can be used to establish an unknown input value based on the output.

We can define the *static sensitivity*, $K$, for any static input value $x_i$,

$$K(x_i)=\frac{dy}{dx}\bigg|_{x=x_i}$$

The static sensitivity is a measure relating the change in the indicated output associated with a given change in a static input.

### Dynamic calibration

The input value are time or space dependent. Again, we want to determine a relation between the input and output, however, now the input is dynamic (e.g. sinusoidal). 

### Range & Span

- The range of an instrument is specified by the lower and upper limit in which the measurement system is designed to operate.
- The span is the difference between that upper and lower limit. $r_i=x_\text{max}-x_\text{min}$ is the input span and $r_o=y_\text{max}-y_\text{min}$ is the output span.

### Resolution

The resolution is the smallest increment in the measured value that can be measured.

### Accuracy and error

The accuracy of a measurement is the closeness between the measured and true value. The accuracy is influenced by many factors, called errors. 

We can quantify those errors by,

$$e=\text{measured value} -\text{true value}$$ 

or in a relative sense as,

$$A= \frac{|e|}{\text{reference value}}\times 100\%$$

- Random errors: random variations in the measured value.
- Systematic errors: creates an offset between the mean and true value of the data set.

### Uncertainty

The uncertainty is a numerical estimate of the possible range of the error in the measured value. The uncertainty is caused by system calibration, measurement techniques, and the statistics of the dataset.

### Hysteresis error

The difference between the measured value between an upscale sequential test and a downscale sequential test.

$$u_h=y_\text{up}-y_\text{down}$$

Hysteresis is the dependence of the state of a system on its history, i.e. when the next measurement depends on the previous measurement.

### Linearity error

Many instruments are designed to achieve a linear relation between an applied static input and the output value. The linearity error describes how well a linear relation is achieved.

$$u_L=y(x)-y_L(x)$$

where $y_L(x)$ describes a linear fit.

### Sensitivity & zero error

The sensitivity error $u_K(x)$ is a statistical measure of random errors in the estimate of the slope of the calibration curve. The zero error $u_z(x)$ is a shift of the calibration curve.

## Verification & Validation

Verification and validation determines if the product complies with their specifications and whether they are fit for their intended use.

- Verification: Establishing the truth of correspondence between a work product and its specification. *Are we building the product right?*
- Validation: Refers to ensuring that the experimental model used is itself correct.

## Significant Digits

In writing numbers, the leftmost nonzero digit is the *most significant digit*. The rightmost is the *least significant digit*. All nonzero digits in a number are significant. All leading zeros are not significant, they only refer to the magnitude. Zeros between nonzero digits are significant. And trailing zeros are also significant.

Rounding is a process in which the number of digits is reduced and the remaining least significant digit(s) adjusted appropriately. In reducing the number of digits, (1) if the digits to be discarded begin with a digit less than 5,the digit preceding the 5 is not changed; (2) if the digits to be discarded begin with a 5 and at least one of the following digits is greater than 0, the digit preceding the 5 is increased by 1; (3) if the digits to be discarded begin with a 5 and all of the following digits are 0, the digit preceding the5 is unchanged if it is an even digit but increased by 1 if it is an odd digit. 

Some rules for numerical operations are:

1. In addition or subtraction, the number of digits following the decimal in the reported result should not be greater than the least number of digits found following a decimal in any of the data points used.
2. In other operations, the significant digits in the result should not be greater than the least number of significant digits in any of the data points or the operand used.
3. The number of significant digits in an exact count (i.e. the number of samples $N$) is not considered when establishing the number of significant digits to be reported.
4. Round your final result, but do not round intermediate calculations.
