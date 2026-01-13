# ☕ Análisis Exploratorio de Ventas: Optimización de Retail de Café

## 📋 1. Antecedentes del Proyecto
La empresa analizada opera en la industria de cafeterías y venta minorista de bebidas y alimentos, con presencia en tres ubicaciones físicas: Astoria, Hell’s Kitchen y Lower Manhattan. El modelo de negocio se basa en ventas transaccionales de alto volumen, con un portafolio de productos que incluye bebidas calientes (café y té), panadería y una línea reducida de productos premium como granos de café especializados y artículos de marca.**. 

Desde la perspectiva de un analista de datos interno, el objetivo principal del proyecto es comprender los patrones de consumo, identificar fuentes reales de ingresos, evaluar la dependencia del volumen frente al valor por transacción, y detectar oportunidades de crecimiento sostenible sin necesidad de incrementar la base de clientes.**.

### Las métricas clave del negocio incluyen:

  * Cantidad vendida por transacción.
  * Precio unitario.
  * Ingresos por factura (Total_Bill).
  * Distribución temporal de las ventas.
  * Desempeño por tienda.

### Áreas Clave de Análisis
Las recomendaciones se estructuran en cuatro fases críticas:
* **Fase 1:** Volumen y Frecuencia de Compra.
* **Fase 2:** Distribución de Ingresos y Precios por Categoría.
* **Fase 3:** Salud Geográfica y Segmentación por Tienda.
* **Fase 4:** Evolución Temporal y Ventanas de Oportunidad.

---

## 💾 2. Estructura de Datos y Comprobaciones
ELa base de datos utilizada para el análisis se compone de una tabla transaccional principal, que concentra la información operativa del negocio, con un total de aproximadamente 149.000 registros (transacciones).**.

* **Tabla Principal:** `Transacciones` (Nivel factura y producto).


<img width="1063" height="453" alt="image" src="https://github.com/user-attachments/assets/de2a8314-5757-47cf-853f-c11bd57af69b" />






### Las comprobaciones iniciales confirmaron:
  * Coherencia entre cantidad, precio unitario y Total_Bill
  * Presencia de valores atípicos reales (no errores), especialmente en precio y facturación
  

* 📅 **Periodo:** Enero - Junio
* ⏰ **Horario:** 6 AM - 20 PM
* 🏪 **Tiendas:** 3 ubicaciones
* 📦 **Categorías de Producto:** 9 categorías
* ☕ **Tipos de Producto:** 29 variedades


---

## 🎯 3. Resumen Ejecutivo
El análisis revela que el negocio depende fuertemente de micro-transacciones de bajo valor, donde la mayoría de los clientes compra una sola unidad y gasta menos de $6 por visita. 
El crecimiento sostenible del negocio no está limitado por la demanda, sino por el mix de productos y el bajo ticket promedio, lo que indica que aumentar el valor por transacción es más crítico que atraer más clientes.
**.

**Insights para Stakeholders:**
1. **Patrón de Consumo:** El cliente típico es funcional y de "paso"; el ingreso adicional proviene de eventos premium poco frecuentes.
2. **Volumen vs. Valor:** Dos categorías concentran el volumen, pero los productos premium tienen un impacto desproporcionado en el margen.
3. **Potencial de Cambio:** Existen ventanas horarias y tiendas específicas donde ya se rompe el patrón de micro-ventas, demostrando viabilidad para el *upselling*.

---

## 🔍 4. Análisis Profundo por Fases

### Fase 1: Volumen y Frecuencia de Compra
Utilizando estadística descriptiva (histogramas y box plots), evaluamos la distribución de las variables:




![Resumen Estadistico](https://github.com/user-attachments/assets/2414a879-6a55-42cd-bf88-1c0e5ae119ea)









* **Interpretación:** El 75% de los clientes adquiere máximo 2 unidades. La convergencia de media y moda en 1 confirma la operación de conveniencia.
* **Impacto:** El crecimiento orgánico depende de "empujar" al cliente de la unidad 1 a la 2 mediante incentivos dirigidos.
* **Outliers:** El CV del 37% es impulsado por pedidos de 4 a 8 unidades, revelando un segmento corporativo aleatorio con potencial de formalización.

### Fase 2: Distribución de Ingresos y Precios
Segmentación de la oferta por valor:

¿Cómo varían los precios unitarios por categoría de producto? Se segmentó la oferta para entender la elasticidad y el posicionamiento de cada línea:


<img width="593" height="319" alt="Seg categorias" src="https://github.com/user-attachments/assets/79db877c-a523-4c64-b113-db80b8e50a5b" />




* **Interpretación**: La varianza de precios es lógica y proporcional a la sofisticación del producto, permitiendo una clara segmentación por valor para guiar al consumidor en su journey de compra.

¿Existe una dependencia crítica de ciertos productos y cómo varía la disposición a pagar?


![ingresos por categoria](https://github.com/user-attachments/assets/73b49603-e26d-4056-b04a-e1c4a9e2fb20)





![unidades vendidas por categoria](https://github.com/user-attachments/assets/6f6f7e97-3cb5-41a3-8939-879ca662c569)







* **Interpretación**: El 66% de los ingresos depende de Coffee y Tea. No obstante, el análisis de Pareto destaca que Coffee Beans y Branded generan un impacto financiero 5 veces superior al promedio.

* **Perspectiva de valor**: El 30% de los clientes prefiere el tamaño Large en café, validando que el consumidor está dispuesto a realizar un upselling si el producto core es de su preferencia.



### Fase 3: Salud Geográfica y Segmentación

¿Existe dependencia de una sola ubicación para la salud del negocio?


![ingreso y unidades por tienda](https://github.com/user-attachments/assets/8546ea1e-bd1a-452f-a53e-1383c5b6facf)



<img width="1775" height="299" alt="image" src="https://github.com/user-attachments/assets/4cdba0d0-76b4-43ea-ab24-7b6c6771ade2" />




* **Lower Manhattan:** El centro más dinámico (3,000+ transacciones de 3 unidades). Es nuestro "laboratorio de éxito" para ventas múltiples.
* **Hell’s Kitchen:** Identificación de facturas de **$360** (8 unidades de Civet Cat) recurrentes los días 17. Esto define un nicho B2B cautivo que requiere atención personalizada.

### Fase 4: Evolución Temporal

¿Cómo es la evolución mensual de los ingresos y existen señales de alerta?



![Evolucion Mensual de ingresos](https://github.com/user-attachments/assets/767c9a52-64f4-4240-873e-3739c2af39b4)





* **Interpretación**: La tendencia es saludablemente creciente. La caída del 6% en febrero se atribuye a la estacionalidad (mes corto). La recuperación inmediata post-febrero confirma una sólida lealtad de marca.

¿Cómo se distribuyen las ventas por día de la semana y turno?


![distribucion por dia de semana y turno](https://github.com/user-attachments/assets/9ae46d40-2f6a-4236-b2cd-cf87e6d111b5)





* **Interpretación**: Los ingresos son consistentes semanalmente, con picos de demanda los martes y viernes. Operativamente, la mañana domina el volumen. El valle más profundo ocurre en la tarde/noche.

* **Impacto**: La oferta actual está limitada a café y pastelería, lo que nos excluye del mercado de "almuerzo/comida sólida" y deja la infraestructura subutilizada en la segunda mitad del día

¿En qué hora exacta se concentra el volumen y qué causa la caída del mediodía?


<img width="1832" height="508" alt="image" src="https://github.com/user-attachments/assets/61c2ced3-47f6-461c-9ab6-7cd15100fec2" />






* **Interpretación**: El pico máximo de transacciones ocurre de 8:00 AM a 10:30 AM. Sin embargo, a las 11:00 AM experimentamos un colapso del 32% en el tráfico.

* **Análisis por Tienda (Impacto y Oportunidades)**:

    * Astoria: Crecimiento sostenido desde las 7:00 AM. A diferencia de otras, su caída a las 11:00 AM es más leve (32%) y mantiene estabilidad hasta las 19:30, sugiriendo un perfil de cliente residencial con consumo vespertino.

    * Hell’s Kitchen: Explosión de demanda a las 8:00 AM (3.6K transacciones). Sufre dos caídas consecutivas (11:00 y 11:30 AM) reduciendo el volumen a menos de la mitad, denotando un perfil puramente corporativo que abandona el local tras el desayuno.

    * Lower Manhattan: Inicio temprano (6:00 AM) con un crecimiento agresivo a las 7:00 AM (64%). Es la tienda que más "sufre" el mediodía con una caída del 62%, pero presenta picos de recuperación marginales entre 11:30 y 18:00.

---

## 💡 Recomendaciones Estratégicas

### 1. Maximización de la "Hora Dorada" (08:00 - 10:30 AM)
* **Acción:** Implementar el **"Power Breakfast Combo"** (Café Grande + Panadería + Proteína) por un precio cerrado (ej. $9.50).
* **Objetivo:** Mover el promedio de 1.4 a 3 unidades por ticket.

### 2. Estrategia "The Treat Receipt" (Tráfico Vespertino)
* **Acción:** Emitir cupones matutinos para beneficios exclusivos (ej. 30% de descuento en **Galletas Artesanales**) válidos entre las 2:00 PM y 5:00 PM.
* **Objetivo:** Incrementar el LTV (Life Time Value) y reactivar el local en horas muertas.

### 3. Tácticas por Ubicación
* **Lower Manhattan:** Lanzar "Office Samplers" para formalizar compras múltiples.
* **Hell’s Kitchen:** Crear el "Club Civet Cat" para asegurar pedidos corporativos recurrentes.
* **Astoria:** Implementar "Bundles de Lealtad Familiar" para fomentar el consumo en local.

### 4. Menú de Mediodía (11:00 AM - 2:00 PM)
* **Acción:** Introducir menú de "Comida Sólida" (Sándwich Gourmet + Bebida + Snack).
* **Objetivo:** Capturar la demanda de almuerzo que actualmente se pierde hacia la competencia.

---

## ⚠️ Suposiciones y Advertencias
* Cada `transaction_id` se considera una compra independiente.
* El análisis es estrictamente transaccional (no se cuenta con datos demográficos de clientes).
* Las variaciones se interpretan como comportamiento orgánico ante la falta de registros promocionales previos.

---
**Analista:** [María Del Mar]  
**Herramientas:** Excel, Power Query  
**Fecha:** Enero 2026

