# Práctica 3: Diagnóstico de IA responsable en un proceso real
**Objetivo:** Aplicar los seis principios de IA responsable a un proceso concreto de tu organización, antes de automatizarlo.

## Paso a Paso:

1. **Elige un proceso real** de tu área que estés considerando apoyar con IA. Debe ser específico. Ejemplos válidos:
   - Filtrado inicial de currículums.
   - Resumen automático de tickets de soporte.
   - Redacción de respuestas a quejas de clientes.
   - Clasificación de facturas de proveedores.

2. **Llena esta matriz.** Una fila por principio, y sé honesto en la columna de riesgo:

   | Principio | ¿Cómo aplica a mi proceso? | Riesgo concreto | Mitigación |
   |---|---|---|---|
   | Equidad | | | |
   | Confiabilidad y seguridad | | | |
   | Privacidad y seguridad | | | |
   | Inclusión | | | |
   | Transparencia | | | |
   | Responsabilidad | | | |

3. **Contesta las tres preguntas de gobernanza:**
   - **¿Qué datos entran al prompt?** Enuméralos. Si alguno es personal, sensible o está sujeto a contrato de confidencialidad, márcalo.
   - **¿Quién revisa la salida antes de que tenga efecto?** Si la respuesta es "nadie", tu proceso no está listo.
   - **¿Qué pasa si la IA se equivoca?** Describe el peor escenario realista y quién responde por él.

4. **Usa Copilot como abogado del diablo.** Pega tu matriz en el chat y pide:

   ```
   Eres un auditor de IA responsable. Revisa esta matriz de riesgos y dime
   qué riesgos NO consideré, qué mitigaciones son insuficientes y qué
   preguntas debería hacerle al área legal antes de avanzar.
   ```

5. **Decide.** Con la matriz en la mano, clasifica tu proceso:
   - 🟢 **Listo para piloto** con supervisión humana.
   - 🟡 **Necesita controles** antes de arrancar (etiquetas de confidencialidad, permisos, capacitación).
   - 🔴 **No debe automatizarse** en su forma actual.

## Qué debiste aprender

- La IA responsable no es una capa que se agrega al final: es un filtro que se aplica **antes** de decidir qué se automatiza.
- El principio que más se olvida en la práctica es **inclusión**; el que más problemas legales genera es **privacidad y seguridad**.
- Un proceso donde nadie revisa la salida no es un proceso automatizado: es un riesgo automatizado.
