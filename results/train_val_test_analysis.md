# Trade-off Train/Validation/Test Split

## Situazione Attuale

Il codice attuale utilizza:
- **Train/Test Split**: 80% training, 20% test
- **Cross-Validation**: 5-fold sul training set per la selezione del modello

## Trade-off e Considerazioni

### 1. **Train Set (Training)**
- **Scopo**: Addestrare il modello
- **Trade-off**: 
  - ✅ Più dati = migliore apprendimento
  - ❌ Meno dati = rischio di underfitting
- **Raccomandazione**: 60-70% dei dati

### 2. **Validation Set**
- **Scopo**: Tuning degli iperparametri, selezione del modello
- **Trade-off**:
  - ✅ Permette di scegliere il miglior modello senza toccare il test set
  - ❌ Sottrae dati al training
- **Raccomandazione**: 15-20% dei dati

### 3. **Test Set**
- **Scopo**: Valutazione finale, stima della performance su dati mai visti
- **Trade-off**:
  - ✅ Stima imparziale della performance
  - ❌ Deve essere usato UNA SOLA VOLTA alla fine
  - ❌ Sottrae dati al training
- **Raccomandazione**: 15-20% dei dati

## Strategie Disponibili

### Strategia A: Train/Test + Cross-Validation (Attuale)
```
[80% Train] [20% Test]
  └─> 5-fold CV sul Train
```
- ✅ Massimo uso dei dati per training
- ✅ Cross-validation riduce overfitting
- ❌ Nessun set dedicato per hyperparameter tuning
- **Quando usare**: Dataset piccoli, cross-validation sufficiente

### Strategia B: Train/Validation/Test
```
[60% Train] [20% Validation] [20% Test]
```
- ✅ Set dedicato per tuning
- ✅ Test set completamente isolato
- ❌ Meno dati per training
- **Quando usare**: Dataset grandi, bisogno di tuning approfondito

### Strategia C: Nested Cross-Validation
```
[80% Train] [20% Test]
  └─> Outer CV (5-fold)
      └─> Inner CV (3-fold) per ogni fold
```
- ✅ Massima robustezza
- ✅ Stima più accurata
- ❌ Computazionalmente costoso
- **Quando usare**: Dataset medi, massima affidabilità

## Raccomandazioni per il Tuo Dataset

Con ~3800 partite (dopo feature engineering ~3000+):

### Opzione 1: Mantenere Attuale (Train/Test + CV)
- **Split**: 80% Train, 20% Test
- **CV**: 5-fold sul training
- **Pro**: Massimo uso dei dati
- **Contro**: Nessun validation set dedicato

### Opzione 2: Train/Validation/Test
- **Split**: 60% Train, 20% Validation, 20% Test
- **Pro**: Set dedicato per tuning
- **Contro**: Meno dati per training (~1800 partite)

### Opzione 3: Time-Based Split (Raccomandato per dati temporali)
- **Train**: Partite più vecchie (es. 2019-2022)
- **Validation**: Partite intermedie (es. 2023)
- **Test**: Partite più recenti (es. 2024)
- **Pro**: Simula scenario reale (predire il futuro)
- **Contro**: Richiede dati ordinati temporalmente

## Metriche da Monitorare

1. **Training Accuracy**: Performance sul training set
2. **Validation Accuracy**: Performance sul validation set
3. **Test Accuracy**: Performance sul test set (UNA VOLTA SOLA)
4. **Gap Train-Validation**: Indica overfitting se troppo grande
5. **Gap Validation-Test**: Indica se il validation è rappresentativo

## Segnali di Problemi

- **Overfitting**: Train accuracy >> Validation accuracy
- **Underfitting**: Train accuracy ≈ Validation accuracy, ma entrambe basse
- **Data Leakage**: Test accuracy >> Validation accuracy (impossibile! Verificare features)

