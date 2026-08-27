# Cómo funciona la IA generativa (el cubo vectorial)

Esta es la parte que casi nadie explica bien y que, si la entiendes, hace que todo lo demás del curso se acomode solo. No hay matemáticas aquí: hay una analogía y sus consecuencias prácticas.

## 1. El problema de fondo

Una computadora no entiende palabras. Entiende números. Entonces, ¿cómo hace un modelo para "saber" que *perro* y *gato* se parecen más entre sí que *perro* y *contabilidad*?

La respuesta es que **convierte cada pedazo de texto en una lista de números**, y esa lista funciona como una coordenada.

## 2. La analogía del cubo vectorial

Imagina un cubo gigantesco, un espacio tridimensional, y que cada palabra del idioma vive en un punto dentro de ese cubo:

- El eje **X** podría representar qué tan "vivo" es un concepto.
- El eje **Y**, qué tan "doméstico" es.
- El eje **Z**, qué tan "grande" es.

Con esos tres ejes, *perro* y *gato* caen casi en el mismo rincón del cubo. *Factura* y *contrato* caen en otro rincón, lejísimos de los animales pero pegaditos entre ellos.

A esa coordenada se le llama **vector** o **embedding**. Y a la distancia entre dos vectores se le llama **similitud semántica**: mientras más cerca están dos puntos, más parecido significan.

> [!NOTE]
> El cubo real no tiene 3 dimensiones. Tiene cientos o miles. Nadie puede dibujarlo, pero la intuición es exactamente la misma: **significado = posición en el espacio**.

### La consecuencia práctica

Cuando le escribes a Copilot *"resume los acuerdos de la junta"*, el modelo no busca la palabra "acuerdos" en tus documentos como lo haría Ctrl+F. Busca **la zona del cubo** donde viven los acuerdos, las decisiones, los compromisos y los pasos siguientes. Por eso te encuentra cosas aunque no uses la palabra exacta, y por eso a veces te trae algo que no pediste: estaba cerca en el espacio.

## 3. De la posición a la predicción

El modelo hace una sola cosa, millones de veces por segundo: **predecir el siguiente token**.

- Un **token** es un pedacito de texto. No siempre una palabra: puede ser una sílaba, un signo o parte de una palabra larga. "Inteligencia" puede ser dos o tres tokens.
- Dado todo lo que lleva escrito, el modelo calcula qué token es el más probable que siga, lo escribe, y vuelve a empezar considerando lo que acaba de escribir.

Escribir un párrafo entero es repetir esa apuesta cientos de veces. Ahí está el truco completo: **no hay una base de datos de respuestas, hay una cadena de predicciones muy bien informadas**.

## 4. La atención: por qué no se pierde en textos largos

Si el modelo solo mirara el token anterior, se perdería en el segundo renglón. El mecanismo que lo evita se llama **atención**: en cada predicción, el modelo pondera qué partes de todo el texto anterior importan más para decidir lo que sigue.

Cuando lees *"El contrato que firmamos en marzo con el proveedor de Monterrey **vence** el..."*, tu cabeza le da peso a "contrato" y a "marzo" para completar la frase, e ignora "Monterrey". El modelo hace lo mismo, y ese fue el gran salto técnico que hizo posible todo esto (la arquitectura *Transformer*, 2017).

## 5. Por qué alucina

Tres consecuencias directas de lo anterior:

1. **El modelo siempre tiene una respuesta.** Predecir el siguiente token nunca falla; siempre hay un token más probable. Si no sabe algo, produce lo que *suena* correcto. A eso le llamamos **alucinación**, y no es un error de programación: es cómo funciona.
2. **La temperatura decide qué tan creativo es.** Es un parámetro que controla si el modelo elige siempre el token más probable (respuestas predecibles y consistentes) o si a veces toma el segundo o el tercero (respuestas más creativas y más riesgosas).
3. **El contexto es limitado.** El modelo solo puede "mirar" cierta cantidad de texto a la vez (la ventana de contexto). Lo que no cabe, no existe para él.

## 6. Y aquí entra la fundamentación (*grounding*)

Si el modelo inventa cuando no sabe, la solución es **no dejar que dependa de su memoria**. Eso hace Copilot:

```
Tu prompt  →  Copilot busca en Microsoft Graph los documentos, correos y chats
              a los que TÚ tienes acceso
           →  mete esos fragmentos reales en el contexto del modelo
           →  el modelo redacta la respuesta apoyándose en ese material
           →  te entrega la respuesta CON CITAS
```

Por eso las citas no son un adorno: son la prueba de que la respuesta salió de un documento real y no del cubo. **Si una respuesta de Copilot no trae fuentes, trátala como una hipótesis, no como un dato.**

> [!TIP]
> Explícale esto a alguien con una frase: *"la IA generativa no busca información, la reconstruye; fundamentarla es obligarla a reconstruirla a partir de tus documentos"*.
