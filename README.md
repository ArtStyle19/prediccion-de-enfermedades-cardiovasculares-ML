# Predicción de Enfermedades Cardiovasculares con Machine Learning

---

## Desarrollado por:

## JHON ALEX CENTENO CCORIMANYA

## OLIVER FRANK CHOQUE CHURA

## CLEVER EDISON PAREDES VELASQUEZ

## JORGE GUILLERMO OLARTE QUISPE

## JACK BENJAMIN CANCAPA PACCO

---

## Universidad Nacional del Altiplano – Ingeniería de Sistemas

## Machine Learning Actividad CRISP-DM (16/09/25)

--

Este proyecto implementa un flujo completo de **Data Science** bajo la metodología **CRISP-DM** para predecir el riesgo de enfermedad cardiovascular a partir de datos clínicos.

Se utilizan distintos algoritmos de **Machine Learning** (Regresión Logística, Árboles de Decisión, SVM y Random Forest) para comparar resultados y seleccionar el mejor modelo, priorizando el **Recall** como métrica clave (enfocada en no dejar pacientes enfermos sin detectar).

---

## 🚀 Objetivo

Desarrollar un modelo predictivo que, con al menos un 80% de precisión, permita identificar pacientes con riesgo de enfermedad cardiovascular y apoyar la **prevención temprana** en entornos clínicos.

---

## 📊 Dataset

- Fuente: [Heart Disease Dataset - Kaggle](https://www.kaggle.com/datasets/johnsmith88/heart-disease-dataset)
- Registros: **1,025 pacientes**
- Variables: **14 columnas (13 predictoras + 1 objetivo)**
- Variable objetivo:
  - `target = 1`: paciente con enfermedad cardiovascular
  - `target = 0`: paciente sano

### Variables principales:

- `age`: Edad del paciente
- `sex`: Sexo (0 = mujer, 1 = hombre)
- `cp`: Tipo de dolor en el pecho (0–3)
- `trestbps`: Presión arterial en reposo
- `chol`: Colesterol sérico (mg/dl)
- `fbs`: Azúcar en sangre en ayunas (>120 mg/dl)
- `restecg`: Resultados ECG en reposo (0–2)
- `thalach`: Frecuencia cardíaca máxima alcanzada
- `exang`: Angina inducida por ejercicio (1 = sí, 0 = no)
- `oldpeak`: Depresión del ST inducida por ejercicio
- `slope`, `ca`, `thal`: Variables relacionadas con resultados clínicos

---

## 🧪 Metodología CRISP-DM

### 1️⃣ Comprensión del Negocio

- Reducir la mortalidad por enfermedades cardiovasculares.
- Apoyar la prevención mediante modelos predictivos.
- Objetivo técnico: modelo con **Recall ≥ 80%**.

### 2️⃣ Comprensión de los Datos

- Dataset balanceado (≈51% enfermos, 49% sanos).
- No hay valores nulos.
- Se identificaron outliers en colesterol (> 500 mg/dl).

### 3️⃣ Preparación de los Datos

- Imputación de valores faltantes (mediana/moda).
- Normalización de variables numéricas.
- One-Hot Encoding para variables categóricas.
- Eliminación de duplicados y corrección de inconsistencias.

### 4️⃣ Modelado

Se probaron cuatro algoritmos:

- **Regresión Logística** (baseline, interpretable).
- **Árbol de Decisión** (explicable pero con riesgo de sobreajuste).
- **SVM (kernel RBF)** (potente pero costoso en datos grandes).
- **Random Forest** (modelo final elegido por mejor desempeño en Recall y AUC).

### 5️⃣ Evaluación

Métricas calculadas:

- Accuracy
- Precision
- Recall (Sensibilidad)
- F1-score
- AUC-ROC

Ejemplo de resultados (conjunto de test):

| Modelo              | Accuracy | Precisión | Recall | F1-Score | AUC  |
| ------------------- | -------- | --------- | ------ | -------- | ---- |
| Regresión Logística | 0.87     | 0.86      | 0.90   | 0.88     | 0.94 |
| Árbol de Decisión   | 0.99     | 1.00      | 0.97   | 0.99     | 0.99 |
| Random Forest       | 1.00     | 1.00      | 1.00   | 1.00     | 1.00 |
| SVM (kernel RBF)    | 0.95     | 0.94      | 0.96   | 0.95     | 0.98 |

🔎 Se seleccionó **Random Forest** como modelo final por su excelente desempeño, aunque se advierte posible **sobreajuste** → recomendable aplicar validación cruzada y ajuste de hiperparámetros.

### 6️⃣ Despliegue

Opciones consideradas:

- Dashboard interactivo con **Streamlit** o **Flask**.
- Script en Python para análisis por lotes.
- Integración en sistemas hospitalarios (fase futura).

---

## ⚙️ Tecnologías

- Python 3.10
- Librerías principales:
  - `pandas`, `numpy`
  - `scikit-learn`
  - `matplotlib`, `seaborn`

---

## 📌 Próximos pasos

- Validación cruzada con más iteraciones.
- Ajuste de hiperparámetros (GridSearchCV).
- Recolección de más datos clínicos.
- Evaluación de sesgos por sexo/edad.
- Despliegue como aplicación web para uso clínico.

---

## 👥 Equipo

Proyecto realizado en equipo como parte del curso de **Minería de Datos / Machine Learning aplicado en medicina**.
