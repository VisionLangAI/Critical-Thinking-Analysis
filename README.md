# Computational Thinking Dataset (Expanded)

## Overview
This repository contains a synthetic dataset of **10,000** entries designed to mirror a computational thinking study sample. Each row represents an individual student’s interaction with various coding tools, capturing their demographics, scores, and engagement metrics. The dataset is intended for educational research, data analysis, and machine learning experimentation focused on computational thinking skills.

## Dataset File
- **Filename:** `expanded_computational_thinking_dataset_10000.csv`
- **Format:** Comma-Separated Values (CSV)
- **Size:** 10,000 rows × 28 columns

## Attributes / Columns

| Column Name                        | Data Type | Description                                                                                                            |
|------------------------------------|-----------|------------------------------------------------------------------------------------------------------------------------|
| `Student_ID`                       | String    | Unique identifier for each student, formatted as `S00001` to `S10000`.                                                |
| `Age`                              | Integer   | Age of the student, ranging from 12 to 35.                                                                             |
| `Grade_Level`                      | String    | Student’s grade level (e.g., “Middle”, “High”).                                                                        |
| `Prior_CT_Experience`              | String    | Prior computational thinking experience level (e.g., “None”, “Beginner”, “Intermediate”).                              |
| `Tool_Used`                        | String    | Coding or computational tool used during the study (e.g., “Scratch”, “Micro:bit”, “Python”).                          |
| `Abstraction_Score`                | Integer   | Score (1–5) measuring the student’s ability to abstract problems.                                                      |
| `Algorithmic_Thinking_Score`       | Integer   | Score (1–5) assessing algorithmic thinking skills.                                                                     |
| `Decomposition_Score`              | Integer   | Score (1–5) evaluating problem decomposition ability.                                                                  |
| `Pattern_Recognition_Score`        | Integer   | Score (1–5) capturing pattern recognition skill.                                                                       |
| `Debugging_Score`                  | Integer   | Score (1–5) indicating debugging proficiency.                                                                          |
| `Creative_Expression_Score`        | Integer   | Score (1–5) reflecting creative expression in programming.                                                             |
| `Tool_Session_Count`               | Integer   | Number of sessions the student had with the assigned tool.                                                             |
| `Time_Spent_Per_Session`           | Integer   | Average time (in minutes) spent per session using the tool.                                                            |
| `Tasks_Completed`                  | Integer   | Number of tasks or exercises completed during the study.                                                               |
| `Tool_Features_Used`               | Integer   | Count of distinct tool features utilized by the student.                                                               |
| `Lines_of_Code`                    | Integer   | Total lines of code written by the student across all sessions.                                                        |
| `Pre_Test_Score`                   | Integer   | Score (0–100) on a pre-test assessing computational thinking knowledge.                                                |
| `Improvement_Score`                | Integer   | Improvement (0–100) between pre-test and post-test scores.                                                             |
| `Post_Test_Score`                  | Integer   | Score (0–100) on a post-test, calculated as `min(Pre_Test_Score + Improvement_Score, 100)`.                            |
| `Critical_Thinking_Score`          | Integer   | Score (1–5) measuring critical thinking ability.                                                                       |
| `Collaboration_Score`              | Integer   | Score (1–5) assessing collaboration and teamwork skills.                                                               |
| `Engagement_Level`                 | Integer   | Score (1–5) indicating level of engagement during sessions.                                                             |
| `Motivation_Score`                 | Integer   | Score (1–5) reflecting student motivation.                                                                              |
| `Error_Rate`                       | Integer   | Number of syntax or logical errors per 100 lines of code (approximate).                                                |
| `Feedback_Received`                | Integer   | Count of feedback instances received from instructors or peers.                                                         |
| `Skill_Improvement_Category`       | Integer   | Categorical indicator (1 or 2) of overall skill improvement classification.                                            |
| `CT_Mastery_Level`                 | String    | Categorical mastery level of computational thinking (e.g., “Beginner”, “Proficient”, “Expert”).                         |
| `Tool_Effectiveness`               | String    | Categorical effectiveness rating of the tool for the student (e.g., “Low”, “Medium”, “High”).                            |

## Generation Process
- This dataset is **synthetic**. It was generated by randomly sampling values within realistic ranges, based on an initial smaller sample (`computational_thinking_dataset_sample.csv`).
- Numeric attributes (e.g., scores, counts) were sampled uniformly from specified ranges:
  - Ages: 12–35
  - Various scores: Scores from 1 to 5 or 0 to 100, depending on the attribute.
  - Counts: Based on plausible classroom usage (e.g., 3–10 sessions, 80–500 lines of code).
- Categorical attributes (e.g., `Grade_Level`, `Tool_Used`, `CT_Mastery_Level`) were sampled from the unique values found in the original sample.
- `Post_Test_Score` was computed as the sum of `Pre_Test_Score` and `Improvement_Score`, capped at 100.

## Usage
1. **Loading Data (Python / pandas)**:
   ```python
   import pandas as pd
   df = pd.read_csv('expanded_computational_thinking_dataset_10000.csv')
   ```

2. **Exploratory Data Analysis**:
   - Analyze score distributions, correlations between tools and performance, and age-related trends.
   - Example:
     ```python
     df['Age'].describe()
     df.groupby('Tool_Used')['Post_Test_Score'].mean()
     ```

3. **Machine Learning Experiments**:
   - Use features like `Abstraction_Score`, `Algorithmic_Thinking_Score`, etc., to build predictive models (e.g., predict `CT_Mastery_Level` or `Tool_Effectiveness`).
   - Example:
     ```python
     from sklearn.model_selection import train_test_split
     from sklearn.ensemble import RandomForestClassifier

     X = df[['Abstraction_Score', 'Algorithmic_Thinking_Score', 'Decomposition_Score', 
             'Pattern_Recognition_Score', 'Debugging_Score']]
     y = df['CT_Mastery_Level']
     X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
     clf = RandomForestClassifier()
     clf.fit(X_train, y_train)
     preds = clf.predict(X_test)
     ```

## License & Attribution
- This synthetic dataset is provided **as-is** for educational and research purposes.
- Please cite the original source (if used in academic publications) as a synthetic dataset example:
  ```
  Computational Thinking Dataset (Expanded). Synthetic dataset generated by AI assistant.
  ```

## Contact
For questions or issues regarding this dataset, please open an issue or contact the maintainer.

