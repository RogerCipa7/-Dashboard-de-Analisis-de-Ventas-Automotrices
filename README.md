# -Dashboard-de-Analisis-de-Ventas-Automotrices




Aquí tienes un README.md profesional y completo para tu repositorio, estructurado con descripción, tecnologías, flujo funcional y pasos detallados con placeholders para tus imágenes:
📊 Dashboard de Análisis de Ventas Automotrices









📌 Descripción del Proyecto
Aplicación web desarrollada con Flask que permite gestionar y analizar ventas de vehículos mediante dos canales: registro manual a través de formulario y procesamiento masivo de archivos CSV/Excel. El sistema incluye un módulo de limpieza de datos robusto que detecta y corrige inconsistencias (duplicados, valores nulos, formatos incorrectos) antes de persistir la información en base de datos, culminando en un dashboard de estadísticas con visualizaciones interactivas.
⚙️ Tecnologías Utilizadas
Capa
Tecnología
Propósito
Backend
Flask
Framework web para rutas y lógica de negocio
Procesamiento
Pandas, NumPy
Limpieza, transformación y análisis de datos
Visualización
Matplotlib, Seaborn
Generación de gráficos profesionales
Base de Datos
SQLite
Almacenamiento persistente de ventas
Frontend
HTML5, CSS3
Interfaz de usuario responsive
🗃️ Estructura de la Base de Datos
Tabla única: ventas
Campo
Tipo
Descripción
referencia
TEXT
Marca/modelo del vehículo (ej: "Toyota Corolla")
version
TEXT
Versión del vehículo (ej: "Limited", "SE")
anio
INTEGER
Año de fabricación del vehículo
fecha_venta
DATE
Fecha en que se realizó la venta
monto_total
REAL
Valor total de la transacción
🔄 Flujo Funcional
mermaid











🚀 Pasos de Uso
Paso 1: Pantalla de inicio
Accede al sistema mediante la ruta raíz para visualizar las opciones principales de registro y análisis.

Paso 2: Registro manual mediante formulario
Completa el formulario con los datos del vehículo vendido (referencia, versión, año, fecha y monto). Los datos se validan en tiempo real y se almacenan inmediatamente en la base de datos.

Paso 3: Procesamiento de archivo CSV/Excel
Sube un archivo con datos masivos de ventas. El sistema ejecuta automáticamente un pipeline de limpieza:
python
123456
# Pipeline de limpieza aplicado
1. Eliminación de filas duplicadas
2. Remoción de registros con valores nulos críticos
3. Conversión y validación de tipos numéricos (monto_total > 0)
4. Normalización de texto (mayúsculas/minúsculas consistentes)
5. Validación de fechas (elimina fechas futuras o inválidas)

Paso 4: Análisis de calidad de datos
El sistema reporta métricas del proceso de limpieza. Ejemplo con dataset de prueba:
Registros originales: 35 filas
Registros descartados: 5 filas (3 duplicados + 2 con montos inválidos)
Registros procesados: 30 filas válidas (85.7% de eficiencia)

Paso 5: Visualización de estadísticas
Dashboard con 4 gráficos generados dinámicamente desde los datos consolidados en la base de datos:
Gráfico
Tipo
Insights clave
Ventas por referencia
Barras verticales
Identifica modelos más populares
Ingresos totales
Barras horizontales
Muestra contribución económica por modelo
Distribución por versión
Circular (pie)
Proporción de ventas por versión
Años más vendidos
Línea con marcadores
Tendencias temporales de demanda

💡 Caso de Uso Real: Limpieza de Dataset
Dataset de entrada: ventas_automotrices.csv (35 registros)
Problema detectado
Cantidad
Acción tomada
Filas duplicadas
3
Eliminadas automáticamente
Monto total negativo/cero
1
Filtrado por validación > 0
Fecha futura (2027)
1
Descartada por validación temporal
Total registros válidos
30
Almacenados en BD
Resultado: Dataset limpio y listo para análisis, con mejora del 14.3% en calidad de datos.
