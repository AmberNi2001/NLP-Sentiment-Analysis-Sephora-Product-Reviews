# Project: Sephora Skincare Product Review Classification & Topic Modeling
**Author**: Amber Ni 
| **Date**: 02-11-2025 | **Course**: Text As Data: Computational Linguistics

## Project Description
This project involves analyzing a dataset of **skincare product reviews from Sephora** to classify reviews into three main categories **(Positive, Neutral, Negative)** and to explore the underlying **themes** in the data training various **machine learning models** and using **topic modeling techniques**. The goal is to identify the best-performing model and determine the most effective approach for understanding different types of reviews. This project employs various modeling methods - including: 
1. **Supervised Machine Learning**: Naive Bayes, LASSO regularized logistic regression, Ridge regression and Support Vector Machine (SVM)
2. **Unsupervise Machine Learning**: K-means clustering ; Latent Dirichlet Allocation (LDA) for **Topic Modeling**

The repository **includes**: 
1. Raw dataset `.csv`
2. R Markdown `.rmd`
3. Output `.html` and `.pdf`

The analysis will identify key themes and categories in customer feedback, such as product effectiveness and user satisfaction. Through classification, the project will uncover factors influencing customer satisfaction and enhance our understanding of customer preferences. This will enable further business analytics and correlation analysis, linking reviews with factors like product type, price, and brand. These insights will be valuable for product development, marketing strategies, and customer engagement. Additionally, the approach is well-suited for classifying and analyzing large-scale, unseen reviews.

## How to Use This Repository

If you'd like to **run the analysis** on your own laptop, follow these steps:
  1. Download the dataset `reviews_0-250.csv` from https://www.kaggle.com/datasets/nadyinky/sephora-products-and-skincare-reviews/data 
  2. Open RMarkdown `Sephora Review Classification_Amber.Rmd`.
  3. Change working directory according to your local path - `setwd("~/path/to/your/local/directory")`.
  4. Access the dataset according to where you put you data in - `reviews <- read.csv("reviews_0-250.csv")`.
  5. Run all to execute the entire analysis.

## Data Source 

This dataset `reviews_0-250.csv` contains **user reviews** of all products from the **Skincare** category, including product IDs, product names, brand names, review texts, review titles, etc.

The dataset contains **602,153 observations** and **19 variables**.

## Key Analysis and Findings

### Data Preparation and Preprocessing

Subset the dataset to only **10,000 observations**, classify reviews based on ratings into three categories - **(Positive, Neutral, Negative)**, check the distribution of categories, and split the data into training and testing sets. After looking at first few rows of the texts and understand the nature of them, perform extensive text preprocessing which includes converting to lower case, removing contractions, symbols, and non-ASCII characters and stemming. Then convert the cleaned text into a document-feature matrix (DFM) for further analysis. 

### Summary Analysis

Create a **word cloud** to visualize the most frequent terms across the dataset, helping to understand key themes and common words in customer reviews. 

<img width="632" alt="Screenshot 2025-04-01 at 4 03 11 PM" src="https://github.com/user-attachments/assets/6476f182-f58b-43ea-ac55-87609249e01e" />

### Supervised Machine Learning

1. Implement several supervised machine learning models, including Naive Bayes, LASSO regularized logistic regression, and Ridge regression.
2. Performance of models is evaluated using confusion matrices and key metrics like accuracy, precision, recall, and F1 score.

<img width="670" alt="Screenshot 2025-04-01 at 4 03 59 PM" src="https://github.com/user-attachments/assets/631e7831-cf6a-44ea-aa4c-24cba0203c7a" />

3. Apply a linear SVM model to classify reviews, aiming to find the optimal hyperplane that separates different sentiment categories. The model is tuned using cross-validation to adjust the cost parameter, and its performance was evaluated using accuracy, precision, recall, and F1 score. While it provided insights into review classification, its overall accuracy was lower compared to other models like Naive Bayes and LASSO.

### Unsupervised Machine Learning

#### K-means clustering 

Perform K-means clustering to group the reviews into different clusters based on the similarity of the words used in the reviews. Choose the optimal K using Elbow Method. Without labels guiding the clustering, K-means cannot differentiate sentiment effectively if the features are not well-separated and the languages are sometimes vague and not straightforward. It doesn’t have the context of class labels to guide the separation, leading to unsatisfied cluster quality.

#### Topic Modeling (Latent Dirichlet Allocation)

1. Apply Latent Dirichlet Allocation (LDA) for topic modeling to identify distinct themes in the reviews. The topics identified include skincare effectiveness, acne treatment, product texture, and hydration.
2. Visualize top words associated with each topic and analyzed their relevance to the reviews.

<img width="699" alt="Screenshot 2025-04-01 at 4 12 13 PM" src="https://github.com/user-attachments/assets/3fb71d56-50ba-4559-8ecb-6117eb55aa27" />
