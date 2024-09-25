
# Climate Change Misinformation Analysis on Reddit

This project focuses on analyzing contrarian claims related to climate change on Reddit. The project uses both supervised classification models (trained on the CARDs dataset) and unsupervised topic modeling (LDA and BERTopic) to extract insights and themes. The combination of these techniques helps in understanding the framing and spread of misinformation.

## Project Structure

```
├── cards_training.ipynb        # Model training and classification using the CARDs dataset.
├── cards_evaluation.ipynb       # Evaluation of trained classification models.
├── cards_inference.ipynb        # Running inference on new Reddit data.
├── Prepare CSV.ipynb            # Preprocessing of raw Reddit data into clean CSV format.
├── topic_modeling.ipynb         # LDA and BERTopic topic modeling.
├── topic_modeling_reddit.ipynb  # Focused topic modeling for Reddit data.
├── ensemble.py                  # Ensemble classification implementation.
├── logistic.py                  # Logistic regression classification implementation.
├── README.md                    # Project documentation (this file).
```

## Steps

### 1. Data Preparation
   - **Script:** `Prepare CSV.ipynb`
   - **Description:** This notebook is responsible for cleaning and preprocessing the raw Reddit dataset. The key steps include:
     - Removing unnecessary characters and links.
     - Text normalization (lowercasing, removing stop words, etc.).
     - Outputting a cleaned CSV file, ready for further analysis.

### 2. Model Training
   - **Script:** `cards_training.ipynb`
   - **Description:** This notebook trains supervised machine learning models using the CARDs dataset to classify Reddit posts into predefined contrarian categories. Key steps include:
     - Loading and exploring the CARDs dataset.
     - Applying various text vectorization techniques (TF-IDF, Word2Vec).
     - Training different machine learning classifiers (e.g., Logistic Regression, Ensemble models).

### 3. Model Evaluation
   - **Script:** `cards_evaluation.ipynb`
   - **Description:** This notebook evaluates the performance of the trained models. Key evaluation metrics such as accuracy, F1-score, precision, and recall are computed. The steps include:
     - Loading test data.
     - Predicting the labels on test data using trained models.
     - Generating classification reports and confusion matrices.

### 4. Inference on New Reddit Data
   - **Script:** `cards_inference.ipynb`
   - **Description:** This notebook is used for running predictions on new, unseen Reddit data using the trained models. The process involves:
     - Loading new Reddit data.
     - Preprocessing the text data.
     - Predicting contrarian categories for each Reddit post.

### 5. Topic Modeling
   - **Script:** `topic_modeling.ipynb`
   - **Description:** This notebook applies two topic modeling techniques, LDA and BERTopic, to identify key themes in the Reddit data. Steps include:
     - Running LDA to discover 10–20 key topics.
     - Using BERTopic for context-rich topic extraction.
     - Assigning topics to each Reddit post and analyzing the results.

### 6. Reddit-Specific Topic Modeling
   - **Script:** `topic_modeling_reddit.ipynb`
   - **Description:** A more focused version of topic modeling, specifically analyzing Reddit discussions around climate change. The steps include:
     - Loading cleaned Reddit data.
     - Applying LDA and BERTopic on the Reddit dataset.
     - Analyzing dominant topics and their relevance to misinformation.

### 7. Ensemble and Logistic Regression Models
   - **Script:** `ensemble.py`, `logistic.py`
   - **Description:** These Python scripts implement the machine learning models used in classification tasks:
     - **ensemble.py:** Contains the code for ensemble models used for classification.
     - **logistic.py:** Implements logistic regression for classifying Reddit posts.

## Conclusion

This project provides a comprehensive approach to understanding the spread and nature of climate change misinformation on Reddit through both classification and topic modeling. The combination of these methods helps to uncover the themes and framing used in contrarian claims and how misinformation is propagated on social media.
