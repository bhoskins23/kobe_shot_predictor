# Hackathon Project 
by Brandon Hoskins

## Problem Statement:

In this project, we will compare model accuracy scores to predict the shots taken by Kobe Bryant throughout his 20 year NBA career were made or missed.

## Data:

This data is provided from Kaggle and it is about every shot that Kobe Bryant has taken over the course of his 20 year career.

## Methodology:

Handling Nulls: The nulls in the shot_made_flag column were the shots used for our predictions.

## EDA:

I found that the correlations of my numeric columns were not very strong with my target (shot_made_flag)

I also found that shot distance is the strongest feature to determine our target.  As the distance increases, the chances of making the shot decreases.

## Data Preprocessing:

Data Augmentation: I one-hot encoded the columns action_type, shot_type, shot_zone_area, shot_zone_basic, opponent, season. I felt that these columns could be good features to use in the model. 

## Modeling:

I decided to drop features such as combined_shot_type, shot_zone_range, team_id, team_name, game_date, matchup, shot_made_flag.  I decided to drop combined_shot_type and shot_zone_range because of their similarity to other features like action_type and shot_distance.  The features team_id, team_name, game_date, matchup did not have any correlation with our target.

## Results:

The first model I used was a Random Forest Classifier with Grid Search to tune parameters. My training score was 0.679. My test score was 0.684. I also made a confusion matrix to get more metrics to evaluate my model.  My specificity was 0.85 and my sensitivity was 0.469.

The second model I used was K-Nearest Neighbors Classifier. After scaling my X_train and X_test using Standard Scaler, my training score was 0.746 and my test score was 0.614. After constructing a confusion matrix, my specificity score was 0.713 and my sensitivity score was 0.488.

I tried using a neural network model for better performance.  I tried three different neural network models just changing the regularization.  The best of these three models, I found was the one with L2 regularization. I constructed a confusion matrix and my specificity score was 0.868 and my sensitivity score was 0.448.

## Conclusions:

These evaluation metrics tell us that it is incredibly difficult to predict which shots are going to be made or missed there are countless other factors not used in this dataset that can contribute as well. 

## Next Steps:

Do some feature engineering with the matchup columns to get data from away and home games.  Also, use more models to see if different models perform better.
