# Lab 04 — Sampling, Seasonality, and Inference from Time Series

**EAES 480: Modern Statistics in Earth & Environmental Science**  
University of Illinois Chicago  
Instructor: Dr. Gavin McNicol  

---

## Dataset & Study Context

This lab uses a **simplified AmeriFlux-style dataset** from the **US-AMS** site at **Argonne National Laboratory (near Chicago, IL)** covering **2023** at **30-minute resolution**.

### What is AmeriFlux?

AmeriFlux is a network of ecosystem observation sites (primarily eddy covariance towers) that measure exchanges of **carbon dioxide (CO₂), water vapor, and energy** between ecosystems and the atmosphere, along with supporting biomet variables.

- AmeriFlux overview: https://ameriflux.lbl.gov/about/about-ameriflux/  
- AmeriFlux variable documentation (for your data dictionary): https://ameriflux.lbl.gov/data/aboutdata/data-variables/

### Why this dataset is ideal for learning sampling

Because the time series has strong **seasonality** and a **day–night cycle**, it provides a realistic setting to practice sampling strategies and to see how sampling choices can bias or stabilize estimates.

---

## Overview

This lab introduces **sampling as the foundation of statistical inference** in Earth & Environmental Science.

Rather than jumping immediately to hypothesis tests, this assignment emphasizes:

- defining the **population** and **sample** clearly,
- recognizing structure in environmental variability (seasonal + diurnal),
- computing **population parameters** (mean, SD),
- comparing **sample estimates** to population truth, and
- testing how **simple random vs stratified sampling** performs.

You will work in a structured **R Markdown (`.Rmd`) document** that asks you to:

- complete missing code (fillable gaps / TODOs),
- generate plots and summaries,
- and write short interpretation responses throughout.

This lab prepares you for Unit 3’s move into **uncertainty and hypothesis testing**.

---

## Learning Goals

By the end of this lab, you should be able to:

- Define a population and sampling frame for an EAES time series  
- Compute population parameters (mean, SD) and compare sample estimates  
- Visualize distributions and identify **latent grouping variables** (e.g., month-of-year, day vs night)  
- Implement simple random sampling using `slice_sample()`  
- Implement stratified sampling (e.g., by month) and explain why it may help  
- Use `set.seed()` to make pseudo-random sampling reproducible  
- Produce a fully reproducible R Markdown analysis  

---

## What You’ll Do

In the provided R Markdown template, you will:

- Load the AmeriFlux-style dataset (US-AMS, 2023)
- Choose a **response variable** (e.g., `gpp`, `fc`, `le`, `ta`, etc.)
- Create time-series and distribution plots for the **full population**
- Explore whether grouping variables (month, day/night) explain variability
- Compute population mean and SD for your chosen response
- Draw a **simple random sample** and compare estimates to the population
- Simulate many samples to visualize sampling variability
- Implement a **stratified sampling** approach (by month) and compare outcomes
- Answer short conceptual prompts in complete sentences

This is a reasoning-first lab: the goal is to understand *why* sampling works (and fails), not just to run code.

---

## Repository Contents

- `lab-04-sampling.Rmd`  
  → The lab template you will complete and submit  

- `README.md`  
  → This file  

- `data/us-ams-simple.csv`  
  → Simplified AmeriFlux-style data for US-AMS (Argonne), 2023  

---

## Instructions

1. **Fork or clone** this repository to your own GitHub account  
2. Open `lab-04-sampling.Rmd` in **RStudio**  
3. Work through the document **from top to bottom**  
4. Fill in missing code **only inside the existing code chunks**  
5. Respond to interpretation prompts in plain text (outside code chunks)  
6. Knit regularly to catch errors early  

> ⚠️ Code that runs in the Console but not in the `.Rmd` does not count.

---

## Reproducibility Requirements

Your submission must:

- Knit without errors  
- Run top-to-bottom in a clean R session  
- Include all required libraries in the setup chunk  
- Avoid hard-coded local file paths  
- Use `na.rm = TRUE` where appropriate  
- Use `set.seed()` where instructed for reproducible sampling  
- Use tidy evaluation correctly when working with `response_var`  

These are not stylistic preferences—they are core scientific skills.

---

## Submission

- Commit and push your completed `.Rmd` file to your GitHub repository  
- Submit the **GitHub repository link** on Canvas  
- You do **not** need to submit the knitted HTML unless instructed  

Your work will be evaluated on:

- correctness of code,  
- quality of interpretation,  
- and reproducibility.

---

## Collaboration Policy

- You may discuss concepts and sampling strategies with classmates  
- You may not copy code verbatim from others  
- Code you submit must be written and understood by you  

If you worked with someone, acknowledge them in a comment.

---

## Tips for Success

- Decide your response variable early and stick with it  
- Look at **time series + distributions** (both matter for sampling)  
- Treat seasonality and day/night structure as *signals*, not nuisances  
- Stratification is not automatically “better”—explain why it helps here  
- If results surprise you, slow down and interpret before changing code  

---

## Why This Matters

In Earth & Environmental Science:

- we rarely observe complete populations,  
- environmental systems are structured in time and space,  
- and sampling design determines what we can claim.

Sampling is how we connect limited measurements to broader inference.  
This lab builds the intuition needed to do that responsibly—before we formalize hypothesis testing and uncertainty in Unit 3.
