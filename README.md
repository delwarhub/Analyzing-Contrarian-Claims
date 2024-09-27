# Analyzing Contrarian Claims on Climate Change Using Reddit Data

This project focuses on analyzing contrarian claims related to climate change on Reddit. The project uses supervised classification models (trained on the CARDs dataset) and unsupervised topic modeling (LDA and BERTopic) to extract insights and themes. Combining these techniques helps understand the framing and spread of misinformation.

## Project Structure

```
Climate-Change-Misinformation-Reddit/
├── data/                              
│   ├── Mapped_Topic.csv          
├── training/                          
│   ├── test.csv          
│   ├── training.csv      
│   ├── valid.csv               
├── roberta/                         
│   ├── cards_training.ipynb           
│   ├── cards_evaluation.ipynb         
│   ├── cards_inference.ipynb          
│   ├── topic_modeling_reddit.ipynb     
├── output/                             
│   ├── predictions/                   
│   │   ├── reddit_predictions.csv     
│   └── reports/                     
│       ├── BERT Cosine Similarity.png   
│       ├── Distribution of cosine similarity scores for each technique.png
│       ├── Manual Inspection.png     
│       ├── Model Performance Metrics.png       
│       ├── Percentage of Rows with Cosine Similarity (BERT) _ 0.5 by Mapped Claim.png       
│       ├── TF-IDF Cosine Similarity.png       
│       ├── Word2Vec Cosine Similarity.png        
├── README.md                        

```

## Steps

### 1. Data Preparation and Inference on New Reddit Data
   - **Script:** `cards_inference.ipynb`
   - **Description:** This notebook is responsible for cleaning and preprocessing the raw Reddit dataset. It is also used for running predictions on new, unseen Reddit data using the trained models. The key steps include:
     - Removing unnecessary characters and links.
     - Text normalization (lowercasing, removing stop words, etc.).
     - Providing code to infer classes in unseen data.
     - Outputting a cleaned CSV file, ready for further analysis.
     - Predicting contrarian categories for each Reddit post.

### 2. Model Training
   - **Script:** `cards_training.ipynb`
   - **Description:** This notebook trains supervised machine learning models using the CARDs dataset to classify Reddit posts into predefined contrarian categories. The dataset used in this process is available [here](https://drive.google.com/uc?export=download&id=14exmlYCT3-K2byYHFFrShAIYiemJQroi). After unzipping the file, you will find a data directory with two subfolders:
     - `analysis/`: Data replicating the base paper's main analysis.
     - `training/`: Data used to train and test the classifier developed in the paper.

   Key steps include:
     - Loading and exploring the CARDs dataset.
     - Applying various text vectorization techniques (TF-IDF, Word2Vec).
     - Including the code (and hyperparameters) used to fit the CARDS model.
     - Training different machine learning classifiers (e.g., Logistic Regression, Ensemble models).

### 3. Model Evaluation
   - **Script:** `cards_evaluation.ipynb`
   - **Description:** The pre-trained model weights for the RoBERTa model used in the paper are available [here](https://drive.google.com/uc?export=download&id=1cbASuoLNY-kJcm7hUFLTGYzblZFzxaVo). This notebook evaluates the performance of the trained models. The project uses the `simpletransformers` library to train, test, and perform inference for the RoBERTa side of the model. For installation instructions on the `simpletransformers` library, refer to [here](https://simpletransformers.ai/docs/installation/). 

   Key evaluation metrics, such as accuracy, F1-score, precision, and recall, are computed. The steps include:
     - Loading test data.
     - Providing code to evaluate model performance on held-out data.
     - Predicting labels on test data using the trained models.
     - Generating classification reports and confusion matrices.

### 4. Reddit-Specific Topic Modeling
   - **Script:** `topic_modeling_reddit.ipynb`
   - **Description:** This notebook applies two topic modeling techniques, LDA and BERTopic, to identify key themes in the Reddit data. The steps include:
     - Loading cleaned Reddit data.
     - Running LDA to discover 17 key topics.
     - Applying LDA and BERTopic on the Reddit dataset.
     - Analyzing dominant topics and their relevance to misinformation.

## Conclusion

This project provides a comprehensive approach to understanding the spread and nature of climate change misinformation on Reddit through both classification and topic modeling. The combination of these methods helps to uncover the themes and framing used in contrarian claims and how misinformation is propagated on social media.

## Reference

This repository makes available the training data and main code used to train the classifier described in the following [paper](https://osf.io/preprints/socarxiv/crxfm/):
1. "Computer-assisted detection and classification of misinformation about climate change" by Travis G. Coan, Constantine Boussalis, John Cook, and Mirjam Nanko.


