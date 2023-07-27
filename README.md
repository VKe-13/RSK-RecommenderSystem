# RecommenderSystem "SmartRecs"


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
   
6. Use the get_top_k_recommendations(user, top_k) method to get recommendations for a single user, specifying the user ID and the number of items to recommend.
   ```
   user_id = 123
   top_k = 5
   user_recommendations = recommender.get_top_k_recommendations(user_id, top_k)
   print(f"Top {top_k} recommendations for user {user_id}: {user_recommendations}")
   ```
   ![](https://github.com/VKe-13/SmartRecs/blob/337c41d1266c215d8d6c9399e2734edc93c7ea62/top_k_one.png)
   
9. Use the get_top_k_recommendations_for_users(user_ids, top_k) method to get recommendations for multiple users, passing a list of user IDs and the number of items to recommend.
    ```
   user_ids = [123, 3000000, 789]
   user_recommendations = recommender.get_top_k_recommendations_for_users(user_ids, top_k)
   for i, user_id in enumerate(user_ids):
       print(f"Top {top_k} recommendations for user {user_id}: {user_recommendations[i]}")
    ```
    ![](https://github.com/VKe-13/SmartRecs/blob/0f02f499effcdd0670b20a7fe506c99f495cb8d0/top_k_multiple.png)
    
   
11. If you have new transactions or new products, you can update data by calling the update(new_transactions, new_products) method. After updating, retrain the model by calling the train_model() method again.
    ```
    recommender.update_data(new_transactions_file='new_transactions.csv', 
                        new_products_file='new_products.csv')
    recommender.train_model()
    ```
