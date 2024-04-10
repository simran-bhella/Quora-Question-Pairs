# Quora Question Pairs Project

## Contributors
- Ryan Niiya
- Simranjit Bhella
- Leo Lu

## Introduction
In the quest to streamline the user experience on Quora, a platform known for its community-driven Q&A format, our project addresses a common concern: duplicate questions. These not only clutter searches but also dilute the quality of answers. Leveraging machine learning algorithms to identify and flag these duplicates presents a solution to enhance content discoverability and efficiency on Quora.

## Dataset
The Quora Question Pairs (QQP) dataset, publicly released by Quora, comprises over 400,000 question pairs with varying statuses of duplication. This dataset is instrumental for testing prediction models on identifying duplicates, with each row detailing question pairs alongside a label indicating their duplicate status. Noteworthy is the dataset's inclination towards negative labels and its meticulous manual sanitization.

## Methodology
Our approach builds on a baseline that assesses 30 arbitrary features across seven classifiers, using accuracy and F1-Score as primary evaluation metrics. This baseline, rooted in feature engineering, sparked our curiosity about the potential of Pretrained Language Models (PLMs) like BERT and GPT-2. Our methodology involved preprocessing, training, and testing on the QQP dataset to evaluate these models against established baselines.

### BERT Model
Chosen for its bidirectional context and transformer architecture, BERT was pre-trained on a vast corpus of text. Despite its moderate performance and conservative duplicate prediction tendency, it underscored the need for leveraging BERT's full potential more effectively.

**Results:**
- Accuracy: 0.67
- Precision: 0.57
- Recall: 0.50
- F1 Score: 0.53

### GPT-2 Model
Selected for its unidirectional autoregressive model characteristics, GPT-2's comparison with BERT was integral to our research. However, it struggled significantly in identifying duplicates, hinting at the limitations of its unidirectional nature.

**Results:**
- Accuracy: 0.64
- Precision: 0.68
- Recall: 0.07
- F1 Score: 0.12

## Baseline Comparison
Our exploration included a variety of traditional machine learning models, with the baseline demonstrating superior performance. This success is attributed to comprehensive feature engineering encompassing basic, fuzzy, and distance features, and optimization via Deep Neural Network architectures, achieving over 80% accuracy.

## Challenges
A significant hurdle was model fine-tuning, hampered by the dataset's size and computational limitations. Even with access to Google Colab's T4 GPU, an RTX 4080, and an M1 Mac, the process proved to be exceedingly time-consuming and often impractical. Consequently, we utilized a fraction of the dataset for training, validation, and testing, and explored cloud computing services like Databricks for enhanced computational capacity.

## Conclusions
Our findings reveal BERT's superiority over GPT-2 for this task, attributable to its bidirectional nature. Nonetheless, the baseline models, bolstered by intricate feature engineering and higher computational resources, outperformed both PLMs. This suggests that for specific tasks like duplicate question identification, domain-specific feature engineering might be more effective than the more generalized approach offered by PLMs. The challenges in training, due to computational constraints, underscore the importance of adequate resources for model refinement and experimentation.

## References
- N. Ansari and R. Sharma, “Identifying Semantically Duplicate Questions Using Data Science Approach: A Quora Case Study.” [Available online](https://arxiv.org/ftp/arxiv/papers/2004/2004.11694.pdf)
