# Stat_Notes

## 5.1.2022

Population
- Tangible Population - Actual physical objects
- Conceptual population - All values that can be observed under identical experimental conditions

Sample - Subset of populations, observed

SRS - Each collection of size n is equally likely to make up the sample

Salpling variation - Random samples differ from population and other SRS's

Data - A measurement from a sample

Independence - Information about one item does not give info about any other item. Items do not affect each other

Variable - characteristic which can be measured. Data item
- Numerical - Values represent a measurable quantity (quantitative)
- Categorical - Values of variable are placed into categories (qualitative)

Observational study
- Take SRS and observe variables
- Cannot conclude causation

Controlled Experiment
- Factors under control of researcher
- Causation conclusions are justified

07.01.2022

Section 1.2 - Numerical Summaries

Sample mean (affected by outliers)
$$\begin{align}
\bar{X} = \frac{1}{n} \Sigma^n_{i=1}X_i
\end{align}$$

Sample variance (units of squared deviation from mean)
$$
	s^2 = \frac{1}{n-1} \Sigma^n_{i=1}(X_i - \bar{X})^2
$$

Sample standard deviation s = sqrt(variance)

Transformations

If 
$$
Y_i = a + bX_i
$$
then
$$
\bar{Y} = a + b \bar{X}
$$
and 
$$
x_Y = |b| s_X.
$$
Median - middle number; not influenced by outliers and skewness
Quartiles
Mode
Range
pth percentile - number at which p% of the sample is less than

## 10.01.2022

IQR = Q3-Q1

Statistics summarize Samples
Parameters summarize Populations

Histograms
Density = relative freq/class width

Right skewed: mean > median
Left skewed: mean < median

Boxplots good for comparing

12.01.2022

Let S be a sample space. Then P(S) = 1.
For any event A, 0 ≤ P(A) ≤ 1.
If A and B mutually exclusive, P(AUB) = P(A) + P(B)

P(A^c ) = 1 − P(A)

P(A ∪ B) = P(A) + P(B) − P(A ∩ B)

P(∅) = 0

$$
P(A | B) = \frac{P(A \cap B)}{P(B)}
$$
Alse (Baye's rule)
$$
P(A | B) = \frac{P(B | A)P(A)}{P(B)}
$$
Law of Total Probability (n=2)
$$
P(B) = P(B|A)P(A) + P(B|A^c)P(A^c)
$$
Law of Total Probability (general)
$$
P(B) = P(B|A_1)P(A_1) +...+ P(B|A_n)P(A_n)
$$
$$
P(A | B) = \frac{P(B | A)P(A)}{P(B|A)P(A) + P(B|A^c)P(A^c)}
$$
Independence
$$
P(B|A) = P(B)
$$
(Can use B and B^c interchangeably for independence, and same with A)
Also independence:
$$
P(A \cup B) = P(A) + P(B) - P(A \cap B)
$$

Permutation (without replacement)
$$
nPr = \frac{n!}{(n-r)!}
$$
Permutation (with replacement)
$$
nP^Rr = n^r
$$

Combination
$$
nCr = \frac{n!}{r!(n-r)!}
$$
## 14.01.2022
DeMorgan's Laws
$$
(A \cap B)^c = A^c \cup B^c
$$
$$
(A \cup B)^c = A^c \cap B^c
$$
Marginal probabilities - Summing up to disregard other factors?

## 19.01.2022
"When Adam was kicked out of the garden what was he told?" "Wear a mask"

## 21.01.2022
The Probability Mass Function (pmf) is the probability distribution of a discrete random variable. It is a table, formula, or graph showing all the possible values of a discrete random variable and their associated probabilities.

For any valid pmf:
$p(x) \geq 0$
$\sum_{all x} p(x) = 0$

The cumulative distribution function (cdf) is defined as
$$
F(x) = P(X \leq x)
$$
Cdf is monotonically increasing

Mean of discrete variable
$$
\mu_x = \sum x \cdot p(x)
$$
Variance of discrete variable
$$
\sigma_x^2 = \sum (x-\mu_x)^2 \cdot p(x) = \biggl ( \sum x^2 \cdot p(x) \biggr) - \mu_x^2
$$
	
A random variable is continuous if its possible values contain an interval. The probabilities of continuous random variables are given by areas under a curve.

Probabilities for a continuous random variable are represented by the area under the probability density function (pdf), f (x). That is
$$
P(a < X < b) = \int_a^b f(t)dt
$$
For any valid pdf f:
$f(x) \geq 0$
$\int_{-\infty}^{\infty} f(t)dt = 1$

##### 24.01.2022
Mean of continuous variable
$$
\mu_x = \int_{-\infty}^{\infty} x \cdot f(x)dx
$$
Variance of continuous variable
$$
\sigma_x^2 = \int_{-\infty}^{\infty} (x-\mu_x)^2 \cdot f(x)dx = \biggl ( \int_{-\infty}^{\infty} x^2 \cdot f(x)dx \biggr) - \mu_x^2
$$

##### 26.01.2022
Bernoulli distribution - success or fail
$$
P(X = x) = 1 - p \text{ if x = 0 }, p \text{ if x = 1}
$$
Summary values
$\mu_X = np, \sigma_X^2 = np(1-p)$

Binomial distribution - bernoulli distribution with $n$ trials
- trials independent
- each trial success has same probability
- X is number of successes
Then $X \~ Bin(n,p)$

Binomial pmf for $x = 0,1,2,...$
$$
p(x) = \frac{n!}{x!(n-x)!} p^x(1-p)^{n-x}
$$
In R:
pmf: P(X = x) =dbinom(x, n, p) 
Cumulative probabilities: P(X ≤ x) =pbinom(x, n, p)

Binomial summary values:
$\mu_X = np$
$\sigma_X^2 = np(1-p)$

## 28.01.2022
Poisson distribution

$$
p(x) = e^{- \lambda} \frac{\lambda ^ x}{x!}
$$

Keyword: RATE

pmf: P(X = x) 
=dpois(x, lambda) 
Cumulative Probabilities: P(X ≤ x) 
=ppois(x, lambda)

$\mu_X = \lambda$
$\sigma_X^2 = \lambda$

## 31.01.2022
Notation: X ∼ N(µ, σ2)
pmf:
$$
f(x) = \frac{1}{\sigma \sqrt{2 \pi}} e^{-(x-\mu)^2/2 \sigma^2}
$$
68-95-99.7 rule
Z-score
$Z = \frac{X-\mu}{\sigma}$
Z has N(0,1) distribution
$X = Z \sigma + \mu$

R coding
Standard Normal, N(0, 1):
- Probabilities to the left (cumulative probabilities): 
	- pnorm(z) 
- Percentiles: 
	- qnorm(p) 
Normal, N(µ, σ2 ):
- Probabilities to the left (cumulative probabilities): 
	- pnorm(x,mean,sd) 
- Percentiles: 
	- qnorm(p,mean,sd)

## 02.02.2022
This distribution of X_bar is called the sampling distribution.

$\mu_{X_{bar}} = \mu$
$\sigma_{X_{bar}}^2 = \frac{\sigma^2}{n}$

If the population is Not Normal and n ≥ 30, we use the Central Limit Theorem.

Central Limit Theorem: If $n$ is sufficiently large, 
$$
\overline{X} ~ N \bigg ( \mu, \frac{\sigma^2}{n} \bigg )
$$

![[Pasted image 20220202134410.png]]
Central Limit Theorem for sums:
$$
S_n ~ N \bigg ( n\mu, n \sigma^2 \bigg )
$$
![[Pasted image 20220202134511.png]]

Probabilities with X_bar
$$
Z = \frac{X_{bar} - \mu}{\sigma / \sqrt{n}}
$$

Probabilities with sums
$$
Z = \frac{S_n - n\mu}{\sigma / \sqrt{n}}
$$

## 04.02.2022
Measurement Error is the difference between a measured value and the true value.
Bias (systemic error) is the part of the error that is the same for every measurement
Random error varies from measurement to measurement and averages out to zero in the long run

Measured Value = True Value + Bias + Random Error
Accuracy - unbiased
Precision - Low random error
	If repeated measurements come out nearly the same every time, the precision is high and uncertainty is low

The sample standard deviation s can be used to estimate the uncertainty.
If the true value is know, the sample mean, X, can be used to estimate the bias: Bias ≈ X − true value

## 07.02.2022
When error in measurement produces error in calculated values, we say that error is propagated from the measurements to the calculated value.

Let X be a measurement with uncertainty $\sigma_X$ and let c be a constant. Suppose Y = c + X. Then the uncertainty in Y , $\sigma_Y$ , is $\sigma_Y = \sigma_X$.

Let X be a measurement with uncertainty $\sigma_X$ and let c be a constant. Suppose Y = cX. Then the uncertainty in Y , $\sigma_Y$ , is  $\sigma_Y = |c| \sigma_X$

Suppose Y is the sum of some independent X values multiplied by some constants
$$
Y = c_1X_1 + ... + c_nX_n,
$$
Then the uncertainty in Y is 
$$
\sigma_Y = \sqrt{c_1^2 \sigma_{X1}^2 + ... + c_n^2 \sigma_{Xn}^2}.
$$


If X1, . . . , Xn are n independent measurements, each with mean µ and uncertainty σ, then the sample mean, X, is a measurement with mean $\mu$ and uncertainty $\sigma / \sqrt{n}$ 

## 09.02.2022
Uncertainty for functions $U = U(x)$:
$$
\sigma_U \approx \bigg | \frac{dU}{dX} \bigg | \sigma_x
$$
![[Pasted image 20220209130236.png]]

Relative uncertainty
$$
R.U. = \frac{\sigma_Y}{\mu_Y}
$$
If bias is negligible, estimate relative uncertainty
$$
R.U. \approx \frac{\sigma_Y}{Y}
$$

## 11.02.2022
Confidence intervals
95% given by $\overline{X} \pm 1.96 \frac{\sigma}{\sqrt{n}}$
99% given by $\overline{X} \pm 2.58 \frac{\sigma}{\sqrt{n}}$

$(1- \alpha)100\%$ given by $\overline{X} \pm z_{\alpha / 2} \frac{\sigma}{\sqrt{n}}$
qnorm(1 − ( α/2 )) in R will compute appropriate zα/2
qnorm(0.975) will return 1.96, the z0.05/2 for a 95% CI

Confidence IS NOT Probability
- Probability refers to random event
- After the sample is taken and the interval computed, there are no random events

Increasing precision
- Decrease level of confidence
- Increase sample size

Sample size required for a $(1- \alpha)100\%$ to have a precision of $\pm m$ (round up to nearest whole number):
$$
n = \bigg (\frac{z_{\alpha / 2} \sigma }{m} \bigg )^2
$$

## 14.02.2022
$\sigma / \sqrt{n}$ is the standard deviation of the sampling distribution of $\overline{X}$ sometimes called the standard deviation of $\overline{X}$ for short

$s / \sqrt{n}$ is the standard error of the sampling distribution of $\overline{X}$ 

Let µ be from a population that is approximately normal. A (1 − α)100% confidence interval for µ when n is small is
$$
\overline{X} \pm t_{n-1,\alpha/2} \frac{s}{\sqrt{n}}
$$
where tn−1,α/2 denotes the value for the Student’s t distribution with n − 1 degrees of freedom whose upper-tail probability is α/2

To find tn−1,α/2 use the function: qt(1-alpha/2, n-1)
