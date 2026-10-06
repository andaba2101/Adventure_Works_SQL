# Adventure_Works_SQL
Sprint 3 | Proyecto 3: Análisis del desempeño financiero con SQL - Resumen ejecutivo

## 🏢 Contexto y objetivos

Desarrollé este proyecto a partir de un escenario de análisis financiero para AdventureWorks. Asumí el rol de analista de datos con el propósito de evaluar en qué mercados se generan mayores ingresos y qué tan rentable resulta cada mercado al considerar la inversión en marketing.

Trabajé con información de órdenes, productos, clientes, territorios y campañas. Mi objetivo fue integrar estas fuentes mediante SQL y preparar indicadores que permitieran orientar la priorización de mercados y la evaluación del presupuesto comercial.

### Preguntas de negocio

Durante el análisis, me enfoqué en responder dos preguntas centrales:

- ¿Cuánto estamos ganando por país?
- ¿Qué tan rentable es cada mercado considerando los gastos de marketing?

También busqué aportar información para evaluar dónde convendría invertir el siguiente dólar de marketing, sin basar la decisión únicamente en el volumen de ingresos.

### Objetivos del proyecto

Para desarrollar el análisis, me propuse:

- Comprender el esquema relacional y las conexiones entre las tablas.
- Escribir consultas con `JOIN` para integrar información de distintas fuentes.
- Extraer, filtrar y preparar los datos mediante SQL.
- Revisar valores `NULL`, convertir tipos de datos y estandarizar categorías.
- Calcular ingresos, costos, beneficio bruto, margen y ROI.
- Validar la coherencia de los resultados mediante controles de calidad.
- Organizar los cálculos en vistas reutilizables.
- Comunicar los resultados mediante un informe ejecutivo y visualizaciones.

## 🗃️ Datos y herramientas

### Tablas utilizadas

Trabajé con un subconjunto del dataset de AdventureWorks. En el siguiente cuadro describo la función de cada tabla dentro del análisis.

| Tabla | Información disponible | Cómo la utilicé |
| --- | --- | --- |
| `ventas_2017` | Transacciones de líneas de pedido correspondientes a 2017. Cada fila representa una línea por producto y pedido. | La utilicé como base transaccional para analizar las ventas. |
| `productos` | Catálogo con atributos, costo y precio unitario por `ClaveProducto`. | Incorporé la información de producto necesaria para calcular costos y contextualizar las ventas. |
| `productos_categorias` | Jerarquía de categorías y subcategorías. | Enriquecí los productos con su clasificación comercial. |
| `clientes` | Información de clientes, segmentos y ubicación. | Complementé el análisis con el contexto de los compradores. |
| `territorios` | Correspondencia entre `ClaveTerritorio`, país y continente. | Organicé la comparación geográfica de los mercados. |
| `campanas` | Gasto de marketing por territorio y campaña. | Incorporé la inversión comercial para evaluar el retorno por mercado. |

### Recursos técnicos

| Recurso | Cómo lo apliqué |
| --- | --- |
| SQL | Extraje, preparé, integré y agregué los datos del proyecto. |
| `JOIN` | Combiné las tablas utilizando sus relaciones y claves correspondientes. |
| Manejo de `NULL` | Revisé valores faltantes y definí su tratamiento dentro de las consultas. |
| Conversión de tipos | Preparé los campos necesarios para realizar cálculos consistentes. |
| Estandarización de categorías | Organicé las etiquetas para facilitar agrupaciones y comparaciones. |
| Vistas SQL | Guardé consultas y cálculos para reutilizarlos durante el análisis. |
| Controles de calidad —QA— | Contrasté totales y márgenes antes de comunicar los resultados. |
| Visualizaciones e informe ejecutivo | Presenté las métricas y su significado para la dirección financiera. |

## 🔄 Proceso de análisis

Organicé el proyecto en cinco etapas, desde la comprensión del esquema hasta la comunicación ejecutiva.

| Etapa | Qué hice | Propósito |
| :---: | --- | --- |
| 1 | Exploré el diagrama de entidades y la definición de las tablas. | Comprendí el nivel de detalle de los datos y las relaciones entre las fuentes. |
| 2 | Extraje y preparé la información mediante consultas y vistas SQL. | Construí una base consistente para los cálculos financieros. |
| 3 | Calculé los KPIs y los organicé en vistas. | Consolidé los indicadores necesarios para comparar mercados. |
| 4 | Validé los resultados mediante controles QA. | Revisé la coherencia de los totales y los márgenes. |
| 5 | Preparé los outputs y el resumen ejecutivo. | Traduje los resultados técnicos en información útil para el negocio. |

### Exploración del esquema

Antes de calcular los indicadores, revisé qué representaba cada tabla y cómo podía relacionarla con las demás.

Presté especial atención al nivel de detalle de `ventas_2017`: una fila corresponde a una línea de producto dentro de un pedido. Esta definición orientó la manera en que organicé las uniones y las agregaciones.

### Extracción y preparación

Durante la preparación de los datos:

- Seleccioné los campos necesarios para responder las preguntas del negocio.
- Apliqué filtros para delimitar el análisis.
- Revisé los valores faltantes.
- Preparé los tipos de datos utilizados en los cálculos.
- Estandaricé las categorías relevantes.
- Organicé las transformaciones mediante consultas y vistas.

### Cálculo de indicadores

Consolidé los siguientes indicadores para evaluar el desempeño financiero de los mercados:

| Indicador | Qué busqué evaluar |
| --- | --- |
| Ingresos | Cuánto genera cada mercado a partir de sus ventas. |
| Costos | Qué magnitud tienen los costos asociados a los productos vendidos. |
| Beneficio bruto | Qué resultado se obtiene al contrastar ingresos y costos de producto. |
| Margen | Cómo se comporta la rentabilidad relativa de las ventas. |
| Gasto de marketing | Cuánta inversión comercial corresponde a cada territorio o campaña. |
| ROI | Cómo se relaciona el retorno calculado con la inversión considerada en el análisis. |

Utilicé estos indicadores de manera conjunta para evitar priorizar un mercado únicamente porque presenta una facturación elevada.

### Validación y controles QA

Antes de preparar el informe, revisé la coherencia de los resultados.

Mis controles se enfocaron en:

- Comprobar los totales obtenidos en las consultas.
- Contrastar ingresos, costos y beneficio.
- Revisar la consistencia de los márgenes calculados.
- Verificar que las agregaciones respondieran al nivel de análisis esperado.
- Mantener una trazabilidad clara entre las tablas de origen, las vistas y los resultados finales.

## 📊 Comunicación ejecutiva

Mi objetivo no fue solamente calcular métricas, sino explicar qué significaban y cómo podían apoyar las decisiones de la dirección financiera.

Para organizar el informe, utilicé el método:

> Contexto → Hallazgo → Implicación

### Estructura del resumen ejecutivo

| Componente | Cómo organicé el contenido |
| --- | --- |
| Contexto | Describí qué analicé, con qué datos trabajé y qué preguntas financieras busqué responder. |
| Hallazgos | Organicé la comparación de ingresos, beneficio, margen y ROI por mercado. |
| Implicación | Relacioné los resultados con la priorización de mercados y la revisión del presupuesto comercial. |
| Ideas accionables | Enfoqué las recomendaciones en decisiones respaldadas por los indicadores y sus controles de calidad. |

### Criterios para seleccionar hallazgos

Para estructurar las conclusiones del informe, me enfoqué en:

- Comparar la contribución económica de cada país.
- Reconocer diferencias de margen entre mercados.
- Contrastar la inversión de marketing con el retorno calculado.
- Identificar mercados o campañas que requirieran una revisión más detallada.

Busqué sintetizar entre tres y cuatro hallazgos principales, evitando saturar el resumen con todos los resultados de las consultas.

### Orientación de las recomendaciones

Planteé que las recomendaciones debían conectar cada hallazgo con una decisión concreta.

Mis dos líneas de evaluación fueron:

1. Priorizar los mercados que presentaran mejores indicadores financieros, considerando tanto su contribución como el retorno de la inversión.
2. Revisar la estructura de costos o el presupuesto de marketing en los mercados que mostraran resultados menos favorables.

La selección de países y las acciones específicas debían quedar respaldadas por la tabla final de indicadores, no por supuestos previos.

## 📦 Entregables y reflexión personal

### Entregables

| Entregable | Contenido |
| --- | --- |
| Consultas SQL | Organicé la extracción, preparación, integración y cálculo de indicadores. |
| Vistas de análisis | Dejé disponibles cálculos reutilizables para consultar los resultados financieros. |
| Tabla final de indicadores | Consolidé ingresos, costos, beneficio, margen, gasto de marketing y ROI por mercado. |
| Controles QA | Documenté las comprobaciones de coherencia de totales y márgenes. |
| Visualizaciones | Apoyé la comparación de mercados y la lectura ejecutiva de las métricas. |
| Resumen ejecutivo | Sinteticé el análisis mediante el enfoque Contexto → Hallazgo → Implicación. |

### Preguntas de reflexión

Para consolidar mi comprensión del proyecto, me planteé las siguientes preguntas:

| Tema | Pregunta que utilicé para reflexionar |
| --- | --- |
| Margen y ROI | ¿Cómo diferencio lo que me indica el margen de lo que me indica el ROI? |
| Comparación entre mercados | ¿Qué factores podrían explicar un ROI más alto en Estados Unidos frente a otros países? |
| Sensibilidad del presupuesto | ¿Cómo cambiaría el ROI si aumentara el gasto de campañas en un 50 % y qué supuestos necesitaría definir para evaluarlo? |

### Aprendizaje del proyecto

Este proyecto me permitió organizar un análisis financiero desde la estructura de los datos hasta su comunicación ejecutiva.

Mi enfoque fue mantener una relación clara entre las consultas, los indicadores, las validaciones y las recomendaciones. También incorporé la búsqueda de información y el uso de recursos de apoyo como parte de mi proceso de aprendizaje.

La principal prioridad de mi trabajo fue transformar los resultados de SQL en una explicación comprensible para la dirección financiera: qué aporta cada mercado, cómo se relacionan sus ingresos con los costos y qué información conviene revisar antes de modificar la inversión en marketing.
```
