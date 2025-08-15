# Project Title
- Twitter Disaster Tweets Classification using LSTM Neural Networks
![1_TYSJ7T8SV9sLuTrSsZfmQQ](https://github.com/user-attachments/assets/d8ccf95b-efd0-4190-a9b9-c8ef6e63f961)
# Objective
- The objective of this project is to build a deep learning model that can automatically classify tweets as "disaster-related" or "not disaster-related". This helps emergency services, government agencies, and - humanitarian organizations to quickly filter social media content and prioritize critical information during disaster events.
# Why We Use This Project
- Social media data is vast — During disasters, millions of tweets are posted in real time, but only a fraction are relevant for rescue and relief operations.
- Manual monitoring is inefficient — Human classification of tweets is too slow and prone to error.
- Automation helps in real-time response — A trained machine learning model can instantly filter relevant tweets, enabling faster decision-making.
- Natural Language Processing (NLP) power — By using LSTM (Long Short-Term Memory) networks, the model can understand sequence context, which is essential in text classification.
# Step-by-Step Approach
### Data Collection
- Dataset: train.csv (Twitter disaster dataset from Kaggle).
- Contains columns: id, keyword, location, text, target (0 = not disaster, 1 = disaster).
# Exploratory Data Analysis (EDA)
- Shape of dataset: Checked the number of rows and columns.
- Class distribution: Counted how many tweets are labeled as disaster (1) and non-disaster (0).
- Sample inspection: Looked at random tweets to understand the text patterns.
# Data Preprocessing
### Text Cleaning
- Remove URLs using regex (https?://\S+ or www.\S+).
- Remove punctuation using string.punctuation.
- Remove stopwords using NLTK’s English stopword set.
- Converted all words to lowercase.
# Tokenization & Padding
- Tokenized text into sequences using Keras Tokenizer.
- Set vocabulary size to number of unique words.
- Padded sequences to a fixed max_length (20) for uniform input size.
# Feature Engineering
- Created a word index mapping (each unique word assigned a unique integer).
- Reversed index for decoding sequences back to text.
- Converted text into dense numerical sequences for model training.
# Model Architecture
### Layers:
- Embedding Layer
- Input: Word indices
- Output: Dense vectors of size 32
- LSTM Layer
- 64 units, dropout rate of 0.1
- Dense Output Layer
- 1 neuron, sigmoid activation for binary classification
# Model Training
- Loss Function: Binary Crossentropy
- Optimizer: Adam (learning rate 0.001)
- Metrics: Accuracy
- Epochs: 20
- Validation Split: 20% of data for validation
# Model Testing
- Predicted on training set to verify correctness.
- Applied threshold p > 0.5 to classify into 1 or 0.
- Compared predictions with actual labels.
# Output
<img width="319" height="73" alt="Screenshot 2025-08-15 194711" src="https://github.com/user-attachments/assets/b7d8c218-bd1b-478c-99f6-bfcddc77daf2" />
