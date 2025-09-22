---
layout: project
title: "Electronic and Thermodynamic Properties of Superconductors"
category: "Reading Project"
institution: "PRL Ahmedabad"
timeline: "March 2023 - June 2023"
published_date: "Jan 2025"
supervisor: "Dr. Paramita Dutta"
description: "Study of electronic and thermodynamic properties of superconductors"
# technologies: ["Theoretical Analysis", "Literature Review", "Scientific Writing"]
links:
  - title: "Project Report"
    url: "https://drive.google.com/file/d/1pMugRofo2XBDe9_rp9F9bGhsqoxaKZc9/view?usp=sharing"
---

## Project Overview

This reading project involved studying the electronic and thermodynamic properties of superconductors under the supervision of Dr. Paramita Dutta at PRL Ahmedabad. It served as a basic introduction to superconductor properties without relying on quantum mechanical descriptions.

While superconductivity at its core is a quantum many-body phenomenon, an introductory understanding can be developed just by using basic of electrodynamics and thermodynamics.

## Summary 

Superconducitivity was discovered in 1911 by Dutch physicist Heike Kamerlingh Onnes. He found that at 4.2 K the resistance in a solid mercury wire immersed in liquid helium suddenly vanished. This property of vanishing resistance below the transition temperature is hallmark of superconductivity.

In 1933, another interesting property of superconductors was discovered, when Meissner and Ochsenfeld realised that superconductors expelled applied magnetic fields, a phenomenon which we today called as the **Meissner effect**. By this time, there was no theoretical description for explaining this effect. Two  years later, in 1935, Fritz and Heinz London showed that the Meissner effect can be explained by the minimization of the electromagnetic free energy carried by superconducting current.

Let's look into the Meissner effect and London's equation in brief.

Consider a bulk Superconductor. To see the exclusion of applied magnetic field from it, one can choose two paths to do it. First is to apply the magnetic field then cool down below the transition temperature and other is to cool it down first and then apply the magnetic field. In both the cases, the superconductor will expell the applied magnetic field and will be in a perfectly diamagnetic state. The two image below shows this pictorically. 


<figure style="margin: 30px 0; text-align: center;">
  <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px; align-items: center; max-width: 800px; margin: 0 auto;">
    <div style="text-align: center;">
      <img src="{{ '/images/Meissner.jpg' | prepend: site.baseurl }}" alt="Meissner Effect - Path 1" style="width: 100%; height: auto; border: 1px solid #333; border-radius: 4px;">
      <p style="font-size: 0.85em; color: #aaaaaa; margin-top: 8px; font-style: italic;">
       <strong>Credit:</strong> James F. Annett - Superconductivity, Superfluids, and Condensates
      </p>
    </div>
    <div style="text-align: center;">
      <img src="{{ '/images/Meissner_paths.jpg' | prepend: site.baseurl }}" alt="Meissner Effect - Path 2" style="width: 100%; height: auto; border: 1px solid #333; border-radius: 4px;">
      <p style="font-size: 0.85em; color: #aaaaaa; margin-top: 8px; font-style: italic;">
       <strong>Credit:</strong> G.D. Mahan - Condensed Matter in a Nutshell
      </p>
    </div>
  </div>
  <figcaption style="font-size: 0.9em; color: #cccccc; margin-top: 20px; max-width: 700px; margin-left: auto; margin-right: auto; line-height: 1.5;">
    <strong>Figure 1:</strong> Demonstration of the Meissner effect through two experimental pathways. Both paths result in complete magnetic field expulsion from the superconductor interior, illustrating the Meissner effect.
  </figcaption>
</figure>


Anyone with the knowledge of electrodynamics can think of explaining that the path where we first cool down and then apply external field using the lenz law which says that the current in the superconductor flows in such a ways that it cancels the net magnetic field, but this is only true when there was a change in magnetic field when one switches it on and the object is already in superconducting state. How does one explain the second path? since it is found that the magnetic flux is excluded anyway. The second path makes it clear that flux exclusion is an important feature of the superconducting state.


London brothers' work aimed to create a phenomenological theory that could explain the Meissner effect. They began by applying classical mechanics to the "superelectrons," which they assumed moved without resistance. They started with the equation of motion of electrons with charge **e** and mass **m** in a electric field **E** given by 


<!-- filepath: /home/aviral/Website_github/Aviral_single_page/_projects/electronic-properties-superconductors.md -->

London brothers' work aimed to create a phenomenological theory that could explain the Meissner effect. They began by applying classical mechanics to the "superelectrons," which they assumed moved without resistance. They started with the equation of motion of electrons with charge $e$ and mass $m$ in an electric field $\mathbf{E}$ given by:

$$m \frac{\partial \vec{v}}{\partial t} = -e \vec{E}$$

For per unit of volume in the superconductor, let ns be the number of superelectrons, then the supercurrent density is defined as,

$$ \vec{J_{s}} = n_s e \vec{v} $$ 

Using the above equations, one can easily get the relation, 

$$ \frac{\partial \vec{J}_s}{\partial t} = \frac{n_s e^2 }{m} \vec{E} $$

This is the first london equation which essentially describes the property of zero resistance, where a constant electric field leads to a continuously accelerating current. Now, to proceed, use maxwell's equations which leads to the result,

$$ \nabla \times \mathbf{J}_s = -\frac{n_s e^2}{m} \mathbf{B}$$

Now to finally reach to the meissner effect, use the maxwell equation, $\nabla \times B = \mu_{o} \vec{J_s}$, and reach to the equation, 

$$ \nabla^2 B = \frac{\mu_{o} n_s e^2}{m} B $$

and the solution of this differential eqaution gives the exponentially decaying form of B, which tells us that magnetic cannot survive in the bulk of the superconductor. 

This was just one of the property, we studied in this project. To find the all content of project, please refer to the report attached below. 
