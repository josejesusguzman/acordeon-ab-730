# Cómo funciona la IA generativa (el cubo vectorial)

Esta es la parte que casi nadie explica bien y que, si la entiendes, hace que todo lo demás del curso se acomode solo: por qué alucina, por qué las citas importan, por qué un prompt específico funciona mejor, por qué hay límites de 20 referencias y de 25 consultas.

No hay matemáticas aquí. Hay una analogía, siete mecanismos y sus consecuencias prácticas.

> [!NOTE]
> **Cómo usar esta página.** Si vas con prisa, mira los diagramas y lee los recuadros. Si vas a dar clase con esto, la sección 12 trae el guion de cinco minutos.

---

## 1. El problema de fondo: una computadora no entiende palabras

Una computadora entiende números. Nada más. Entonces, ¿cómo hace un modelo para "saber" que *perro* y *gato* se parecen más entre sí que *perro* y *contabilidad*?

Durante décadas se intentó por el camino obvio: escribir reglas y diccionarios a mano. *Perro es un animal, animal es un ser vivo, gato también.* Ese enfoque nunca escaló, porque el lenguaje tiene demasiadas excepciones, ambigüedades y contextos.

La solución que sí funcionó fue otra: **convertir cada pedazo de texto en una lista de números**, y dejar que esa lista se aprenda sola a partir de millones de ejemplos de uso real. Esa lista funciona como una coordenada.

---

## 2. El cubo vectorial: el significado es una posición

![El cubo vectorial](/images/cubo-vectorial.svg)

Imagina un cubo gigantesco, un espacio tridimensional, donde cada palabra vive en un punto:

- El eje **X** podría representar qué tan "vivo" es un concepto.
- El eje **Y**, qué tan "doméstico" es.
- El eje **Z**, qué tan "grande" es.

Con esos tres ejes, *perro* y *gato* caen casi en el mismo rincón. *Factura* y *contrato* caen en otro rincón, lejísimos de los animales pero pegaditos entre ellos.

A esa coordenada se le llama **vector** o **embedding**. A la distancia entre dos vectores se le llama **similitud semántica**: mientras más cerca están dos puntos, más parecido significan.

### Las dimensiones reales

El cubo real no tiene 3 ejes. Tiene cientos o miles. El modelo `text-embedding-ada-002` de Azure OpenAI, por ejemplo, ubica cada fragmento de texto en un espacio de **1,536 dimensiones**.

Y aquí viene lo importante: **nadie decidió qué significa cada eje**. El modelo los construyó solo, buscando la forma más eficiente de acomodar todo el lenguaje que leyó. Algunos ejes resultan interpretables (hay uno que separa singular de plural, otro que separa pasado de presente); la mayoría no significa nada que un humano pueda nombrar. Son simplemente las coordenadas que mejor funcionan.

### La prueba de que el espacio tiene estructura

El experimento clásico, de 2013, sigue siendo la mejor demostración de que esto no es magia sino geometría. Si tomas los vectores y haces aritmética con ellos:

```
vector("rey")  −  vector("hombre")  +  vector("mujer")  ≈  vector("reina")
```

Funciona. Y también:

```
vector("París")  −  vector("Francia")  +  vector("México")  ≈  vector("Ciudad de México")
```

La dirección que va de "hombre" a "mujer" es aproximadamente la misma que va de "rey" a "reina" y de "actor" a "actriz". El espacio **codifica relaciones como direcciones**, no solo conceptos como puntos.

### La consecuencia práctica en Copilot

Cuando le escribes *"resume los acuerdos de la junta"*, el modelo **no** busca la palabra "acuerdos" en tus documentos como lo haría `Ctrl+F`. Busca **la zona del cubo** donde viven los acuerdos, las decisiones, los compromisos y los pasos siguientes.

De ahí salen dos comportamientos que ya habrás notado:

| Lo que observas | Por qué pasa |
|---|---|
| Encuentra el documento correcto aunque no uses la palabra exacta | Buscó por cercanía de significado, no por coincidencia de texto |
| A veces te trae algo que no pediste | Ese contenido estaba cerca en el espacio, aunque no fuera relevante para ti |
| Dos formas de preguntar lo mismo dan resultados distintos | Cada frase cae en un punto ligeramente distinto del cubo |

> [!TIP]
> Esto explica por qué **agregar contexto al prompt mejora tanto la respuesta**: cada palabra adicional mueve tu consulta a una zona más precisa del espacio. "Resume la junta" apunta a una región enorme; "resume los acuerdos de presupuesto de la junta del martes con el proveedor" apunta a un punto.

---

## 3. Tokens: en qué pedacitos parte el modelo tu texto

![Tokenización](/images/tokenizacion.svg)

El modelo no procesa palabras ni letras: procesa **tokens**. Un token es la unidad mínima que sabe manejar, y no coincide con nuestras palabras.

- Palabras frecuentes suelen ser **un solo token**: *la*, *de*, *casa*.
- Palabras largas o poco frecuentes se parten: *Inteligencia* puede ser `Intel` + `igen` + `cia`.
- Los espacios, signos de puntuación y saltos de línea **también cuentan**.

El método que usan casi todos los modelos se llama **BPE** (*Byte Pair Encoding*): se empieza con letras sueltas y se van fusionando los pares que más aparecen juntos, hasta armar un vocabulario de decenas de miles de tokens. Los pedazos más comunes del idioma acaban siendo tokens completos; los raros se arman por partes.

### Por qué el español sale más caro

Los vocabularios de los grandes modelos se construyeron con muchísimo más texto en inglés que en español. Resultado: **el mismo contenido consume entre 20% y 50% más tokens en español**. Nuestras palabras se parten más veces porque el modelo las vio menos.

### Por qué te importa esto en la práctica

Todos los límites que te vas a encontrar en Copilot se miden, por debajo, en tokens:

- La **ventana de contexto** (cuánto puede leer de una vez).
- El **costo** de cada consulta a los servicios de IA.
- El comportamiento de las **cuotas** (los 20 archivos de referencia de un cuaderno, las 25 consultas mensuales de los agentes).
- Por qué un documento larguísimo se resume por secciones en lugar de leerse completo.

> [!NOTE]
> Regla de bolsillo: en inglés, **1 token ≈ 4 caracteres ≈ 0.75 palabras**. En español, calcula un poco más. Una página de Word ronda los 600–800 tokens.

---

## 4. La predicción: el motor completo

![Predicción del siguiente token](/images/prediccion-token.svg)

Aquí está todo el truco, y es más simple de lo que la gente imagina. El modelo hace **una sola cosa**: dado todo el texto que lleva, calcula qué tan probable es cada uno de los ~50,000 tokens de su vocabulario como continuación, elige uno, lo escribe, y **vuelve a empezar leyendo también lo que acaba de escribir**.

Eso se llama **generación autorregresiva**. Escribir un párrafo es repetir esa apuesta cientos de veces.

```
"El contrato vence el"  →  calcula probabilidades  →  elige "15"
"El contrato vence el 15"  →  calcula de nuevo  →  elige " de"
"El contrato vence el 15 de"  →  calcula de nuevo  →  elige " marzo"
...
```

**No hay una base de datos de respuestas.** No hay un lugar donde esté guardada la frase que te devolvió. Hay una cadena de predicciones muy bien informadas que, vistas juntas, parecen conocimiento.

> [!IMPORTANT]
> Ésta es la frase que hay que entender de todo el documento: **la IA generativa no busca información, la reconstruye.** Todo lo demás —las alucinaciones, la fundamentación, las citas— se deduce de ahí.

---

## 5. La atención: por qué no se pierde en textos largos

![El mecanismo de atención](/images/atencion.svg)

Si el modelo solo mirara el token anterior, se perdería en el segundo renglón. El mecanismo que lo evita se llama **atención**: en cada predicción, el modelo pondera qué partes de todo el texto anterior importan más para decidir lo que sigue.

Cuando lees *"El contrato que firmamos en marzo con el proveedor de Monterrey **vence** el..."*, tu cabeza le da peso a "contrato" y a "marzo" para completar la frase, e ignora "Monterrey". El modelo hace exactamente lo mismo, y calcula ese peso para **cada par de tokens** del texto.

### Por qué esto fue el gran salto

La arquitectura que lo introdujo se llama **Transformer** y viene de un artículo de Google de 2017 titulado, muy literalmente, *"Attention Is All You Need"*. Antes de eso, los modelos leían el texto palabra por palabra en orden, como una fila, y eso los hacía lentos de entrenar y malos con dependencias lejanas.

El Transformer procesa **todo el texto a la vez** y deja que la atención decida qué se conecta con qué. Dos consecuencias:

1. Se puede **paralelizar** el entrenamiento, y por eso fue posible entrenar modelos gigantescos.
2. La distancia entre dos palabras **deja de importar**: una referencia a diez párrafos atrás pesa igual de fácil que la palabra anterior.

Todo lo que usas hoy —Copilot, ChatGPT, Gemini, Claude— es, en el fondo, esa misma idea de 2017 llevada a una escala absurda.

---

## 6. De dónde salió lo que sabe: las tres fases

![Entrenar no es lo mismo que usar](/images/entrenamiento-vs-uso.svg)

Confundir "entrenar" con "usar" es el origen del miedo más común en las organizaciones: *"¿mis documentos entrenan al modelo?"*. Son cosas distintas y ocurren en momentos distintos.

### Fase 1 — Preentrenamiento
El modelo lee cantidades enormes de texto público y ajusta sus **parámetros** (los números internos que definen su comportamiento; los modelos grandes tienen del orden de cientos de miles de millones). Aquí aprende idioma, hechos, estilos, estructura. Toma meses y cuesta millones de dólares.

### Fase 2 — Ajuste fino (*fine-tuning*)
Con ejemplos de buenas respuestas, aprende a **comportarse como asistente** en vez de simplemente continuar texto. Sin esta fase, si le escribes una pregunta, el modelo te contestaría con más preguntas parecidas: estaría completando el patrón, no ayudándote.

### Fase 3 — Alineación
Personas califican respuestas y el modelo aprende a preferir las útiles y seguras sobre las dañinas o inútiles. La técnica más conocida se llama **RLHF** (*aprendizaje por refuerzo con retroalimentación humana*). Aquí es donde el modelo aprende a rechazar peticiones peligrosas y a admitir cuando no sabe algo.

### Y después: la inferencia

Cuando tú escribes un prompt, **no ocurre ninguna de las tres**. Ocurre la **inferencia**: el modelo ya congelado recibe tu texto, predice tokens y responde. Al terminar queda exactamente igual que antes. Es una calculadora enorme y fija.

> [!IMPORTANT]
> Por eso Microsoft puede afirmar que **los datos de tu organización no se usan para entrenar los modelos base**: tu contenido entra únicamente en la fase de inferencia. Nunca toca las tres fases de arriba.

### El corte de conocimiento

Como el preentrenamiento ocurrió en un momento del pasado, el modelo tiene una **fecha de corte de conocimiento**. Lo que pasó después, simplemente no lo vivió. De ahí que el modo Web de Copilot exista: para traerle información actual desde el índice de búsqueda, en vez de confiar en su memoria congelada.

---

## 7. Temperatura: el mismo modelo, dos personalidades

![Temperatura](/images/temperatura.svg)

Ya vimos que el modelo calcula una probabilidad para cada token candidato. Falta decidir **cómo elige** entre ellos. Ahí entra la **temperatura**:

- **Temperatura baja (0.0 – 0.3):** casi siempre toma el token más probable. Respuestas predecibles, consistentes y algo repetitivas. Es lo que quieres en auditoría, cumplimiento, respuestas de política o cualquier cosa que deba ser igual cada vez.
- **Temperatura alta (0.8 – 1.2):** reparte la probabilidad, así que a veces toma el segundo o el tercero. Respuestas más creativas, más variadas y con más riesgo de imprecisión. Es lo que quieres para lluvia de ideas o textos de marketing.

Hay un parámetro hermano, **top-p** (o *nucleus sampling*), que en vez de aplanar la curva limita la elección a los tokens que acumulan cierto porcentaje de probabilidad. En la práctica se ajusta uno o el otro, no los dos.

### Dónde lo ves aunque no lo controles

En Copilot **no hay una perilla de temperatura**, pero está ahí: por eso la misma pregunta te da respuestas ligeramente distintas dos veces seguidas. Y cuando construyes un agente propio sí decides el equivalente al elegir entre una **orquestación determinística** (comportamiento estricto y predecible, como el *Audit Assist* de Grupo Bimbo) y una generativa más libre.

---

## 8. La ventana de contexto: lo que no cabe, no existe

![Ventana de contexto](/images/ventana-contexto.svg)

El modelo no tiene memoria. Tiene un **escritorio de tamaño fijo** donde cabe cierta cantidad de tokens: tu prompt, los documentos recuperados, las instrucciones del sistema y la propia respuesta que va escribiendo. A eso se le llama **ventana de contexto**.

Todo lo que no cabe en ese escritorio, para el modelo **no existe**. No es que lo olvide: nunca lo vio.

De aquí se explican varios comportamientos concretos:

| Comportamiento | Causa |
|---|---|
| Con un documento larguísimo, resume por secciones en vez de leerlo palabra por palabra | No cabe entero en la ventana |
| Los cuadernos aceptan más de 20 referencias pero solo usan las 20 primeras | Límite práctico de lo que cabe y se puede procesar bien |
| En una conversación muy larga "se le olvida" lo que dijiste al principio | Los primeros mensajes salieron de la ventana |
| Referenciar el archivo exacto con `/nombre.docx` da mejores resultados | Le ahorras adivinar y le garantizas que lo correcto entre en la ventana |

> [!TIP]
> **Pocas fuentes bien elegidas superan a muchas fuentes revueltas.** No es una opinión de productividad: es una consecuencia directa de cómo funciona la ventana de contexto.

---

## 9. Por qué alucina (y por qué no se puede "arreglar")

Junta los mecanismos anteriores y la alucinación deja de ser un misterio. Son cuatro causas estructurales:

1. **Predecir nunca falla.** Siempre existe un token más probable, aunque el modelo no tenga idea del tema. No hay un estado interno de "no sé"; hay una distribución de probabilidad que siempre tiene un ganador.
2. **Lo aprendido es estadístico, no factual.** El modelo no guardó hechos: guardó patrones sobre cómo se escriben los hechos. Un nombre de ley, un número de artículo o una cifra que *suenan* correctos son, para él, tan válidos como los verdaderos.
3. **La fluidez y la veracidad son cosas distintas.** El modelo fue optimizado para producir texto plausible. Que además sea cierto es un efecto secundario, no el objetivo de la función que optimizó.
4. **Fuera de la ventana no hay nada.** Si el dato correcto no estaba en el contexto, el modelo lo reconstruye desde el cubo, y ahí es donde inventa.

Por eso **la alucinación no es un bug que se vaya a parchar**: es el mecanismo funcionando como fue diseñado. Se puede reducir mucho, pero no eliminar. Y la forma de reducirla es la siguiente sección.

---

## 10. Fundamentación (*grounding*): la solución de verdad

![Fundamentación](/images/fundamentacion.svg)

Si el modelo inventa cuando no sabe, la solución no es esperar un modelo más listo: es **no dejarlo depender de su memoria**. A eso se le llama **fundamentación** o *grounding*, y es exactamente lo que hace Microsoft 365 Copilot.

```
Tu prompt
   ↓
Copilot busca en Microsoft Graph los documentos, correos, chats y reuniones
a los que TÚ tienes acceso  (ni uno más)
   ↓
Mete esos fragmentos reales dentro de la ventana de contexto
   ↓
El modelo redacta apoyándose en ese material, no en su memoria
   ↓
Te entrega la respuesta CON CITAS
```

El patrón general se llama **RAG** (*Retrieval-Augmented Generation*, generación aumentada por recuperación) y es el mismo que usan por debajo el agente Investigador, los cuadernos y los agentes que conectas a SharePoint.

### Por qué las citas son el punto entero

Las citas no son un adorno de interfaz: son **la prueba de que la respuesta salió de un documento real y no del cubo vectorial**. Es el principio de transparencia de la IA responsable, convertido en un mecanismo que puedes verificar.

> [!IMPORTANT]
> **Si una respuesta de Copilot no trae fuentes, trátala como una hipótesis, no como un dato.**

Y ojo con el matiz que casi nadie menciona: fundamentar reduce la invención, pero **no la elimina**. El modelo todavía puede resumir mal un documento correcto, mezclar dos fuentes o exagerar una conclusión. Por eso el paso de abrir al menos una cita sigue siendo tuyo.

---

## 11. Lo que la IA generativa NO es

Cinco malentendidos que vas a tener que desmontar en tu organización, y la respuesta corta para cada uno:

| El malentendido | Lo que realmente pasa |
|---|---|
| "Razona como una persona" | Predice tokens. Cuando parece razonar, está reproduciendo la forma en que se escribe un razonamiento. Que a veces llegue a la respuesta correcta no significa que haya seguido el camino |
| "Busca en internet cada vez" | Solo en modo Web, y lo que hace es traer resultados de búsqueda al contexto. En modo Trabajo no navega: recupera de Microsoft Graph |
| "Aprende de lo que le escribo" | No. Dentro de una conversación recuerda por el contexto, no por aprendizaje. Los "recuerdos" de Copilot son notas guardadas aparte, no cambios en el modelo |
| "Tiene opiniones o intenciones" | Produce el texto que sigue estadísticamente. Un tono seguro no es evidencia de certeza |
| "Si se equivoca, es porque le faltan datos" | A veces. Pero muchas veces el dato estaba y lo resumió mal, o estaba fuera de la ventana de contexto |

### Un apunte sobre multimodalidad

Los modelos actuales también procesan imágenes, audio y video. El mecanismo no cambia: **una imagen también se convierte en vectores** y entra al mismo espacio que el texto. Por eso puedes subirle una foto de una tabla y pedirle que la analice: para el modelo, la imagen y tu pregunta viven en el mismo cubo. Es también la razón por la que el análisis de imágenes hereda los mismos riesgos, incluida la alucinación.

---

## 12. De la teoría al prompt: siete consecuencias prácticas

Cada mecanismo de arriba tiene una traducción directa a cómo escribir mejores prompts:

| Porque… | Haz esto |
|---|---|
| El significado es posición en el espacio | **Da contexto**. Cada palabra relevante mueve tu consulta a una zona más precisa |
| Todo se mide en tokens | **Sé conciso pero específico**. Ni telegrama ni novela |
| Predice el siguiente token, uno a uno | **Encadena en pasos**. Primero el resumen, luego el formato, luego el tono. No pidas todo de golpe |
| La atención pondera lo que ya está escrito | **Pon lo importante al principio y al final** de un prompt largo |
| No tiene un estado de "no sé" | **Dale permiso explícito de admitirlo**: *"si no está en las fuentes, dilo en vez de suponer"* |
| La ventana de contexto es finita | **Referencia el archivo exacto** con `/`, en vez de esperar que adivine |
| Puede inventar con toda seguridad | **Pide fuentes y ábrelas.** Dos minutos de verificación valen más que cualquier técnica de prompting |

> [!TIP]
> El prompt más subutilizado que existe, y que sale directamente de entender el mecanismo:
> ```
> Antes de responder, dime qué información te falta para hacerlo bien.
> ```
> Le estás pidiendo que exponga los huecos de su contexto **antes** de rellenarlos con invención.

---

## 13. Cómo explicarlo en cinco minutos

Un guion probado, por si tienes que dar esta explicación a alguien que no tiene tiempo:

1. **"Una computadora no entiende palabras, entiende números."** Así que convertimos cada palabra en una coordenada dentro de un espacio enorme. Las palabras que significan cosas parecidas quedan cerca. *(30 segundos)*
2. **"El modelo hace una sola cosa: adivinar el siguiente pedacito de texto."** Y lo repite cientos de veces. Escribir un párrafo son cientos de apuestas seguidas. *(1 minuto)*
3. **"Para no perderse, pondera qué partes de lo anterior importan."** Como tú cuando completas *'el contrato firmado en marzo vence el…'*: le haces caso a "contrato", no a "Monterrey". *(1 minuto)*
4. **"Como siempre hay un siguiente pedacito más probable, nunca dice 'no sé'."** Cuando no sabe, escribe lo que suena bien. A eso le decimos alucinación, y no es una falla: es cómo funciona. *(1 minuto)*
5. **"Por eso Copilot no le pregunta al modelo a secas."** Primero le pone enfrente tus documentos —solo los que tú puedes ver— y le pide que responda con eso, citando de dónde salió cada cosa. *(1 minuto)*
6. **Cierre:** *"La IA generativa no busca información: la reconstruye. Fundamentarla es obligarla a reconstruirla a partir de tus documentos."* *(30 segundos)*

---

## 14. Glosario rápido

| Término | En una línea |
|---|---|
| **Token** | El pedacito de texto que el modelo procesa. No es una palabra |
| **Embedding / vector** | La lista de números que representa el significado de un texto |
| **Similitud semántica** | Qué tan cerca están dos vectores; qué tan parecido significan |
| **Parámetros** | Los números internos ajustados durante el entrenamiento. Definen el comportamiento del modelo |
| **Transformer** | La arquitectura, de 2017, basada en atención. La base de todos los modelos actuales |
| **Atención** | El mecanismo que decide qué partes del texto pesan más en cada predicción |
| **Autorregresivo** | Que genera un token a la vez, releyendo lo que ya escribió |
| **Temperatura** | Qué tan dispuesto está a no elegir el token más probable |
| **Ventana de contexto** | Cuánto texto puede tener enfrente a la vez |
| **Inferencia** | El momento en que usas el modelo. No aprende nada aquí |
| **Fundamentación / grounding** | Darle documentos reales para que responda con ellos |
| **RAG** | El patrón técnico de recuperar documentos y generar la respuesta con ellos |
| **Alucinación** | Contenido inventado que suena correcto. Consecuencia estructural, no bug |
| **Corte de conocimiento** | La fecha hasta la que el modelo leyó el mundo |

---

## 15. Para profundizar

Ninguno requiere saber programar, y todos son gratuitos:

- **[3Blue1Brown — Redes neuronales y transformadores](https://www.3blue1brown.com/topics/neural-networks)** — la mejor explicación visual que existe. Si solo ves una cosa de esta lista, que sea ésta.
- **[The Illustrated Transformer, de Jay Alammar](https://jalammar.github.io/illustrated-transformer/)** — el artículo que le explicó la arquitectura al mundo, con dibujos.
- **[Hugging Face LLM Course](https://huggingface.co/learn/llm-course)** — gratuito y sin anuncios, para entender tokens y embeddings de verdad.
- **[Generative AI for Beginners (Microsoft)](https://microsoft.github.io/generative-ai-for-beginners/)** — curso abierto, con la perspectiva del ecosistema que estás certificando.
- **[Elements of AI](https://www.elementsofai.com/es)** — completo en español, para la base conceptual sin tecnicismos.

---

> [!TIP]
> Si te llevas una sola frase de todo esto, que sea ésta:
> ***"La IA generativa no busca información, la reconstruye. Fundamentarla es obligarla a reconstruirla a partir de tus documentos."***
