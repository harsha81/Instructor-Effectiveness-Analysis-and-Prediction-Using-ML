# 🎓 Instructor Effectiveness Prediction & Analytics

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-150458.svg?style=flat&logo=pandas&logoColor=white)
![Seaborn](https://img.shields.io/badge/seaborn-3776AB.svg?style=flat&logo=python&logoColor=white)

A comprehensive data analysis and machine learning pipeline designed to evaluate, categorize, and predict instructor performance based on student engagement, feedback, and course completion metrics.

## 🚀 Overview

This project analyzes a dataset of 2,000 individual course batches taught by various instructors. By aggregating batch-level data into an instructor-level overview, the pipeline engineers a custom **Instructor Effectiveness Score** and uses a **Random Forest Classifier** to predict instructor performance tiers (Low, Medium, High) based on historical metrics.

## 🧠 Core Evaluation Metric

Instructor effectiveness isn't just about feedback. The model calculates a custom `final_score` for each instructor using a weighted formula:

*   **40% - Completion Rate:** The percentage of students who finish the course.
*   **30% - Student Effort:** A combined metric of `avg_watch_time` and `assignment_submission_rate`.
*   **30% - Normalized Feedback:** Average feedback scores scaled to a 0.0–1.0 range.

Instructors are then bucketed into three equal tiers (`Low`, `Medium`, `High`) using quantile-based discretization (`pd.qcut`).

## 📊 Data Pipeline & Modeling

1. **Exploratory Data Analysis (EDA):** Generates distribution histograms and correlation heatmaps to identify relationships between dropout rates, completion rates, and feedback.
2. **Data Aggregation:** Groups 2,000 individual batches down to 120 unique instructors, calculating the mean of their performance metrics and counting total batches taught.
3. **Machine Learning:** 
   * Drops target-leaking columns.
   * Splits data 80/20 for training and testing.
   * Trains a `RandomForestClassifier` with 100 estimators.
4. **Model Evaluation:** Outputs a full classification report, a confusion matrix heatmap, and a feature importance bar chart.

## 📈 Visualizations Generated

When you run the script, it automatically generates a highly visual dashboard of insights:

| Visualization | Description |
| :--- | :--- |
| **Histograms** | 1x3 grid showing the distribution of Completion Rates, Dropout Rates, and Feedback Scores. |
| **Correlation Heatmap** | A `coolwarm` heatmap revealing the linear correlations between all numerical features. |
| **Tier Distribution** | A `viridis` bar chart showing the balance of Low, Medium, and High effectiveness tiers. |
| **Confusion Matrix** | A `Blues` heatmap comparing the Random Forest's Predicted Tiers vs. Actual Tiers. |
| **Feature Importance** | A `magma` bar chart ranking which metrics (e.g., watch time, feedback) most heavily influence the model's predictions. |

## 🛠️ Setup & Execution

### Prerequisites
Ensure you have Python installed along with the necessary data science libraries.

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

### Running the Pipeline
1. Clone this repository.
2. Ensure your dataset `instructor_effectiveness_dataset_2000_rows.csv` is in the same directory as the script.
3. Run the python script:

```bash
python effectiveness_model.py
```

## 📂 Dataset Structure Requirements

To use your own data, ensure your CSV contains the following columns at minimum:
* `batch_id`
* `instructor_id`
* `completion_rate`
* `dropout_rate`
* `avg_feedback_score`
* `avg_watch_time`
* `assignment_submission_rate`
* `avg_score_improvement`
* `avg_quiz_score`
* `forum_activity_rate`
* `feedback_response_rate`

---
*Built for Educational Data Mining & EdTech Analytics.*
