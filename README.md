# MLE

Maximum Likelihood Estimation (MLE) is a method used to estimate the parameters of a statistical model. The basic idea is to find the parameter values that maximize the likelihood of the observed data under the given model.


The likelihood function, denoted as L(theta | X), measures the likelihood of observing the data X given the parameters theta. Here, theta represents the parameters of the model.

For a given set of independent and identically distributed (i.i.d.) observations X = {x1, x2, ..., xn}, the likelihood function is:
L(theta | X) = P(X | theta) = P(x1 | theta) * P(x2 | theta) * ... * P(xn | theta)
This is the product of the probability density (or mass) functions evaluated at each observed data point xi, given the parameter theta.

Log-Likelihood Function:
Since the likelihood function is a product of many probabilities, it can be difficult to work with. Instead, we use the log-likelihood function, which is easier to differentiate and optimize:
l(theta | X) = log(L(theta | X)) = sum(log(P(xi | theta))) for i = 1 to n
The log-likelihood function l(theta | X) is the sum of the log of the probabilities.

Maximum Likelihood Estimation:
The goal of MLE is to find the parameter theta_hat that maximizes the log-likelihood function:
theta_hat = argmax_theta l(theta | X)
In other words, theta_hat is the value of theta that makes the observed data most probable.



For a normal distribution, the parameters to be estimated are the mean (mu) and the standard deviation (sigma).

The probability density function for a normal distribution is:
f(x | mu, sigma) = (1 / (sigma * sqrt(2 * pi))) * exp(- (x - mu)^2 / (2 * sigma^2))

The likelihood function for a sample X = {x1, x2, ..., xn} is:
L(mu, sigma | X) = product(f(xi | mu, sigma)) for i = 1 to n

Log-Likelihood Function:
Taking the natural logarithm of the likelihood function gives the log-likelihood function:
l(mu, sigma | X) = -n/2 * log(2 * pi) - n * log(sigma) - 1/(2 * sigma^2) * sum((xi - mu)^2) for i = 1 to n

Maximizing the Log-Likelihood:
To find the MLE estimates for mu and sigma, we differentiate the log-likelihood function with respect to mu and sigma, and set the derivatives to zero:
d(l(mu, sigma | X))/dmu = 0  -> mu_hat = sum(xi) / n
d(l(mu, sigma | X))/dsigma = 0  -> sigma_hat^2 = sum((xi - mu_hat)^2) / n

This gives the MLE estimates:
mu_hat is the sample mean.
sigma_hat is the sample standard deviation.
