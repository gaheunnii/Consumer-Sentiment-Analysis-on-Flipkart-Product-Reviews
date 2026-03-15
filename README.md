# Consumer Sentiment Analysis on Flipkart Product Reviews

A data analysis and machine learning project that explores consumer sentiment in Flipkart product reviews through exploratory data analysis, text mining, visualization, and sentiment classification.

---

## 1. Project Overview

This project analyzes consumer sentiment in Flipkart product reviews using a dataset downloaded from Kaggle. The main goal is to understand how customers express satisfaction and dissatisfaction in review text, identify the major factors influencing sentiment, and build a machine learning model to predict review sentiment.

The project combines exploratory data analysis, text preprocessing, TF-IDF feature extraction, keyword analysis, word clouds, and Random Forest classification to provide both analytical insights and practical value for e-commerce applications such as customer feedback analysis, product improvement, and recommendation enhancement.

---

## 2. Objectives

This project is designed to answer the following questions:

- How are sentiment labels distributed across Flipkart product reviews?
- How are review sentiment and rating scores related?
- Do review length and textual patterns vary by sentiment?
- Which keywords are most strongly associated with positive, neutral, and negative sentiment?
- How effectively can machine learning predict sentiment from review summaries?

---

## 3. Dataset

The original dataset used in this project was downloaded from **Kaggle** and contains Flipkart product reviews with associated sentiment labels and rating scores.

For the modeling stage, the raw data was further cleaned, filtered, and balanced to support more reliable analysis and fairer sentiment classification.

### Main fields used
- **Summary**: short review text used for text analysis and modeling
- **Rate / Rating**: customer rating score from 1 to 5
- **Sentiment**: sentiment label (`positive`, `neutral`, `negative`)

### Original data characteristics
According to the original data distribution:

- **81.6%** of reviews are positive
- **4.9%** of reviews are neutral
- **13.5%** of reviews are negative

This shows a strong bias toward positive customer feedback. Ratings range from 1 to 5, and most customers give high ratings, especially 4 or 5, indicating generally favorable opinions toward products.

The original dataset reflects real-world platform behavior, while the processed dataset is used for downstream modeling and evaluation.

---

## 4. Data Preprocessing

The raw review data was cleaned to remove missing values and inconsistent entries. The preprocessing pipeline includes:

- Converting text to lowercase
- Removing special characters
- Filtering stop words
- Measuring review length
- Filtering overly short or excessively long reviews
- Applying resampling techniques to reduce class imbalance

This step is important because the original data distribution is highly imbalanced, and the balanced dataset is more suitable for training and evaluating classification models fairly.

---

## 5. Exploratory Data Analysis

The exploratory analysis examines:

- Sentiment distribution
- Rating distribution
- Relationship between sentiment and rating
- Review length by sentiment and rating
- Example review samples for qualitative understanding

The analysis suggests that higher ratings typically align with more positive sentiment, and negative reviews tend to be longer, meaning dissatisfied customers are often more detailed in their comments.

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

### 5.4 Key Exploratory Findings
- Higher ratings generally correspond to more positive sentiment
- Lower ratings are strongly associated with negative sentiment
- Neutral sentiment mainly appears around the middle rating range
- Customers tend to give **extreme ratings** such as 1 or 5 more often than moderate ratings
- Most reviews are concise, while negative reviews are relatively longer and more descriptive

---

## 6. Text Feature Engineering

To convert review text into numerical features, the project uses **TF-IDF vectorization** on the `Summary` field.

### Why TF-IDF?
TF-IDF helps identify words that are important in a specific review while reducing the influence of overly common words across all reviews.

### Output
- Numerical representation of review text
- Top informative keywords based on TF-IDF scores
- Input features for machine learning classification

This approach makes it possible to quantify review text and use it for both interpretive analysis and supervised learning.

---

## 7. TF-IDF and Keyword Analysis

The TF-IDF analysis shows several consistent patterns:

- Customers express sentiment using **direct and simple words**
- Negative words are common, but positive words are more associated with stronger sentiment scores
- **Quality** and **price** are the most important recurring concerns in customer reviews

These insights are further reinforced by keyword frequency analysis and word cloud visualizations.

The project also analyzes high-frequency keywords across sentiment classes using `CountVectorizer` and word cloud visualization.

### Positive reviews
Frequently used terms include:
- `nice`
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

---

## 8. Key Factors Affecting Customer Satisfaction

Word cloud analysis supports the TF-IDF results and shows that customers focus heavily on:

- **Product quality**
- **Price / value for money**
- Overall product experience

This means customer satisfaction in Flipkart reviews is not driven only by general emotion, but also by concrete product-related concerns such as usefulness, quality, and affordability.

---

## 9. Sentiment Classification

This project uses a **Random Forest** model to predict sentiment categories from review summaries.

### Modeling pipeline
1. Transform review summaries into TF-IDF vectors
2. Split the dataset into training and test sets
3. Train the Random Forest model
4. Evaluate classification performance
5. Interpret results using feature importance and confusion matrix analysis

### Model setting
- **Model**: Random Forest
- **Train/Test Split**: 80:20
- **Number of Trees**: 100
- **Text Input**: Review summaries (`Summary`)

### Model Performance
- **Accuracy**: 71%
- **F1-score**: 71%

### Classification Findings
- **Positive** and **negative** sentiments are easier to classify
- **Neutral** sentiment is more difficult to distinguish
- Neutral language often overlaps with weakly positive or weakly negative expressions

### Feature Space Visualization
The project also uses **t-SNE** to reduce TF-IDF features into two dimensions for visualization.

The visualization suggests:

- Positive and negative reviews form relatively clearer clusters
- Neutral reviews are more dispersed and mixed between the two
- This supports the classification results, where neutral sentiment is the most difficult category

---

## 10. Key Takeaways

The main takeaways from this project are:

- Consumer sentiment is strongly related to rating behavior
- Customers care most about **quality**, **price**, and overall product value
- Negative reviews tend to be longer and more descriptive
- Machine learning can predict review sentiment with reasonable effectiveness
- Neutral sentiment remains the most challenging class to classify accurately

These results show that combining text mining and supervised learning is a practical way to analyze customer feedback in e-commerce settings.

---

## 11. Future Directions

Possible future extensions include:

- **Aspect-Based Sentiment Analysis**  
  Analyze sentiment separately for aspects such as price, quality, delivery, and customer service

- **Advanced NLP Models**  
  Compare Random Forest with more advanced methods such as Logistic Regression, XGBoost, LSTM, or BERT-based classifiers

- **Recommendation System Integration**  
  Incorporate sentiment signals into product recommendation pipelines

- **Fake Review Detection**  
  Detect suspicious or unreliable reviews to improve platform trustworthiness

- **Full Review Modeling**  
  Use longer review text instead of summaries only for richer sentiment representation


---

## 12. Project Workflow

```text
Data Collection (Kaggle)
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
```

---

## 13. Conclusion

This project builds a complete sentiment analysis pipeline for Flipkart product reviews, from data preprocessing and exploratory analysis to text feature engineering and machine learning classification.

The results show that customer sentiment is closely associated with rating behavior, and that product quality and price are central drivers of consumer opinion. Although the Random Forest model achieves solid baseline performance, neutral sentiment remains difficult to classify, suggesting room for improvement through more advanced NLP methods.

Overall, this project demonstrates how review data can be transformed into actionable insights for customer understanding, product evaluation, and data-driven e-commerce analysis.
