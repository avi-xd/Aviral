---
layout: project
title: "Machine Learning Based Digital Holographic Microscopy"
category: "Semester Project"
institution: "ETH Zurich (Online)"
timeline: Dec 2023 - July 2024
supervisor: "Dr. Falko Schmidt"
description: "Using machine learning for 3D particle tracking in holographic microscopy for lab-on-chip applications"
technologies: ["U-Net", "LodeSTAR", "DeepTrack", "Python", "Holography"]
links:
  - title: "Project Documentation"
    url: "#"
---

## Project Overview

This semester project explored the application of machine learning techniques to digital holographic microscopy, specifically focusing on developing automated particle tracking solutions for lab-on-chip applications.

## Summary

 Holography is a technique used to capture the properties of an object in 3D, providing spatial depth, detailed volumetric information, and the ability to analyze dynamic processes, all of which are not possible with traditional 2D imaging methods. On the other hand, a lab-on-a-chip is a device designed to replicate the functionality of a laboratory, performing a variety of reactions on a miniature scale. However, mixing reactants on such a small scale poses significant challenges due to limitations in fluid dynamics, such as low Reynolds numbers that inhibit turbulence, and reaction kinetics that require precise control over diffusion. These difficulties often necessitate specialized equipment like pressure syringes to achieve efficient mixing. To address this issue, researchers have been exploring innovative solutions, including the use of light to control the dynamics of particles.
      
One such approach involves utilizing gold nanorods (AuNRs) at the bottom of a lab-on-a-chip. By shining light on these AuNRs, plasmon resonance, a phenomenon where conduction electrons on the metal surface oscillate in resonance with incident light is induced, allowing localized temperature control around the nanorods. Holography is then employed to image these systems, providing detailed 3D information about particle positions over time. By reconstructing velocity profiles of particles at different temperatures, holography enables researchers to understand and manipulate particle dynamics with precision. This is critical for controlling movement, as it allows for the fine-tuning of conditions that drive specific reactions or processes within the lab-on-a-chip system.

The process of tracking particles and analyzing velocity profiles from holographic data, however, is both computationally intensive and labor-intensive. To streamline this process, machine learning models can be employed to trace particle positions directly from holographic data. In our work, we utilized U-Net, a supervised model widely used in bioimaging applications, and LodeSTAR, a label-free, self-supervised model implemented through the DeepTrack framework, to track particles in 3D using off-axis holographic data.
      
LodeSTAR showed good tracking performance in the x and y axes, achieving sub-pixel accuracy, as validated by comparing its results to ground truth data from numerical simulations. However, when compared with numerically derived data, the z-axis results exhibited occasional sudden jumps, indicating room for further refinement.