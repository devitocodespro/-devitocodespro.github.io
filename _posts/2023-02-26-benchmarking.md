---
date: 2022-11-09T00:00:00.000Z
layout: post
title: Cross-platform seismic imaging benchmarking
subtitle: 'Collaborative optimization and benchmarking of seismic imaging workloads'
description: >-
  A framework for cross-platform benchmarking of seismic imaging
  workloads is described. The vision is that it evolves into a collaborative
  platform for the community to create better software and better decisions.
image: >-
  /images/robot_devito_pro_banner.png
optimized_image: >-
  /images/robot_devito_pro_banner-opt.png
category: DevOps
tags:
  - benchmarking
  - HPC
  - Cloud
  - AMD
  - ARM
  - Intel
  - Nvidia
author: Gerard Gorman, Fabio Luporini
paginate: true
mermaid: true
---

### TLDR

We have created a [GitHub](https://github.com/)-based extensible framework for
benchmarking seismic imaging kernels. The platform includes a development
cluster of servers with various computer architectures, configured as [GitHub
self-hosted
runners](https://docs.github.com/en/actions/hosting-your-own-runners/about-self-hosted-runners),
and utilizes [GitHub Actions](https://docs.github.com/en/actions) to automate
workflows. The platform allows for standardized and reproducible comparisons of
different methods, hardware, and skills. It also enables collaboration and
code/data reuse, ultimately leading to better performance of the software and
efficient use of human capital. The platform is also easily extendable by
configuring self-hosted runners, adding different benchmarks to the GitHub
Actions workflow, and more servers (either on-prem or Cloud-based).

The table with a summary of the current benchmark highlights is available
[here](https://www.devitocodes.com/benchmarks/private-cA1DbM/index.html).
**Disclaimer:** There results are *work-in-progress* and are included only to
stimulate community collaboration on benchmarking. There is ongoing effort to
optimize the code generated for different target architectures and so these
performance figures will evolve over the next few months. Do not make commercial
decisions based on this data.

### The vision: creating a platform for collaboration.

The key idea behind the seismic imaging benchmarking platform is to bring
together stakeholders in the industry, such as energy companies, service
companies, processor manufacturers, and academic researchers, to standardize
benchmarking of seismic imaging kernels and provide reference implementations
for a range of architectures.

The objective is to enable accurate and reproducible benchmark experiments,
facilitate collaboration and code/data reuse, reduce the duplication of effort
and improve the overall performance of seismic imaging software. Additionally,
robust performance data will help organizations make informed purchasing
decisions for on-premise or cloud computing systems. 

Overall, the proposed platform aims to address the common issues in benchmarking
seismic imaging kernels, such as differences in the PDEs, discretization,
algorithmic optimizations, and runtime choices, and provide a more standardized
and reproducible approach for comparing different methods, hardware, and skill.

#### Anatomy of a standard benchmark

<div class="mermaid">
  graph TB
    subgraph Standard: Benchmark setup/input
    A(Problem specification: PDEs, BCs, grid size/shape, ...) 
    end
    subgraph Concrete implementation 
    A-->B1(OSS Devito)
    A-->B2(DevitoPRO)
    A-->B3(Hardware vendor implementation)
    A-->B4(Other ISV, research, proprietary implementations)
    end
    subgraph Execution environment
    B2-->C1(Docker container)
    B2-->C2(Singularity container)
    end
    subgraph Target architecture
    C1-->D1(Bare metal)
    C2-->D2(Cloud)
    D1-->E1(CPU)
    D1-->E2(GPU)
    D2-->E3(CPU)
    D2-->E4(GPU)
    end
    subgraph Standard: benchmark output
    F(JSON: performance metrics, solution norms, status, implementation specific metadata)
    E1-->F
    E2-->F
    E3-->F
    E4-->F
    end;
</div>

### The software infrastructure

We have created a GitHub-based extensible framework for benchmarking seismic
imaging kernels. The Seismic Benchmark Platform e-infrastructure comprises
GitHub Actions for automating workflows and a development cluster of servers
with various computer architectures, each configured as a GitHub self-hosted
runner.

GitHub Actions is a feature that allows users to automate software development
workflows. It allows users to create custom workflows, called actions, triggered
by specific events such as a code push, pull request, or the creation of an
issue. These workflows include building and testing code, deploying software,
and integrating with other tools. With GitHub Actions, users can automate
repetitive tasks, reduce manual errors, and improve the overall efficiency of
their development process. In our case, GitHub Actions are used to

* Execute one or more benchmarks.
* Upload benchmark data to a results repository.
* Post-process benchmark data.
* Publish results on a website.

#### Workflow of benchmark automation with GitHub Actions

<div class="mermaid">
  graph TB
    subgraph GitHub Action: manual event trigger
      A(Benchmark matrix of jobs: benchmarks x architectures)
      B(GitHub actions schedules individual jobs to self-hosted runners)
      A-->B
    end
    subgraph Foreach benchmark job
      C(Job allocated to self-hosted runner)
      D(Setup execution environment)
      E(Run benchmark)
      F(Push benchmark output to data repo)
      B-->C
      C-->D
      D-->E
      E-->F
    end
    subgraph GitHub Action: triggered by data push
      G(Process data)
      H(Publish results to gh-pages)
      F-->G
      G-->H
    end;
</div>


GitHub Actions can run on either GitHub-hosted runners or self-hosted runners.
Self-hosted runners are used to execute a workflow on machines the users have
direct access to, rather than on GitHub-managed infrastructure. Self-hosted
runners allow users more control over the environment in which their workflows
run, including access to specific software, libraries, or hardware resources.
Users can also use self-hosted runners to run workflows on-premises, in a
virtual private cloud, or in a hybrid environment. Self-hosted runners are a
flexible solution for organizations with specific requirements for their
development environments and need more control over their workflow execution.

For the work described here, we have configured the following self-hosted runners:

* NVIDIA A100-PCIE-40GB (on-prem)
* NVIDIA A100-SXM4-40GB (Oracle Cloud Infrastructure, BM.GPU4.8)
* NVIDIA Tesla PG503-216 (on-prem)
* AMD Instinct™ MI210 (on-prem)
* Intel(R) Xeon(R) Gold 5218R CPU (on-prem)
* AMD EPYC 7413 24-Core Processor (on-prem)

The advantages of this design based on GitHub Actions are

* Fully automated workflow.
* Fully reproducible:
* All software is maintained in GitHub repositories.
* Reuses existing CI/CD infrastructure and know-how.
* Readily extendable:
  * Add benchmarks by adding extra jobs to the GitHub actions workflow.
  * Add more servers by configuring GitHub self-hosted runners.
  * Self-hosted runners can be bare-metal servers or running on the Cloud.

While the vision is to advance standardization in our industry and grow a
community around this platform, it is also straightforward to fork our codebase
and create a private instance with proprietary benchmarks.

Another fundamental aspect of our software infrastructure is the use of virtual
containers, in particular Docker. This makes it straightforward to configure new
machines and reproduce performance results. In our experience, virtual
containers are the only realistic way of maintaining and extending a software
and hardware infrastructure like the one we envision in this project. 

### Software Description

Here, we delve into the inner workings of the software framework. The main
software repo is at https://github.com/devitocodespro/benchmarks. All the
benchmark data is pushed to a designated branch of the repo, named `data`, to
enable data exploration. Two files are created for each benchmark:

* `data/<arch>/<benchmark-name>.log` contains the full combined stdout and stderr of GitHub action as if it was executed from the command line.
* `data/<arch>/<benchmark-name>.json` contains a summary of the autotuning experiments.

The Jupyter notebook, sandbox.ipynb, provides examples of how the data can be explored.

HTML pages are automatically generated, containing a performance 'leaderboard' and other summary data.

The GitHub Actions workflow file is at https://github.com/devitocodespro/benchmarks/blob/main/.github/workflows/benchmark.yml. 

The Dockerfiles to create the virtual containers are those used in Devito and
DevitoPRO. These Dockerfiles are used by Devito’ and DevitoPRO’s CI, which means
they are heavily tested.

Currently, all benchmarking is carried out using the DevitoPRO benchmark and
autotuning tool, `/devitopro/devitotuner/benchmark.py`. Rather than running a
single instance of the benchmark, the autotuner sweeps through code optimization
options and other tunable parameters (e.g., cache-block size) to discover the
best achievable performance.

The performance measure in this context is giga-grid-points-per-second, GPt/s
(sometimes called giga-cells-per-second). The advantages of this performance
measure are:

* Directly relates to the work throughout, and therefore the dollar cost of data processing.
* Unlike FLOPs, it is a non-gamble measure of performance.

Currently, three benchmarks are configured:

#### Isotropic acoustic
* Shortcut: iso
* Dimensions: 512x512x512
* Number of time steps: 400
* Space order: 8
* Time order: 2
* Implementation: /devitopro/demos/iso_acoustic

#### Fletcher and Fowler TTI
* Shortcut: tti_fl
* Dimensions: 512x512x512
* Number of time steps: 400
* Space order: 8
* Time order: 2
* Implementation: /devitopro/demos/tti_fletcher

#### Skew-adjoint TTI
* Shortcut: tti_sa
* Dimensions: 512x512x512
* Number of time steps: 400
* Space order of operator: 8
* Time order: 2
* Implementation: /devitopro/demos/tti_acoustic_self_adjoint

The numerical correctness of the benchmarks is validated by `/devitopro/devitotuner/benchmark.py`.

### The output

The table with the current benchmark results is available
[here](https://www.devitocodes.com/benchmarks/private-cA1DbM/index.html). As
explained earlier, this page is automatically updated each time the benchmark
suite runs via GitHub Actions. In each case, we are only benchmarking the best
implementation. Therefore, while we support OpenMP offloading and OpenACC, we
only benchmark CUDA for Nvidia and HIP for AMD GPUs, as these outperform OpenMP
offloading and OpenACC implementations.

### Future work

* Add a link to the page capturing the benchmark characteristics
* Add more metrics such as FLOPS.
* Add more benchmarks:
  * Laplacian operator (trivial case helps when working with vendors).
  * Gradient operators to stress backward propagation.
  * Elastic formulation, as these are of growing importance.
* Add support for 3rd parties to provide their implementation of the benchmarks.
* Add more benchmark configurations:
* MPI for NUMA CPUs.
* MPI for multiple GPUs per server.
* Add more bare metal nodes to the development cluster.
* Engage with hardware vendors to get test nodes.
* Add Cloud-based self-hosted runners:
  * In the case of OCI, we used a VM instance that needed to be manually brought up and taken down when finished.
  * Ideally, this would be configured as an on-demand runner.
* Community engagement.
* Organize benchmarking workshops.
* Engage with hardware and Cloud vendors to review and optimize benchmarks.
* Encourage community submissions.
* Miscellaneous issues list - https://github.com/devitocodespro/benchmarks/issues

### Process for manually run benchmarks

<div class="mermaid">
  graph TB
    A(Manual execution of benchmark)
    B(git-pull benchmarking data repo)
    A-->B
    C(Add results)
    B-->C
    D(Submit pull-request to trigger peer review)
    C-->D
    E1(Approve)
    D-->E1
    E2(Revise)
    D-->E2
    E2-->A
    F(Merge)
    E1-->F
    G(GitHub Action: publish to gh-pages)
    F-->G;
</div>

### Acknowledgements

Many thanks to Chevron for the funding and feedback to kickstart this
initiative.  We would also like to thank AMD, AWS, Dell, Oracle, Nvidia and
Supermicro for providing hardware and cloud resources. 
