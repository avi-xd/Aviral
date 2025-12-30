---
layout: project
title: "Magnon Visualization System"
category: "Summer Internship"
institution: "SN Bose National Centre for Basic Sciences "
timeline: "May 2025 - July 2025 (on-going)"
date: 2024-07-01
supervisor: "Dr. Arijit Haldar"
description: "Worked on developing a software to analyse and visualize magnon on different kinds of lattice systems based on generalised linear spin wave theory."
#   - title: "Lab Images"
#     url: "#"
---

## Project Overview

During this Internship at SNBNCBS, I worked on developing a software tool to visualize magnon modes in 3D. The tool allows us to select from various 1,2 or 3 dimensional lattice systems and observe the magnon modes under specfic conditions. 
It includes the features to select and delete an atom, give any non-collinear spin structure to the lattice, or to choose between periodic or open boundary conditions in any available direction and adding an interaction between any two atoms in a lattice. 

By implementing the Generalized Linear Spin Wave Theory (LSWT) and utilizing the Bogoliubov-de Gennes (BdG) formalism in real space, the system can solve for eigenmodes in complex, finite lattices where translational symmetry might be broken.
From a computational perspective, the software can handle high performance requirements using a strict Model-View-Controller (MVC) architecture. One of the significant technical challenges was the "neighbor search" bottleneck in large supercells; a brute-force approach scales poorly at $O(N^2)$. To solve this, I implemented a KD-Tree (k-dimensional tree) spatial indexing algorithm, which  reduced the bond-finding complexity to $O(N \log N)$. This optimization allows the software to generate large crystal structures efficiently without lag.


I developed a Command Line Interface (CLI) alongside the GUI. This tool (magnon-cli.py) allows for fully scriptable workflows. Users can programmatically build lattices, inject specific defects by manually adding or removing bonds, and modify coupling strengths ($J_{ij}$) without opening the window. The CLI integrates seamlessly with the visualization pipeline; one can perform heavy diagonalization calculations in the background (calc) and immediately inspect the resulting wavefunctions or spin textures in 3D using simple commands like view-wavefunction.

For the visualization engine, it uses VisPy, which leverages OpenGL to render thousands of spin vectors directly on the GPU. This enabled the implementation of smooth, real-time animations of magnon precession modes, where the cone angle and phase of every spin are dynamically updated based on the calculated eigenvectors. It also have a color-based "picking" algorithm using off-screen framebuffer rendering, allowing users to interactively select and inspect individual atoms in 3D space with pixel-perfect precision. 

Currently, only real space calculations can be done on the software, but we aim to include k-space calculations and plotting the band structures for further analysis. We also aim to include the different types interactions, like Dzyaloshinskii-Moriya (DM) interaction and single-ion anisotropy. As of now, it can handle only heisenberg interactions.


---

### 1. The Interactive Builder & Architecture

<div align="center">
  <img src="{{ site.baseurl }}/images/Screenshot from 2025-12-29 03-06-21.jpg" width="100%" style="border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.2);" />
  <p><em>Figure 1: The Main Builder Interface (GUI). Users can define lattice geometry (e.g., Honeycomb, Kagome, Cubic, etc), set periodic boundary conditions, and configure interaction shells interactively.</em></p>
</div>

---

### 2. Real-Space Analysis

<div align="center">
  <img src="{{ site.baseurl }}/images/Screenshot from 2025-12-29 03-07-48.jpg" width="100%" style="border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.2);" />
  <p><em>Figure 2: The Analysis Panel. The system solves the BdG Hamiltonian to find magnon energy eigenvalues (left panel) and visualizes the resulting wavefunction amplitudes (blue spheres).</em></p>
</div>

The physics engine implements **Generalized Linear Spin Wave Theory (LSWT)**. Instead of relying on momentum-space (k-space) solutions which require infinite periodicity, I utilized the **Bogoliubov-de Gennes (BdG)** formalism in real space.

This approach allows for the study of finite systems, defects, and disordered materials. 

---

### 3. Wavefunction Mapping

<div align="center">
  <img src="{{ site.baseurl }}/images/Screenshot from 2025-12-29 02-52-30.jpg" width="100%" style="border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.2);" />
  <p><em>Figure 3: Static Wavefunction Amplitude Map. The probability density of a magnon mode is visualized as a "cloud," where the size of the blue spheres corresponds to the amplitude $|\psi_i|^2$ at that site.</em></p>
</div>

To visualize the spatial distribution of a magnon mode, the software renders a static map where the marker size for each atom is proportional to the wavefunction probability density. This provides an immediate, intuitive understanding of where excitations are localized within the lattice structure.

---

### 4. Topological Edge States

One of the critical capabilities of the real-space solver is identifying **Topological Edge States** modes where energy is localized entirely at the boundaries of the material.

<div align="center">
  <img src="{{ site.baseurl }}/images/Screenshot from 2025-12-29 02-53-04.jpg" width="90%" style="border-radius: 8px; margin-bottom: 15px;" />
  <p><em>Figure 4: An edge state in a honeycomb lattice strip, showing high-amplitude excitations (large blue spheres) strictly confined to the boundary.</em></p>
  
  <br>

  <img src="{{ site.baseurl }}/images/Screenshot from 2025-12-29 03-11-41.jpg" width="90%" style="border-radius: 8px;" />
  <p><em>Figure 5: A anti-ferromagnet structure of Honeycomb lattice with just nearest neighbour interactions.</em></p>
</div>

---

### 5. GPU-Accelerated using VisPy

<div align="center">
  <img src="{{ site.baseurl }}/images/24.jpg" width="100%" style="border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.2);" />
  <p><em>Figure 6: The Live Visualizer (drawn using command line interface instead of GUI) showing spin vectors (cones) and lattice connectivity.</em></p>
</div>



---

