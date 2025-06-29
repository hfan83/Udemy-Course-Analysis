# Udemy IT Courses Analysis: Trends & Performance

**Tagline:** *An End-to-End Analysis to Uncover Learning Trends, Predict Course Success, and Drive Business Strategy on the Udemy Platform.*

<!-- Make sure to replace this link with the public link to your dashboard image -->
![Udemy Analysis Dashboard[](https://github.com/user-attachments/assets/7bf30832-604a-4712-a7d1-e62a0c8d1959](https://public.tableau.com/views/UdemyAnalysisDashboard_17433362503760/DashboardOverview?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link))
---

## 1. Project Overview

This project presents an end-to-end data analysis workflow, from data scraping and preprocessing to machine learning modeling and interactive visualization. The primary goal is to gain deep insights into the Information Technology (IT) course market on the Udemy platform.

Beyond simple analysis, this project focuses on extracting **actionable insights** and providing **data-driven recommendations** to optimize course performance, enhance user engagement, and improve Udemy's competitive edge.

### 📌 Business Problem

This project aims to answer core business questions:
*   **Learning Trends:** What are the most popular topics, languages, and course formats currently attracting students in the IT field?
*   **User Behavior:** Which factors (price, duration, level, instructor reputation) most significantly influence a student's enrollment decision and satisfaction?
*   **Course Performance:** What defines a successful course? Can we predict the potential number of enrollments for a new course?
*   **Strategic Optimization:** How can we leverage data to formulate strategies that boost revenue, increase engagement, and effectively develop different course segments?

### 💾 The Data
The dataset was collected via web scraping from `Udemy.com` in March 2025. It contains information on **over 24,000 IT courses**, described by 18 attributes, including:
*   **Course Information:** Title, category, level, duration, price, number of lectures, language, etc.
*   **Performance Metrics:** Total enrollments, average rating, number of ratings, etc.
*   **Instructor Details:** Name, total courses, total students, average rating, etc.

### 🛠️ Tech Stack & Tools

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-0066B0?style=for-the-badge&logo=xgboost&logoColor=white)
![LightGBM](https://img.shields.io/badge/LightGBM-A6569A?style=for-the-badge)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557c?style=for-the-badge&logo=Matplotlib&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-3776AB?style=for-the-badge&logo=seaborn&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=Jupyter&logoColor=white)
![Tableau](https://img.shields.io/badge/Tableau-E97627?style=for-the-badge&logo=tableau&logoColor=white)

---

## 2. Project Workflow
This project follows a systematic data analysis pipeline:

1.  **Data Collection & Preprocessing:**
    *   Cleaned the data by handling missing values, duplicates, and special characters.
    *   Performed data type conversions for consistency.
    *   Modeled the data into a relational schema (Course, Instructor, Language, etc.).
    *   Applied **Logarithmic Transformation** to normalize skewed numerical features.

2.  **Exploratory Data Analysis (EDA):**
    *   Utilized descriptive statistics and visualizations (Histograms, Boxplots, Heatmaps) to understand data distributions and correlations.
    *   Analyzed key factors like price, duration, and level to generate initial insights.

3.  **Interactive Dashboard Development:**
    *   Built two interactive dashboards in **Tableau** to:
        *   Provide a high-level overview of business performance (revenue, enrollments, market size).
        *   Conduct a deep-dive analysis of student behavior and learning trends.

4.  **Predictive Modeling (Regression):**
    *   **Objective:** To predict the total number of enrollments (`Total Enrollments`).
    *   **Feature Engineering:**
        *   Used **PCA (Principal Component Analysis)** to reduce dimensionality and address multicollinearity among course structure features.
        *   Applied **Hybrid Sampling (SMOTE + Random Undersampling)** to handle class imbalance in the categorical price feature.
    *   **Modeling:**
        *   Trained and compared three models: `Linear Regression`, `LightGBM`, and `XGBoost`.
        *   Implemented **Early Stopping** to prevent overfitting.
    *   **Evaluation:** Assessed models using `R-squared`, `MAE`, and `RMSLE` metrics.

5.  **Clustering Model (Unsupervised Learning):**
    *   **Objective:** To segment courses into distinct groups based on popularity and quality.
    *   **Methodology:**
        *   Used the **Empirical Rule** to separate the data into "Common" and "Special" (outlier) datasets for more robust clustering.
        *   Implemented the **Gaussian Mixture Model (GMM)** algorithm, chosen for its flexibility in handling clusters of varying shapes and sizes.
        *   Used **AIC/BIC** criteria and the **Silhouette Score** to determine the optimal number of clusters and evaluate clustering quality.

6.  **Insight Synthesis & Strategic Recommendations:**
    *   Synthesized findings from EDA, dashboards, and models to formulate actionable business strategies.

---

## 3. Key Findings & Insights

### 📊 Insights from the Dashboard
1.  **Premium Content Commands Premium Prices:** High-priced (> $40) and long-duration (> 24 hours) courses, despite fewer enrollments, generate the **highest revenue**. This indicates a willingness from students to pay for comprehensive, in-depth content.
2.  **The Mid-Price Segment Underperforms:** Courses in the mid-price range ($20 - $40) consistently show the poorest performance across all metrics.
3.  **"All Levels" is King:** Courses marketed for "All Levels" dominate in volume, enrollments, and revenue, highlighting a strong demand for accessible and flexible learning paths.
4.  **Engagement is a Challenge:** The platform-wide average rating rate is low (9.6%). Low-cost, short-duration courses suffer from extremely low engagement (3-4%), suggesting a lack of student commitment.
5.  **Niche Stars with High Engagement:** Topics like **Software Testing** and **Development Tools**, while smaller in scale, boast exceptionally high rating and engagement rates, indicating a highly active community and quality content.

### 🤖 Insights from Machine Learning Models

#### Predictive Model
*   The **XGBoost** model performed best, achieving an **R-squared of 80.62%** on the test set, demonstrating a strong ability to explain and predict student enrollments.
*   The most important feature influencing enrollments is **`Total Ratings`**. This confirms that the **social proof effect** is a critical driver for attracting new students.

#### Clustering Model
The GMM algorithm successfully segmented courses into 6 meaningful clusters. The most notable are:
*   **The "Hot-Ticket" Cluster:** Courses with massive enrollments and high ratings, often centered on trending topics. However, their engagement rates are low, suggesting students enroll due to hype but may not complete or interact deeply with the content.
*   **The "Niche & Unproven" Cluster:** New or niche courses with low enrollments and poor ratings. They are typically short but have a high price point, indicating a struggle to find product-market fit.
*   **The "Elite Performer" Cluster:** A tiny, exclusive group of courses (only 11) with outstanding performance: an average of **1.2 million students per course** and near-perfect ratings (4.5-4.7). These are the platform's "blockbusters"—long, expensive, and highly engaging.

