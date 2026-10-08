# Premier League match outcome prediction

Predicting the result of Premier League matches (**Win / Draw / Loss**) from the recent form of the two teams, comparing seven classifiers.

Homework for the *Machine Learning* course, Sapienza University of Rome (2025).

## Data

- `final_matches.csv`: 3,800 team-match records from the 2020/21 to 2024/25 seasons (goals, xG, possession, shots, ...).
- `PL_MatchDay11_25_26.csv`: real results of Matchday 11 of the 2025/26 season, used as an out-of-sample test.

## Approach

1. **Feature engineering**: rolling averages over the last 5 matches for both teams (xG, goals, possession, points), venue, and the differences between the two teams.
2. **Stratified 80/20 split**, compared against the majority-class baseline.
3. **Models**: Gaussian Naive Bayes, Softmax Regression, Logistic Regression, Decision Tree, Random Forest, linear SVM and RBF SVM, evaluated with 5-fold cross-validation, confusion matrices, ROC and learning curves.
4. **Real-world test** on the 10 matches of Matchday 11 (2025/26).

## Results (test set)

| Model | Accuracy | Macro F1 |
|---|---|---|
| Softmax / Logistic Regression | **61.5%** | 0.50 |
| SVM (linear) | 61.1% | 0.51 |
| SVM (RBF) | 60.1% | 0.49 |
| Random Forest | 59.9% | 0.46 |
| Naive Bayes | 55.9% | 0.50 |
| Decision Tree | 54.0% | 0.48 |

Wins and losses are predicted reasonably well; **draws remain the hardest class** for every model. More details are in [`results/`](results/).

## Running it

```bash
pip install -r requirements.txt
jupyter notebook premier_league_prediction.ipynb
```
