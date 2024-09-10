---
layout: page
menu: false
date: '2020-01-01 00:00:00'
title: Features
description: DevitoPRO features
permalink: /features/
---

DevitoPRO, an advanced extension of the open-source Devito platform, is designed to cater specifically to high-performance computing (HPC) needs, especially in seismic imaging and inversion. While both platforms enable symbolic computation for developing finite-difference kernels, DevitoPRO offers several added features tailored for more demanding, production-level workflows.

### Key Differentiators for Seismic Imaging Users:
1. **Enhanced Performance Portability**: DevitoPRO supports advanced GPU acceleration using CUDA, HIP, and SYCL, offering better cross-platform flexibility. This means you can deploy high-performance applications on most commercially available processors, including Nvidia, AMD, and Intel GPUs, as well as ARM and x86_64 processors. Performance portability is crucial for both on-premise and cloud environments, where availability has become as important a consideration as price performance. DevitoPRO’s portability maintains performance even as you switch between available cloud instances or on-premise hardware.

2. **Advanced Domain-Specific Optimizations**: DevitoPRO introduces a wide range of optimizations like the expanding-box technique, which focuses computational resources only on active domains, resulting in more efficient memory and compute usage. We are also increasing support for mixed-precision computation options, which reduce memory pressure without compromising accuracy, further enhancing performance for seismic imaging tasks.

3. **Compression and Data Streaming for Back-Propagation**: A key feature for production seismic workloads, DevitoPRO integrates compression-based back-propagation and asyncronious data-streaming techniques to optimize disk-host-GPU transfers. This is essential for handling the large datasets typically involved in seismic imaging, significantly improving memory management and computational efficiency during reverse time migration (RTM) and full-waveform inversion (FWI).

4. **Enterprise-Ready Features**: DevitoPRO integrates seamlessly with major cloud platforms like AWS, Azure, and Google Cloud, and offers specific support for tuning and benchmarking cloud instances. The platform includes pre-defined, optimized propagators for common seismic tasks, reducing development overhead and allowing teams to immediately leverage high-performance solutions. Additionally, DevitoPRO offers enterprise-grade support, including tailored benchmarking and private consultation services, which are critical for production-level applications.

These features make DevitoPRO an essential tool for seismic imaging professionals who need robust, scalable, and highly optimized computational tools that can adapt to fluctuating hardware availability and complex workflows.

<style>
.table-cell {
    padding-left: 10px;
    white-space: normal;
    word-wrap: break-word;
    text-align: center;
}

.toggle-content {
  display: none;
  transition: all 0.3s ease-in-out;
}

.feature-row td{
    background-color: #75C3A5;
     text-align: left;
}

.content-row td{
    background-color: #e6fff6;
    text-align: center;
}

.visible {
    display: table-row;
  }
</style>

<script>
  document.addEventListener('DOMContentLoaded', function() {
    const headings = document.querySelectorAll('.feature-row');
    
    headings.forEach(heading => {
      heading.addEventListener('click', function() {
        let nextRow = this.nextElementSibling;
        while (nextRow && !nextRow.classList.contains('feature-row')) {
          nextRow.classList.toggle('visible');
          nextRow = nextRow.nextElementSibling;
        }
      });
    });
  });
</script>

<table width="100%">
  <tr class="table-cell">
    <td class="center"><b>Features</b></td>
    <td class="center"><b>Open-source Devito</b></td>
    <td class="center"><b>DevitoPRO</b></td>
  </tr>
  <tr class="feature-row">
    <td colspan="3"> Domain-specific language (DSL) for finite-differences </td>
  </tr>
  <tr class="content-row toggle-content">
    <td>Write PDE solvers symbolically</td>
    <td>✔</td>
    <td>✔</td>
  </tr>
  <tr class="content-row toggle-content">
    <td>Tensor algebra</td>
    <td>✔</td>
    <td>✔</td>
  </tr>
  <tr class="content-row toggle-content">
    <td>Taylor series weights for any order</td>
    <td>✔</td>
    <td>✔</td>
  </tr>
  <tr class="content-row toggle-content">
    <td>Customizable stencil weights (eg variable-z, dispersion minimizing)</td>
    <td>✔</td>
    <td>✔</td>
  </tr>
  <tr class="content-row toggle-content">
    <td>Immersed boundary support (eg accurate land topography)</td>
    <td></td>
    <td>✔</td>
  </tr>
  <tr class="content-row toggle-content">
    <td>Explicit methods</td>
    <td>✔</td>
    <td>✔</td>
  </tr>
  <tr class="content-row toggle-content">
    <td>Implicit methods (via PETSc)</td>
    <td>Alpha</td>
    <td>Alpha</td>
  </tr>
  <tr class="content-row toggle-content">
    <td>Source/receivers (fully customizable)</td>
    <td>✔</td>
    <td>✔</td>
  </tr>
  <tr class="content-row toggle-content">
    <td>Boundary conditions (fully customizable)</td>
    <td>✔</td>
    <td>✔</td>
  </tr>
  <tr class="content-row toggle-content">
    <td>Staggered grids</td>
    <td>✔</td>
    <td>✔</td>
  </tr>
  <tr class="content-row toggle-content">
    <td>Subsampling (e.g. space/time decimation)</td>
    <td>✔</td>
    <td>✔</td>
  </tr>
    <tr class="content-row toggle-content">
      <td>Subdomains</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>API for third-party library callbacks</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>Jupyter notebook tutorials,
      examples and documentation</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
        <tr class="feature-row">
        <td colspan="3">Devito Cookbook
        (includes forward, adjoint and 2D/3D)</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>Isotropic acoustic and viscoacoustic</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>Isotropic elastic and viscoelastic</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>Acoustic VTI and TTI</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>Viscoacoustic VTI and TTI</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>Elastic VTI and TTI</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="feature-row">
        <td colspan="3"> PDE-constrained optimization
        and adjoint method </td>
    </tr>
    <tr class="content-row toggle-content">
      <td>Express adjoint-method optimization
      problems symbolically</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>Checkpoint(/Revolve)-based back-propagation</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>Compression-based back-propagation</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>Intelligent data-streaming disk-host-GPU</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>Lossy data compression for
      floating-point data</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="feature-row">
      <td colspan="3"> Algorithmic and compiler
          performance optimizations </td>
    </tr>
    <tr class="content-row toggle-content">
      <td>Decoupler (software integration layer for seismic codes)</td>
      <td></td>
      <td>✔</td>
    </tr> 
    <tr class="content-row toggle-content">
      <td>Automated multi-level parallelization</td>
      <td></td>
      <td>✔</td>
    </tr> 
    <tr class="content-row toggle-content">
      <td>Expanding-box (only compute active domain)</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>Mixed-precision computation</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>Data-locality optimization (e.g. cache-blocking)</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>Autotuning/Devitotuner</td>
      <td>Basic</td>
      <td>Advanced</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>FLOP reduction (e.g. factorization, hoisting, CSE)</td>
      <td>Comprehensive</td>
      <td>Advanced</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>Advanced low-level optimization (e.g., memory alignment)</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="feature-row">
        <td colspan="3">Supported architectures</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>CPUs: AMD, ARM, and Intel</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>GPUs: AMD, Intel, Nvidia</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>Accelerators: Intel KNC, KNL</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="feature-row">
        <td colspan="3"> Programming models </td>
    </tr>
    <tr class="content-row toggle-content">
      <td>OpenMP for CPUs and GPUs</td>
      <td>✔</td>
      <td>✔</td>
    </tr>  
    <tr class="content-row toggle-content">
      <td>OpenACC for Nvidia GPUs</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>CUDA</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>HIP</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>SYCL</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>NUMA-aware MPI-OpenMP</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>MPI: Single-node-multi-gpu</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>MPI: Multi-node-multi-gpu</td>
      <td></td>
      <td>Beta</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>Optimized GPU-aware MPI</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="feature-row">
        <td colspan="3">Supported cloud platforms</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>AWS</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>Azure</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>GCP</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="feature-row">
        <td colspan="3"><i>
        Cross-platform industry benchmarks. Includes iso-acoustic and acoustic
        TTI. All benchmarks are independently autotuned to get best performance
        on each target.</i></td>
    </tr>
    <tr class="content-row toggle-content">
      <td>Access to benchmark reports and raw logs for reproducibility.</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>Cloud instance tuning and benchmarking.</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="feature-row">
      <td colspan="3">Support</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>Slack: community support on public channels</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>Slack: Private/NDA support channels</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>Projects</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>Training</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>Consultancy</td>
      <td></td>
      <td>✔</td>
    </tr>
    <tr class="content-row toggle-content">
      <td>Support/maintenance</td>
      <td></td>
      <td>✔</td>
    </tr>
</table>
