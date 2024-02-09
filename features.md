---
layout: page
menu: false
date: '2020-01-01 00:00:00'
title: Features
description: DevitoPRO features
permalink: /features/
---

## Devito/DevitoPRO feature overview

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
      <td align="right" style="padding-left:10px">Support for CPUs across AMD, ARM, and Intel architectures</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Support for AMD GPUs with OpenMP compatibility</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr> 
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Support for NVidia GPUs with OpenMP and OpenACC support</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr> 
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Support for AMD GPUs through HIP technology</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Support for Intel GPUs with SYCL (beta)</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i>(beta)</td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Support for NVidia GPUs via CUDA</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Enables multi-node parallelism through MPI for CPU-based computations</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>    
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Enhanced MPI communications optimization for GPUs</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Facilitates lazy data streaming to and from GPUs</td>
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
      <td align="right" style="padding-left:10px">Custom operators for boundary conditions and more</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Supports sub-domains, staggered-grids, and sub-sampling techniques</td>
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
      <td align="right" style="padding-left:10px">Support for reduced-precision computations</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Implements lossy data compression for floating-point data</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Enables serialization of data for disk storage</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Integration with external C/C++ functions for extended functionality</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Utilizes an adaptive box for dynamic spatial domain adjustments</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Comprehensive solution for performance autotuning to optimize execution</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="left" bgcolor="#75C3A5">
        <td style="padding-left:10px" colspan="5"><i>Solvers (forward and adjoint), 2D/3D</i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Solvers for isotropic acoustic and visco-acoustic equations</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Solvers for isotropic elastic and visco-elastic equations</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Acoustic TTI solvers for advanced seismic imaging</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Solvers for VTI visco-acoustic equations for anisotropic media</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px">Elastic TTI solvers for comprehensive seismic modeling</td>
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
