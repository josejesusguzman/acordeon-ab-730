# Tutorial de Excel con Copilot

Un recorrido práctico de principio a fin. Tiempo estimado: 30 minutos.

## 0. Preparación (no te la saltes)

> [!IMPORTANT]
> Tres condiciones sin las cuales nada de esto funciona:
> 1. El archivo debe estar **guardado en OneDrive o SharePoint**.
> 2. Los datos deben estar en **formato de tabla** (`Ctrl + T`) o en un rango admitido.
> 3. Los encabezados deben ser **únicos, descriptivos y sin celdas combinadas**.

Arma un archivo de práctica con estas columnas y unas 60 filas de datos ficticios:

| Fecha | Región | Producto | Vendedor | Unidades | Precio unitario | Total |
|---|---|---|---|---|---|---|

Si no tienes datos, pídeselos a Copilot Chat:
```
Genera una tabla de 60 filas de ventas ficticias con columnas Fecha, Región,
Producto, Vendedor, Unidades, Precio unitario y Total. Cuatro regiones de México,
cinco productos, seis vendedores, fechas del último año, con estacionalidad
realista en diciembre.
```

## 1. Explorar los datos

Abre Excel → pestaña **Inicio** → botón **Copilot**.

```
Dame un panorama general de esta tabla: qué contiene, qué periodo cubre,
cuántos registros hay y qué columnas tienen valores faltantes o inconsistentes.
```

```
Revisa esta hoja e identifica valores atípicos en la columna Total. Explica por
qué los consideras atípicos.
```

## 2. Encontrar tendencias

```
¿Cuál es la tendencia de ventas por trimestre? Muéstrame el resultado como
tabla dinámica.
```

```
Compara el desempeño entre regiones y dime cuál creció más y cuál se estancó.
```

```
Revisa los comentarios de clientes de esta hoja e identifica los temas principales.
```

> [!TIP]
> Cuanto más específica sea la pregunta, mejor la respuesta. Y si quieres un formato concreto —tabla dinámica, resumen, gráfico— pídelo explícitamente en el mismo prompt.

## 3. Crear gráficos

**Creación:**
```
Crea un gráfico de barras que muestre las ventas por región.
```
```
Genera un gráfico de líneas con las tendencias de ventas trimestrales.
```

**Refinamiento** (aquí está el verdadero valor):
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

Cuando te guste el resultado: **Agregar a una nueva hoja**.

## 4. Fórmulas: crearlas y entenderlas

**Crear en lenguaje natural:**
```
Calcula el aumento porcentual de la celda A1 a la celda B1.
```
```
Extrae el nombre de pila del nombre completo en la celda C1.
```
```
Crea una columna que clasifique cada venta como Alta, Media o Baja según si el
Total está arriba del percentil 75, entre el 25 y el 75, o abajo del 25.
```

**Entender una fórmula heredada:** copia la fórmula y pregunta:
```
Explícame paso a paso qué hace esta fórmula y en qué caso podría fallar:
=SI(Y(B2>0;C2<>"");BUSCARV(A2;Datos!$A:$D;4;FALSO);"")
```

Este es probablemente el uso más subestimado de Copilot en Excel: **traducir el trabajo de alguien que ya no está en la empresa**.

## 5. Traer datos de la web

1. Panel de Copilot → icono de **globo** → contenido conectado a la **web**.
2. Pide los datos:
   ```
   Busca en la web una tabla de países y sus tipos de cambio.
   ```
3. **Insertar en nueva hoja**, o copiar y pegar.

> [!WARNING]
> Verifica siempre la fuente y la fecha de los datos importados de la web antes de usarlos en un cálculo que alguien va a leer como oficial.

## 6. Cierre: del análisis al entregable

```
Resume los tres hallazgos más importantes de este análisis en viñetas para una
diapositiva de dirección, cada una con la cifra que la respalda.
```

## Lo que Copilot en Excel NO hace bien

| Limitación | Alternativa |
|---|---|
| Archivos fuera de OneDrive/SharePoint | Súbelo primero |
| Datos sin formato de tabla | `Ctrl + T` antes de empezar |
| Celdas combinadas y encabezados dobles | Limpia la estructura |
| Modelos financieros complejos con dependencias circulares | Sigue siendo trabajo humano |
| Garantizar exactitud aritmética en cálculos largos | **Verifica siempre** con una fórmula |

## Lista de verificación

- [ ] El archivo está en OneDrive y los datos son una tabla.
- [ ] Verifiqué al menos un cálculo generado con una fórmula propia.
- [ ] Los gráficos tienen ejes etiquetados y una escala honesta.
- [ ] Los datos importados de la web tienen fuente y fecha anotadas.
- [ ] El entregable final dice qué hacer, no solo qué pasó.
