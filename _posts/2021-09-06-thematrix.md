---
date: 2021-09-06T23:48:05.000Z
layout: post
title: TheMatrix v0.2 - The Devito benchmark matrix
subtitle: 'Benchmark everything, trust no one'
description: >-
  Benchmarking Devito solvers across computer architectures, execution models,
  compilers and anything else one can think of. Thought for developers and
  enterprises.
image: >-
  /images/thematrix_screenshot.png
optimized_image: >-
  /images/thematrix_screenshot.png
category: Benchmarking
tags:
  - benchmarking
  - HPC
  - Cloud
  - AMD
  - ARM
  - Intel
  - NVidia
author: Dr. Fabio Luporini (CTO)
paginate: true
---

We developed **TheMatrix** as an automated, cross-platform benchmarking suite for
[Devito](https://www.devitoproject.org). By the push of a button, utilizing
GitHub Actions in tandem with Airspeed Velocity (ASV), Devito's benchmarking
tools, and computing platforms, a spectrum of benchmarks and regression tests
can quickly be executed, and compared across a broad range of hardware
configurations.

TheMatrix is the most comprehensive apples-to-apples comparison of the
performance of seismic imaging workloads yet to be published. You can dive
straight into one of the TheMatrix [auto-generated
plots](https://www.devitoproject.org/thematrix/#acoustic_iso.IsotropicAcousticForward.track_gpointss)!
This plot shows the performance of the 3D isotropic acoustic equation, a basic
benchmark used by the seismic imaging community. **Gigapoints per second** is
used as the performance metric as it is widely used in the O&G sector to
estimate the price of data processing. Indeed, thanks to the FLOP reduction
technology in Devito, it is often observed that gigapoints per second can be
increased while FLOPS decreases!

Use the *benchmarks* tab at the bottom-left of the page to jump to the many
other juicy results.

## Devito and TheMatrix

Devito is a domain-specific language for explicit
finite-difference/stencil-based computation on structured grids. At the user
level, all Devito operations (e.g. finite-difference stencils, boundary
conditions, interpolations, cross-correlation) are expressed symbolically - a
layer of abstraction built upon SymPy. This code is jit-compiled into a dynamic
C–library for the specific hardware at hand with the compiler of choice (GCC,
Clang, ICC, NVCC, PGI).

Devito natively supports a range of architectures, including CPUs (Intel,
Power, ARM, AMD) and GPUs (NVidia, AMD). Notably, the user code for any
particular simulation is identical for all supported platforms, regardless of
the chosen target programming models (e.g., C, OpenMP, OpenMP+MPI,
OpenACC+MPI).

TheMatrix has been developed as a tool to quickly and efficiently evaluate the
performance portability of Devito across multiple hardware configurations for a
range of production-level stencil-based computations. The aims of this software
are:

* Assess the performance of stencil codes across a range of architectures.
* Monitor performance regression on a range of benchmarks.
* Provide a robust and reproducible environment for benchmarking.
* Automate benchmarking across many different application configurations, execution, environments, and architectures.

## Our vision

Devito Codes' objective is to create an ecosystem around the open-source
package Devito to maximize productivity, portability, and performance. Our new
software, TheMatrix, pushes in this direction by:

* featuring a fully automated workflow
* reusing CI and Cloud infrastructure
* being straightforward to extend to new benchmarks and architectures
* running on all kinds of hardware supported by Devito
* providing key metrics to assess the efficiency and cost of a benchmark

While TheMatrix currently runs on our on-prem development cluster, we also
support Cloud platforms such as Azure.

Our vision is to build a platform that provides live monitoring of the pricing
on different clouds. With comprehensive performance data and Cloud resource
pricing, TheMatrix provides the means to optimize cost-of-solution as well as
time-to-solution.

## What's next

The current version, v0.2 is only the beginning. We're keen to incorporate the
feedback that some companies have already provided. For example, we know the
visualization needs improvements; we want to make it straightforward to
understand what a plot is showing, which involves customizing AVS. We also
generate many more detailed performance metrics than what is displayed via ASV.

At the same time, we are exploring with the community how to offer this as a
service best. For example, add a REST API so the TheMatrix can be
programmatically queried. We are also working on adding new benchmarks and
architectures. We also intend to shift to using Docker rather than Conda to set
up the runners. This should make it even faster to configure a new architecture
and reproduce experiments.
