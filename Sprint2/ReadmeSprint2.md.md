<a name="_vjtybcyisrqk"></a>Sprint 2

Desarrollo del informe en Power BI

Se llevó a cabo la importación de archivos Parquet almacenados en BigQuery a Power BI, utilizando el método de importación en lugar de otros métodos disponibles como la conexión directa o la consulta en vivo. Este proceso consistió en los siguientes pasos:

`    `Conexión a BigQuery: Primero, se estableció la conexión entre Power BI y BigQuery utilizando la opción de "Obtener datos" en Power BI. Se seleccionó BigQuery como fuente de datos y se autenticó el acceso utilizando las credenciales de Google Cloud, permitiendo que Power BI pudiera acceder a los archivos almacenados en BigQuery.

`    `Selección de archivos Parquet: Una vez conectados, se exploraron las tablas y archivos disponibles en BigQuery. Se seleccionaron los archivos Parquet específicos que contenían los datos relevantes para el análisis. Estos archivos están almacenados en BigQuery en formato columnar, lo que permite una lectura eficiente y de alto rendimiento para grandes volúmenes de datos.

`    `Importación de datos: Se optó por utilizar el método de importación de los datos en Power BI en lugar de usar la conexión directa o la consulta en vivo. Esto significa que los datos fueron cargados localmente en Power BI, creando una copia del archivo Parquet dentro del archivo de proyecto de Power BI.

`    `Este proceso tuvo varias ventajas:

`        `Rendimiento mejorado: Dado que los datos se cargan directamente en Power BI, las consultas y el análisis son más rápidos, ya que los datos no requieren conexión constante a BigQuery.

`        `Desempeño estable: Los informes pueden ser consultados de forma más estable sin depender de la conexión en tiempo real con BigQuery, lo que reduce la latencia y mejora la experiencia del usuario.

`        `Posibilidad de trabajar offline: Al importar los datos, Power BI permite trabajar con los informes sin necesidad de estar conectado continuamente a la fuente externa.

`    `Transformación y modelado de datos: Después de la importación, se realizaron transformaciones adicionales en Power BI utilizando el editor de consultas para limpiar, transformar y modelar los datos según las necesidades del análisis. Esto puede incluir renombrar columnas, cambiar tipos de datos, filtrar registros innecesarios o crear nuevas métricas.

`    `Visualización y análisis: Una vez que los datos fueron importados y transformados, se crearon las visualizaciones necesarias en Power BI, como gráficos, tablas y paneles de control. Esto permitió realizar análisis más detallados y obtener insights de los datos que anteriormente se encontraban en BigQuery.

Limpieza y transformación de datos

Se realizó la limpieza y transformación de los datos, asegurando que todos los valores fueran correctos, sin duplicados, y en los formatos adecuados para su análisis. Se creo una tabla con el fin de categorizar los productos por tipo de licor y una tabla de medidas donde se almacenaron todas las medidas calculadas. 

Creación de medidas, columnas y relaciones en Power BI

Se generaron medidas que permitieran realizar cálculos específicos que no estaban presentes en los datos crudos, así como definir las relaciones entre las tablas para habilitar un análisis cruzado. Con estas herramientas, se logró preparar los datos para su uso en las visualizaciones y gráficos del informe final

Medidas Creadas:

1. Margen de Ganancia (%) = DIVIDE([Utilidad Neta], SUM(Ventas[TotalVenta]), 0) \* 100
1. Utilidad Neta = SUM(Ventas[TotalVenta]) - SUM(Ventas[Costo]) -SUM(Ventas[Impuestos])
1. Stock\_Actual = SUM(InventarioFinal[cantidad])
1. Stock\_Inicial = SUM(InventarioInicial[Cantidad])
1. Rotacion\_Inventario = DIVIDE([CMV], [Promedio\_Inventario])
1. CMV = SUMX(Ventas, Ventas[cantidadVendida] \* RELATED(Productos[Costo]))
1. Costo Total de Compras = SUMX(DetalleCompra, DetalleCompra[Cantidad] \* DetalleCompra[CostoUnitario])
1. Total\_Ventas = SUM(Ventas[TotalVenta])

Diseño de reportes y gráficos

- Paleta de colores

Se utilizó una paleta de colores alineada con el logo de la empresa para mantener coherencia visual y reforzar la identidad de marca. Esto no solo mejora la estética, sino que también facilita la interpretación de la información, creando una experiencia más intuitiva y profesional. Una identidad visual bien definida genera confianza y credibilidad, haciendo que los reportes sean más atractivos y fáciles de comprender.



![](Aspose.Words.e842e65e-cfa8-4744-826f-0d24f13e565a.001.png)**Oro metálico:** #CFA567  
![](Aspose.Words.e842e65e-cfa8-4744-826f-0d24f13e565a.002.png)


**Púrpura profundo:** #5E239D
![](Aspose.Words.e842e65e-cfa8-4744-826f-0d24f13e565a.003.png)


**Azul medianoche:** #2C3E50
![](Aspose.Words.e842e65e-cfa8-4744-826f-0d24f13e565a.004.png)


**Blanco humo:** #F5F5F5
![](Aspose.Words.e842e65e-cfa8-4744-826f-0d24f13e565a.005.png)


**Gris oscuro:** #2E2531
![](Aspose.Words.e842e65e-cfa8-4744-826f-0d24f13e565a.006.png)


**Rosa champaña:** #EDA9BA
![](Aspose.Words.e842e65e-cfa8-4744-826f-0d24f13e565a.007.png)


**Azul petróleo:** #1F4E79
![](Aspose.Words.e842e65e-cfa8-4744-826f-0d24f13e565a.008.png)


**Verde esmeralda:** #50C878
![](Aspose.Words.e842e65e-cfa8-4744-826f-0d24f13e565a.009.png)

**Azul petroleo claro:** #447AB5 

### <a name="_u1kpvm5sk3p4"></a>**Esquema de uso de colores en el dashboard:**
#### <a name="_5x23edfnrzwz"></a>**1. Fondo general y áreas principales:**
- **Azul medianoche (#2C3E50)**
  Para el fondo general o secciones principales (sidebar, encabezados de secciones). Ofrece un aspecto profesional y elegante.
#### <a name="_y9hz4de4iee1"></a>**2. Encabezados principales:**
- **Oro metálico (#D4AF37)**
  Para títulos y encabezados principales del dashboard. Este color destaca de inmediato, capturando la atención.
#### <a name="_xjq1g8j01klf"></a>**3. Subtítulos y texto destacado:**
- **Púrpura profundo (#5E239D)**
  Para subtítulos y texto que necesita énfasis, como etiquetas de gráficos o métricas importantes.
#### <a name="_3qice0xvw1na"></a>**4. Texto general:**
- **Gris oscuro (#2E2531)**
  Para texto estándar, ya que es legible y neutral.
#### <a name="_ba75wa2vbm3j"></a>**5. Fondos de tarjetas o widgets:**
- **Blanco humo (#F5F5F5)**
  Para fondo en tarjetas de información, tablas o gráficos.
#### <a name="_8xfyjx3bsh0b"></a>**6. Gráficos positivos (crecimiento, métricas altas):**
- **Verde esmeralda (#50C878)**
  Para** asignar a barras, líneas o indicadores que representen datos positivos, como ganancias o crecimiento.
#### <a name="_mqfqr4js02hm"></a>**7. Gráficos negativos (pérdidas, métricas bajas):**
- **Rosa champaña (#E5B8C4)**
  Para métricas negativas o advertencias en gráficos.
#### <a name="_wwxswn28f02g"></a>**8. Elementos interactivos (botones, enlaces):**
- **Azul petróleo (#1F4E79)**
  Para botones, enlaces o íconos interactivos.
- Tipos de gráficas
  - Gráfico de Líneas: Es útil para mostrar **tendencias a lo largo del tiempo** o **cambios continuos** en datos. Permite visualizar cómo varían los valores de una métrica a lo largo de un período. Se utilizó para mostrar la rotación del inventario en el año 2016 y 2017 tanto a nivel general como por producto.
  - Gráfico de barras: Se utiliza para **comparar magnitudes** entre diferentes categorías o grupos. Las barras horizontales o verticales muestran la cantidad o tamaño de cada categoría.
  - Pie Chart: Es útil para mostrar cómo se distribuyen las partes de un **todo**. Cada "rebanada" del gráfico representa una **proporción** de un total, por lo que es ideal para representar **porcentajes** o distribuciones. Se utilizó este gráfico para realizar un análisis ABC y establecer que productos tienen el mayor impacto en las ventas o en el valor total del inventario, y así optimizar la gestión de existencias y recursos.
  - Tabla: Las tablas son útiles para mostrar datos detallados y **numéricos** de manera estructurada y fácil de leer. Dentro del dashboard se realizó una tabla para mostrar el costo, el total vendido, la utilidad neta y el margen de ganancia de cada producto. 

<a name="_ogpgzgce1xqc"></a>Pruebas de calidad del reporte

**Tipos de pruebas de calidad del reporte:**

1. **Pruebas de precisión:**
   1. Verificar que los datos presentados en el reporte sean correctos, es decir, que se basen en información exacta y verificada.
1. **Pruebas de consistencia:**
   1. Comprobar que los datos sean consistentes en el reporte, es decir, que no haya contradicciones o discrepancias entre diferentes secciones del reporte.
1. **Pruebas de usabilidad:**
   1. Evaluar si el reporte es fácil de entender y utilizar para el público objetivo. Esto incluye el diseño, la disposición y la claridad del reporte.
1. **Pruebas de formato:**
   1. Comprobar que el reporte tenga el formato correcto, con una presentación ordenada, tablas bien alineadas, gráficos adecuados, etc.

Recomendaciones

![Gráfico, Gráfico de dispersión

El contenido generado por IA puede ser incorrecto.](Aspose.Words.e842e65e-cfa8-4744-826f-0d24f13e565a.010.png)

**Resumen:**

- **Cluster 0:** Productos con baja rotación, precios elevados y niveles de inventario limitados.
- **Cluster 1:** Productos de alta demanda, precios más bajos y mayor cantidad en stock, lo que indica alta rotación.
- **Cluster 2:** Productos con demanda y stock moderados, con precios intermedios, mostrando un patrón proporcional entre cantidad y demanda.
- **Cluster 3:** Productos con demanda extremadamente baja y precios muy altos, posiblemente artículos de lujo o de nicho.

**Sugerencias:**

- Para los productos en el Cluster 1, sería conveniente optimizar los niveles de inventario y asegurarse de que haya suficiente stock disponible para satisfacer la alta demanda.
- Los productos en el Cluster 0 podrían beneficiarse de una revisión de precios o de implementar una estrategia de marketing para mejorar la rotación.
- Los productos del Cluster 3 parecen pertenecer a una categoría exclusiva, por lo que podría ser útil evaluar si su bajo volumen de ventas está justificado o si la estrategia de precios de alto valor es sostenible. Otra opción sería revisar las tiendas que los venden o aquellas ubicadas en zonas exclusivas de la ciudad y considerar reubicarlos allí.
- El Cluster 2 muestra una demanda estable, por lo que mantener un inventario equilibrado podría ser crucial para satisfacer las necesidades del mercado.

