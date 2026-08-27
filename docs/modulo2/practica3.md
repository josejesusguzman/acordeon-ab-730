# Práctica 3: Construye y prueba un agente personalizado
**Objetivo:** Crear un agente con instrucciones, conocimiento y capacidades, y someterlo a pruebas antes de compartirlo.

## Paso a Paso:

1. **Define el trabajo del agente en una sola frase.** Si no cabe en una frase, es demasiado amplio.
   > *"Convierte notas de llamadas de venta en borradores de propuesta con nuestras tarifas oficiales."*

2. **Crea el agente.** Copilot Chat → **Crear agente** → describe el propósito en lenguaje natural → **Configurar**.

3. **Escribe las instrucciones** con la estructura de tres partes:
   ```
   QUIÉN ERES:
   Eres un asistente de propuestas para [tu empresa / tu área].

   QUÉ HACES:
   Conviertes notas de llamadas en borradores con las secciones: Contexto,
   Necesidad, Solución, Alcance, Supuestos y Siguientes pasos.

   CÓMO RESPONDES:
   Tono profesional y directo. Sin superlativos. Máximo dos páginas.
   Si falta información, escribe [PENDIENTE: qué falta]. Nunca inventes cifras.
   ```

4. **Conecta el conocimiento.** Agrega entre 2 y 5 fuentes reales (documentos de OneDrive, una página de SharePoint, un sitio público). No cargues 20 de golpe: empieza con lo mínimo.

5. **Activa las capacidades que necesites.** ¿Va a hacer cálculos? Intérprete de código. ¿Va a producir diagramas? Creador de imágenes. Si no, déjalas apagadas.

6. **Escribe tres avisos sugeridos** que reflejen preguntas reales de tu equipo.

7. **Somételo a la prueba de las cinco preguntas:**

   | # | Pregunta de prueba | ¿Qué esperas? | ¿Qué pasó? |
   |---|---|---|---|
   | 1 | Una tarea típica y bien especificada | Resultado utilizable | |
   | 2 | La misma tarea con información incompleta | Que marque `[PENDIENTE]`, no que invente | |
   | 3 | Una pregunta fuera de su alcance | Que lo diga en vez de improvisar | |
   | 4 | Una pregunta cuya respuesta está en el conocimiento conectado | Que cite la fuente | |
   | 5 | Una petición con un dato falso metido a propósito | Que lo detecte o al menos no lo repita como cierto | |

8. **Ajusta las instrucciones** con lo que hayas encontrado y vuelve a correr las cinco pruebas.

9. **Compártelo.** Configuración → Compartir → grupo específico → rol **Visor** para quien lo usa y **Editor** para quien lo mantendrá contigo.

10. **Anota el mantenimiento.** ¿Quién actualiza las fuentes cuando cambien las tarifas? Un agente sin dueño se vuelve obsoleto en un trimestre.

## Qué debiste aprender

- Las instrucciones valen más que el conocimiento: un agente con buenas reglas y tres documentos supera a uno sin reglas y veinte.
- La prueba 2 y la 3 son las que separan un agente confiable de un generador de plausibilidad.
- Compartir sin dueño ni mantenimiento es sembrar deuda técnica organizacional.
