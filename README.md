# Udemy IT Courses Data Analysis: Trends & Performance

**Tagline:** *An end-to-end project to uncover learning trends, build predictive models, and propose data-driven business strategies for IT courses on Udemy.*

*Business Overview Dashboard — [View the interactive dashboard on Tableau Public](https://public.tableau.com/app/profile/truonghuyphan.da/viz/UdemyAnalysisDashboard_17433362503760/DashboardOverview)*

---

## 🚀 Project Overview

This project is a complete data analysis and machine learning pipeline, from raw web-scraped data to strategic business recommendations. It focuses on the **Information Technology (IT) course market on Udemy**, identifying key trends, understanding student behaviors, and predicting course performance.

### 🎯 Business Goals
- **Learning Trends:** Identify top IT topics, languages, and structures attracting learners.
- **User Behavior:** Understand how price, duration, level, and instructor reputation impact enrollments and engagement.
- **Course Success:** Predict enrollments for new courses.
- **Strategic Optimization:** Recommend data-driven strategies to boost revenue and engagement.

### 💾 Data
Collected by **web scraping Udemy.com in March 2025**, including **24,000+ IT courses** with:
- **Course Features:** Title, category, level, duration, price, lectures, language.
- **Performance Metrics:** Total enrollments, ratings, number of reviews.
- **Instructor Stats:** Number of courses, total students, total reviews.

---

## 🛠 Tech Stack & Libraries
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-0066B0?style=for-the-badge&logo=xgboost&logoColor=white)
![LightGBM](https://img.shields.io/badge/LightGBM-A6569A?style=for-the-badge)
![Seaborn](https://img.shields.io/badge/Seaborn-3776AB?style=for-the-badge&logo=seaborn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557c?style=for-the-badge&logo=Matplotlib&logoColor=white)
![Tableau](https://img.shields.io/badge/Tableau-E97627?style=for-the-badge&logo=tableau&logoColor=white)

---

## 📈 Project Workflow

### 1️⃣ Data Cleaning & Feature Engineering
- Removed duplicates, handled special characters, standardized data types.
- **Log Transform** applied to nearly all numeric features (except ratings) to reduce extreme skewness.
- **Encoding:**
  - `Language` → Frequency Encoding
  - `Level`, `Mini_Subject_Name` → OneHot Encoding
- **PCA:** 
  - Reduced course structure features (`Duration`, `Lectures`, `Sections`) into 2 components.
  - Reduced instructor stats (`Total Instructor Reviews`, `Total Students`) into 1 component.

### 2️⃣ Exploratory Data Analysis (EDA)
- Visualized distributions, outliers, correlations.
- Identified how price, duration, and level affect revenue and engagement.

### 3️⃣ Predictive Modeling
- **Objective:** Predict `Total Enrollments`.
- Compared three models using **K-Fold Cross Validation**:
  | Model             | RMSE       | MAE      | R²    |
  |-------------------|------------|----------|-------|
  | Linear Regression | 1.4500 ±0.019 | 1.1330 ±0.012 | 0.5519 ±0.0065 |
  | LightGBM          | 0.8595 ±0.008 | 0.6297 ±0.007 | 0.8426 ±0.0013 |
  | **XGBoost**       | **0.8375 ±0.004** | **0.6038 ±0.006** | **0.8505 ±0.0021** |
- ✅ **Best Model:** `XGBoost`
- Extracted feature importances, showing:
  - `Total Ratings` as the strongest predictor (social proof).
  - Instructor metrics & PCA components also highly influential.

### 4️⃣ Clustering Analysis
- Focused on **`df_Common`**, data cleaned by removing outliers using Empirical Rule (mean ±3σ).
- Applied **Gaussian Mixture Model (GMM)** with `covariance='tied'`.
- Used **AIC, BIC, Silhouette Score** to determine optimal clusters.
- Visualized with 3D scatter plots and boxplots by cluster.

---

## 🔍 Key Insights

### 📊 From EDA & Dashboards
- **Premium strategy:** Courses priced >`$40` and >`24 hours` long have fewer enrollments but highest revenue — students pay for depth.
- **"All Levels" leads:** Most popular in volume and earnings, proving broad accessibility is key.
- **Mid-priced gap:** Courses `$20-$40` underperform in enrollments and revenue.
- **Engagement concerns:** Despite high enrollments, platform-wide average rating engagement is low (~9%), worse for cheap, short courses.
- **Hidden gems:** `Software Testing` & `Development Tools` show high engagement despite small market share.

### 🤖 From XGBoost Model
- **R² ≈ 0.85**, indicating strong predictive power.
- **Total Ratings** is the top driver, confirming the power of reviews & social proof.

### 📈 From Clustering
- Identified 3 meaningful course clusters:
  - **Hot but Low Engagement:** Large enrollments, low ratings engagement — likely hype-driven.
  - **Underperformers:** Low enrollments and reviews, often short and overpriced.
  - **Elite Courses:** Few in number, but high enrollments + stellar ratings, typically long, expensive, instructor-led.

---

## 💡 Strategic Recommendations
- **Double down on "All Levels" courses:** Long duration & top instructors.
- **Boost social proof:** Display ratings and total reviews more prominently.
- **Rethink mid-tier pricing:** Consider bundles or special offers.
- **Feature hidden gems:** Target marketing towards high-engagement segments like `Software Testing`.
- **Continue dimensional analysis:** Use PCA to keep tracking course structures vs outcomes.

---

## 📊 Interactive Dashboard
- Explore market trends, student behavior, and topic-specific performance:
[👉 Tableau Dashboard](https://public.tableau.com/app/profile/truonghuyphan.da/viz/UdemyAnalysisDashboard_17433362503760/DashboardOverview)

---
