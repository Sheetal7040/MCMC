# MCMC

This project focused on constraining the key cosmological parameters of the standard ΛCDM model — specifically the matter density parameter Ωₘ and the dimensionless Hubble constant h — using Type Ia Supernova data.

To do this, I implemented the Metropolis-Hastings MCMC algorithm from scratch in Python. The observational dataset used was the JLA (Joint Lightcurve Analysis) dataset of 31 Type Ia Supernovae, which provides redshift and distance modulus values, along with a covariance matrix.

The core idea was to simulate a posterior distribution for Ωₘ and h based on the observed supernova data. I defined a likelihood function that uses the theoretical distance modulus (computed from a given cosmological model) and compared it to the observed values, accounting for the full covariance matrix.

To compute the theoretical distance modulus, I first calculated the luminosity distance using a specific analytical formulation involving the scale factor and a function called η(a, ω) — an approximation used for solving cosmological integrals. Then, I constructed the μ(z) relation for given Ωₘ and h values.

In the MCMC algorithm, I initialized Ωₘ and h and performed 10,000 iterations. At each step, new values were proposed using Gaussian perturbations, and I calculated the likelihood ratio to decide whether to accept the move. I also experimented with two different step sizes: σ = 0.05 and σ = 100, and compared the results to show how proposal width impacts sampling quality.

To validate convergence and the quality of sampling, I analyzed:

Histograms of the posterior samples,

2D scatter plots of Ωₘ vs h,

Path plots of the MCMC chains,

And also computed covariance and variance.

Finally, I compared the theoretical μ(z) with the observed data and found good agreement for the best-fit parameters. This exercise taught me a lot about Bayesian inference, cosmological modeling, and the impact of proposal distributions on MCMC sampling.
