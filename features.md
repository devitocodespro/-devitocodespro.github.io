---
layout: page
menu: false
date: '2020-01-01 00:00:00'
title: Features
description: DevitoPRO features
permalink: /features/
---

## DevitoPRO feature overview


### Architectures and Parallel Programming Models Supported
* CPUs (AMD, ARM, Intel)				
* GPUs (AMD/HIP, NVidia/CUDA, Intel/SYCL)				
* Multi-node parallelism via MPI [cpu-only]

### IO
* Lazy data streaming from/to GPUs
* Lossy compression of data
* Serialization of data to disk
* Asynchronous IO

### Algorithmic Optimizations
* Optimized MPI communications on GPUs				
* Adaptive (expanding/contracting) box				
* Comprehensive performance autotuning
* Leading edge performance optimization

### Recipe of Solvers (forward and adjoint)
* Isotropic acoustic and visco-acoustic
* Isotropic elastic and visco-elastic
* VTI visco-acoustic
* TTI acoustic
* Elastic TTI

## Features comparison

<table>
    <tr align="center">
      <td class=""></td>
      <td class="top aligned"><h3 class="ui header"><b>Devito (Open-source)</b></h3></td>
      <td class="top aligned"><h3 class="ui header"><b>DevitoPRO</b></h3></td>
    </tr>
    <tr align="left" bgcolor="#75C3A5">
        <td style="padding-left:10px" colspan="5"><i>Platform support</i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Cloud-readiness</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">CPUs (Intel, AMD, ARM)</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">AMD GPUs - OpenMP</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr> 
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> NVidia GPUs - OpenMP, OpenACC</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr> 
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> AMD GPUs - HIP</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
        <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Intel GPUs - SYCL</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i>(beta)</td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> NVidia GPUs - CUDA</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Multi-node parallel via MPI</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>    
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Optimized MPI communications on GPUs</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Lazy data streaming from/to GPUs</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="left" bgcolor="#75C3A5">
        <td style="padding-left:10px" colspan="5"><i>Algorithms</i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Domain-specific language for finite-differences</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Unstructured operations</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Custom operators (for, e.g., BCs)</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Sub-domains, staggered-grids, sub-sampling</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Extensive examples and documentation</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Checkpointing</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Reduced-precision</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Floating-point (lossy) compression</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Serialization of data to disk</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Calls to external C/C++ functions</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Adaptive (expanding/contracting) box</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Comprehensive performance autotuning</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="left" bgcolor="#75C3A5">
        <td style="padding-left:10px" colspan="5"><i>Solvers (forward and adjoint), 2D/3D</i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Isotropic (visco-)acoustic</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Isotropic (cisco-)elastic</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Acoustic TTI</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">VTI visco-acoustic</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Elastic TTI</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="left" bgcolor="#75C3A5">
        <td style="padding-left:10px" colspan="5"><i>Support</i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Projects</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Training</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr> 
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Consultancy</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Support/maintenance</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>

</table>


