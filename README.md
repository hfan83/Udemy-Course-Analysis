Udemy IT Courses Data Analysis: Trends & Performance
Tagline: An end-to-end project to uncover learning trends, build predictive models, and propose data-driven business strategies for IT courses on the Udemy platform.


Business Overview Dashboard — View full interactive dashboard on Tableau Public

1. Project Overview
This project delivers a complete data analytics and machine learning pipeline, moving from raw data collection to business-focused insights and strategic recommendations. The main objective is to analyze the Information Technology (IT) course market on Udemy, uncovering actionable insights that can guide decision-making and competitive strategies.

🚀 Business Goals
Learning Trends: What IT topics, languages, and course structures are most popular?

User Behavior: How do price, duration, level, and instructor reputation influence enrollment and engagement?

Course Performance: What drives enrollments, and can we predict them for new courses?

Strategic Optimization: Based on these insights, how can Udemy improve revenues and grow its IT course segment?

💾 Data
The dataset was scraped from Udemy.com in March 2025, including over 24,000 IT courses described by:

Course features: Title, category, level, duration, price, lectures, language.

Performance metrics: Total enrollments, ratings, reviews.

Instructor stats: Number of courses, total students, total reviews.

2. Project Workflow
🛠 Tech Stack & Libraries









🔎 Data Processing & Feature Engineering
Removed duplicates, standardized data types, cleaned special characters.

Applied Log Transformation to nearly all numeric features (except ratings) to handle extreme skewness.

Used Frequency Encoding on Language, OneHot Encoding on Level and Mini_Subject_Name.

Applied PCA (Principal Component Analysis) on structured course features (Duration, Lectures, Sections) and instructor features (Instructor Reviews, Instructor Students), capturing ~95% variance.

📊 Exploratory Data Analysis (EDA)
Analyzed distributions and correlations to understand market dynamics.

Identified how price, duration, and level affect enrollments and revenue.

📈 Predictive Modeling
Objective: Predict Total Enrollments as a regression problem.

Compared three models using K-Fold Cross Validation:

Linear Regression

LightGBM

XGBoost

Evaluated on RMSE, MAE, and R² scores.

Selected the best model based on lowest RMSE, then trained on full data and extracted feature importances.

🔬 Clustering
Isolated common dataset (df_Common) by removing outliers via the Empirical Rule (mean ± 3σ).

Applied Gaussian Mixture Model (GMM) with covariance='tied'.

Used AIC, BIC, and Silhouette Scores to determine the optimal number of clusters.

Visualized clusters with 3D scatter plots and analyzed distributions across clusters.

📊 Dashboards
Built interactive dashboards in Tableau for:

Business overview: market size, total revenue, enrollments by topic & level.

Behavioral deep dives: exploring student engagement and ratings by segment.

3. Key Findings & Insights
📌 Insights from EDA & Dashboards
Premium pays off: Courses priced over $40 and longer than 24 hours have fewer enrollments but generate the highest revenue, indicating willingness to pay for depth.

"All Levels" dominate: Flexible courses targeting all skill levels are the most popular in enrollments and revenue.

Mid-price segment struggle: Courses priced $20-$40 underperform in both enrollments and revenue.

Engagement issues: While enrollment is high for trending topics, average engagement (based on ratings rate) is under 10%, especially poor for low-cost, short courses.

Hidden gems: Software Testing and Development Tools have small market shares but high engagement and satisfaction.

🤖 Predictive Model Results
The best model (example LightGBM) achieved:

RMSE: ~0.32

MAE: ~0.25

R²: ~0.79

Most important features:

Total Ratings (social proof is key for attracting students)

Followed by instructor popularity and course structural complexity (via PCA components).

🔍 Clustering Insights
Segmented only on the cleaned df_Common data.

Identified three clear clusters:

Popular but Low Engagement: High enrollments but low ratings rate, often hype-driven.

Underperformers: Few enrollments and reviews, often due to poor positioning (short, overpriced).

Elite Courses: Tiny segment with massive enrollments and top ratings, typically long, expensive, and instructor-backed.

💡 Strategic Recommendations
Invest in "All Levels" courses with long durations and top instructors to maximize both enrollments and willingness to pay.

Leverage social proof: Promote total ratings and reviews prominently on course pages.

Revamp mid-price segment: Consider repackaging or bundling to better fit demand.

Spotlight hidden gems: Drive more traffic to high-engagement topics like Software Testing via targeted campaigns.

Continue PCA-style feature monitoring: Regularly reduce high-dimensional data for new courses to identify structural strengths and weaknesses.
