# Recommender System (Surprise library): SVD, NMF, PMF

## Data
https://grouplens.org/datasets/movielens/
These datasets will change over time, and are not appropriate for reporting research results. We will keep the download links stable for automated downloads. We will not archive or make available previously released versions.
100,000 ratings and 3,600 tag applications applied to 9,000 movies by 600 users. Last updated 9/2018.
- movies.csv  (movies ids with title and gendre)
- ratings.csv (movies ids wit use ids and ratings)

## Motivation
Use collaborative filtering matrix factorization techniques (SVD, NMF, PMF) and recommend n unseen movies to any user in the dataset.

## Methodology
SVD and NMF trained a fitted with cross validation and gridsearch methods. The model accuracy is measured with RMSE. 
Defined `get_top_n()`function allows one to evaluate the model on individual level (see the Added Value below).

## Added Value
Function get_top_n() that returns two data frames in a readable format. `hist_usr` is a dataframe of historical ratings. The function is defined in a way that it merges metadata associated with movie ids with actual ids of movies the user has rated. Movies are displayed in a descending order based on ratings (movies with the highest rates on the top). 
`pred_user` is a dataframe with predictions and has the same structure and order (sorted bysed on predicted ratings) as `hist_usr`.
The function allows one to holistically evaluate model's accuracy (one can observe if the recommended genres are in line with the user's historical record).

## Notes
PMF model is not definite yet. The intention was to define PMF algorithm missing in Surprise package. I am currently finishing the code for PMF algorithm.
