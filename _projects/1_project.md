---
layout: page
title: Análisis de Utilización en Redes TSN Asíncronas para Industria 4.0
description: Evaluación del rendimiento de redes TSN en la Industria 4.0 mediante análisis de utilización máxima para tráfico sensible al retardo.
img: assets/img/tsn_pilares.png  # Cambia a la ruta de la imagen de fondo que elijas
importance: 1
category: Telecommunications
related_publications: false
---

Este proyecto analiza el rendimiento y la viabilidad de redes TSN asíncronas para su implementación en Industria 4.0. A través de un simulador, evalúa la capacidad de estas redes para cumplir con los estrictos requisitos de latencia y rendimiento que exige la industria moderna.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/foto_TSN.png" title="TSN architecture Model" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/traffic_scheduler.png" title="TSN traffic scheduler" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5gacia.png" title="TSN  Control Gate" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    A la izquierda, modelo completamente centralizado TSN; en el centro, red esquematizada con planificación del tráfico; a la derecha, lista de control de puertas que permite la transmisión de la cola
de tráfico 7 sólo en T0 y todas las demás colas de tráfico en T1.
</div>

Además del desarrollo del simulador, se implementaron estrategias para optimizar la asignación de recursos en redes industriales, garantizando así que el tráfico crítico mantenga una latencia mínima y un rendimiento óptimo.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/PorPCP_Prior.jpg" title="Análisis por PCP" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/ProFlujos_Prior.jpg" title="Análisis por Flujos" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Comparativa entre el análisis por clases de tráfico (PCP) y por flujos individuales. La metodología PCP agrupa flujos de tráfico con características similares, mientras que el análisis por flujos individuales permite una diferenciación más precisa, aunque a costa de un mayor tiempo de ejecución.
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/Excel_Ut.png" title="Utilización máxima del ATS" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Impacto del porcentaje de tráfico Cyclic-Synchronous en la utilización del ATS. A medida que aumenta el porcentaje de este tipo de tráfico, la utilización máxima se reduce, especialmente en configuraciones que manejan múltiples ATS, debido a los mayores requisitos de retardo de estos flujos.
</div>

Dividir y tratar cada flujo de forma individual en el algoritmo permite una mayor utilización del ATS en comparación con el enfoque de macro-flujos, aunque a costa de un tiempo de ejecución más elevado. Sin embargo, al aumentar el tráfico con altos requisitos de retardo, como el Cyclic-Synchronous, la utilización máxima se reduce, ya que el algoritmo encuentra dificultades para gestionar un volumen elevado de flujos en estas condiciones.

Este proyecto muestra cómo las redes TSN pueden adaptarse a las exigencias de la Industria 4.0, haciendo posible una infraestructura de comunicación robusta y escalable para futuras aplicaciones industriales.
