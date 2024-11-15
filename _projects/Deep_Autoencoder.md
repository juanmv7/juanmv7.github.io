---
layout: page
title: Deep Autoencoder for Denoising Noisy Images
description: Development of a deep autoencoder model to reconstruct clean images from noisy inputs, improving image quality in datasets like MNIST and FMNIST.
img: assets/img/autoencoder_denoising_header.png  # Path for header image
importance: 1
category: Machine Learning
related_publications: false
pdf_link: /assets/pdf/Deep_Autoencoder.pdf  # Link to the full project report
---

## Abstract
This project explores the development and performance of a deep autoencoder for denoising noisy images. Using dense neural networks, the autoencoder was trained on the MNIST and FMNIST datasets to reconstruct clean images from noisy inputs, providing insights into dimensionality reduction, noise handling, and optimal model configurations.

## Key Components

1. **Autoencoder Architecture**:
   - A fully connected neural network designed for dimensionality reduction.
   - Utilizes an encoder-decoder structure, with ReLU activation functions and Mean Squared Error (MSE) loss.
   - Evaluated across multiple configurations with varying layers and projected dimensions (15, 30, 50, 100), demonstrating the balance between dimensionality and reconstruction quality.

2. **Results Analysis**:
   - **Loss over Epochs**: Observed decreasing loss over epochs across both datasets, highlighting the autoencoder's learning progression.
   - **Peak Signal-to-Noise Ratio (PSNR)**: Best results achieved with a projected dimension of 50 for MNIST and FMNIST, where increased depth did not necessarily improve performance.
   - **Regularization**: Lasso and dropout regularization tested, with dropout showing reduced PSNR, indicating the model's sensitivity to node deactivation.

3. **Denoising Autoencoder**:
   - Built on the optimal configuration from the autoencoder study (3-layer model, 50 projected dimensions).
   - Trained on images with Gaussian noise of varying variances to learn robust representations for denoising tasks.

<div class="row justify-content-sm-center">
    <div class="col-md-6 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/psnr_mnist.png" title="MNIST dataset" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-md-6 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/psnr_fmnist.png" title="FMNIST dataset" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    PSNR across varying dimensions in the autoencoder.
</div>

---

## Denoising Results

Using Gaussian noise, the denoising autoencoder was trained for images with different noise variances (0.1, 0.2, 0.5, 1, 2). Best performance was noted with lower variance noise, yielding high-quality reconstructed images that closely resembled the original inputs, even with higher noise that the one it was trained with.

<div class="row justify-content-sm-center">
    <div class="col-md-6 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/denoising_numbers.png" title="MNIST dataset" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-md-6 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/denoising_clothes.png" title="FMNIST dataset" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
    Reconstructed images from the denoising autoencoder (Gaussian noise with variance 1) with both datasets.
</div>

---

## Conclusion and Future Applications

The developed autoencoder model has demonstrated its effectiveness in denoising images, offering a robust solution for applications where image clarity is crucial. This technique has promising potential across various fields where image quality may be degraded by noise or other visual artifacts. 

### Further Adaptations

Moving forward, the autoencoder model could be refined to recognize and filter specific types of noise, enhancing its adaptability to different environments. This could involve training the model to selectively remove particular noise patterns, allowing it to serve as a more specialized tool for high-sensitivity applications.

#### Integration with Foundation Models for Wireless Communications

Beyond imaging, the autoencoder's denoising capabilities present valuable applications in wireless communications. Specifically, this framework could be adapted and integrated into the "Foundation Models for Wireless Communications" project I am currently working in. By training the autoencoder to handle noisy or interference-prone signals, it could serve as a preprocessing step to enhance signal quality, separating meaningful data from background interference. This adaptation would contribute to improved signal clarity in challenging environments, supporting further advancements in signal processing and robust communication technologies.

In summary, this project not only provides a viable solution for image denoising but also paves the way for broader applications, particularly in enhancing the quality and clarity of data in both visual and communication fields.

---
This project was carried out in collaboration with [Elena Almagro](https://www.linkedin.com/in/elena-almagro-azor-a06942217/) and [Mario Golbano](https://www.linkedin.com/in/mario-golbano-corzo/).

---
## Full Report
You can download the complete report document via the following link:

[Download Full Report PDF]({{ page.pdf_link }})

