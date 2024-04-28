# ucboulder-ml-supervised

## Data

Data is acquired from:
https://www.kaggle.com/datasets/sujaykapadnis/top-100-billboard

Data preprocessing:
- Filter data between years 2010 and 2020
- Summarize weekly billboard data into song statistics
- Clean the data
- Merge with Spotify audio features

Cleaning is done in `data.ipynb`.

Cleaned dataset is stored in `data/billboard_2010s.csv`.

## Model

Learn `highest_position` of a song reached on the Billboard chart.

### Regression

Try regression in `model_v1.ipynb`.

Audio features have very low correlation with song position.

### Classification

Transform `highest_position` into `high_low` class.
Songs that reach position higher than 50 are considered high performers
and others are in the low class.

Learn classifier on song metadata (entry position, weeks on chart).

Learn classifiers on audio features:
- RandomForest
- SVC
- AdaBoosting DecisionTrees

Notebook: `model_v3.ipynb`

## Conclusion

We cannot learn a good classifier from the audio features only.

But can predict the highest position achieved by a song based on the lowest_position (usually the position it enters the chart at) and weeks_on_chart.

This suggests a strong momentum effect in song popularity and ranking.

**The higher a song enters the billboard chart and the longer it stays on it, the higher position it will reach.**
