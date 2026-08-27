# Guía de prompts efectivos

Escribir prompts es la única habilidad de este curso que vas a usar todos los días, tengas o no la certificación. Esta es la guía completa.

## 1. Los cuatro elementos (el marco oficial)

Un prompt de Copilot es una pregunta o instrucción. Para que funcione, incluye estos cuatro elementos:

| Elemento | Pregunta que responde | Ejemplo |
|---|---|---|
| **Contexto** | ¿Por qué lo necesito y quién está involucrado? | *"Voy a presentar esto al comité directivo el viernes"* |
| **Objetivo** | ¿Qué quiero que haga Copilot? | *"Resume"*, *"redacta"*, *"compara"*, *"convierte"* |
| **Origen** | ¿Dónde debe buscar? | *"de mis correos del último mes"*, `/Presupuesto2026.xlsx` |
| **Expectativas** | ¿Cómo debe entregarlo? | *"en cinco viñetas, tono profesional, máximo 150 palabras"* |

### Un prompt malo vs. el mismo prompt bien escrito

❌ **Malo:**
```
Hazme un resumen de ventas.
```

✅ **Bueno:**
```
Voy a presentar el desempeño trimestral al equipo directivo el viernes (contexto).
Resume los resultados de ventas (objetivo) del archivo /VentasQ3.xlsx y de mis
correos etiquetados como "Cierre" del último mes (origen).
Entrégalo en cinco viñetas, con la cifra de crecimiento por región y una línea
final de recomendación. Tono ejecutivo, sin tecnicismos (expectativas).
```

## 2. Tabla de qué hacer y qué no

| ✔️ HACER | ❌ NO HACER |
|---|---|
| Ser claro y específico | Ser vago |
| Mantenerlo conversacional | Pedir contenido inadecuado |
| Dar ejemplos | Usar jerga o argot |
| Pedir retroalimentación | Dar instrucciones en conflicto |
| Escribir de forma legible | Interrumpir o cambiar de tema de golpe |
| Comprobar la precisión | |
| Proporcionar detalles | |
| Ser educado | |
| Iterar y refinar | |

> [!NOTE]
> "Ser educado" no es cortesía vacía: los prompts redactados como una petición completa a una persona tienden a ser más específicos y contextualizados que los redactados como comandos sueltos.

## 3. Referencias: `/`, `#` y `@`

| Símbolo | Caso de uso | Cómo se usa | Ejemplo |
|---|---|---|---|
| `/` | Persona, archivo o ubicación | Escribe `/` y el nombre del archivo, persona o carpeta | `Resume los puntos clave de /Q4MarketingStrategy.pptx` |
| `#` | Tema, reunión o evento | Etiqueta un tema, reunión o evento recurrente | `¿Cuáles fueron los pendientes de #WeeklyOpsSync?` |
| `@` | Agente | Invoca la capacidad de un agente | `@Investigador compara los 3 principales competidores en CRM: precios, funciones clave y diferenciadores` |

## 4. Seis prompts de negocio listos para usar

**Redactar correo**
```
Escribe un correo felicitando al equipo por el arranque exitoso del proyecto.
```

**Crear presentación**
```
Genera una presentación de 10 diapositivas sobre el desempeño de ventas trimestral.
```

**Prepararse para una reunión**
```
Con base en mis interacciones anteriores con /persona, dame los cinco temas más
probables de nuestra próxima reunión.
```

**Organizar tu tiempo**
```
Revisa mi calendario y mi correo del último mes y agrupa en 5 a 7 categorías los
proyectos en los que paso más tiempo, con el porcentaje de tiempo invertido y una
descripción breve de cada uno.
```

**Pronosticar ventas**
```
Genera un pronóstico visual de ventas del próximo año usando las tendencias
históricas, resaltando patrones estacionales, proyecciones de crecimiento y
posibles anomalías.
```

**Extraer conclusiones**
```
Analiza la hoja de cálculo abierta, extrae las principales conclusiones y
tendencias, y genera una visualización clara que resalte patrones, valores
atípicos y acciones sugeridas.
```

## 5. Técnicas que elevan el resultado

### Encadenar (no pedir todo de golpe)
```
1. "Resume este hilo en cinco puntos."
2. "Ahora separa decisiones de pendientes."
3. "Convierte los pendientes en una tabla con responsable y fecha."
4. "Redacta el correo de seguimiento con esa tabla incluida."
```

### Dar un ejemplo del formato deseado
```
Redacta tres asuntos de correo con este estilo:
"Cierre Q3 — 3 decisiones y 2 pendientes"
```

### Asignar un rol
```
Actúa como director financiero revisando esta propuesta. Señala los tres supuestos
más débiles y qué evidencia pedirías para aceptarlos.
```

### Pedir el trabajo inverso
```
Antes de redactar, dime qué información te falta para hacerlo bien.
```
Este es probablemente el prompt más subutilizado que existe.

### Fijar restricciones duras
```
Máximo 120 palabras. Sin adjetivos superlativos. Sin viñetas. Un solo párrafo.
```

## 6. Cómo corregir cuando la respuesta no sirve

| Síntoma | Causa probable | Arreglo |
|---|---|---|
| Genérico, suena a folleto | Faltó contexto y público | Agrega quién lo va a leer y para qué |
| Inventó datos | No hubo origen | Referencia el archivo con `/` o cambia a modo Trabajo |
| Muy largo | No hubo expectativas | Pon límite de palabras y formato |
| Tono equivocado | No lo especificaste | *"Tono directo, profesional, sin exclamaciones"* |
| Se desvió del tema | Cambio brusco de tema en el mismo hilo | Abre un chat nuevo |
| Repite lo que ya dijiste | Le pediste resumir su propio resumen | Vuelve a la fuente original |

## 7. Voz: dictado, lectura y chat de voz

| Capacidad | Qué hace | Cómo se usa |
|---|---|---|
| **Dictado** | Compones mensajes, documentos o notas hablando | Icono de micrófono → *Iniciar dictado* |
| **Lectura en voz alta** | Copilot lee su respuesta (Word y PowerPoint, en web, escritorio y Mac) | Desde el panel de chat |
| **Chat de voz** | Conversación hablada bidireccional que mantiene el contexto | *Iniciar un nuevo chat de voz*, o `Win + C` / tecla Copilot |

Además de productividad, son herramientas de **accesibilidad** para personas con dificultades de movilidad, visión o lectura.

## 8. Guarda lo que funciona

Cuando un prompt te salga bien: **márcalo con el icono de Marcador**, ponle nombre y compártelo con tu equipo desde la Galería de consultas. Usa marcadores de posición para reutilizarlo:

```
Resume las actualizaciones del proyecto [NOMBRE DEL PROYECTO] de la última
[SEMANA/QUINCENA] y formatea el resultado para [AUDIENCIA].
```

> [!TIP]
> La [Galería de consultas de Copilot](https://m365.cloud.microsoft/copilot-prompts) tiene prompts oficiales listos para copiar. Es el mejor lugar para empezar cuando no sabes cómo pedir algo.
