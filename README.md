# airline-price-prediction
Flight price prediction &amp; analysis: API data collection, EDA, and ML pipeline (regression, classification, clustering)
# ✈️ Airline Price Prediction

ML-пайплайн для анализа и прогнозирования цен на авиабилеты по внутренним рейсам Казахстана: от сбора данных через API до моделей регрессии, классификации, кластеризации и рекомендательной системы.

## Пайплайн

| Шаг | Ноутбук | Что делает |
|---|---|---|
| 1 | `01_api_collection.ipynb` | Сбор данных через [Travelpayouts API](https://travelpayouts.com/) — 100+ пар городов Казахстана, 90–200 билетов на маршрут |
| 2 | `02_data_cleaning.ipynb` | Объединение источников, обработка IATA-кодов городов, приведение временных зон |
| 3 | `03_eda.ipynb` | Разведочный анализ: распределение цен, топ-10 дешёвых/дорогих маршрутов, влияние пересадок, дня недели и авиакомпании на стоимость |
| 4 | `04_ml_pipeline.ipynb` | RandomForest-регрессия цены (R² = 0.85), классификация "дешёвый/выгодный" билет, KMeans-кластеризация (5 сегментов) с визуализацией через PCA, content-based рекомендательная система на cosine similarity |

## Данные

Полный датасет — 1347 записей о ценах на авиабилеты по внутренним рейсам Казахстана, собранных через Travelpayouts API. В репозитории — `sample_flights.csv`, сэмпл из 20 строк (по одному маршруту на строку) для демонстрации структуры данных.

## Стек

Python, pandas, NumPy, scikit-learn, Keras/TensorFlow, matplotlib, seaborn, plotly, requests

## Результаты

- Регрессия цены билета: **R² = 0.85**, MAE ≈ 0.01, RMSE ≈ 0.03 (RandomForest)
- Кластеризация билетов: 5 сегментов с визуализацией через PCA
- Рекомендательная система: похожие билеты по cosine similarity между признаками
