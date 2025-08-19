# Krok1
Kroczek po kroku
koncepcja:trening modeli lightGMB ze sciagnietych swiecach sekundowych i dodanych do nich wskaznikow ,nastepnie stream do postaci mozliwej predykcji.

wskazniki maja byc kalkulowane z rollingwindow lub z probek kompletowanych wylacznie do kalkulacji

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
-



