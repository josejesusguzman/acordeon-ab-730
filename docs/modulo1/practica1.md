# Práctica 1: Explora el cubo vectorial con tus propias palabras
**Objetivo:** Comprobar de forma empírica que la IA generativa trabaja con **cercanía de significado** y no con coincidencia de palabras.

> [!NOTE]
> Esta práctica funciona con Copilot Chat gratuito. No necesitas licencia de Microsoft 365 Copilot.

## Paso a Paso:

1. **Abre Copilot Chat** en [microsoft365.com](https://www.microsoft365.com) o desde Teams, con tu cuenta profesional.

2. **Primer experimento — vecinos semánticos.** Pega este prompt:

   ```
   Actúa como un modelo de lenguaje explicando su propio funcionamiento.
   Para la palabra "factura", dame 10 palabras que estarían cerca de ella
   en un espacio vectorial y 10 que estarían lejos. Explica en una línea
   por qué cada grupo está donde está.
   ```

3. **Observa el resultado.** Deberían aparecer cosas como *recibo, comprobante, proveedor, pago, CFDI* en el grupo cercano. Ninguna de ellas comparte letras con "factura": comparten **contexto de uso**. Eso es el cubo vectorial en acción.

4. **Segundo experimento — el mismo concepto, distintas palabras.** Pide:

   ```
   Escribe tres frases que signifiquen lo mismo que "el proyecto se retrasó"
   pero sin usar las palabras "proyecto" ni "retraso".
   ```

   Luego pregunta:

   ```
   Si yo buscara información sobre retrasos de proyecto en mis documentos,
   ¿encontrarías esas tres frases? ¿Por qué?
   ```

5. **Tercer experimento — la ambigüedad.** Prueba:

   ```
   ¿Qué significa "banco" en un espacio vectorial? Explica cómo decide un
   modelo si me refiero a la institución financiera, al asiento o al banco
   de peces, y qué información necesita para decidirlo.
   ```

6. **Documenta tu conclusión.** En un párrafo, responde: *¿por qué Copilot a veces me trae un documento que no mencioné?*

## Qué debiste aprender

- La búsqueda semántica encuentra **significados**, no cadenas de texto.
- El contexto de la frase completa es lo que desambigua una palabra (mecanismo de **atención**).
- Entre más contexto le des a tu prompt, menos margen de interpretación le dejas al modelo.
