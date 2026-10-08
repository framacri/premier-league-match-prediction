# Risultati Test Set - Tutti i Modelli

Questo documento contiene i risultati di tutti i modelli sul **Test Set** (20% dei dati).

## Classifica per Test Accuracy

| Posizione | Modello                       | Test Accuracy | Precision (Loss) | Precision (Draw) | Precision (Win) | F1-Score (Macro) |
| --------- | ----------------------------- | ------------- | ---------------- | ---------------- | --------------- | ---------------- |
| 🥇 **1°** | **Logistic Regression**       | **61.45%**    | 0.63             | 0.30             | 0.64            | 0.50             |
| 🥇 **1°** | **Softmax Regression**        | **61.45%**    | 0.63             | 0.30             | 0.64            | 0.50             |
| 🥈 **3°** | **SVM (Linear)**              | **61.05%**    | 0.62             | 0.28             | 0.65            | 0.51             |
| 🥉 **4°** | **SVM (RBF)**                 | **60.13%**    | 0.62             | 0.22             | 0.63            | 0.49             |
| 5°        | **Random Forest**             | **59.87%**    | 0.60             | 0.14             | 0.61            | 0.46             |
| 6°        | **Naive Bayes (Gaussian)**    | **55.92%**    | 0.57             | 0.30             | 0.64            | 0.50             |
| 7°        | **Decision Tree**             | **53.95%**    | 0.59             | 0.24             | 0.62            | 0.48             |

## Analisi Dettagliata per Classe

### Predizione Loss (Sconfitta)

| Modello                   | Precision | Recall | F1-Score |
| ------------------------- | --------- | ------ | -------- |
| SVM (Linear)              | 0.62      | 0.75   | 0.68     |
| Logistic Regression       | 0.63      | 0.76   | 0.68     |
| Softmax Regression        | 0.63      | 0.76   | 0.68     |
| SVM (RBF)                 | 0.62      | 0.75   | 0.68     |
| Random Forest             | 0.60      | 0.75   | 0.67     |
| Decision Tree             | 0.59      | 0.66   | 0.62     |
| Naive Bayes (Gaussian)    | 0.57      | 0.67   | 0.61     |

### Predizione Draw (Pareggio)

| Modello                   | Precision | Recall | F1-Score |
| ------------------------- | --------- | ------ | -------- |
| Naive Bayes (Gaussian)    | 0.30      | 0.19   | 0.23     |
| Logistic Regression       | 0.30      | 0.06   | 0.10     |
| Softmax Regression        | 0.30      | 0.06   | 0.10     |
| SVM (Linear)              | 0.28      | 0.09   | 0.13     |
| Decision Tree             | 0.24      | 0.18   | 0.20     |
| SVM (RBF)                 | 0.22      | 0.06   | 0.10     |
| Random Forest             | 0.14      | 0.01   | 0.02     |

### Predizione Win (Vittoria)

| Modello                   | Precision | Recall | F1-Score |
| ------------------------- | --------- | ------ | -------- |
| SVM (Linear)              | 0.65      | 0.78   | 0.71     |
| Logistic Regression       | 0.64      | 0.80   | 0.71     |
| Softmax Regression        | 0.64      | 0.80   | 0.71     |
| Naive Bayes (Gaussian)    | 0.64      | 0.67   | 0.65     |
| SVM (RBF)                 | 0.63      | 0.77   | 0.70     |
| Decision Tree             | 0.62      | 0.63   | 0.62     |
| Random Forest             | 0.61      | 0.80   | 0.69     |

## Confusion Matrix - Tutti i Modelli

Le confusion matrix mostrano la distribuzione delle predizioni per ogni modello. Le righe rappresentano la classe REALE, le colonne la classe PREDETTA.

### 1. Naive Bayes (Gaussian)

```
                Predetto
              Loss  Draw  Win
Reale  Loss   [196   43   55]
       Draw   [ 85   33   55]
       Win    [ 64   33  196]

Interpretazione:
- Loss: 196/294 corretti (66.7%), 43 confusi con Draw, 55 con Win
- Draw: 33/173 corretti (19.1%), 85 confusi con Loss, 55 con Win
- Win: 196/293 corretti (66.9%), 64 confusi con Loss, 33 con Draw
```

### 2. Logistic Regression

```
                Predetto
              Loss  Draw  Win
Reale  Loss   [222   17   55]
       Draw   [ 83   11   79]
       Win    [ 50    9  234]

Interpretazione:
- Loss: 222/294 corretti (75.5%), 17 confusi con Draw, 55 con Win
- Draw: 11/173 corretti (6.4%), 83 confusi con Loss, 79 con Win
- Win: 234/293 corretti (79.9%), 50 confusi con Loss, 9 con Draw
```

### 3. Softmax Regression

```
                Predetto
              Loss  Draw  Win
Reale  Loss   [222   17   55]
       Draw   [ 83   11   79]
       Win    [ 50    9  234]

Interpretazione:
- Loss: 222/294 corretti (75.5%), 17 confusi con Draw, 55 con Win
- Draw: 11/173 corretti (6.4%), 83 confusi con Loss, 79 con Win
- Win: 234/293 corretti (79.9%), 50 confusi con Loss, 9 con Draw

Nota: Identica a Logistic Regression (stesso algoritmo)
```

### 4. Decision Tree

```
                Predetto
              Loss  Draw  Win
Reale  Loss   [195   47   52]
       Draw   [ 81   31   61]
       Win    [ 57   52  184]

Interpretazione:
- Loss: 195/294 corretti (66.3%), 47 confusi con Draw, 52 con Win
- Draw: 31/173 corretti (17.9%), 81 confusi con Loss, 61 con Win
- Win: 184/293 corretti (62.8%), 57 confusi con Loss, 52 con Draw
```

### 5. Random Forest

```
                Predetto
              Loss  Draw  Win
Reale  Loss   [220    6   68]
       Draw   [ 92    2   79]
       Win    [ 54    6  233]

Interpretazione:
- Loss: 220/294 corretti (74.8%), 6 confusi con Draw, 68 con Win
- Draw: 2/173 corretti (1.2%), 92 confusi con Loss, 79 con Win
- Win: 233/293 corretti (79.5%), 54 confusi con Loss, 6 con Draw
```

### 6. SVM (Linear Kernel)

```
                Predetto
              Loss  Draw  Win
Reale  Loss   [220   25   49]
       Draw   [ 82   15   76]
       Win    [ 50   14  229]

Interpretazione:
- Loss: 220/294 corretti (74.8%), 25 confusi con Draw, 49 con Win
- Draw: 15/173 corretti (8.7%), 82 confusi con Loss, 76 con Win
- Win: 229/293 corretti (78.2%), 50 confusi con Loss, 14 con Draw
```

### 7. SVM (RBF Kernel)

```
                Predetto
              Loss  Draw  Win
Reale  Loss   [220   21   53]
       Draw   [ 84   11   78]
       Win    [ 49   18  226]

Interpretazione:
- Loss: 220/294 corretti (74.8%), 21 confusi con Draw, 53 con Win
- Draw: 11/173 corretti (6.4%), 84 confusi con Loss, 78 con Win
- Win: 226/293 corretti (77.1%), 49 confusi con Loss, 18 con Draw
```

## Analisi Pattern Confusion Matrix

### Pattern Comuni

1. **Predizione Loss**:

   - Migliori: Logistic/Softmax (222/294 = 75.5%), Random Forest (220/294 = 74.8%)
   - Peggiori: Decision Tree (195/294 = 66.3%)

2. **Predizione Draw**:

   - Migliori: Naive Bayes Gaussian (33/173 = 19.1%), Decision Tree (31/173 = 17.9%)
   - Peggiori: Random Forest (2/173 = 1.2%)

3. **Predizione Win**:
   - Migliori: Logistic/Softmax (234/293 = 79.9%), Random Forest (233/293 = 79.5%)
   - Peggiori: Decision Tree (184/293 = 62.8%)

### Errori Principali

- **Draw → Loss**: 81-94 casi (tutti i modelli confondono Draw con Loss)
- **Draw → Win**: 55-79 casi (tutti i modelli confondono Draw con Win)
- **Loss ↔ Win**: 49-68 casi (confusione bidirezionale tra Loss e Win)

## Osservazioni Principali

### ✅ Punti di Forza

1. **Logistic Regression e Softmax**: Migliori performance complessive (61.45%)
2. **SVM (Linear)**: Performance eccellente, buon bilanciamento tra classi
3. **Predizione Win/Loss**: Tutti i modelli mantengono buone performance (60-65% precision)

### ⚠️ Problemi Comuni

1. **Predizione Draw**: Tutti i modelli hanno difficoltà con i pareggi

   - Precision Draw: 14-57% (molto variabile)
   - Recall Draw: 1-19% (estremamente basso)
   - F1-Score Draw: 2-23% (molto basso)

### 📊 Distribuzione Errori

**Pattern comune nei modelli migliori:**

- **Loss**: Buona predizione (precision 60-63%, recall 75-76%)
- **Win**: Buona predizione (precision 61-65%, recall 77-80%)
- **Draw**: Scarsa predizione, spesso confuso con Loss o Win

## Raccomandazioni

### 🎯 Modelli da Usare

1. **Logistic Regression / Softmax**: Miglior accuracy complessiva
2. **SVM (Linear)**: Performance simili, buona interpretabilità
3. **Random Forest**: Buona accuracy, feature importance disponibile

### 🔧 Miglioramenti Suggeriti

1. **Class Weights**: Bilanciare le classi per migliorare predizione Draw
2. **SMOTE**: Oversampling della classe Draw per training
3. **Feature Engineering**: Aggiungere features specifiche per distinguere pareggi
4. **Ensemble**: Combinare i migliori modelli (Logistic + SVM Linear + Random Forest)

### ❌ Modelli da Evitare

- **Decision Tree**: Performance instabili, rischio overfitting

## Confronto Cross-Validation

| Modello                   | CV Accuracy | Std Dev |
| ------------------------- | ----------- | ------- |
| Logistic Regression       | 65.69%      | ±2.43%  |
| Softmax Regression        | 65.69%      | ±2.43%  |
| SVM (Linear)              | 64.61%      | ±2.02%  |
| SVM (RBF)                 | 64.14%      | ±3.35%  |
| Random Forest             | 61.64%      | ±3.20%  |
| Naive Bayes (Gaussian)    | 56.35%      | ±4.88%  |
| Decision Tree             | 54.97%      | ±3.83%  |

**Nota**: Le performance di CV sono generalmente migliori del test set, indicando che i modelli sono ben generalizzati.

## Conclusioni

- **Miglior modello**: Logistic Regression / Softmax (61.45% accuracy)
- **Performance realistiche**: 55-61% è normale per predizioni sportive
- **Problema principale**: Predizione dei pareggi (tutti i modelli hanno difficoltà)
- **Modelli comparabili**: Logistic, Softmax, SVM Linear hanno performance molto simili
