---
layout: page
title: Sentiment Analysis Using RNNs with and without Attention
description: Comparing two RNN architectures for sentiment analysis on financial news data.
img: assets/img/header_RNN_attention.png  # Update this with your header image path
importance: 1
category: Machine Learning
related_publications: false
---

## Abstract
This project explores the application of Recurrent Neural Networks (RNNs) to perform sentiment analysis on financial news data. The primary objective is to classify sentences from the **Financial Phrase Bank** into **Positive/Neutral** or **Negative** sentiment categories. The project compares two RNN architectures:

1. **RNN without Attention**
2. **RNN with Attention Mechanism**

Both models were evaluated using the **ROC Curve** and **AUC Score** to measure their performance. Additionally, an **MLP baseline model** using mean embeddings was included to provide a reference point.

---

## Model Descriptions

### Model 1: RNN without Attention
The first model uses a basic **RNN with LSTM cells** to process sequences of word embeddings and predict sentiment labels based on the final state of the LSTM.

#### Key Layers:
- **LSTM Layer**: Processes the input sequences and generates hidden states.
- **Dropout Layer**: Reduces overfitting by randomly dropping units during training.
- **Fully Connected Layer**: Converts the final hidden state to output logits.
- **LogSoftmax Activation**: Converts logits to log probabilities for classification.

#### Results
The RoC curve obtained is shown below.
<div class="row justify-content-sm-center">
    <div class="col-md-6 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/roc_curve.png" title="RoC Curve for the RNN model without Attention Mechanism" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
The **AUC for RNN without Attention** is 0.92. This is a very good value at first.

---

### Optional Experiment: MLP Classifier
In addition to the RNN, the project includes an optional experiment using a **Multi-Layer Perceptron (MLP)** classifier to predict sentiment labels based on the mean of word embeddings.

<div style="display: flex; justify-content: center;">
    <table style="border-collapse: collapse; width: 50%; text-align: center;">
        <thead>
            <tr>
                <th style="border: 1px solid #ddd; padding: 8px;">Layer Type</th>
                <th style="border: 1px solid #ddd; padding: 8px;">Neurons</th>
                <th style="border: 1px solid #ddd; padding: 8px;">Activation Function</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td style="border: 1px solid #ddd; padding: 8px;">Fully Connected 1</td>
                <td style="border: 1px solid #ddd; padding: 8px;">10</td>
                <td style="border: 1px solid #ddd; padding: 8px;">ReLU</td>
            </tr>
            <tr>
                <td style="border: 1px solid #ddd; padding: 8px;">Fully Connected 2</td>
                <td style="border: 1px solid #ddd; padding: 8px;">5</td>
                <td style="border: 1px solid #ddd; padding: 8px;">ReLU</td>
            </tr>
            <tr>
                <td style="border: 1px solid #ddd; padding: 8px;">Output Layer</td>
                <td style="border: 1px solid #ddd; padding: 8px;">2</td>
                <td style="border: 1px solid #ddd; padding: 8px;">LogSoftmax</td>
            </tr>
        </tbody>
    </table>
</div>


#### Results
The RoC curve obtained is shown below.
<div class="row justify-content-sm-center">
    <div class="col-md-6 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/roc_curve_MLP.png" title="RoC Curve for the MLP classifier" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
The **AUC for RNN without Attention** is 0.76 which is shows a much poorer performance than the RNN model, which was expected. 

---

### Model 2: RNN with Attention
The second model incorporates an **attention mechanism**, which allows the network to focus on specific parts of the input sequence when making predictions. This mechanism improves the model's interpretability and overall performance.

#### Key Layers:
- **LSTM Layer**: Generates hidden states for each token in the input sequence.
- **Attention Mechanism**: Calculates attention weights to identify important tokens.
- **Dropout Layer**: Reduces overfitting.
- **Fully Connected Layer**: Converts the context vector to output logits.


#### Results
The RoC Curve obtained is shown below.
<div class="row justify-content-sm-center">
    <div class="col-md-6 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/roc_curve_Attention.png" title="RoC Curve for the RNN model with Attention Mechanism" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
The **AUC for RNN without Attention** is 0.95, which has improved from the model without Attention.

---

## Dataset Details
The dataset used in this project is the **Financial Phrase Bank**, which contains 4,840 sentences from financial news articles labeled as **Positive**, **Negative**, or **Neutral**. The labels were adjusted for this project to combine **Positive** and **Neutral** into a single category.

### Dataset Summary
<div style="display: flex; justify-content: center;">
    <table style="border-collapse: collapse; width: 70%; text-align: center;">
        <thead>
            <tr>
                <th style="border: 1px solid #ddd; padding: 10px;"><strong>Attribute</strong></th>
                <th style="border: 1px solid #ddd; padding: 10px;"><strong>Description</strong></th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td style="border: 1px solid #ddd; padding: 8px;">Dataset Name</td>
                <td style="border: 1px solid #ddd; padding: 8px;">Financial Phrase Bank</td>
            </tr>
            <tr>
                <td style="border: 1px solid #ddd; padding: 8px;">Number of Sentences</td>
                <td style="border: 1px solid #ddd; padding: 8px;">4,840</td>
            </tr>
            <tr>
                <td style="border: 1px solid #ddd; padding: 8px;">Categories</td>
                <td style="border: 1px solid #ddd; padding: 8px;">Positive/Neutral, Negative</td>
            </tr>
            <tr>
                <td style="border: 1px solid #ddd; padding: 8px;">Source</td>
                <td style="border: 1px solid #ddd; padding: 8px;">
                    <a href="https://www.researchgate.net/profile/Pekka-Malo/publication/251231364_FinancialPhraseBank-v10/data/0c96051eee4fb1d56e000000/FinancialPhraseBank-v10.zip" target="_blank">
                        Financial Phrase Bank
                    </a>
                </td>
            </tr>
        </tbody>
    </table>
</div>


---

## Results and Comparison
The performance of all models was evaluated using the **ROC Curve** and **AUC Score**.

<div style="display: flex; justify-content: center;">
    <table style="border-collapse: collapse; width: 50%; text-align: center;">
        <thead>
            <tr>
                <th style="border: 1px solid #ddd; padding: 10px;">Model</th>
                <th style="border: 1px solid #ddd; padding: 10px;">AUC Score</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td style="border: 1px solid #ddd; padding: 8px;">RNN without Attention</td>
                <td style="border: 1px solid #ddd; padding: 8px;">0.92</td>
            </tr>
            <tr>
                <td style="border: 1px solid #ddd; padding: 8px;">MLP Model</td>
                <td style="border: 1px solid #ddd; padding: 8px;">0.76</td>
            </tr>
            <tr>
                <td style="border: 1px solid #ddd; padding: 8px;">RNN with Attention</td>
                <td style="border: 1px solid #ddd; padding: 8px;">0.95</td>
            </tr>
        </tbody>
    </table>
</div>


Observing these results, we can conclude:

- The **MLP classifier** does not perform well compared to RNN-based models.
- The **RNN with Attention** significantly outperforms the **RNN without Attention**, demonstrating the effectiveness of attention mechanisms in improving sentiment analysis.

---
This project was carried out in collaboration with [Elena Almagro](https://www.linkedin.com/in/elena-almagro-azor-a06942217/) and [Mario Golbano](https://www.linkedin.com/in/mario-golbano-corzo/).

---

## GitHub Repository
You can find the Python notebooks and pre-trained models for this project on [GitHub](https://github.com/mariogolbano/RNN_setiment_analysis_with_Attention).