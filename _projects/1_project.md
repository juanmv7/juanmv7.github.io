---
layout: page
title: Utilization Analysis in Asynchronous TSN Networks for Industry 4.0
description: Evaluation of TSN network performance in Industry 4.0 through maximum utilization analysis for delay-sensitive traffic.
img: assets/img/tsn_pilares.png  # Change to your selected background image path
importance: 1
category: Telecommunications
related_publications: false
df_link: /assets/pdf/NLP_project.pdf 
---
## Abstract

This project analyzes the performance and feasibility of asynchronous TSN networks for their implementation in Industry 4.0. Through a simulator, it evaluates the capacity of these networks to meet the strict latency and performance requirements demanded by modern industry.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/foto_TSN.png" title="TSN architecture Model" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/traffic_scheduler2.png" title="TSN traffic scheduler" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5gacia.png" title="TSN Control Gate" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    On the left, a fully centralized TSN model; in the center, a network diagram with traffic scheduling; on the right, a control gate list allowing transmission of traffic queue 7 only at T0, and all other traffic queues at T1.
</div>

In addition to the simulator development, strategies were implemented to optimize resource allocation in industrial networks, thus ensuring that critical traffic maintains minimal latency and optimal performance.

<div class="row justify-content-sm-center">
    <div class="col-md-6 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/PorPCP_Prior.jpg" title="Analysis by PCP" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-md-6 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/ProFlujos_Prior.jpg" title="Flow-Based Analysis" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Comparison between traffic class-based (PCP) and individual flow analysis. The PCP methodology groups traffic flows with similar characteristics, while individual flow analysis allows for more precise differentiation, albeit with a longer execution time.
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/Excel_Ut.png" title="ATS Maximum Utilization" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Impact of the Cyclic-Synchronous traffic percentage on ATS utilization. As the percentage of this type of traffic increases, maximum utilization decreases, especially in configurations managing multiple ATSs, due to the higher delay requirements of these flows.
</div>

Dividing and treating each flow individually in the algorithm allows for higher ATS utilization compared to the macro-flow approach, albeit with a higher execution time. However, as traffic with high delay requirements, like Cyclic-Synchronous traffic, increases, the maximum utilization decreases since the algorithm struggles to manage a high volume of flows under these conditions.

This project demonstrates how TSN networks can adapt to the demands of Industry 4.0, enabling a robust and scalable communication infrastructure for future industrial applications.


## Full Report
You can download the complete report document via the following link:

[Download Full Report PDF]({{ page.pdf_link }})