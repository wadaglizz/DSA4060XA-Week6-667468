DSA4060XA Week 6: Guided Evaluation Lab

Name: IAN KAMAU NJIRU
Student ID: 667468
Course: DSA4060XA – Recommender Systems

1. Lab Objective
The objective of this lab was to implement and evaluate different movie recommender systems using rating prediction, ranking metrics, coverage, novelty, and diversity.

2. Dataset
The lab used two CSV files:
`DSA4060_Week6_Movies.csv` — movie IDs, titles, and genres.
`DSA4060_Week6_Ratings.csv` — user IDs, movie IDs, ratings, and timestamps.

The dataset contained 20 movies, 12 users, and 120 ratings. The evaluation used 108 training interactions and 12 test interactions, holding out the latest interaction for each user.

3. Models Compared
Popularity-based recommender: Recommends movies using overall popularity and rating information.
Content-based recommender: Uses movie genres and user preferences to recommend similar content.
Item-based collaborative filtering: Uses patterns in users’ ratings to identify related movies.

4. Rating Prediction Results

| Model | MAE | RMSE |
|---|---:|---:|
| Popularity baseline | 1.086 | 1.201 |
| Content-based | 1.094 | 1.381 |
| Item-based collaborative filtering | 0.924 | 1.070 |

Best model for rating prediction: Item-based collaborative filtering, because it achieved the lowest MAE and RMSE.

5. Ranking Evaluation
Using the reported Precision@3, Recall@3, and NDCG@3 results:

| Model | Precision@3 | Recall@3 | NDCG@3 |
|---|---:|---:|---:|
| Popularity | 0.028 | 0.200 | 0.042 |
| Content-based | 0.028 | 0.200 | 0.083 |
| Item-based collaborative filtering | 0.000 | 0.000 | 0.000 |

Best model for ranking: Content-based filtering, because it achieved the highest NDCG@3 among the three models in this evaluation.

6. Coverage, Novelty, and Diversity

| Model | Coverage | Novelty | Diversity |
|---|---:|---:|---:|
| Popularity | 0.350 | 4.733 | 0.736 |
| Content-based | 0.700 | 4.453 | 0.542 |
| Item-based collaborative filtering | 0.850 | 4.720 | 0.780 |

Coverage: Item-based collaborative filtering had the highest coverage at 85%, meaning it recommended a larger proportion of the available movie catalogue.
Novelty: The popularity-based recommender had the highest reported novelty score of 4.733.
Diversity: Item-based collaborative filtering achieved the highest diversity score of 0.780.

7. Final Recommended Model
For a streaming service that wants to recommend relevant movies without repeatedly showing only the same popular titles, the content-based recommender is a reasonable starting point because it achieved the highest NDCG@3 in this evaluation. However, its ranking metrics were low overall, and item-based collaborative filtering achieved higher catalogue coverage and diversity. A hybrid recommender combining content-based and collaborative signals could be explored in future work.

8. Limitations
The dataset was small, containing only 12 users and 20 movies, so the results may not generalize to a larger streaming service.
The test set contained only 12 held-out interactions, making the evaluation metrics sensitive to individual recommendations.
The available user-rating history was limited, which may reduce the reliability of learned user preferences and item similarities.
The evaluation used a limited set of recommendation metrics and did not establish how real users would respond to the recommendations.

9. Reproducibility
The repository contains the completed Jupyter notebook and the two CSV datasets used in the lab. To reproduce the analysis, open the notebook in Jupyter or Google Colab, ensure the CSV files are accessible, restart the kernel, and run all cells from top to bottom.
