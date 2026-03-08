---
layout: ../../layouts/ProjectLayout.astro
title: "Earthquake Damage Classification"
description: "Classifying earthquake damage levels using Logistic Regression, LDA, QDA, and Naive Bayes with k-fold cross-validation."
date: "March 2025"
github: "https://github.com/anjelicam/earthquake-classification"
tags: ["Machine Learning", "Python", "scikit-learn"]
---

## Overview

In this project, I explored several classification methods to predict earthquake damage levels based on building and geographic features. The goal was to compare the performance of different classifiers and understand which approaches work best for this type of multi-class problem.

## Data

The dataset contains information about buildings affected by earthquakes, including structural features, geographic location, and the resulting damage grade. I cleaned and prepared the data using pandas, handling missing values and encoding categorical variables.

## Methods

I implemented and compared four classification approaches:

- **Logistic Regression** — a baseline linear model
- **Linear Discriminant Analysis (LDA)** — assumes shared covariance across classes
- **Quadratic Discriminant Analysis (QDA)** — allows each class its own covariance
- **Naive Bayes** — assumes feature independence

Each model was evaluated using **k-fold cross-validation** with macro-averaged F1 score to account for class imbalance.

## Results

_Add your results here — which model performed best? What were the F1 scores? Were there any surprising findings?_

## What I Learned

_Reflect on the project — what was challenging? What would you do differently? What techniques would you try next?_

## Code

The full code for this project is available on [GitHub](https://github.com/anjelicam/earthquake-classification).
