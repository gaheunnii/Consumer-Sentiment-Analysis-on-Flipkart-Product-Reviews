# Consumer Sentiment Analysis on Flipkart Product Reviews

A consumer sentiment analysis project based on Flipkart product reviews, combining exploratory data analysis, text mining, visualization, and machine learning classification to understand customer opinions and predict review sentiment.

---

## 1. Project Overview

This project focuses on analyzing consumer sentiment from Flipkart product reviews. The main objective is to understand how customers express satisfaction and dissatisfaction in textual reviews, identify the major factors influencing sentiment, and build a machine learning model for sentiment prediction.

By combining rating analysis, text preprocessing, TF-IDF feature extraction, keyword analysis, word clouds, dimensionality reduction, and classification modeling, this project provides both analytical insights and practical business value for e-commerce platforms.

---

## 2. Objectives

The project is designed around the following goals:

- Analyze the distribution of review sentiment and rating scores
- Explore how textual characteristics such as review length relate to sentiment
- Identify important keywords associated with different sentiment classes
- Build a machine learning model to predict sentiment from review summaries
- Interpret the major drivers behind positive, neutral, and negative feedback

---

## 3. Dataset

The dataset contains Flipkart product reviews with associated rating scores and sentiment labels.

### Main fields used
- **Summary**: short review text used for text analysis and modeling
- **Rating**: numerical score from 1 to 5
- **Sentiment**: sentiment label such as positive, neutral, or negative

### Original data characteristics
The original dataset is imbalanced, with positive reviews taking the largest proportion. Most customers also give high ratings, especially 4 or 5, showing an overall tendency toward positive feedback.

However, for the modeling stage, the data is further cleaned, filtered, and balanced in order to support fairer training and evaluation.

---

## 4. Data Preprocessing

The preprocessing pipeline includes:

- Removing missing or invalid entries
- Keeping only valid ratings
- Using the `Summary` field as the main text feature
- Converting text to lowercase
- Removing special characters and stopwords
- Calculating review length
- Filtering out overly short and overly long reviews
- Balancing the sentiment classes through resampling

This is an important point in the project:

> The original dataset is used to reflect the real-world review distribution, while the balanced dataset is used for model training and fair evaluation.

---

## 5. Exploratory Data Analysis

The exploratory analysis focuses on understanding the structure of the dataset and the relationship between ratings, sentiment, and text.

### 5.1 Rating Distribution
- Most reviews are associated with high ratings
- Rating 5 appears most frequently
- Extreme ratings are more common than middle-range ratings

### 5.2 Sentiment Distribution
- Positive reviews dominate the original dataset
- Neutral reviews represent the smallest portion
- Negative reviews are fewer than positive but still important for analysis

### 5.3 Review Length Analysis
- Most review summaries are relatively short
- Negative reviews tend to be longer on average
- This suggests dissatisfied customers are more likely to provide detailed explanations

### 5.4 Relationship Between Rating and Sentiment
- Higher ratings generally correspond to more positive sentiment
- Lower ratings are strongly associated with negative sentiment
- Neutral sentiment mainly appears around the middle rating range

---

## 6. Text Feature Engineering

To transform text into numerical features, the project applies **TF-IDF vectorization** to the review summaries.

### Why TF-IDF?
TF-IDF helps identify words that are important in a specific review while reducing the influence of overly common words across all reviews.

### Output
- Numerical representation of review text
- Top informative keywords based on TF-IDF scores
- Input features for machine learning classification

The analysis shows that customers frequently express opinions using direct and simple language, especially when referring to product **quality**, **price**, and overall experience.

---

## 7. Keyword Analysis and Word Clouds

The project further analyzes high-frequency keywords across sentiment classes using `CountVectorizer` and word cloud visualization.

### Positive reviews
Frequently used terms include:
- `good`
- `best`
- `quality`

### Negative reviews
Frequently used complaint-related terms include:
- `bad`
- `waste`
- `dont buy`

### Neutral reviews
- Tend to contain weaker emotional expressions
- Often shorter and less distinctive than positive or negative reviews

Across different analysis methods, **quality** and **price** consistently emerge as the most important consumer concerns.

---

## 8. Sentiment Classification

For sentiment prediction, the project uses a **Random Forest Classifier**.

### Modeling pipeline
1. Convert review summaries into TF-IDF vectors
2. Split the balanced dataset into training and test sets
3. Train a Random Forest model
4. Evaluate model performance using classification metrics
5. Interpret results with confusion matrix and feature importance

### Model setting
- **Model**: Random Forest
- **Train/Test Split**: 80:20
- **Number of Trees**: 100
- **Text Input**: Review summaries (`Summary`)

---

## 9. Results

### 9.1 Classification Performance
The Random Forest model achieves approximately:

- **Accuracy**: around 71%
- **F1-score**: around 71%

### 9.2 Class-wise Performance
- Positive and negative reviews are relatively easier to classify
- Neutral reviews are harder to predict accurately
- This is likely because neutral language often overlaps with weakly positive or weakly negative expressions

### 9.3 Feature Space Visualization
The project also uses **t-SNE** to reduce TF-IDF features into two dimensions for visualization.

The visualization suggests:

- Positive and negative reviews form relatively clearer clusters
- Neutral reviews are more dispersed and mixed between the two
- This supports the classification results, where neutral sentiment is the most difficult category

---

## 10. Key Findings

This project leads to several important insights:

- Consumer sentiment is strongly associated with rating behavior
- Product **quality** and **price** are the most influential topics in reviews
- Negative reviews tend to be longer and more detailed
- TF-IDF combined with Random Forest can provide reasonable sentiment classification performance
- Neutral sentiment is the most challenging category because it is less clearly separated in language use

---

## 11. Strengths of the Project

- Combines exploratory analysis and machine learning in one workflow
- Includes interpretable text mining methods such as TF-IDF and keyword analysis
- Connects business insights with predictive modeling
- Uses data balancing to improve fairness in model evaluation
- Provides both descriptive and predictive understanding of customer feedback

---

## 12. Limitations

Although the project produces meaningful results, it also has several limitations:

- The model only uses the `Summary` field rather than full review text
- TF-IDF does not fully capture semantic context
- Random Forest serves as a solid baseline, but more advanced NLP models may perform better
- The balanced dataset improves evaluation fairness, but does not fully reflect real-world sentiment proportions

---

## 13. Future Improvements

Possible future extensions include:

- **Aspect-Based Sentiment Analysis**  
  Identify sentiment toward specific aspects such as price, quality, delivery, or packaging

- **Advanced NLP Models**  
  Compare baseline performance with Logistic Regression, XGBoost, LSTM, or BERT-based classifiers

- **Recommendation System Integration**  
  Incorporate sentiment signals into product recommendation pipelines

- **Fake Review Detection**  
  Detect suspicious or unreliable reviews to improve platform trustworthiness

- **Full Review Modeling**  
  Use longer review text instead of summaries only for richer sentiment representation

---

## 14. Tech Stack

- **Python**
- **Pandas**
- **NumPy**
- **Matplotlib / Seaborn**
- **Scikit-learn**
- **NLTK**
- **WordCloud**

---

## 15. Project Workflow

```text
Data Collection
   ↓
Data Cleaning and Filtering
   ↓
Exploratory Data Analysis
   ↓
Text Preprocessing
   ↓
TF-IDF Feature Extraction
   ↓
Keyword / Word Cloud Analysis
   ↓
Random Forest Classification
   ↓
Evaluation and Interpretation