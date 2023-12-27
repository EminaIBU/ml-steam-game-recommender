Steam Game Recommender System (Content-Based KNN)
==============================

What is this?
---------------

This is a recommender system written in Python which will give you 10 game recommendations for game you provide.

Prerequisites
-------------

Jupyter Notebook

Dataset
-------------

We have included two files: `formattedSteamGames.csv` and `formattedSteamGames_reduced.csv`.\
First one has 27K+ inserts, while the second one is smaller dataset which we generated in a way that it maintained same feature distribution using CFD statistical method.\
Use the one which fits your purpose the best.

How To Run This?
---------------
1. Download/clone this project
2. Run every block in `game_recommender.ipynb` or in `game_recommender_basic.ipynb`

Model Differences
---------------

#### `game_recommender_basic.ipynb`
This is the basic model whihc takes all features `categories`, `genres`, `steamspy_tags` and conbine them into `combined_features`.
These `combined_features` are converted to vectors by using `TfidfVectorizer` and every vetor is used later to calculate `cosine_similarity`

#### `game_recommender.ipynb`
This model is using a more complex model with more fatures.
We are using `categories`, `genres`, and `steamspy_tags` which are converted to vectors with `MultiLabelBinarizer`.\
We are also using the `time_engaged_category`, `player_acclaim_category`, `adopters_choice_category`, and `game_nexus_category` which are converted to vectors with `pd.get_dummies()` function.

For this mdoel we are using **weighted features** depending on which feature we want to put more focus. This is done inside `get_distance()` function.
