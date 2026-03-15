# Instructor Effectiveness Modeling (EdTech)

This project analyzes instructor performance using learner outcomes, engagement metrics, and feedback data. The goal is to estimate instructor effectiveness and build a machine learning model to classify instructors into effectiveness tiers.

## Problem Context

EdTech platforms often run the same course across multiple batches taught by different instructors. The platform wants to understand how instructor performance affects learner outcomes.

This project:

- Defines instructor effectiveness using available metrics
- Aggregates batch-level data to instructor-level
- Trains machine learning models to predict instructor effectiveness tiers
- Interprets model results and discusses limitations

## Dataset

Each row represents a course batch.

### Identifier Columns

- batch_id — Unique ID for a course batch
- instructor_id — Unique instructor identifier
- course_id — Course identifier

### Learner Outcome Metrics

- completion_rate
- dropout_rate
- avg_score_improvement
- avg_quiz_score

### Engagement Metrics

- avg_watch_time
- assignment_submission_rate
- forum_activity_rate

### Feedback Metrics

- avg_feedback_score
- feedback_response_rate

## Methodology

### 1. Exploratory Data Analysis

Explored the distribution of metrics and instructor teaching patterns.

Key findings:

- Instructors teach varying numbers of batches
- Effectiveness scores follow a roughly normal distribution

### 2. Instructor Effectiveness Definition

A composite effectiveness score was defined using learner outcomes, engagement metrics, and feedback.

Higher values indicate stronger instructor performance.

### 3. Aggregation

Since instructors teach multiple batches, batch-level metrics were aggregated to the instructor level using mean values.

### 4. Machine Learning Models

Two models were trained:

- Logistic Regression (baseline model)
- Random Forest Classifier

### 5. Model Evaluation

Models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion matrices

Both models achieved similar performance (~87.5% accuracy).

### 6. Feature Importance

Feature importance analysis showed that the most influential variables were:

1. Average score improvement
2. Dropout rate
3. Completion rate
4. Average quiz score

This suggests that learning improvement and course completion are the strongest indicators of instructor effectiveness.

## Limitations

- Effectiveness score was constructed using the same variables used in modeling.
- Course difficulty and student background were not available.
- Dataset size is relatively small.

## Ethical Considerations

The model should not be used as the sole measure of instructor performance. Quantitative metrics should be combined with qualitative evaluation and peer review.

## Tools Used

- Python
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn

## Conclusion

The analysis demonstrates how learner outcomes and engagement metrics can be used to estimate instructor effectiveness. While the model provides useful insights, additional contextual data would be required for robust instructor evaluation in real-world educational systems.
