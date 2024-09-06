---
layout: page
menu: false
date: '2020-01-01 00:00:00'
title: Features
description: DevitoPRO features
permalink: /features/
---

DevitoPRO is an enhanced, commercial extension of the open-source Devito, designed specifically for high-performance computing (HPC) tasks such as seismic imaging and inversion. While both platforms share a foundation in symbolic computation for developing finite-difference kernels, DevitoPRO offers several advanced features that cater to more complex, production-level workflows.

Key differentiators include:

* **Code Generation for GPUs and Accelerators**: DevitoPRO supports advanced GPU acceleration with CUDA, HIP, and SYCL, offering better performance portability across Nvidia, AMD, and Intel GPUs, compared to the more basic GPU support in the open-source Devito.
* **Compression and Data Streaming**: It introduces compression-based back-propagation and intelligent disk-host-GPU data streaming, crucial for large-scale seismic workloads. This significantly improves memory management and performance during back-propagation, a feature absent in the open-source version.
* **Advanced Optimizations**: DevitoPRO includes domain-specific optimizations like the *expanding-box* technique, which focuses computations only on active domains, leading to more efficient resource usage. The platform also offers mixed-precision computation and enhanced auto-tuning mechanisms for superior performance tuning.
* **Enterprise-Ready Features**: It integrates with cloud platforms (AWS, Azure, GCP), offers tailored support services (e.g., private Slack channels), and provides advanced benchmarking, autotuning support that are critical for enterprise applications.

These features make DevitoPRO a powerful option for organizations requiring robust, scalable, and highly optimized computational tools for seismic imaging.

<style>
.table-cell {
    padding-left: 10px;
    white-space: normal;
    word-wrap: break-word;
    text-align: center;
}

.feature-row td{
    background-color: #75C3A5;
    font-style: italic;
    text-align: left;
}

.content-row td{
    background-color: #e6fff6;
    text-align: center;
}

</style>

<table width="100%">
  <tr class="table-cell">
    <td class="top aligned"><h3 class="ui header"><b>Features</b></h3></td>
    <td class="top aligned"><h3 class="ui header"><b>Devito (Open-source)</b></h3></td>
    <td class="top aligned"><h3 class="ui header"><b>DevitoPRO</b></h3></td>
  </tr>
  <tr class="feature-row">
    <td colspan="3"> Domain-specific language (DSL) for finite-differences </td>
  </tr>
  <tr class="content-row">
    <td>Write PDE solvers symbolically</td>
    <td>✔</td>
    <td>✔</td>
  </tr>
  <tr class="content-row">
    <td>Tensor algebra</td>
    <td>✔</td>
    <td>✔</td>
  </tr>
  <tr class="content-row">
    <td>Taylor series weights for any order</td>
    <td>✔</td>
    <td>✔</td>
  </tr>
  <tr class="content-row">
    <td>Customizable stencil weights</td>
    <td>✔</td>
    <td>✔</td>
  </tr>
  <tr class="content-row">
    <td>Explicit methods</td>
    <td>✔</td>
    <td>✔</td>
  </tr>
  <tr class="content-row">
    <td>Implicit methods (via PETSc)</td>
    <td>Alpha</td>
    <td>Alpha</td>
  </tr>
  <tr class="content-row">
    <td>Source/receivers (fully customizable)</td>
    <td>✔</td>
    <td>✔</td>
  </tr>
  <tr class="content-row">
    <td>Boundary conditions (fully customizable)</td>
    <td>✔</td>
    <td>✔</td>
  </tr>
  <tr class="content-row">
    <td>Staggered grids</td>
    <td>✔</td>
    <td>✔</td>
  </tr>
  <tr class="content-row">
    <td>Subsampling (e.g. space/time decimation)</td>
    <td>✔</td>
    <td>✔</td>
  </tr>
    <tr class="content-row">
      <td>Subdomains</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td>API for third-party library callbacks</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td>Jupyter notebook tutorials,
      examples and documentation</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="feature-row">
        <td colspan="3"> PDE-constrained optimization
        and adjoint method </td>
    </tr>
    <tr class="content-row">
      <td>Express adjoint-method optimization
      problems symbolically</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td>Checkpoint(/Revolve)-based back-propagation</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td>Compression-based back-propagation</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td>Intelligent data-streaming disk-host-GPU</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td>Lossy data compression for
      floating-point data</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="feature-row">
      <td colspan="3"> Algorithmic and compiler
          performance optimizations </td>
    </tr>
    <tr class="content-row">
      <td>Expanding-box (only compute active domain)</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td>Mixed-precision computation</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td>Data-locality optimization (e.g. cache-blocking)</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td> Auto-tuning</td>
      <td>Basic</td>
      <td>Advanced</td>
    </tr>
    <tr class="content-row">
      <td>FLOP reduction (e.g. factorization, hoisting, CSE)</td>
      <td>Comprehensive</td>
      <td>Advanced</td>
    </tr>
    <tr class="content-row">
      <td>Advanced low-level optimization (e.g., memory alignment)</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="feature-row">
        <td colspan="3">Supported architectures</td>
    </tr>
    <tr class="content-row">
      <td>CPUs: AMD, ARM, and Intel</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td>GPUs: AMD, Intel, Nvidia</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td>Accelerators: Intel KNC, KNL</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="feature-row">
        <td colspan="3"> Programming models </td>
    </tr>
    <tr class="content-row">
      <td>OpenMP for CPUs and GPUs</td>
      <td>✔</td>
      <td>✔</td>
    </tr>  
    <tr class="content-row">
      <td>OpenACC for Nvidia GPUs</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td>CUDA</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td>HIP</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td>SYCL</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td>NUMA-aware MPI-OpenMP</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td>MPI: Single-node-multi-gpu</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td>MPI: Multi-node-multi-gpu</td>
      <td></td>
      <td>Beta</td>
    </tr>
    <tr class="content-row">
      <td>Optimized GPU-aware MPI</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="feature-row">
        <td colspan="3">Supported cloud platforms</td>
    </tr>
    <tr class="content-row">
      <td>AWS</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td>Azure</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td>GCP</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="feature-row">
        <td colspan="3">Devito Cookbook
        (includes forward, adjoint and 2D/3D)</td>
    </tr>
    <tr class="content-row">
      <td>Isotropic acoustic and viscoacoustic</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td>Isotropic elastic and viscoelastic</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td>Acoustic VTI and TTI</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td>Viscoacoustic VTI and TTI</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td>Elastic VTI and TTI</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="feature-row">
        <td colspan="3"><i>
        Cross-platform industry benchmarks. Includes iso-acoustic and acoustic
        TTI. All benchmarks are independently autotuned to get best performance
        on each target.</i></td>
    </tr>
    <tr class="content-row">
      <td>Access to benchmark reports and raw logs for reproducibility.</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td>Cloud instance tuning and benchmarking.</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="feature-row">
      <td colspan="3"> Support </td>
    </tr>
    <tr class="content-row">
      <td>Slack: community support on public channels</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td>Slack: Private/NDA support channels</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td>Projects</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td>Training</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td>Consultancy</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row">
      <td>Support/maintenance</td>
      <td></td>
      <td>✔</td>
    </tr>
</table>
