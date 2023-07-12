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

2. Open the RecommenderSystem.ipynb notebook.

3. Create an instance of the RecommenderSystem class by providing the path to the transaction history data.
   
4. Call the train_model() method to train the recommender system and generate recommendations.
5. Use the get_top_k_recommendations(user, num_items) method to get recommendations for a single user, specifying the user ID and the number of items to recommend.
6. Use the get_top_k_recommendations_for_users(user_ids, num_items) method to get recommendations for multiple users, passing a list of user IDs and the number of items to recommend.
7. If you have new transaction data, you can update the transaction history by calling the update(new_transactions) method. After updating, retrain the model by calling the train_model() method again.
