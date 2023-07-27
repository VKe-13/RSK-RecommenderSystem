# RSK-RecommenderSystem


## Table of Contents

- [Introduction](#introduction)
- [Requirements](#requirements)
- [Usage](#usage)

## Introduction

This repository contains code for a Recommender System. It recommends the top K most relevant products to users based on their transaction history.

## Requirements

To run the Recommender System, you'll need the following dependencies:

- Pandas
- NumPy


## Usage

1. Download the dataset from Kaggle and place it in the appropriate directory.
https://www.kaggle.com/competitions/skillbox-recommender-system/data)https://www.kaggle.com/competitions/skillbox-recommender-system/data

2. Open the SmartRecs.ipynb notebook.

3. Create an instance of the SmartRecs class by providing the path to the transaction history and products data.
   ```
   recommender = SmartRecs('transactions.csv', 'products.csv')
   ```
   
5. Call the train_model() method to train the recommender system and generate recommendations.
   ```
   recommender.train_model()
   ```
   
7. Use the get_top_k_recommendations(user, top_k) method to get recommendations for a single user, specifying the user ID and the number of items to recommend.
   ```
   user_id = 123
   top_k = 5
   user_recommendations = recommender.get_top_k_recommendations(user_id, top_k)
   print(f"Top {top_k} recommendations for user {user_id}: {user_recommendations}")
   ```
   **Output:**
   Top 5 recommendations for user 123:
   ['Organic Unsweetened Almond Milk', 'Hass Avocados', 'Soy Sauce', 'Organic Spring Mix', 'Organic Tortilla Chips']
   
9. Use the get_top_k_recommendations_for_users(user_ids, top_k) method to get recommendations for multiple users, passing a list of user IDs and the number of items to recommend.
    ```
   user_ids = [123, 3000000, 789]
   user_recommendations = recommender.get_top_k_recommendations_for_users(user_ids, top_k)
   for i, user_id in enumerate(user_ids):
       print(f"Top {top_k} recommendations for user {user_id}: {user_recommendations[i]}")
    ```
    >**Top 5 recommendations for user 123:**
    >['Organic Unsweetened Almond Milk', 'Hass Avocados', 'Soy Sauce', 'Organic Spring Mix', 'Organic Tortilla Chips']
    >
    >**Top 5 recommendations for user 3000000:**
    >['Banana', 'Bag of Organic Bananas', 'Organic Strawberries', 'Organic Baby Spinach', 'Organic Hass Avocado']
    >
    >**Top 5 recommendations for user 789:**
    >['Cheez-It Baked Snack Crackers', 'French Vanilla Creamer', 'Organic Half & Half', 'Chunky Peanut Butter', 'Balsamic Vinegar']
    
   
11. If you have new transaction or new products data, you can update data by calling the update(new_transactions, new_products) method. After updating, retrain the model by calling the train_model() method again.
    ```
      recommender.update_data(new_transactions_file='new_transactions.csv', 
                        new_products_file='new_products.csv')
      recommender.train_model()
    ```
