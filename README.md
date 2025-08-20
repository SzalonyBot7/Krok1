# Krok1
Kroczek po kroku
koncepcja:trening modeli lightGMB ze sciagnietych swiecach sekundowych i dodanych do nich wskaznikow ,nastepnie stream do postaci mozliwej predykcji.

wskazniki maja byc kalkulowane z rollingwindow lub z probek zapewniajac wylacznie do kalkulacji

wyliczanie srednich ma sie odbywac roznymi metodami

plan dzialania:
-ustawienie pary
-ustawienie czasu od kiedy sciagnac do kiedy
-wyliczenie jaki zapas historycznych danych potrzeba do warmupu wszystkich wskaznikow
-waliduj wartosci wskaznikow co 1000 cykli liczenia w trakcie treningu
-trening wlasciwy: ( jesli to pierwszy trening ,ustawienia do czego bedziemy uzywac modelu,
-klasyfikacja(wielomianowa lub binarna),
-regresja(klasyczna,regresja l1 l2,quanitil regresion),
-chcialbym tez survival analiz oraz zostawic w kodzie miejsce na custom objective(do krzyzowej korelacji predykcji)
-custom metrics ,zeby decydowac o procesie oceny treningu
-parametry wspilne dla wszystkich zastosowan:

  "hiperparametry_wspolne": {
    "num_leaves": 63,
    "max_depth": -1,
    "learning_rate": 0.02,
    "n_estimators": 2000,
    "feature_fraction": 0.8,
    "bagging_fraction": 0.8,
    "bagging_freq": 5,
    "lambda_l1": 0.1,
    "lambda_l2": 0.5,
    "min_data_in_leaf": 50,
    "min_gain_to_split": 0.01,
    "early_stopping_rounds": 100,
    "verbosity": -1,
    "seed": 42
  },
  
zakladka do  "binary_classification": {
    "objective": "binary",
    "metric": ["binary_logloss", "auc"]
  },
  
zakladka do  "regression": {
    "objective": "regression",
    "metric": ["l2", "l1"]
  },
  
zakladka do  "multiclass": {
    "objective": "multiclass",
    "metric": ["multi_logloss", "multi_error"],
    "num_class": 3
  },
  
zakladka do  "ranking": {
    "objective": "lambdarank",
    "metric": ["ndcg"],
    "label_gain": [0, 1, 2]
  }
}
- FORMA TRENINGU:
DANE:
- pobierane z binance ,paczki do warmup
- nastepnie synchronizacja z ustawionym poczatkiem 


