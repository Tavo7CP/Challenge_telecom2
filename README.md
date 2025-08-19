# Challenge_telecom2
¡Listo! Te dejo una versión **corregida, estructurada y más profesional** de tu texto, lista para usar como `README.md`:

---

# 📉 TelecomX — Predicción de Cancelación de Clientes (Churn)

Proyecto de **análisis y modelado predictivo** para anticipar la cancelación de clientes en una empresa de telecomunicaciones. Combina **EDA**, **machine learning** y **herramientas de interpretabilidad** (SHAP) para comprender los factores que influyen en el abandono y proponer **estrategias de retención** efectivas.

## 📁 Estructura del repositorio

```
TelecomX-Churn
├── data/                       # Datos procesados y tratados
├── notebooks/                  # Notebooks de análisis y modelado
├── models/                     # Modelos entrenados (opcional)
├── outputs/                    # Resultados y visualizaciones
├── informe_cancelacion_telecom_x.md   # Informe técnico en Markdown
├── requirements.txt            # Paquetes necesarios
└── README.md                   # Este archivo
```

## 🧠 Objetivo del proyecto

Desarrollar un modelo que **prediga la cancelación** de un cliente a partir de sus **características de contrato**, **historial de pagos** y **uso de servicios**, habilitando acciones proactivas para **reducir la tasa de churn**.

## 🧪 Proceso de desarrollo

**1) Carga y limpieza de datos**

* Eliminación de identificadores únicos (ID).
* Codificación de variables categóricas con `get_dummies`.
* Balanceo de clases con **SMOTE**.
* Normalización con **StandardScaler**.

**2) Análisis exploratorio (EDA)**

* Histogramas, boxplots y matriz de correlación.
* Identificación de variables influyentes.
* Análisis de churn por **tipo de contrato**, **servicios** y **método de pago**.

**3) Selección de características**

* `SelectKBest` con `f_classif`.
* **K óptimo: 29** variables por rendimiento.

**4) Entrenamiento de modelos**

* **Regresión Logística** (`LogisticRegression`)
* **Random Forest** (`RandomForestClassifier`)
* **Gradient Boosting** (`GradientBoostingClassifier`)
* **K-Nearest Neighbors** (KNN)
* **Ensemble** (VotingClassifier: **LR + GB**)

**5) Optimización de hiperparámetros**

* **GridSearchCV** con validación cruzada estratificada.

**6) Evaluación**

* Métricas: **Accuracy, Precision, Recall, F1 Score**.
* **Matriz de confusión**.
* **Curva ROC** y **AUC**.
* Interpretabilidad con **SHAP** y coeficientes logísticos.

## 🏆 Resultados

| Modelo                 |  Accuracy  |  Precision | Recall | F1 Score |    AUC    |
| ---------------------- | :--------: | :--------: | :----: | :------: | :-------: |
| Gradient Boosting      |   0.7887   |   0.5907   | 0.5864 |  0.5886  |   0.850   |
| Regresión Logística    |   0.7956   |   0.5997   | 0.6221 |  0.6107  |   0.840   |
| **Ensemble (LR + GB)** | **0.8025** | **0.6277** | 0.5740 |  0.5996  | **0.851** |

✅ El **Ensemble (LR + GB)** combina la **interpretabilidad** de LR y el **desempeño** de GB, logrando el **mejor AUC**.

## 🔍 Principales factores de cancelación

(Según **SHAP** y correlación)

* Contratos **“month-to-month”**.
* Método de pago: **electronic check**.
* **Ausencia** de servicios adicionales (soporte técnico, seguridad, respaldo online).
* **Baja antigüedad** (pocos meses en la empresa).
* **Altos cargos mensuales** y **bajo engagement**.

## 💡 Estrategias de retención sugeridas

* Incentivar **contratos de mayor plazo** (1–2 años).
* Ofrecer **bundles** de valor (soporte + seguridad + respaldo).
* Promover **pagos automáticos** (tarjeta o transferencia).
* **Monitoreo proactivo** a clientes con cargos mensuales altos.
* **Programas de fidelización** para clientes nuevos o con baja antigüedad.

## ⚙️ Requisitos

* Python **3.8+**
* `pandas`, `numpy`, `matplotlib`, `seaborn`
* `scikit-learn`, `imblearn`, `shap`

Instalación rápida:

```bash
pip install -r requirements.txt
```

> Si no usas `requirements.txt`, instala manualmente:
>
> ```bash
> pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn shap
> ```

## ▶️ Cómo reproducir

1. Clona el repositorio y crea un entorno virtual.
2. Instala dependencias (`pip install -r requirements.txt`).
3. Abre los notebooks en `notebooks/` y ejecuta en orden:

   * `01_eda.ipynb` → EDA y preprocesamiento
   * `02_feature_selection.ipynb` → Selección de variables
   * `03_modeling.ipynb` → Entrenamiento, tuning y evaluación
   * `04_explainability.ipynb` → SHAP y análisis interpretativo
4. Revisa resultados en `outputs/` y modelos (si se guardan) en `models/`.

---
  Autor: Gustavo Angel Chaparro Pacheco
