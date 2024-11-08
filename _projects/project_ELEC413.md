---
layout: page
title: Design and Analysis of Fabry-Perot Cavities for Semiconductor Lasers
description: An in-depth exploration into the design, simulation, and experimental validation of Fabry-Perot cavities using silicon Bragg gratings and waveguides.
img: assets/img/header_fabry_perot.png  # Update with your header image path
importance: 1
category: Photonics
related_publications: false
pdf_link: /assets/pdf/UBC_ELEC413_JuanMunoz.pdf  # Place the report PDF in assets/pdf
---

## Abstract
This project provides a comprehensive analysis of Fabry-Perot cavities designed for a central wavelength of 1310 nm, leveraging silicon-based Bragg gratings, couplers, and waveguides. Using Lumerical software, this project simulates different cavity configurations and compares results with experimental data to validate the design.

### Project Objectivesx
- **Optimize Fabry-Perot cavity designs** for effective laser performance at 1310 nm.
- **Compare simulation data** with experimental results to understand deviations.
- **Evaluate the effects of manufacturing variances**, such as deviations in Bragg period, on wavelength accuracy.

---

## Design and Simulation Process

### 1. Waveguide Design and Effective Index Calculation
Using Lumerical’s simulation tools, waveguides were designed to operate at a wavelength of 1310 nm. The dimensions were optimized to achieve the desired effective index, essential for constructing Fabry-Perot resonators. A frequency sweep simulation yielded the effective index values necessary for the Transfer Matrix Method (TMM) calculations.

#### Figure: Frequency Sweep Simulation
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/frequency_sweep.png" title="Frequency Sweep Simulation Results" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Frequency sweep simulation of the waveguide design, illustrating the effective index at the target wavelength of 1310 nm.
</div>

---

### 2. Bragg Grating and Cavity Design
Bragg gratings were implemented with varying periods and configurations to assess their impact on wavelength selectivity and cavity quality. Using KLayout, different Fabry-Perot cavity structures were constructed.

#### Table: Bragg Grating Parameters
| Parameter          | Value       | Description                                   |
|--------------------|-------------|-----------------------------------------------|
| Central Wavelength | 1310 nm     | Target wavelength for Fabry-Perot resonator   |
| Grating Period     | 250 nm      | Period for Bragg reflectivity tuning         |
| Coupler Spacing    | 500 nm      | Optimized for minimal insertion loss         |

---

### 3. Transfer Matrix Method Analysis
The TMM was used to simulate cavity resonances and quality factors. Simulations were performed to assess the impact of cavity length, Bragg period, and waveguide geometry on the Fabry-Perot cavity’s optical performance.

#### Figure: Quality Factor Simulation
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/quality_factor_simulation.png" title="Quality Factor vs Cavity Length" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Relationship between quality factor and cavity length, demonstrating that longer cavities yield higher Q-factors but may introduce greater sensitivity to manufacturing tolerances.
</div>

---

## Experimental Results and Comparison

### 1. Quality Factor and Wavelength Accuracy
Experimental tests were performed to verify the accuracy of the simulated Fabry-Perot cavity models. Quality factors were measured, and wavelength shifts were analyzed for various cavity configurations.

#### Table: Experimental vs Simulated Quality Factors
| Cavity Configuration | Simulated Q-Factor | Experimental Q-Factor | Deviation (%) |
|----------------------|--------------------|-----------------------|---------------|
| Configuration 1      | 12000             | 11500                | 4.17%         |
| Configuration 2      | 10500             | 10000                | 4.76%         |
| Configuration 3      | 9500              | 9100                 | 4.21%         |

#### Figure: Experimental Measurement Comparison
<div class="row justify-content-sm-center">
    <div class="col-md-6 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/experimental_comparison.png" title="Experimental vs Simulation Results" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-md-6 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/wavelength_shift_effects.png" title="Wavelength Shifts due to Manufacturing Errors" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left: Comparison between experimental and simulated measurements for Fabry-Perot configurations. Right: The impact of Bragg period deviations on wavelength accuracy.
</div>

---

## Key Findings and Insights

- **Accuracy of Simulation Models**: The simulation results aligned closely with experimental data, confirming the reliability of the models.
- **Impact of Manufacturing Variability**: Even minor deviations in Bragg period significantly affect wavelength precision, underscoring the need for precise manufacturing controls in applications requiring wavelength stability.

### Conclusion
This study successfully validates the design and simulation methodologies for Fabry-Perot cavities targeting 1310 nm. The findings demonstrate the potential of using TMM and other simulation tools to predict real-world performance accurately, proving the feasibility of Fabry-Perot cavities for precise laser applications in integrated photonics.

---

This project was carried out at the University of British Columbia as part of the ELEC 413 course, under the supervision of Professor Jaeger.

---

## Full Report
Download the complete project report:

[Download Full Report PDF]({{ page.pdf_link }})
        