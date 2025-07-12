# Recommendation-using-Collaborative-Filtering
This project implements a user-user collaborative filtering movie recommendation system on the Movie Lens Dataset, predicting ratings using a weighted average of similar users' ratings and evaluating performance with an RMSE of 1.057.

# Problem Statement
<img width="1339" height="113" alt="image" src="https://github.com/user-attachments/assets/1950b6c7-5208-4755-be95-09c4c70c6dfb" />
# Solution Summary
- Implemented a **user-user collaborative filtering movie recommendation system** on the **MovieLens dataset**.

- **Technical Workflow**:
  - Loaded MovieLens dataset:
    - Split into **80,000-entry training set** and **20,000-entry test set**.
    - Included **943 users** and **1650 movies**.
  - Created **user-movie rating matrix (r_um)** (943 × 1682), initialized with zeros and populated with actual ratings.
  - Normalized ratings:
    - For each user, subtracted mean rating and divided by standard deviation (non-zero entries).
  - Computed **user-user similarity (user_sim)**:
    - Matrix multiplication of normalized `r_um` and its transpose.
    - Normalized similarity scores by number of movies rated in common between user pairs.

- **Rating Prediction**:
  - Used **K-Nearest Neighbors (KNN)-like approach**:
    - Predicted rating = weighted average of other users’ ratings for the movie.
    - Weights = similarity scores.
    - Denormalized predictions using the target user’s mean and standard deviation.

- **Evaluation**:
  - Calculated **Root Mean Squared Error (RMSE)** between actual and predicted test ratings.
  - Achieved **RMSE = 1.0572** on MovieLens test set.

- **Key Insights**:
  - Successfully implemented user-user collaborative filtering as intended.
  - Normalization of user ratings was crucial to handle individual rating biases.
  - Refining similarity with shared movie counts improved similarity reliability.
  - RMSE provided a clear quantitative benchmark for recommendation accuracy.

- **Conclusion**:
  - Established a functional collaborative filtering pipeline, offering a solid baseline for future enhancements (e.g., item-item models, matrix factorization, hybrid methods).

