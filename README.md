# Modelo Predictivo para la Proyección de Ventas

## Descripción General

Este proyecto desarrolla un modelo predictivo utilizando técnicas de Machine Learning para proyectar ventas futuras basado en datos históricos de transacciones comerciales. Utilizando Random Forest como algoritmo principal, el modelo alcanza un alto nivel de precisión en la predicción de volúmenes de venta, identificando patrones estacionales y factores clave que influyen en los resultados comerciales.

## Motivación

En el entorno empresarial actual, la capacidad de anticipar con precisión las ventas futuras es fundamental para la planificación estratégica, gestión de inventario y optimización de recursos. Los métodos tradicionales de proyección, basados en promedios históricos o ajustes manuales, a menudo carecen de la precisión necesaria en mercados complejos y dinámicos.

Este proyecto surge como respuesta a estas limitaciones, buscando desarrollar un modelo que:

- Capture relaciones complejas entre múltiples variables
- Identifique patrones estacionales y tendencias a largo plazo
- Proporcione proyecciones precisas con un margen de error cuantificable
- Ofrezca insights accionables para la toma de decisiones comerciales

## Dataset

El análisis se realizó sobre un conjunto de datos que comprende 5,000 transacciones comerciales con 24 variables diferentes, incluyendo:

- Detalles de órdenes (fecha, prioridad)
- Información de clientes (tipo de cliente, ubicación)
- Características de productos (categoría, tipo de envase)
- Datos financieros (precios, márgenes, cantidades, descuentos)
- Información logística (método de envío, fechas, costos)

Enlace original del Dataset:
https://www.kaggle.com/datasets/rajneesh231/retail-insights-a-comprehensive-sales-dataset

### Análisis Exploratorio

El análisis descriptivo reveló varios patrones significativos:

1. **Distribución por categorías**: El 78% de las ventas provienen de artículos de oficina, 19% de tecnología y solo 3% de mobiliario.

2. **Concentración de ingresos**: Dos productos (copiadoras) generan más de $1 millón en ventas totales.

3. **Estacionalidad marcada**: Junio y julio se identificaron consistentemente como los meses de mayor volumen de ventas.

## Resultados

El modelo predictivo alcanzó métricas de rendimiento notables:

- **R²: 0.9341** - El modelo explica más del 93% de la variabilidad en los valores de venta.
- **MAPE: 10.05%** - Error porcentual absoluto medio del 10%, indicando un nivel aceptable de precisión.
- **RMSE: 0.2477** - Raíz del error cuadrático medio bajo, confirmando la precisión de las predicciones.

Además, el análisis de series temporales identificó una tendencia de crecimiento moderado para los próximos seis meses, con ventas proyectadas aproximadamente 8.7% superiores al promedio histórico.

## Conclusiones

1. **Alta capacidad predictiva**: El algoritmo Random Forest demuestra ser excepcionalmente efectivo para predecir ventas en contextos comerciales complejos.

2. **Importancia de patrones temporales**: La dimensión temporal se confirma como factor crucial en la proyección de ventas, con variaciones significativas entre diferentes períodos del año.

3. **Valor de la segmentación**: La distribución desigual entre categorías de productos sugiere la necesidad de estrategias diferenciadas por segmento.

4. **Precisión práctica**: Con un margen de error del 10%, el modelo ofrece proyecciones suficientemente precisas para aplicaciones prácticas en planificación comercial.

## Estructura del Repositorio

```
proyecto_prediccion_ventas/
│
├── ANEXO/                     # Archivos del proyecto organizados por categorías
│   ├── 1. Base de Datos/      # Datos utilizados en el análisis
│   │   ├── data.xlsx          # Dataset principal
│   │   └── nota.txt           # Notas sobre los datos
│   │
│   ├── 2. Descripcion de la Base de Datos/  # Diccionario de datos
│   │   ├── Descripcion de las columnas.docx
│   │   └── Descripcion de las columnas.txt
│   │
│   ├── 3. Analisis Descriptivo/    # Visualizaciones y análisis exploratorio
│   │   ├── analisis_descriptivo.ipynb
│   │   ├── ordenes_por_criticidad.png
│   │   ├── productos_mas_vendidos.png
│   │   ├── ventas_categoria_producto.png
│   │   ├── ventas_mesuales.png
│   │   ├── ventas_por_gestor.png
│   │   ├── ventas_por_periodo.png
│   │   ├── ventas_tipo_cliente.png
│   │   └── README.txt
│   │
│   ├── 4. Analisis Predictivo/     # Desarrollo y evaluación del modelo
│   │   ├── modelo_predictivo_final.ipynb
│   │   ├── tendencia_estacionalidad_residuos.png
│   │   └── ventas_historicas_prediccion.png
│   │
│   └── 5. Script de Codigos/       # Código fuente y scripts
│       ├── modelo.pdf
│       ├── modelo_final_unificado.ipynb
│       └── nota.txt
│
├── Presentación PPT Proyecto de Prediccion de Ventas.pdf  # Presentación del proyecto
├── Reporte Final - Proyecto Prediccion de Ventas.pdf      # Informe detallado
└── README.md                                             # Este archivo
```

## Tecnologías Utilizadas

- Python 3.8+
- Pandas y NumPy para manipulación de datos
- Matplotlib y Seaborn para visualizaciones
- Scikit-learn para modelado predictivo
- Statsmodels para análisis de series temporales

## Instalación y Uso

1. Clonar el repositorio:
```bash
git clone https://github.com/lMigev/proyecto_prediccion_ventas.git
cd proyecto_prediccion_ventas
```

2. Instalar dependencias:
```bash
pip install -r requirements.txt
```

3. Explorar los notebooks para ver el análisis detallado

4. Cargar el modelo pre-entrenado para hacer predicciones:
```python
import pickle

# Cargar el modelo
with open('model/modelo_random_forest.pkl', 'rb') as file:
    model = pickle.load(file)
    
# Hacer predicciones con nuevos datos
predictions = model.predict(X_new)
```

## Autor

Miguel Valzania - Estudiante de Maestría en Analítica de Datos - Universidad Tecnológica de Panamá

## Agradecimientos

Este proyecto fue desarrollado como parte del curso de Modelos Predictivos bajo la guía del Prof. Juan Marcos Castillo, PhD.

Agradecimiento especial a mis compañeras Katherine Batista y Victoria Rodriguez, quienes siempre estuvieron a disposición ante cualquier consulta puntual sobre la materia.
