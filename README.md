# Predicció del Valor de Jugadors FIFA – README

## Descripció del Projecte

Aquest projecte té com a objectiu desenvolupar un model de *Machine Learning* capaç de predir el **valor de mercat de jugadors de futbol** utilitzant dades de jugadors FIFA. S'han aplicat tècniques d'anàlisi exploratòria, enginyeria de característiques i comparació de diversos models per trobar la millor arquitectura predictiva.

---

## Contingut del Projecte

* **price_prediction.ipynb** – Notebook principal amb tot el pipeline:

  * Carrega de dades
  * Neteja i preprocessat
  * Anàlisi exploratòria (EDA)
  * Visualitzacions avançades
  * Enginyeria de característiques
  * Entrenament i comparació de models
  * Conclusions
* **fifa_players.csv** – Dataset original utilitzat
* **png/** – Gràfics generats durant l'anàlisi

---

## Preprocessament i Enginyeria de Característiques

Durant el preprocessat s'han aplicat diverses transformacions:

### Neteja de dades

* Eliminació o imputació de valors *NaN*.
* Conversió de formats (valors econòmics a milions €).
* Tractament de categories i variables de text.

### Noves característiques generades

* **primary_position**: posició principal extreta de la llista de posicions.
* **position_count**: nombre de posicions que pot ocupar cada jugador.
* **age_groups**: classificació d'edats.
* **interaccions** entre rating, potencial i edat.

Aquestes noves variables milloren la capacitat predictiva del model.

---

## Anàlisi Exploratori (EDA)

Es van generar múltiples visualitzacions per entendre millor el dataset:

### Distribucions generals

* Histogrames de valor, edat, rating i potencial.

### Relacions clau

* Relació no lineal exponencial entre **rating general** i **valor**.
* Jugadors **més joves** = valors més alts.
* Potencial impacta fortament en el preu.

### Gràfic destacat

Un bubble scatter que mostra:

* X: rating general
* Y: valor (€)
* Color: edat
* Mida: potencial

El gràfic mostra clarament patrons no lineals, motivant l'ús de models com Random Forest o XGBoost.

---

## Models de Machine Learning

S'han provat tres models:

| Model             | R2         | RMSE         | MAE          |
| ----------------- | ---------- | ------------ | ------------ |
| Linear Regression | 0.6409     | €3,657,027   | €1,916,931   |
| Random Forest     | 0.9642     | €1,154,216   | €203,902     |
| **XGBoost**       | **0.9750** | **€964,605** | **€183,075** |

### Model guanyador: **XGBoost**

* Explica el **97.5%** de la variabilitat del valor.
* Millor rendiment en tots els errors.
* Captura excel·lentment relacions no lineals.

---

## Conclusions

* El valor de mercat depèn principalment de **rating**, **edat** i **potencial**.
* La relació és clarament **no lineal**, per això XGBoost obté millor rendiment.
* Les noves característiques (primera posició, versatilitat...) milloren la predicció.
* El model resultant és sòlid i apte per predir valors de jugadors dins d'un marge d'error raonable.

---

## Requisits

* Llibreries principals:

  * pandas
  * numpy
  * matplotlib / seaborn
  * scikit-learn
  * xgboost


## Execució del Projecte

Obrir el notebook:

```
jupyter notebook price_prediction.ipynb
```

Executeu totes les cel·les en ordre.

---

## Autor

**Héctor Sánchez i Roger Garcia**
Projecte de predicció de valor de jugadors basat en dades FIFA.

Link de github
https://github.com/NIU1704248/fifa_prediction
---
