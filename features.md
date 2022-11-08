---
layout: page
menu: false
date: '2020-01-01 00:00:00'
title: Features
description: DevitoPRO features
permalink: /features/
---

## Feature overview

* CPUs (Intel, AMD, ARM)				
* GPUs (NVidia, AMD)				
* Multi-node architectures via MPI				
* Lazy data streaming from/to GPUs
* Lossy-compression of data				
* Optimized MPI communications on GPUs				
* Adaptive (expanding/contracting) box				
* Comprehensive performance autotuning

## Features comparison

<table>
    <tr align="center">
      <td class=""></td>
      <td class="top aligned"><h3 class="ui header"><b>Devito (Open-source)</b></h3></td>
      <td class="top aligned"><h3 class="ui header"><b>DevitoPRO</b></h3></td>
    </tr>
    <tr align="left" bgcolor="#75C3A5">
        <td style="padding-left:10px" colspan="5"><i>Solvers</i></td>
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
      <td align="right" style="padding-left:10px"> Custom operators (for, e.g., BCs)</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Sub-domains, staggered-grids, sub-sampling</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Extensive examples and documentation</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Checkpointing</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Reduced-precision</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Floating-point compression</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Calls to external C/C++ functions</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="left" bgcolor="#75C3A5">
        <td style="padding-left:10px" colspan="5"><i>Solver catalog</i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Isotropic (visco)acoustic + adjoints</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Isotropic (visco)elastic</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> TTI acoustic + adjoints</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> VTI viscoacoustic + adjoints</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Optimized templates for RTM/FWI</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="left" bgcolor="#75C3A5">
        <td style="padding-left:10px" colspan="5"><i>Compute</i></td>
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
      <td align="right" style="padding-left:10px"> AMD GPUs - HIP</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i>(beta)</td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> NVidia GPUs - OpenMP, OpenACC</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr> 
       <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> NVidia GPUs - CUDA</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i>(beta)</td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Multi-node architectures via MPI</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Lazy data streaming from/to GPUs</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Optimized MPI communications on GPUs</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Adaptive (expanding/contracting) box</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Comprehensive performance autotuning</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="left" bgcolor="#75C3A5">
        <td style="padding-left:10px" colspan="5"><i>Features</i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Cloud-readiness</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Benchmarking league table</td>
      <td><i class="fas fa-check text-xl"></i></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> In-depth performance analysis via TheMatrix</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Customization of TheMatrix</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="left" bgcolor="#75C3A5">
        <td style="padding-left:10px" colspan="5"><i>Support</i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Consultancy</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>
    <tr align="center" bgcolor="#e6fff6">
      <td align="right" style="padding-left:10px"> Prioritized issue resolution</td>
      <td></td>
      <td><i class="fas fa-check text-xl"></i></td>
    </tr>

</table>
