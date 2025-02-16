# 📝 Conclusiones Generales

## 1. Dependencia de un grupo reducido de productos:

El Análisis ABC revela que solo el 8% de los productos (Categoría A) son de alta rotación y son los que generan las mayores ventas y utilidad, mientras que más del 58% (Categoría C) presentan baja rotación.
Esto sugiere que la empresa depende fuertemente de unos pocos productos clave para generar la mayor parte de sus ventas, lo cual puede aumentar el riesgo si alguno de estos productos falla en su abastecimiento o pierde demanda.

## 2. Exceso de productos de baja rotación:

La alta proporción de productos de baja rotación podría estar inmovilizando capital y generando costos de almacenamiento innecesarios.
Estos productos no aportan significativamente a las ventas, y algunos podrían convertirse en inventario obsoleto.

## 3. Niveles de Reorden variables:

El análisis por punto de reorden muestra diferencias importantes entre las categorías de productos:
Alto (mayor a 50) → Productos con demanda constante o ventas recurrentes.
Medio (20 a 50) → Productos con demanda intermedia.
Bajo (menor a 20) → Productos poco vendidos o con ciclo de reposición largo.
Esto evidencia la necesidad de una gestión diferenciada de inventario según la rotación y criticidad de cada producto.

## 4. Divergencia entre Categorías de Productos:

Algunas categorías concentran la mayor parte del inventario, mientras que otras tienen pocos productos.
Esto podría indicar que ciertas líneas de productos están sobrerrepresentadas, mientras que otras podrían no estar siendo explotadas adecuadamente.

## 5. Riesgo por falta de optimización del inventario:

La combinación de alta concentración en pocos productos (A) y exceso de productos de baja rotación (C) sugiere que el inventario no está optimizado.
Esto podría afectar la liquidez de la empresa y generar pérdidas por productos estancados o faltantes en productos clave.

## 6. Proyección de las ventas:
Se realizó una proyección a traves de suavizacion exponencial tomando en cuenta los datos de los 7 dias anteriores(Febrero) para el calculo de  los primeros 3 días de Marzo con  el fin de tener una visual de la cantidad y el total de las ventas.
Se observa un repunte gradual en las ventas de licores en general, pero se debe abordar otra estrategia de ventas en los tipos de licor que no  aportan en utilidad a la compañia y continuar con  la estrategia de ventas implementada en Enero.

## 7. Modelo de clusterizacion:
Se realizó un modelo de clusters tipo K-Means en Python y se obtuvieron 4 grupo a saber, además se estableció la cantidad de productos en el invetario que pertenecen a cada grupo;
Cluster 0:Productos con baja rotación, precios elevados y niveles de inventario limitados.
Cluster 1: Productos de alta demanda, precios más bajos y mayor cantidad en stock, lo que indica alta rotación.
Cluster 2: Productos con demanda y stock moderados, con precios intermedios, mostrando un patrón proporcional entre cantidad y demanda.
Cluster 3: Productos con demanda extremadamente baja y precios muy altos, posiblemente artículos de lujo o de nicho.
 

## 📣 Mensaje Final para la Empresa:
*"Una gestión eficiente del inventario no solo reduce costos, sino que también garantiza que los productos más demandados siempre estén disponibles para los clientes. La optimización basada en el análisis ABC, seguimiento del cálculo de la rotación de inventario y la correcta asignación de puntos de reorden permitirá mejorar el rendimiento financiero de la empresa, aumentando las ventas y reduciendo las pérdidas por productos obsoletos."*