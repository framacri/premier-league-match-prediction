# Results Analysis - Premier League Matchday 11 (2025/2026)

## Real-match test results

### Model leaderboard by accuracy

| Position | Model                       | Correct | Total | Accuracy  |
| -------- | --------------------------- | ------- | ----- | --------- |
| 🥇 **1st** | **Logistic Regression**       | **5**   | 10    | **50.0%** |
| 🥇 **1st** | **Softmax Regression**        | **5**   | 10    | **50.0%** |
| 🥈 **3rd** | **Decision Tree**             | **4**   | 10    | **40.0%** |
| 🥈 **3rd** | **Random Forest**             | **4**   | 10    | **40.0%** |
| 🥈 **3rd** | **SVM (RBF)**                 | **4**   | 10    | **40.0%** |
| 🥉 **6th** | **SVM (Linear)**              | **3**   | 10    | **30.0%** |
| 7th       | **Naive Bayes (Gaussian)**    | **0**   | 10    | **0.0%**  |

## Matches under test

1. **Tottenham vs Manchester United**: 2-2 (Draw)
2. **West Ham vs Burnley**: 3-2 (Win for West Ham)
3. **Everton vs Fulham**: 2-0 (Win for Everton)
4. **Sunderland vs Arsenal**: 2-2 (Draw) ⚠️ Sunderland has no historical data
5. **Chelsea vs Wolves**: 3-0 (Win for Chelsea)
6. **Brentford vs Newcastle**: 3-1 (Win for Brentford)
7. **Crystal Palace vs Brighton**: 0-0 (Draw)
8. **Aston Villa vs Bournemouth**: 4-0 (Win for Aston Villa)
9. **Nottingham Forest vs Leeds United**: 3-1 (Win for Nottingham Forest)
10. **Manchester City vs Liverpool**: 3-0 (Win for Manchester City)

## Observations

### ✅ Top-performing models

- **Logistic Regression / Softmax**: 50% accuracy - best performers on the held-out fixtures
- **Decision Tree / Random Forest / SVM (RBF)**: 40% accuracy - decent performance

### ⚠️ Issues spotted

1. **Naive Bayes**: 0% accuracy - completely failed on real matches
2. **Draw prediction**: Still hard (only the Decision Tree got the first draw right)
3. **Sunderland**: Team missing from the historical dataset, so predictions rely on default values

### 📊 Comparison with the test set

| Model              | Test Set Accuracy | Real Match Accuracy | Difference |
| ------------------ | ----------------- | ------------------- | ---------- |
| Logistic Regression | 61.45%           | 50.0%               | -11.45%    |
| Softmax Regression  | 61.45%           | 50.0%               | -11.45%    |
| Decision Tree       | 53.95%           | 40.0%               | -13.95%    |
| Random Forest       | 59.87%           | 40.0%               | -19.87%    |
| SVM (RBF)           | 60.13%           | 40.0%               | -20.13%    |
| SVM (Linear)        | 61.05%           | 30.0%               | -31.05%    |

**Note**: Real-match performance is generally lower than the test set, which is expected and signals either mild overfitting or that the real fixtures have a different distribution.

## Conclusions

- **Best model on real matches**: Logistic Regression / Softmax (50%)
- **Realistic performance**: 30-50% is normal for sports predictions on brand-new fixtures
- **Naive Bayes**: Not suitable for this task
- **Recommendation**: Use Logistic Regression or Softmax for real-world predictions
