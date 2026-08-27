# Módulo 4: Análisis y visualización de datos con Copilot

## 4.1 Análisis de flujos de trabajo de datos en Excel

> [!IMPORTANT]
> **Requisito que sí se pregunta:** Copilot en Excel **solo trabaja con archivos guardados en OneDrive** (o SharePoint), y los datos deben estar en **formato de tabla o rango admitido**. Si el archivo está en tu escritorio, Copilot no lo ve.

### Buscar e importar datos con Copilot Chat

1. Abre Excel.
2. Pestaña **Inicio** → botón **Copilot**.
3. Selecciona el icono de **globo** y elige contenido conectado a la **web**.
4. Pide los datos en el panel de chat.
5. Si el resultado sirve: **Insertar en nueva hoja**, o copia y pega donde quieras.

Ejemplos:
```
Busca en la web una tabla de países y sus tipos de cambio.
```
```
Obtén [dato] de mi archivo acerca de [tema].
```

Palabras que ayudan a que traiga contenido web: *"pruebas comparativas del sector"*, *"tendencias recientes"*.

### Buscar tendencias

1. Abre el panel de Copilot Chat en Excel.
2. Pide lo que buscas. **Entre más específica la pregunta, mejor la respuesta.** Puedes indicar el formato deseado (tabla dinámica, gráfico, resumen).
3. Copilot devuelve gráficos, tablas dinámicas, resúmenes, tendencias y valores atípicos.
4. Revisa las conclusiones.
5. **Agregar a una nueva hoja** para conservar lo generado.

Ejemplos:
```
¿Cuántas personas de esta lista residen en Estados Unidos?
```
```
Revisa los comentarios de clientes de esta hoja e identifica los temas principales.
```

### Generar gráficos

1. Selecciona los datos a visualizar.
2. Pide el gráfico.
3. Refínalo con mensajes de seguimiento.

**Creación:**
```
Crea un gráfico de barras que muestre las ventas por región.
```
```
Genera un gráfico de líneas de tendencias de ventas trimestrales.
```
```
Visualiza el rendimiento del producto con un gráfico circular.
```

**Refinamiento:**
```
Agrega etiquetas a los ejes.
```
```
Resalta las tres regiones principales del gráfico.
```
```
Cambia el tipo de gráfico a uno de columnas.
```
```
Usa 10,000 como línea base. Crea un gráfico de líneas que muestre el cambio con
el tiempo. Muestra etiquetas de datos y líneas de cuadrícula.
```

### Comprender y crear fórmulas

Dos caminos:

1. **Sugerir una fórmula** directamente desde el panel de Copilot Chat.
2. Pedirla en lenguaje natural:
   ```
   Calcula el aumento porcentual de la celda A1 a la celda B1.
   ```
   ```
   Extrae el nombre de pila de un nombre completo en la celda C1.
   ```

Copilot también **explica** fórmulas existentes: útil para ese archivo heredado que nadie entiende.

### Resumen de capacidades

| Capacidad | Para qué | Dónde |
|---|---|---|
| Búsqueda web | Importar datos externos | Panel Copilot Chat → icono de globo |
| Análisis de tendencias | Identificar patrones e información | Copilot Chat |
| Generación de gráficos | Visualizar datos | Copilot Chat |
| Creación de fórmulas | Generar y explicar cálculos | Panel Copilot Chat |

## 4.2 El agente Analista (*Analyst*)

**Definición:** asistente de IA integrado en Microsoft 365 Copilot, optimizado para análisis de datos, visualización y generación de información, con **razonamiento de cadena de pensamiento**.

**Qué hace:**

1. **Analiza datos** de hojas de cálculo, bases de datos y almacenamiento en la nube.
2. **Genera información**: identifica tendencias, detecta valores atípicos, calcula métricas clave.
3. **Produce informes** con gráficos y tablas listos para compartir.
4. **Soporta tareas** como previsión de demanda, patrones de compra o comparación de ventas entre regiones.

| | **Copilot Chat estándar** | **Agente Analista** |
|---|---|---|
| Centrado en | Redacción y edición | Análisis, visualización e información |

**Acceso:** licencia de Microsoft 365 Copilot → [microsoft365.com](https://www.microsoft365.com) o app de escritorio → sección **Agentes** → **Analista**.

**Límite:** **25 consultas combinadas al mes** con el agente Investigador.

**Archivos que acepta:** Excel, CSV, JSON, .txt, .doc, .pdf.

**Tipos de análisis:** estadístico, visualización de datos, informes sobre archivos de datos, análisis de contenido, extracción de palabras clave y resumen de documentos.

### Cómo usarlo

1. Abre Copilot Chat desde el navegador.
2. Sección **Agentes** → **Analista**.
3. Icono **+** para adjuntar archivos desde el dispositivo o la nube.
4. Escribe tu pregunta.

**Prompt principal:**
```
Resalta las tendencias clave del rendimiento de ventas por región y trimestre.
```

**Seguimientos:**
```
Identifica los productos de alto rendimiento según métricas de participación del cliente.
```
```
Visualiza el crecimiento de ventas en los últimos cuatro trimestres.
```
```
Compara el rendimiento de ventas entre regiones.
```

**Formatos de salida:**
```
Resume los resultados en tres viñetas para una diapositiva de liderazgo.
```
```
Escribe un resumen ejecutivo para este informe.
```
```
Redacta una actualización por correo que resuma estas conclusiones.
```

> [!TIP]
> El Analista admite **resolución iterativa**: refina la consulta, explora métricas adicionales y haz preguntas aclaratorias. No trates la primera respuesta como la final.
