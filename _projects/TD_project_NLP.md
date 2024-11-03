---
layout: page
title: Analysis of Research Projects with NLP techniques
description: Developing a robust pipeline for data preprocessing and text vectorization for classification tasks.
img: assets/img/header_NLP_project.png 
importance: 1
category: Machine Learning
related_publications: false
pdf_link: /assets/pdf/NLP_project.pdf  # Place the PDF in the assets/pdf folder

---
## Abstract
This project focuses on analyzing and classifying research project descriptions through various Natural Language Processing (NLP) techniques. The main goal is to process and classify text data to extract meaningful insights from a large dataset of research projects.

Our approach involves several key steps:

1. **Data Preprocessing Pipeline**:
   We built a preprocessing pipeline to clean and standardize the text data, removing irrelevant information such as HTML tags and URLs, expanding contractions, and lemmatizing terms. This step is essential to prepare the data for accurate vector representation. The pipeline is versatile and can be extended to other text classification tasks.

2. **Text Vectorization Techniques**:
   We implemented three vectorization methods to convert text into numerical representations:
   - **TFIDF (Term Frequency-Inverse Document Frequency)**: Captures the importance of terms across documents.
   - **Word2Vec**: Provides dense vector embeddings with context-based similarities.
   - **BERT (Bidirectional Encoder Representations from Transformers)**: Uses transformer-based embeddings for deeper contextual understanding.

3. **Classification Models**:
   Using the preprocessed and vectorized data, we trained classification models, including Random Forest (via Scikit-learn) for traditional vectorizations and fine-tuned BERT for deep learning-based classification. These models were evaluated to determine the most effective approach for categorizing research projects.

---
#### Insights
TFIDF, Word2Vec, and BERT were compared for performance. Word2Vec showed improved context-based classification over TFIDF, while BERT provided the highest accuracy due to its robust handling of semantic relationships.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/tabla_NLP.png" title="Classification Results" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Comparison of classification results across different vectorization methods.
</div>

The code in this project is designed for NLP analysis of research summaries but can be adapted for other domains by modifying key steps in the data preprocessing and vectorization process:

1. **Adjust Data Preprocessing**: 
Adapt the code to accommodate different fields or text structures and adjust tokenization, stopword removal, or text normalization settings based on the characteristics of the new text data

2. **Update Vectorization and Embedding Methods**:
Select embeddings relevant to the new context, such as **BioBERT** for biomedical text or **SciBERT** for scientific literature.

3. **Revise Classification and Clustering Models**:
Adapt or retrain classification algorithms based on the new data categories. For example, in a healthcare application, categories might include disease types or treatment methods.

---
This project exemplifies the integration of data preprocessing, vectorization, and classification to achieve efficient categorization of large-scale textual data.

---
This project was carried out in collaboration with [Elena Almagro](https://www.linkedin.com/in/elena-almagro-azor-a06942217/) and [Mario Golbano](https://www.linkedin.com/in/juan-munoz-villalon/).

---
## Full Report
You can download the complete report document via the following link:

[Download Full Report PDF]({{ page.pdf_link }})

---
## GitHub Repository
You can find the Python notebook for this project, with its results and the whole process on [GitHub](https://github.com/mariogolbano/Research-projects-analysis-NLP/tree/main)

