# Credit Card Recommender System for Website Personalization
_An applied machine learning model developed at RBC_

## 🔍 Overview
The RBC website is the front door for potential clients, offering a space for product exploration and an opportunity to make a strong first impression. Personalizing credit card recommendations in the hero banner and “Our Top Cards” section can surface products that are more relevant to each user, increasing engagement and driving conversion.
This project presents a machine learning–based recommender system designed to identify the credit cards prospective clients are most likely to apply for, and to personalize website content accordingly in real time.

## 📊 Analysis Details
The model was built using LightGBM and combined multiple data sources:
- Session-specific user behavior (e.g., device details, clicks)
- Aggregated RBC client data at the postal code level
- Credit card offers

The primary modeling challenge was the *cold-start* problem: since prospective website visitors are not logged in or identifiable RBC clients, it is difficult to personalize recommendations as we have very little prospect-specific data to leverage. To address this, we adopted a “people like you” strategy. By aggregating attributes of existing RBC clients within the same postal code, we inferred approximate demographic and behavioral characteristics for anonymous users — e.g., using average income of local clients as a proxy for the visitor’s income.

## 🧠 Methods & Tools
- **Languages**: Python (Pandas, PySpark)
- **Techniques**: LightGBM, multiclass classification
- **Workflow**: Training set curation → feature engineering → hyperparameter tuning → evaluation and model interpretation

## 🎯 Outcomes
- Achieved 60% accuracy in predicting the credit card that a prospective client is most likely to apply for
- A/B testing revealed a 4% lift in credit card applications, translating to approximately $150,000 in incremental annual revenue
- Model is slated for broader integration across key user flows (e.g., post-account-opening experience, website chatbot)

## 📂 Contents
- `scripts/`: Code
- `slides/`: Final deck summarizing findings and recommendations (PDF)
- `README.md`: Overview of the project
