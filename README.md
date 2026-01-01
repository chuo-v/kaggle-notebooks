# kaggle-notebooks

## What is this?

This repository contains [Jupyter notebooks](https://jupyter.org/) that I created or worked on as part of some activity related to [Kaggle](https://www.kaggle.com/), a platform for data science and machine learning.

As Kaggle hosts competitions that are splendid opportunities for honing skills in data science and machine learning (as participants get to build models and submit predictions from provided datasets, and compare results on leaderboards), a lot of the notebooks found here will likely be related to Kaggle competitions. As I work iteratively on the models, I tend to rely on Kaggle's GitHub integration and save a version of the work at certain points (e.g. when submitting a prediction to the competition) to keep track of my progress.

The Jupyter notebooks, which can be identified by the `.ipynb` extension at the end of their file names, cannot (at this moment) be directly run on GitHub's interface, but GitHub does have support to automatically render them quite nicely in most cases.

## Content

### Competitions

Competitions are listed in reverse chronological order (based on start date).

- ["Diabetes Prediction Challenge"](competitions/playground-series-s5e12/)
    - final [ROC AUC scores](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.roc_auc_score.html) & rankings
        - [private](https://www.kaggle.com/competitions/playground-series-s5e12/leaderboard): **0.69612** (1099 / 4208)
        - [public](https://www.kaggle.com/competitions/playground-series-s5e12/leaderboard?tab=public): 0.69879 (1126 / 4208)
    - My second try at ensembling! I initially played around with different models to establish some baselines before moving to build an ensemble of base models using the [two classes I implemented before](https://github.com/chuo-v/machine-learning-utils/blob/68997ef1778570d7361aa38efb912dbe14de59c3/ensemble-learning/stacking/stacking_predictions_retriever.py).
    - Heeding the lessons learned from my previous competition (see below):
        - I was more attentive in applying regularization and proactively removing base models from the ensemble that were redundant and mainly contributed noise.
            - From a high of 59 base models in my ensemble, I whittled the number of base models down to 31 by the end of the competition by removing the base models that got low feature importances consistently from the meta-models trained through numerous iterations.
        - I added a more diverse mix of base models (CatBoostClassifiers, LGBMClassifiers, XGBClassifiers) using a few different feature sets and various hyperparameter combinations (tuned via a lot of Optuna studies) picked to further promote diversity in the base model predictions.
    - In the second half of the competition, I was able to continue climbing the public leaderboard by supplementing a sizable amount of feature generation, and due largely to the strong brakes (high regularization) I applied to the meta-model, it seems I was able to avoid overfitting this competition! My main takeaway from this competition is that I should explore using even more generated features to provide my models with the signal that they otherwise have difficulty latching on to.
- ["Predicting the Beats-per-Minute of Songs"](competitions/playground-series-s5e9/)
    - final [RMSE scores](https://en.wikipedia.org/wiki/Root_mean_square_deviation) & rankings
        - [private](https://www.kaggle.com/competitions/playground-series-s5e9/leaderboard): **26.40941** (1395 / 2583)
        - [public](https://www.kaggle.com/competitions/playground-series-s5e9/leaderboard?tab=public): 26.38670 (655 / 2583)
    - This was my first try at ensembling! I implemented two classes (which can be found [here](https://github.com/chuo-v/machine-learning-utils/blob/68997ef1778570d7361aa38efb912dbe14de59c3/ensemble-learning/stacking/stacking_predictions_retriever.py) as well) to streamline the process of retrieving and reusing my base model predictions.
    - I got a bit overzealous and in the spirit of experimentation, ended up amassing 85 base models (mostly XGBRegressors). To help my meta-model (also an XGBRegressor) wade through all the noise and latch on to signal, I tried pruning base models using Optuna studies where whether a base model was included in a particular study was [suggested](https://optuna.readthedocs.io/en/stable/reference/generated/optuna.trial.Trial.html#optuna.trial.Trial.suggest_categorical) by Optuna, which in retrospect I did not handle very efficiently.
    - Unfortunately, I ended up overfitting quite a bit to the public leaderboard. My main takeaway from this competition is that even with ensembling, one needs to be more careful with applying regularization to avoid overfitting.
- ["Binary Classification with a Bank Dataset"](competitions/playground-series-s5e8/)
    - final [ROC AUC scores](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.roc_auc_score.html) & rankings
        - [private](https://www.kaggle.com/competitions/playground-series-s5e8/leaderboard): **0.96609** (1900 / 3367)
        - [public](https://www.kaggle.com/competitions/playground-series-s5e8/leaderboard?tab=public): 0.96599 (1986 / 3367)
    - This was my second competition. Following the previous competition, I initially used traditional machine learning techniques for predictions, but towards the last few days of the competition, improvements in scores were harder to come by, so I decided to try my hand at my first neural network. I had to allocate some time for learning the new concepts, so I only designed a simple network, but it did allow me to gain a ~0.2% increase in both public/private scores.
    - Unlike my previous competition, it seemed I did _not_ have a problem with overfitting to the public leaderboard for this competition.
    - Of the solutions shared by top-ranking teams, it seems that (a lot of) _ensembling_ was a common theme, so this approach is something I would like to explore sometime.
- ["Predict the Introverts from the Extroverts"](competitions/playground-series-s5e7/)
    - final [accuracy scores](https://www.kaggle.com/code/metric/accuracy-score) & rankings
        - [private](https://www.kaggle.com/competitions/playground-series-s5e7/leaderboard): **0.96842** (2281 / 4331)
        - [public](https://www.kaggle.com/competitions/playground-series-s5e7/leaderboard?tab=public): 0.97489 (1917 / 4331)
    - This was my first competition! I was only able to join it later and so I only had 3 days (out of the 1 month period the competition was held) to work on it, but it was still a good opportunity to examine some data and build models to make predictions.
    - I was wary from the start about overfitting to the public leaderboard, but it seems I still have much to learn (my private leaderboard ranking was 364 lower than the one for the public leaderboard).
- and more to come!