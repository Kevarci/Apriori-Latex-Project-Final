# Proyecto de Análisis de Reglas de Asociación con Apriori

## Configuración del Entorno

Para configurar el entorno de desarrollo:

1. Crear un entorno virtual:
-python -m venv venv

2. Activar el entorno virtual:
- Windows (cmd): `venv\Scripts\activate`
- Windows (PowerShell): `venv\Scripts\Activate.ps1`
- Linux/Mac: `source venv/bin/activate`

3. Instalar dependencias:
- pip install -r requirements.txt

## Implementaciones Recientes

### Preprocesamiento de Datos
- Carga de datos de transacciones desde el archivo 'order_products__train.csv'
- Implementación de enfoque optimizado para manejar grandes volúmenes de datos:
- Selección de los 1000 productos más frecuentes para reducir dimensionalidad
- Creación de matriz binaria usando crosstab para representar presencia/ausencia de productos
- Conversión a formato binario (1 para presencia, 0 para ausencia)

### Estructuras de Datos Eficientes
- Implementación de múltiples estructuras para almacenar transacciones:
- Estructura de diccionario: Eficiente para búsquedas y operaciones de conjuntos
- Arrays de bits: Representación compacta en memoria para operaciones bit a bit
- DataFrame sparse: Combinación de pandas con ahorro de memoria para matrices dispersas
- Cada estructura optimizada para diferentes fases del algoritmo Apriori

### Generación de Itemsets Frecuentes
- Implementación de la generación de 1-itemsets frecuentes
- Establecimiento de umbral de soporte mínimo configurable
- Cálculo del soporte para cada producto individual
- Filtrado de productos que cumplen con el soporte mínimo
- Ordenamiento de itemsets por soporte en orden descendente
- Preparación de estructura de datos para generación de itemsets de mayor tamaño

### Próximos Pasos
- Generación de itemsets de mayor tamaño (2-itemsets, 3-itemsets, etc.)
- Implementación de reglas de asociación basadas en los itemsets frecuentes
- Evaluación de reglas mediante métricas como soporte, confianza y lift
- Visualización de resultados y patrones descubiertos