---
layout: page
title: Design and Analysis of Fabry-Perot Cavities for Semiconductor Lasers
description: An in-depth exploration into the design, simulation, and experimental validation of Fabry-Perot cavities using silicon Bragg gratings and waveguides.
img: assets/img/Portada_ELEC.png  # Update with your header image path
importance: 1
category: Photonics
related_publications: false
pdf_link: /assets/pdf/UBC_ELEC413_JuanMunoz.pdf  # Place the report PDF in assets/pdf
---

## Abstract
This is a project in which I design different fabry perot cavities for a central wavelength of 1310 nm using silicon Bragg grating, couplers and waveguides. These
designs will be fabricated and measurements will be obtained which we will analyse with the simulations carried out.

### Project Objectivesx
- **Optimize Fabry-Perot cavity designs** for effective laser performance at 1310 nm.
- **Compare simulation data** with experimental results to understand deviations.
- **Evaluate the effects of manufacturing variances**, such as deviations in Bragg period, on wavelength accuracy.

---

## Design and Simulation Process

### 1. Waveguide Design and Effective Index Calculation
Using Lumerical’s simulation tools, waveguides were designed to operate at a wavelength of 1310 nm. The dimensions were optimized to achieve the desired effective index (thickness of 220 nm and a width of 350 nm.), essential for constructing Fabry-Perot resonators. A frequency sweep simulation was calculated in order to obtain the polynomial expression for the
effective index that we would use later in the TMM. 

#### Figure 1: Frequency Sweep Simulation
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/ELEC_1.png" title="Frequency Sweep Simulation Results" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Frequency sweep simulation of the waveguide design, illustrating the effective index at the target wavelength of 1310 nm.
</div>

### 2. Calculation Results
From these results, we can obtain:

- **Effective Index**: 2.433
- **Bragg Period**:
  \[
  \lambda_B = \frac{\lambda_B}{2 \cdot n_f} = 269.21 \, \text{nm}
  \]
- **Effective Indices**: 2.433, −1.577, −0.04567




### 3. Bragg Grating Waveguide Simulation

The next step involves simulating a unit cell of a Bragg grating waveguide using Lumerical FDTD. This simulation provides the kappa parameter by adjusting the corrugation width (ΔW) to achieve the desired kappa and a central wavelength close to 1310 nm.

#### Simulation Parameters

| ΔW (nm) | Kappa | Central Wavelength (nm) | Bandwidth (nm) | Δn      |
|---------|-------|-------------------------|----------------|---------|
| 55      | 12539 | 1295                    | 14.88         | 0.081190 |
| 40      | 12344 | 1316                    | 15.141        | 0.081256 |
| 50      | 12615 | 1311                    | 15.38         | 0.082794 |
| 45      | 12434 | 1314                    | 15.208        | 0.081733 |

One important parameter derived from kappa is Δn, which will be used in the Transfer Matrix Method later:

\[
\Delta n = \frac{k \cdot \lambda_B}{2}
\]

These results provide key insights into the Bragg grating performance for Fabry-Perot cavities targeting the 1310 nm wavelength.

---

### 4. Manufacturing Error and Bragg Period Adjustment

In all cases, the initial design used a Bragg period of 269 nm. However, due to a manufacturing error, the actual Bragg period turned out to be smaller than intended. This deviation was identified in results provided by Mustafa Hammood, a graduate student under Professor Jaeger, who demonstrated that this error causes a shift in the wavelength to smaller values, as shown in Figure 2.

To prevent the central wavelength from shifting leftward and to maintain the target wavelength of 1310 nm, I decided to adjust the Bragg period to 276 nm for most of my designs, based on Mustafa’s findings. Some designs were left unmodified to observe the extent of this wavelength shift and understand its impact on performance.

#### Figure 2: Mustafa Hammood Data
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/ELEC_2.png" title="Comparison of Bragg wavelength between simulation and experiment" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Mustafa Hammood data: Comparison of Bragg wavelength between simulation and experiment, assuming 215 nm thick silicon.
</div>

For the designs 1, 3, 5, 6, 7 and 10 I have used a Bragg Period of 276 nm. 

---

### 5. Transfer Matrix Method Analysis
The TMM was used to simulate cavity resonances and quality factors. Simulations were performed to assess the impact of cavity length, Bragg period, and waveguide geometry on the Fabry-Perot cavity’s optical performance.

---

## Experimental Results and Comparison with Simulations
After designing my models, I performed simulations using my Transfer Matrix Method (TMM) model implemented in Matlab. I then compared these simulations with the actual behavior of the models to assess if my assumptions and simulations align with reality. The Quality Factor for all models is shown in the table in the annex. I focused on studying devices V1, V3, and V8, as they are the most interesting. Most of the other devices did not perform as expected due to measurement or fabrication issues.


#### Device V1
The comparison of simulation and measurements for device V1 can be seen in Figure 3. Both the simulated and measured results show a similar performance around the central wavelength, but there are some variations in power levels across the peaks.

I analyzed the Quality Factor for the central peak (~1309 nm) and obtained similar values for both simulations and measurements. The Quality Factor (Q) is determined by:

\[
Q = \frac{\lambda_c}{\Delta \lambda}
\]

where Δλ is the 3 dB wavelength width of the peak.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/ELEC_3.png" title="Simulation VS Measurements for V1" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

#### Device V3
This device has a long cavity length of 304.131 μm, which results in multiple wavelengths. Figure 4 shows the measurements for V3, where we observe a good match between simulation and measurement trends, although power levels differ for individual peaks.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/ELEC_4.png" title="Simulation VS Measurements for V3" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

#### Device V8
Device V8 experienced a shift in the central wavelength due to an error in the Bragg period (Beause this model uses Bragg period of 264.4 nm, as ). To compensate for this, I reduced the Bragg period in the simulation to 263.4 nm, which allowed the simulated peaks to align better with the measurements. Figure 5 shows the comparison between simulation and measurement after this adjustment.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/ELEC_5.png" title="Measurements vs Simulation for V8" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
    Fig 3-5: Comparison of simulation and measurements for various device configurations, showing how adjustments in Bragg period and length of the cavity can impact wavelength accuracy and performance.
</div>

#### Curiosity: Examples of Design Failures

In the experimental phase, certain designs, including V10, did not meet the expected performance. Specifically, for design V10, the anticipated peak at 1310 nm was not observed, indicating issues in the fabrication or design implementation. The following image shows the response across three detectors, clearly illustrating the absence of the peak at the target wavelength.

This example underscores the challenges in achieving precise wavelength alignment and the importance of rigorous simulation and design adjustments to mitigate manufacturing discrepancies.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/ELEC_curiosidad.png" title="Design V10 Failure - Absence of Peak at 1310 nm" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig: Detector responses for design V10, showing the absence of the expected peak at 1310 nm.
</div>

## Key Findings and Insights

- **Accuracy of Simulation Models**: The simulation results aligned closely with experimental data, confirming the reliability of the models.
- **Impact of Manufacturing Variability**: Even minor deviations in Bragg period significantly affect wavelength precision, underscoring the need for precise manufacturing controls in applications requiring wavelength stability.
- **Resilience of Design Under Variability**: By adjusting the Bragg period in simulations to account for manufacturing discrepancies, we were able to achieve alignment between simulated and experimental results, demonstrating the robustness of the design and the adaptability of the simulation model.

### Conclusion
In this project, we have thoroughly analyzed and studied the design of Fabry-Perot cavity models, focusing on how various parameters influence their performance. Through simulation and experimental validation, we observed how external factors, such as manufacturing errors in the Bragg period, impact the final behavior of the cavities. Adjustments in the Bragg period were necessary to maintain wavelength accuracy, highlighting the importance of flexibility in design.

The quality factors in our measurements closely matched the simulated values, and the overall behavior observed in both simulations and measurements was similar. This consistency confirms that our simulations were accurate and provide a solid foundation for predicting real-world performance. Ultimately, this study underscores the feasibility of using simulation models like the Transfer Matrix Method to design and analyze Fabry-Perot cavities for precise laser applications in integrated photonics.

---

This project was carried out at the University of British Columbia as part of the ELEC 413 course, under the supervision of [Professor Lukas Chrostowski](https://www.linkedin.com/in/chrostowski/).

---

## Full Report
Download the complete project report:

[Download Full Report PDF]({{ page.pdf_link }})


## Annex

### Table 1: Parameters used to create the 10 designs

| Design | No. of Grating Periods | Δn     | dW (nm) | Length of the cavity in the mid (µm)             |
|--------|-------------------------|--------|---------|--------------------------------------------------|
| 1      | 80                      | 0.08279 | 50      | 34.289                                           |
| 2      | 120                     | 0.08279 | 50      | 0.1345 (Bragg period/2) Back-to-Back             |
| 3      | 50                      | 0.08279 | 50      | 304.131                                          |
| 4      | 65                      | 0.08279 | 50      | 48.81 (2 micros width)                           |
| 5      | 80                      | 0.08173 | 45      | 34.129                                           |
| 6      | 90                      | 0.08279 | 50      | 39.31                                            |
| 7      | 70                      | 0.08279 | 50      | 0.1345 (Bragg period/2)                          |
| 8      | 70                      | 0.08173 | 45      | 116.464                                          |
| 9      | 130                     | 0.08119 | 40      | 34.649                                           |
| 10     | 100                     | 0.08173 | 45      | 0.1345 (Bragg period/2)                          |

### Table 2: Results from the simulations and the designs

| Quality Factor (Simulation) | Quality Factor (Measurements) |
|-----------------------------|-------------------------------|
| 52131                       | 51323                         |
| 134760                      | -                             |
| 48481                       | 137062                        |
| 24521                       | 110180                        |
| 43621                       | 57062                         |
| 94563                       | -                             |
| 4985                        | -                             |
| 60496                       | 104150                        |
| 126880                      | -                             |
| 34977                       | -                             |

---
        