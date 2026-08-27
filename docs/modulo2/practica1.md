# Práctica 1: El mismo encargo, cuatro veces
**Objetivo:** Medir el impacto de los cuatro elementos del prompt (contexto, objetivo, origen y expectativas) sobre la calidad de la respuesta.

## Paso a Paso:

1. **Elige un encargo real** que hoy resolverías a mano. Ejemplo: preparar el resumen semanal de tu área.

2. **Ronda 1 — solo objetivo.** Escribe lo mínimo:
   ```
   Hazme el resumen semanal.
   ```
   Guarda la respuesta.

3. **Ronda 2 — objetivo + contexto.**
   ```
   Necesito el resumen semanal de mi área para enviarlo el viernes a mi director,
   que solo lee el primer párrafo. Hazlo.
   ```

4. **Ronda 3 — objetivo + contexto + origen.**
   ```
   Necesito el resumen semanal de mi área para mi director. Usa mis correos de
   los últimos siete días y las notas de #JuntaSemanal.
   ```

5. **Ronda 4 — los cuatro elementos.**
   ```
   Necesito el resumen semanal de mi área para enviarlo el viernes a mi director,
   que solo lee el primer párrafo (contexto).
   Redáctalo (objetivo) con mis correos de los últimos siete días y las notas de
   #JuntaSemanal (origen).
   Formato: un párrafo de tres líneas al inicio con lo esencial, después tres
   viñetas de avances, dos de riesgos y una de decisión que necesito de él.
   Máximo 200 palabras, tono directo (expectativas).
   ```

6. **Compara las cuatro salidas en una tabla:**

   | Ronda | ¿Sirve tal cual? | ¿Cuánto tendría que editar? | Qué le faltó |
   |---|---|---|---|
   | 1 | | | |
   | 2 | | | |
   | 3 | | | |
   | 4 | | | |

7. **Guarda el ganador.** Pasa el cursor sobre el prompt de la ronda 4 → icono de **Marcador** → nómbralo *"Resumen semanal para dirección"*.

8. **Vuélvelo reutilizable.** Edítalo cambiando los datos fijos por marcadores:
   ```
   ... para enviarlo el [DÍA] a [AUDIENCIA] ...
   ```
   y guárdalo como una versión nueva.

## Qué debiste aprender

- El salto de calidad más grande ocurre al agregar **expectativas**, no al agregar contexto.
- Un prompt bien hecho se escribe una vez y se usa cincuenta.
- Si el resultado necesita mucha edición, casi siempre falta el **origen**.
