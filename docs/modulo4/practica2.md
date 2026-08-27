# Práctica 2: Rescata el archivo que nadie entiende
**Objetivo:** Usar Copilot en Excel para documentar, limpiar y explicar una hoja heredada.

## Paso a Paso:

1. **Consigue el archivo.** Ese Excel que heredaste, con fórmulas enredadas, hojas ocultas y columnas llamadas "Col1". Súbelo a OneDrive.

2. **Pide el mapa general:**
   ```
   Dame un panorama de este libro: qué contiene cada hoja, qué columnas tiene
   cada tabla, qué relaciones hay entre hojas y qué parece ser el propósito
   del archivo.
   ```

3. **Documenta las fórmulas críticas.** Para cada fórmula que no entiendas:
   ```
   Explica paso a paso qué hace esta fórmula, qué supone sobre los datos y en
   qué caso daría un resultado incorrecto:
   [pega la fórmula]
   ```

4. **Detecta problemas de calidad de datos:**
   ```
   Revisa esta tabla e identifica: celdas vacías en columnas críticas, formatos
   de fecha inconsistentes, duplicados y valores atípicos. Ordénalos por
   gravedad para el cálculo final.
   ```

5. **Propón la limpieza, no la ejecutes a ciegas:**
   ```
   Con base en los problemas anteriores, propón un plan de limpieza paso a paso.
   Para cada paso, dime qué se corrige y qué riesgo tiene aplicarlo.
   ```

6. **Aplica solo los pasos que entiendas y verifica.** Compara los totales antes y después de cada cambio.

7. **Genera la documentación que faltaba.** Pide:
   ```
   Escribe una hoja de documentación para este archivo: propósito, origen de los
   datos, descripción de cada columna, fórmulas clave explicadas en lenguaje
   sencillo y advertencias para quien lo use después.
   ```
   Pégala como primera hoja del libro, llamada **LÉEME**.

8. **Cierra el círculo:** guarda el archivo con nombre versionado y avisa a quien lo use.

## Qué debiste aprender

- Documentar es la tarea que más se pospone y la que Copilot resuelve más rápido.
- Copilot explica fórmulas mejor de lo que las escribe: úsalo primero como traductor.
- Nunca apliques una limpieza automatizada sin comparar totales antes y después.
