# Dating App STI Network Model

This repository contains the code and documentation for an agent-based simulation model studying how dating-app matching mechanisms influence sexually transmitted infection (STI) diffusion.

The project models two key structural mechanisms of dating platforms:

1. **Assortative matching**: users are more likely to match with others who share similar demographic or behavioral traits.
2. **Hub formation**: a small number of highly visible or highly active users accumulate disproportionate numbers of contacts.

These mechanisms are used to generate dynamic sexual contact networks, which are then passed into a multi-pathogen SEIS epidemiological model for Chlamydia, Gonorrhoea, and Syphilis.

## Project Overview

Dating applications do not simply increase the number of potential partners available to users. They also reshape the structure of sexual contact networks by concentrating interactions around popular users and by encouraging preference-driven matching across demographic and behavioral traits.

This project investigates how these network structures affect STI transmission outcomes. Instead of assuming random partner selection, the model builds a dynamic contact network where matches emerge from user compatibility, similarity, visibility, and popularity.

The simulation focuses on three main outcomes:

- Disease prevalence over time
- Exposure propagation speed
- Network clustering and hub-driven transmission patterns

## Research Question

How do assortative matching and user popularity concentration, calibrated from real dating-app behavior, influence STI diffusion dynamics in an agent-based SEIS model?

## Model Summary

The model is a discrete-time agent-based simulation where each time step represents one calendar day.

Each simulation consists of four main stages:

1. **Population initialization**
   - Agents are assigned demographic and behavioral attributes.
   - Initial disease states are assigned for Chlamydia, Gonorrhoea, and Syphilis.
   - Each agent receives activity, attractiveness, and protection-preference traits.

2. **Similarity and popularity scoring**
   - Pairwise compatibility is determined using sex and sexual orientation.
   - Assortative similarity is computed across traits such as ethnicity, education, age, religion, smoking, drinking, and drug use.
   - Popularity scores are updated based on recent and cumulative matching activity.

3. **Matching and network formation**
   - Agents receive daily swipe budgets.
   - Candidate partners are sampled using attractiveness-weighted visibility.
   - Mutual acceptance creates a contact edge.
   - Casual contacts may be promoted to longer-term relationships.

4. **STI transmission**
   - Transmission occurs over the active daily contact graph.
   - Each pathogen follows a Susceptible–Exposed–Infectious–Susceptible, or SEIS, structure.
   - The three diseases run concurrently, allowing co-infection.
