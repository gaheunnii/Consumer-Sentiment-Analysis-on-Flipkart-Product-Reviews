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
The original dataset is imbalanced, with positive reviews taking the largest proportion. Most customers also give high ratings, especially 4 or 5, showing an overall tendency toward positive feedback.

However, for the modeling stage, the data is further cleaned, filtered, and balanced in order to support fairer training and evaluation.

---

## 4. Dataset Overview

According to the original data distribution:

- **81.6%** of reviews are positive
- **4.9%** of reviews are neutral
- **13.5%** of reviews are negative

This shows a strong bias toward positive customer feedback. Ratings range from 1 to 5, and the majority of users give the highest rating, indicating generally favorable opinions toward the products.

The original dataset reflects real-world platform behavior, while the processed dataset is used for downstream modeling and evaluation.

---

## 5. Data Preprocessing

The raw review data was cleaned to remove missing values and inconsistent entries. The text preprocessing pipeline includes:

- Converting text to lowercase
- Removing special characters
- Filtering stop words
- Measuring review length
- Filtering overly short or excessively long reviews
- Applying resampling techniques to reduce class imbalance

This step is important because the original data distribution is highly imbalanced, and the balanced dataset is more suitable for training and evaluating classification models fairly.

---

## 6. Exploratory Data Analysis

The exploratory analysis examines:

- Sentiment distribution
- Rating distribution
- Relationship between sentiment and rating
- Review length by sentiment and rating
- Example review samples for qualitative understanding

The analysis suggests that higher ratings typically align with more positive sentiment, and negative reviews tend to be longer, meaning dissatisfied customers are often more detailed in their comments.

### 6.1 Rating Distribution
- Most reviews are associated with high ratings
- Rating 5 appears most frequently
- Extreme ratings are more common than middle-range ratings

### 6.2 Sentiment Distribution
- Positive reviews dominate the original dataset
- Neutral reviews represent the smallest portion
- Negative reviews are fewer than positive but still important for analysis

### 6.3 Review Length Analysis
- Most review summaries are relatively short
- Negative reviews tend to be longer on average
- This suggests dissatisfied customers are more likely to provide detailed explanations

### 6.4 Relationship Between Rating and Sentiment
- Higher ratings generally correspond to more positive sentiment
- Lower ratings are strongly associated with negative sentiment
- Neutral sentiment mainly appears around the middle rating range

---

## 7. Exploratory Findings

### Sentiment and Rating Patterns

The project finds a strong positive relationship between sentiment and rating:

- Higher ratings usually correspond to more positive sentiment
- Customers tend to give **extreme ratings** such as 1 or 5 more often than moderate ratings

This suggests that rating behavior and text-based sentiment are closely connected.

### Review Length

Most reviews are relatively concise, typically under 100 characters.  
Although no strong relationship appears between review length and rating, negative reviews are generally longer than positive ones, implying that dissatisfied customers often provide more detailed explanations.

---

## 8. Text Feature Engineering

To convert review text into numerical features, the project uses **TF-IDF vectorization** on the `Summary` field.

This allows the model to identify important words in review summaries while reducing the influence of very common but less informative terms.

### Why TF-IDF?
TF-IDF helps identify words that are important in a specific review while reducing the influence of overly common words across all reviews.

### Output
- Numerical representation of review text
- Top informative keywords based on TF-IDF scores
- Input features for machine learning classification

---

## 9. TF-IDF and Keyword Analysis

The TF-IDF analysis shows several consistent patterns:

- Customers express sentiment using **direct and simple words**
- Negative words are common, but positive words are more associated with stronger sentiment scores
- **Quality** and **price** are the most important recurring concerns in customer reviews

These insights are further reinforced by keyword frequency analysis and word cloud visualizations.

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

---

## 10. Key Factors Affecting Customer Satisfaction

Word cloud analysis supports the TF-IDF results and shows that customers focus heavily on:

- **Product quality**
- **Price / value for money**
- Overall product experience

This means customer satisfaction in Flipkart reviews is not driven only by general emotion, but also by concrete product-related concerns such as usefulness, quality, and affordability.

---

## 11. Sentiment Classification

This project uses a **Random Forest** model to predict sentiment categories from review summaries.

### Modeling pipeline
1. Transforming summaries into TF-IDF vectors
2. Splitting the dataset into training and test sets
3. Training the Random Forest model
4. Evaluating classification results
5. Interpreting feature importance and confusion matrix results

### Model setting
- **Model**: Random Forest
- **Train/Test Split**: 80:20
- **Number of Trees**: 100
- **Text Input**: Review summaries (`Summary`)

### Model Performance

- **Accuracy**: 71%
- **F1-score**: 71%

The confusion matrix and classification results show that:

- **Positive** and **negative** sentiments are easier to classify
- **Neutral** sentiment is more difficult to distinguish

This is also supported by the t-SNE visualization, where positive and negative reviews form more distinct clusters, while neutral reviews are more mixed in the middle.

### Class-wise Performance
- Positive and negative reviews are relatively easier to classify
- Neutral reviews are harder to predict accurately
- This is likely because neutral language often overlaps with weakly positive or weakly negative expressions

### Feature Space Visualization
The project also uses **t-SNE** to reduce TF-IDF features into two dimensions for visualization.

The visualization suggests:

- Positive and negative reviews form relatively clearer clusters
- Neutral reviews are more dispersed and mixed between the two
- This supports the classification results, where neutral sentiment is the most difficult category

---

## 12. Key Takeaways

The main takeaways from this project are:

- Consumer sentiment is strongly related to rating behavior
- Customers care most about **quality**, **price**, and overall product value
- Negative reviews tend to be longer and more descriptive
- Machine learning can predict review sentiment with reasonable effectiveness
- Neutral sentiment remains the most challenging class to classify accurately

These results show that combining text mining and supervised learning is a practical way to analyze customer feedback in e-commerce settings.

---

## 13. Strengths of the Project

- Combines exploratory analysis and machine learning in one workflow
- Includes interpretable text mining methods such as TF-IDF and keyword analysis
- Connects business insights with predictive modeling
- Uses data balancing to improve fairness in model evaluation
- Provides both descriptive and predictive understanding of customer feedback

---

## 14. Limitations

Although the project produces meaningful results, it also has several limitations:

- The model only uses the `Summary` field rather than full review text
- TF-IDF does not fully capture semantic context
- Random Forest serves as a solid baseline, but more advanced NLP models may perform better
- The balanced dataset improves evaluation fairness, but does not fully reflect real-world sentiment proportions

---

## 15. Future Directions

Possible future extensions include:

- **Aspect-Based Sentiment Analysis**  
  Analyze sentiment separately for aspects such as price, quality, delivery, and customer service

- **Recommendation System Integration**  
  Use sentiment scores to improve personalized product recommendations

- **Fake Review Detection**  
  Apply anomaly detection methods to identify misleading or unreliable reviews

- **Advanced NLP Models**  
  Compare Random Forest with more advanced methods such as Logistic Regression, XGBoost, LSTM, or BERT-based classifiers

- **Full Review Modeling**  
  Use the full review text instead of summaries only for richer sentiment representation

These directions are consistent with the improvement ideas proposed in the original PDF report.

---

## 16. Tech Stack

- **Python**
- **Pandas**
- **NumPy**
- **Matplotlib**
- **Seaborn**
- **Scikit-learn**
- **NLTK**
- **WordCloud**

---

## 17. Project Workflow

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