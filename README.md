# Disparities in COVID-19 Infection in San Francisco: A Bayesian Latent Time Trend Model
This repo investigates COVID-19 infection risk disparities across racial and ethnic groups in San Francisco using hierarchical Bayesian Negative Binomial (NB) models. Publicly available case data were modeled using a log-link with group-level effects and a Gaussian random walk that captures broad changes in infection intensity.

## Problem Statement
Were racial and ethnic disparities in COVID-19 infection risk in San Francisco real, persistent, and consistent across the pandemic, or did they vary by era (pre-vaccine, vaccine/Delta, Omicron)?

## Approach
Raw case counts are confounded by population size and by shared temporal dynamics (surges, mandates, variant waves) that affect all groups simultaneously. A hierarchical Bayesian Negative Binomial (NB) model with a latent Gaussian Random Walk time trend let me separate group-level effects from shared epidemic dynamics, model overdispersion in count data, and quantify uncertainty in disparities via posterior credible intervals rather than point estimates.

## Model Validation 
I ran 4 MCMC (Markov chain Monte Carlo) chains (5,000 draws, 1,000 burn-in) and confirmed convergence via R values near 1. I compared the baseline NB model against Poisson and Zero-Inflated NB alternatives using leave-one-out cross-validation (ELPD-LOO), confirming NB as the best fit. Posterior predictive checks showed the model captured the broad epidemic trend while appropriately smoothing extreme spikes. A second era-interaction model explored whether disparities shifted across pandemic phases.

## Key Finding
Native Hawaiian/Pacific Islander and Hispanic/Latino residents faced substantially higher per-capita infection risk than white residents throughout the pandemic, with the disparity not constant across eras, revealing how public health interventions interacted differently across demographic groups.
