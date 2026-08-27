# Práctica 2: Caza de alucinaciones y verificación de citas
**Objetivo:** Desarrollar el reflejo de verificar antes de reenviar, y aprender a distinguir una respuesta fundamentada de una inventada.

## Paso a Paso:

1. **Pide algo que el modelo probablemente no sepa con certeza.** En Copilot Chat, en **modo Web**, escribe:

   ```
   Dame cinco estadísticas sobre la adopción de inteligencia artificial en
   empresas medianas de México, con la fuente exacta y el año de cada dato.
   ```

2. **Revisa las citas una por una.** Abre cada fuente que Copilot enumere debajo de la respuesta y contesta:
   - ¿La fuente existe?
   - ¿El dato aparece realmente en esa fuente?
   - ¿El año coincide?
   - ¿La fuente es primaria (el estudio original) o secundaria (alguien citando el estudio)?

3. **Anota los resultados en esta tabla:**

   | # | Dato | ¿Tiene cita? | ¿La cita lo respalda? | Veredicto |
   |---|------|--------------|----------------------|-----------|
   | 1 | | | | ✅ / ⚠️ / ❌ |
   | 2 | | | | |
   | 3 | | | | |
   | 4 | | | | |
   | 5 | | | | |

4. **Repite en modo Trabajo** (si tienes licencia). Pide algo fundamentado en tus propios documentos:

   ```
   ¿Cuáles fueron los tres acuerdos principales de mis reuniones del último mes?
   Cita el documento o la reunión de donde sacaste cada uno.
   ```

5. **Compara la calidad de las citas** entre modo Web y modo Trabajo. Anota la diferencia.

6. **Fuerza el límite a propósito.** Pregunta por algo que sabes que no existe:

   ```
   Resume las conclusiones del informe interno "Estrategia Vega 2031"
   de nuestra organización.
   ```

   Un buen comportamiento es que Copilot te diga que no encontró ese documento. Si en cambio te inventa un resumen plausible, acabas de ver una alucinación en vivo. Guarda la captura: es el mejor argumento de capacitación que vas a tener.

## Qué debiste aprender

- **Sin fuentes, no hay dato.** Hay una hipótesis bien redactada.
- El modo Trabajo produce respuestas más verificables porque se fundamenta en documentos reales a los que tú tienes acceso.
- La verificación toma dos minutos. Retractarse frente a un cliente toma mucho más.
