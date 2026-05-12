# 🏠 Proyecto 1 — Predicción de Precios Airbnb NYC

Análisis exploratorio y modelado predictivo sobre **35.036 listados** de Airbnb en Nueva York (scraping de abril 2026).

## 🌎 **[REPORTE MODELO ARIBNB](https://juanguana21.github.io/Proyecto_Airbnb/)**

## 📊 Resultados

| Modelo | MAE ($) | RMSE ($) | R² |
|---|---|---|---|
| **Random Forest** ✅ | 50.76 | 82.00 | 0.68 |
| XGBoost | 51.21 | 81.67 | 0.69 |
| Red Neuronal (MLP) | 58.95 | 91.95 | 0.60 |
| KNN | 59.24 | 94.83 | 0.58 |

> El modelo acierta dentro de un margen del ±15% en el **42.11%** de los casos.

## 📁 Estructura

```
├── Proyecto_1_Airbnb.ipynb   # Notebook principal (Google Colab)
├── reporte_airbnb.html        # Reporte visual del proyecto
└── README.md
```

## 🔄 Pipeline

1. **Exploración** — 90 columnas, 35.036 filas, precio como objeto string
2. **Limpieza** — Eliminación de columnas vacías, selección de 20 features relevantes
3. **Filtrado** — Filas sin precio eliminadas (40.94% de pérdida, decisión correcta)
4. **Imputación** — Mediana por grupo para baños/camas, moda para categóricas, 0 para reseñas sin reviews
5. **Feature Engineering** — `has_license`, conteo de amenities, capping de outliers
6. **Transformación** — StandardScaler, OneHot, TargetEncoder, transformación log del target
7. **Modelado** — 4 modelos con cross-validation (5 folds)

## 🛠️ Tecnologías

- Python 3.12
- pandas · numpy · scikit-learn · XGBoost · category_encoders
- matplotlib · seaborn · missingno

## 📂 Datos

Dataset de [InsideAirbnb](http://insideairbnb.com/) para Nueva York — `listings.csv` (no incluido por tamaño).

---
*Proyecto desarrollado en Google Colab*
