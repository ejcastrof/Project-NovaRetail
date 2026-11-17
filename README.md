# Project-NovaRetail
# 🛒 NovaRetail+ — Análisis correlacional del comportamiento de clientes

Proyecto de análisis exploratorio en Python para el equipo de **Crecimiento y retención** de NovaRetail+, una plataforma de comercio electrónico en Latinoamérica. Hecho como parte del bootcamp de Análisis de Datos de TripleTen.

## 🎯 Pregunta de negocio

> ¿Qué factores del comportamiento del cliente están más fuertemente asociados con el ingreso anual generado?

Es un análisis **correlacional**: correlación ≠ causalidad.

## 📊 Dataset

- **15,000 clientes** y **12 columnas**, sin valores nulos.
- **Numéricas:** `edad`, `nivel_ingreso`, `visitas_mes`, `compras_mes`, `gasto_publicidad_dirigida`, `satisfaccion`, `ingreso_anual`.
- **Binarias:** `miembro_premium`, `abandono`.
- **Categóricas:** `id_cliente`, `tipo_dispositivo`, `region`.
- **Variable objetivo:** `ingreso_anual`.

## 🔍 Metodología

1. **Exploración y limpieza:** revisión de tipos, nulos y rangos. `edad` se convirtió de `float64` a `int`.
2. **Supuestos:** escala de magnitud (< 0.1 prácticamente nula, 0.1–0.5 débil, 0.5–0.8 moderada, > 0.8 fuerte) y umbral de colinealidad de 0.85.
3. **Visualización:** heatmap de correlaciones, pairplot (muestra de 2,000 filas) y scatterplots.
4. **Correlaciones:** Pearson y Spearman entre variables numéricas, y correlación punto-biserial para variables binarias.
5. **Asociación categórica:** V de Cramér (chi-cuadrado) para dispositivo, región, premium y abandono.
6. **Interpretación:** cada hallazgo incluye evidencia visual y numérica, interpretación no causal, "no podemos afirmar" e implicación de negocio.

## 💡 Hallazgos principales

1. **Las compras mensuales son el factor más asociado con el ingreso anual.** La correlación es de 0.97 y de 0.93 al excluir a los 4,567 clientes sin compras (30.4 %). La relación es en parte mecánica: cada compra genera ingreso.
2. **Premium se asocia con un ingreso algo mayor y menos abandono.** El ingreso promedio es de 44.58 frente a 35.30, y el abandono de 4.4 % frente a 16.8 % (V de Cramér = 0.12, asociación débil). Puede haber autoselección y causalidad inversa.
3. **Visitas y publicidad dirigida se asocian débilmente con el ingreso.** Las correlaciones con el ingreso son 0.34 (visitas) y 0.20 (gasto publicitario). La edad, el nivel de ingreso y la satisfacción casi no se asocian con él (0.02, 0.02 y 0.06).
4. **El abandono no se distingue por las variables analizadas.** Las correlaciones están entre -0.024 y 0.008. Dispositivo y región tampoco se asocian, y la única señal es la asociación modesta con premium.

## 🧭 Implicaciones de negocio

- Priorizar las acciones que impulsen las compras (conversión, recompra, ofertas).
- Probar un piloto de conversión a premium con grupo de control antes de apostar por él.
- Evaluar con un experimento A/B la eficiencia del gasto publicitario antes de aumentarlo.
- Incorporar nuevos datos (antigüedad, precio, motivo de baja) para entender el abandono.

## ⚠️ Limitaciones

- Correlación ≠ causalidad.
- Corte transversal de un solo año (2024).
- Análisis de a pares, sin controlar por otras variables ni pruebas de significancia.
- Variables limitadas: sin precio, tipo de producto ni antigüedad.

## 🚀 Próximos pasos

- Segmentar por grupos (premium, región, dispositivo, niveles de compras).
- Construir un modelo multivariado para el riesgo de abandono.
- Validar con experimentos (piloto premium y pruebas A/B de publicidad).

## 🛠️ Herramientas

Python · pandas · NumPy · SciPy · Matplotlib · Seaborn · Jupyter Notebook

## 📁 Estructura del repositorio

```
├── NovaRetail_Proyecto.ipynb   # Notebook con el análisis completo
├── data/                       # Dataset (si aplica)
└── README.md
```

## 👤 Autor

**Elkin Javier Castro Fonseca** — Analista de datos en formación (TripleTen)
[LinkedIn] www.linkedin.com/in/elkin-castro-fonseca · [GitHub](https://github.com/ejcastrof)
