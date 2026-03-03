# NBA Player Replacement Recommendation System

This project builds a data-driven system to identify statistically similar NBA players. The goal is to help teams quickly identify potential replacements when a player is injured, traded, or unavailable.

The project was completed as the **final project for CSCA 5632: Unsupervised Algorithms in Machine Learning**.

---

## Project Goal

When teams lose a key player, they need to answer an important question:

> *Who can replicate this player's statistical role on the court?*

Rather than simply identifying good players, this project focuses on identifying players who perform **similar statistical roles**, allowing teams to make more informed roster decisions.

---

## Dataset

**Source:** [NBA Players Dataset (Kaggle)](https://www.kaggle.com/datasets/justinas/nba-players-data)

The dataset contains player statistics including:

- Points
- Assists
- Rebounds
- Usage rate
- Net rating
- Height and weight
- Games played
- Advanced metrics (e.g., assist %, rebound %, usage %)

These statistics were used to identify player archetypes and similarity relationships.

---

## Methodology

The project explores multiple unsupervised learning techniques to understand player roles and identify replacement candidates.

### 1. K-Means Clustering – Player Archetypes

K-Means clustering was used to group players into **statistical archetypes**.  
The optimal number of clusters was determined using:

- **Elbow Method**
- **Silhouette Score**

Five interpretable clusters emerged, representing recognizable basketball roles such as:

- Power Forward / Center
- Backup Big / Fringe Roster
- Role Player / Bench Wing
- Star Playmaker
- Developmental / Young Player

This provides a first step in identifying what type of player needs replacing.

---

### 2. NMF-Based Player Similarity Recommender

Non-negative Matrix Factorization (NMF) was used to learn latent factors representing underlying skill dimensions.

Using the NMF representation, **cosine similarity** was applied to identify players with the most similar statistical profiles.

This enables a recommendation system that can answer questions like:

- "Which players most closely resemble Player X?"
- "Who could fill a similar role statistically?"

---

### 3. DBSCAN – Outlier Detection

DBSCAN was used to identify players who do not belong to any typical archetype.

This helps highlight **statistical outliers**, often corresponding to superstar players such as:

- Nikola Jokic
- Giannis Antetokounmpo
- Luka Dončić
- LeBron James

These players exhibit unique statistical profiles that do not cluster with typical roles.

---

## Results

- **K-Means** successfully identified interpretable player archetypes.
- **NMF** enabled a player similarity recommendation system.
- **DBSCAN** detected statistical outliers representing elite players.

Together, these models create a two-step workflow for identifying replacement players:

1. Identify the player's **archetype** (role classification).
2. Use **similarity recommendations** to find statistically comparable players.

---

## Repository Contents
- ['notebook'](https://github.com/niliacklein33/usl-final-nba-player-replacement/blob/main/USL%20Final%20-%20nba_player_replacement_presentation.pdf) – Full analysis including EDA, model development, evaluation, and tuning
- [`slides/`](https://github.com/niliacklein33/usl-final-nba-player-replacement/blob/main/usl-final-nba-player-recommendation-system%20(2).ipynb) – Presentation slides summarizing the project
-  https://drive.google.com/file/d/1nU9idVkbl00uuMJ46EQP-x1p1OWKGM6U/view?usp=drive_link – Recorded presentation of the project
