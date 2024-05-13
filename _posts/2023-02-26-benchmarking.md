---
date: 2023-02-26T00:00:00.000Z
layout: post
title: Cross-platform seismic imaging benchmarking
subtitle: 'Optimization and benchmarking of seismic imaging workloads'
description: >-
  A framework for cross-platform benchmarking of seismic imaging
  workloads is described. The vision for this platform is that
  it will be used to support collaboration between Devito Codes,
  hardware vendors and Cloud providers to continuously optimize 
  the performance of seismic imaging workloads.
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

We have launched a groundbreaking framework to benchmark seismic imaging
workloads across different platforms. This initiative brings together key
stakeholders from Devito, hardware vendors, cloud providers, and the broader
industry, setting a stage for standardization, reproducibility, and elevated
performance in seismic imaging workloads.

Key Highlights:

1. **Standardization and Reproducibility**:
   - Advocates for standardized comparisons and robust performance data, aiding organizations in insightful hardware or cloud system acquisitions.

2. **Efficient Resource Utilization**:
   - Promotes code/data reuse and minimizes redundant efforts, leading to efficient resource and human capital utilization.

3. **Extendable and Automated Workflow**:
   - The flexible architecture allows for extensibility and employs automation for a streamlined benchmarking process, catering to evolving needs.

4. **Community Engagement**:
   - The initiative welcomes community engagement and dialogue, laying the groundwork for future collaborations, workshops, and benchmarking expansions.

5. **Transparency and Validation**:
   - Even in its alpha phase, the emphasis on transparency and validation of benchmark data ensures responsible use of preliminary data. However, because of the commercial sensitivity of the data, the benchmarking data is only available under NDA.

This framework signifies a substantial stride towards nurturing a collaborative
ecosystem aimed at advancing standardization and optimization of seismic imaging
workloads across diverse computing architectures. The collaborative ethos
facilitated by this platform is geared towards driving notable advancements in
seismic imaging performance, contributing to the overarching goal of efficient
resource utilization and heightened computational capabilities.

### Overview 

The framework is build on [GitHub](https://github.com/)-based having being
heavily influenced by our existing CI/CD framework. The platform includes a
development cluster of servers with various computer architectures, configured
as [GitHub self-hosted
runners](https://docs.github.com/en/actions/hosting-your-own-runners/about-self-hosted-runners),
and utilizes [GitHub Actions](https://docs.github.com/en/actions) to automate
workflows.

One of the advantages of this approach is that it naturally supports automation,
standardized and reproducible comparisons of different methods, hardware, and
skills. It also enables collaboration and code/data reuse, ultimately leading to
better performance of the software and efficient use of human capital. The
platform is also easily extendable by configuring self-hosted runners, adding
different benchmarks to the GitHub Actions workflow, and more servers (either
on-prem or Cloud-based).

### Benchmarking as a platform

The key idea behind the seismic imaging benchmarking platform is to bring
together stakeholders in the industry, such as energy companies, service
companies, processor manufacturers, and academic researchers, to standardize
benchmarking of seismic imaging kernels.

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
    B2-->C1(Singularity)
    B2-->C2(Docker)
    B2-->C3(Conda)
    end
    subgraph Target platform
    C1-->D1(On-Prem dev-cluster)
    C1-->D2(Vendor/slurm dev-cluster)
    C1-->D3(Public Cloud)
    D1-->E1(Vendor CPUs)
    D1-->E2(Vendor GPUs)
    end
    subgraph Standard: benchmark output
    F(JSON: performance metrics, solution norms, status, implementation specific metadata)
    E1-->F
    E2-->F
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

Currently, three benchmarks are configured:

#### Isotropic acoustic

* Shortcut: iso
* Dimensions: 512x512x512
* Number of time steps: 400
* Space order: 8
* Time order: 2

#### Fletcher and Fowler TTI

* Shortcut: tti_fl
* Dimensions: 512x512x512
* Number of time steps: 400
* Space order: 8
* Time order: 2

#### Skew-adjoint TTI

* Shortcut: tti_sa
* Dimensions: 512x512x512
* Number of time steps: 400
* Space order of operator: 8
* Time order: 2

### Results preview

We have included a snapshot of results below. FLOPS (Floating Point Operations
Per Second) is a well-recognized measure in High-Performance Computing (HPC),
but it may not always be the most revealing. Its value can be inflated by
employing inefficient numerical methods. In seismic imaging, GPts/s (Giga-Points
Per Second) — also termed giga-cells-per-second — is often favored. This metric
directly measures work throughput, offering a clearer gauge of performance. In
essence, GPts/s helps in accurately estimating the time or cost required to
solve a specific problem.

**Disclaimer:** *Although we have exerted maximum effort to guarantee precise,
*equitable, and replicable results, it is crucial to understand that the
*benchmarking framework is still in the alpha development phase. Consequently,
*the benchmarks provided here are preliminary and subject to change. The
*benchmark data should not be considered comprehensive or final, and are not
*suited for making any financial decisions.*

*No warranty, express or implied, is provided with the data. The information is
*supplied on an "as is" basis. We expressly disclaim, to the maximum extent
*permitted by law, any liability for any damages or losses, direct or
*consequential, resulting from the use of these benchmarks. Please utilize this
*information responsibly, keeping in mind its tentative nature.*

### 3D Isotropic acoustic

| Processor                          | GPts/s |
|-----------------------------------|-------|
| NVIDIA A100-80GB                   | 62.7  |
| NVIDIA A100-PCIE-40GB              | 54.2  |
| AMD Instinct™ MI250                | 54    |
| NVIDIA Tesla PG503-216 (V100)      | 31    |
| AMD Instinct™ MI210                | 29.2  |
| Intel(R) Xeon(R) Gold 5218R CPU    | 7.97  |
| AMD EPYC 7413 24-Core Processor    | 1.49  |

### 3D Fletcher Du Fowler TTI

| Processor                          | GPts/s |
|-----------------------------------|-------|
| AMD Instinct™ MI250                | 16.1  |
| NVIDIA A100-80GB                   | 12.4  |
| NVIDIA A100-PCIE-40GB              | 12.2  |
| AMD Instinct™ MI210                | 9.83  |
| NVIDIA Tesla PG503-216 (V100)      | 9.34  |
| Intel(R) Xeon(R) Gold 5218R CPU    | 1.72  |
| AMD EPYC 7413 24-Core Processor    | 0.797 |

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
  * Ideally, this would be configured as an on-demand runner.
* Community engagement.
* Organize benchmarking workshops.
* Engage with hardware and Cloud vendors to review and optimize benchmarks.

### Acknowledgements

Many thanks to Chevron for the funding and feedback to kickstart this
initiative.  We would also like to thank AMD, AWS, Dell, Nvidia and
Supermicro for providing hardware and cloud resources.
