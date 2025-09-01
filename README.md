# kaggle-notebooks

## What is this?

This repository contains [Jupyter notebooks](https://jupyter.org/) that I created or worked on as part of some activity related to [Kaggle](https://www.kaggle.com/), a platform for data science and machine learning.

As Kaggle hosts competitions that are splendid opportunities for honing skills in data science and machine learning (as participants get to build models and submit predictions from provided datasets, and compare results on leaderboards), a lot of the notebooks found here will likely be related to Kaggle competitions. As I work iteratively on the models, I tend to rely on Kaggle's GitHub integration and save a version of the work at certain points (e.g. when submitting a prediction to the competition) to keep track of my progress.

The Jupyter notebooks, which can be identified by the `.ipynb` extension at the end of their file names, cannot (at this moment) be directly run on GitHub's interface, but GitHub does have support to automatically render them quite nicely in most cases.

## Content

### Competitions

Competitions are listed in reverse chronological order (based on start date).

- ["Binary Classification with a Bank Dataset"](competitions/playground-series-s5e8/)
    - final scores/rankings
        - [private](https://www.kaggle.com/competitions/playground-series-s5e8/leaderboard): **0.96609** (1900 / 3367)
        - [public](https://www.kaggle.com/competitions/playground-series-s5e8/leaderboard?tab=public): 0.96599 (1986 / 3367)
    - This was my second competition. Following the previous competition, I initially used traditional machine learning techniques for predictions, but towards the last few days of the competition, improvements in scores were harder to come by, so I decided to try my hand at my first neural network. I had to allocate some time for learning the new concepts, so I only designed a simple network, but it did allow me to gain a ~0.2% increase in both public/private scores.
    - Unlike my previous competition, it seemed I did _not_ have a problem with overfitting to the public leaderboard for this competition.
    - Of the solutions shared by top-ranking teams, it seems that (a lot of) _ensembling_ was a common theme, so this approach is something I would like to explore sometime.
- ["Predict the Introverts from the Extroverts"](competitions/playground-series-s5e7/)
    - final scores/rankings
        - [private](https://www.kaggle.com/competitions/playground-series-s5e7/leaderboard): **0.96842** (2281 / 4331)
        - [public](https://www.kaggle.com/competitions/playground-series-s5e7/leaderboard?tab=public): 0.97489 (1917 / 4331)
    - This was my first competition! I was only able to join it later and so I only had 3 days (out of the 1 month period the competition was held) to work on it, but it was still a good opportunity to examine some data and build models to make predictions.
    - I was wary from the start about overfitting to the public leaderboard, but it seems I still have much to learn (my private leaderboard ranking was 364 lower than the one for the public leaderboard).
- and more to come!