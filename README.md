

## Project Overview

This project focuses on sentence classification using the PubMed 200k RCT dataset. 

We developed two models: a baseline model using a bag of words approach and an advanced model utilizing pre-trained biomedical word embeddings.

## Key Achievements

* **Dataset Reduction**: Reduced the dataset size for manageable computation without losing data integrity.
  * Original Size:
    * Train: 1,777,456
    * Validation: 28,932
    * Test: 29,493
  * Reduced Size:
    * Train: 8,887
    * Validation: 1,928
    * Test: 1,966

* **Class Imbalance Management**: Tackled class imbalance issues using oversampling, undersampling, and SMOTE, though these methods did not significantly impact model performance.

## Models and Techniques

### Baseline Model: using TF-IDF
* **Preprocessing**:
  * Implemented tokenization and lemmatization.
  * Utilized a TF-IDF vectorizer for numerical transformation of text data.
* **Parameter Tuning**:
  * Conducted a Grid Search CV and manual parameter exploration.
* **Tested Models**:
  * Linear SVC
  * GradientBoostingClassifier
  * Random Forest
* **Custom Stopwords List**:
  * Created and tested a custom stopwords list, which did not significantly improve model performance.

### Advanced Model: Pre-trained Biomedical Word Embeddings
* **Pre-trained Embeddings**:
  * Utilized a pre-trained model from Hugging Face, trained on clinical case reports with 100-dimensional embeddings.
* **Vector Representation**:
  * Represented sentences as 100-dimensional vectors by averaging word embeddings.
* **Tested Models**:
  * Linear SVC
  * Random Forest
  * GradientBoostingClassifier
* **Feature Engineering**:
  * **Sentence Length**: Added sentence length as a feature, resulting in a slight improvement.
  * **POS Tagging**: Incorporated Part-of-Speech tagging, which improved accuracy by 0.02.

## Evaluation and Comparison

* **Consistent F1 Scores**:
  * Baseline Model: ~0.71
  * Advanced Model: ~0.73

## Results and Discussion

* **Challenges and Limitations**:
  * Performance plateau likely due to data constraints.
  * Potential for improvement with more data, constrained by current computational resources.

Despite these challenges, the achieved results are commendable given the computational limitations.


## Next Steps

Explore advanced feature engineering methods such as Named Entity Recognition (NER) and Semantic Similarity.
