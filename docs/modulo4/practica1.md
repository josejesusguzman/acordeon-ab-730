# Práctica 1: De hoja cruda a decisión ejecutiva

**Objetivo:** recorrer el ciclo completo de trabajo con datos usando Copilot en las tres aplicaciones donde de verdad se trabaja —**Excel** para analizar, **Word** para argumentar y **PowerPoint** para presentar— y salir con tres entregables reales.

**Tiempo estimado:** 75 a 90 minutos. Hay una variante de 60 minutos al final.

**Entregables:** un análisis en Excel, un informe de dos páginas en Word y una presentación de seis diapositivas.

> [!IMPORTANT]
> Esta práctica está diseñada para que **la puedas terminar aunque no tengas licencia de Microsoft 365 Copilot**. Cada paso trae tres rutas. Elige tu renglón y no lo sueltes.

---

## 0. Antes de empezar

### 0.1 ¿Qué ruta te toca?

![Tres aplicaciones, tres rutas](/images/rutas-excel-word-ppt.svg)

Contesta estas cuatro preguntas y sabrás dónde te paras:

| Pregunta | Si la respuesta es… | Tu ruta |
|---|---|---|
| ¿Ves el icono de Copilot dentro de Excel, Word y PowerPoint? | Sí, en las apps instaladas | **Ruta A** |
| ¿Lo ves solo al abrir los archivos en el navegador? | Sí | **Ruta B** |
| ¿No lo ves en ninguna app, pero sí entras a Copilot Chat con tu cuenta de trabajo? | Sí | **Ruta C** |
| ¿No tienes ni eso? | — | Ruta C con funciones nativas (te las doy en cada paso) |

> [!NOTE]
> Que tu organización tenga Copilot **no** garantiza que tú tengas la licencia asignada: se asigna usuario por usuario. Y hay un caso intermedio muy común: licencia asignada pero apps de escritorio en un canal de actualización viejo. Si sospechas eso, abre el archivo en el navegador (Ruta B) y sigue adelante; lo resuelves después con TI.

### 0.2 Preparación técnica del archivo (no te la saltes)

Aquí se cae la mitad de los intentos. Cinco condiciones:

| # | Condición | Cómo lo compruebas |
|---|---|---|
| 1 | El archivo está **en OneDrive o SharePoint**, no en el escritorio | La barra de título muestra la ubicación en la nube |
| 2 | El **autoguardado** está encendido | Interruptor arriba a la izquierda en Excel |
| 3 | El formato es **.xlsx moderno**, no *Hoja de cálculo Strict Open XML* | Archivo → Información → o guarda como *Libro de Excel (.xlsx)* |
| 4 | Los datos están en **formato de tabla** | Selecciona el rango y pulsa `Ctrl + T` |
| 5 | El **cálculo está en Automático** | Fórmulas → Opciones para el cálculo → Automático |

> [!WARNING]
> Dos errores que verás en clase y que no son culpa de nadie:
> - **"Estado de archivo no admitido"**: el archivo está *desprotegido* (checked out) en SharePoint. Protégelo de nuevo, o ábrelo en Excel para la web.
> - **Copilot en gris**: casi siempre es el cálculo en Manual, o el archivo fuera de OneDrive.

### 0.3 Si no tienes datos de práctica

Pídelos en Copilot Chat —esto funciona en las tres rutas— y pégalos en una hoja nueva:

```
Genera una tabla de 80 filas de ventas ficticias con las columnas Fecha, Región,
Producto, Vendedor, Unidades, Precio unitario y Total. Cuatro regiones de México,
cinco productos, seis vendedores, fechas del último año. Incluye estacionalidad
realista en diciembre, una región que se estanca y tres valores atípicos.
Devuélvela como texto separado por tabuladores para pegar directo en Excel.
```

Guárdalo en OneDrive como `Ventas-practica.xlsx`, conviértelo en tabla con `Ctrl + T` y ya tienes con qué trabajar.

---

# FASE 1 — Excel: del dato al hallazgo

**Meta de la fase:** salir con tres hallazgos numéricos verificados y un gráfico.

## Paso 1 — Panorama general

**Qué buscas:** entender qué tienes antes de preguntar nada inteligente.

**🖥️ Ruta A — Escritorio con licencia**
Abre el archivo y selecciona el **icono de Copilot, abajo a la derecha**. Se abre el panel con los modos de **edición, chat y planeación**. Pide:

```
Dame un panorama general de esta tabla: qué contiene, qué periodo cubre, cuántos
registros hay, y qué columnas tienen valores faltantes o inconsistentes.
```

**🌐 Ruta B — Navegador**
Idéntico. Copilot en Excel para la web tiene las mismas capacidades que en Windows y Mac. Si estás aquí porque el archivo estaba desprotegido en SharePoint, ésta es justamente la salida recomendada.

**🔁 Ruta C — Sin licencia**
Abre **Copilot Chat** con tu cuenta de trabajo, adjunta el archivo con el clip y usa el mismo prompt. La carga de archivos está disponible aunque no tengas licencia.
*Alternativa nativa:* en Excel, **Inicio → Analizar datos**. Te da un panel con patrones y sugerencias automáticas sin IA generativa.

---

## Paso 2 — Encontrar lo que duele

**Qué buscas:** pasar de "aquí están los datos" a "aquí está el problema".

**🖥️🌐 Rutas A y B**
```
¿Cuál es la tendencia de ventas por trimestre? Muéstramelo como tabla dinámica.
```
```
Compara el desempeño entre regiones y dime cuál creció más y cuál se estancó.
Incluye el porcentaje de cambio.
```
```
Identifica valores atípicos en la columna Total y explica por qué los consideras
atípicos.
```

**🔁 Ruta C**
Los mismos tres prompts en Copilot Chat con el archivo adjunto. Copilot Chat no puede insertar la tabla dinámica en tu hoja, así que pídele:
```
...y dime exactamente qué campos poner en Filas, Columnas y Valores para armar
esa tabla dinámica yo mismo.
```
*Alternativa nativa:* **Insertar → Tabla dinámica recomendada**.

> [!TIP]
> El paso que separa un análisis de un reporte: **nombra la decisión**. Cambia *"analiza estas ventas"* por *"quiero decidir en qué región concentrar el presupuesto del próximo semestre"*. La respuesta cambia por completo.

### Variante: hacerlo con el agente Analista

Cuando la pregunta amerita razonamiento de varios pasos —no solo un cálculo—, el **agente Analista** es mejor herramienta que el panel de Excel, y aparece en el examen.

**Cómo:** Copilot Chat → **Agentes** → **Analista** → icono **+** para adjuntar el archivo. Acepta Excel, CSV, JSON, .txt, .doc y .pdf.

```
Analiza estos tickets de ventas del último trimestre. Quiero decidir en qué región
concentrar el presupuesto del próximo semestre. Dame el panorama por región y
trimestre, el tiempo de reacción de cada una y el cálculo que respalda tu
recomendación.
```

> [!WARNING]
> **Cuesta cuota:** el Analista comparte un límite de **25 consultas al mes** con el agente Investigador. Diseña la consulta antes de escribirla, y usa el panel de Excel para todo lo que sea cálculo directo.

**Sin licencia (Ruta C):** no tienes agente Analista. La compensación es adjuntar el archivo en Copilot Chat y **encadenar** tres preguntas en vez de una sola grande: panorama, luego el corte que te interesa, luego el porqué.

---

## Paso 3 — El gráfico

**Qué buscas:** una imagen que puedas pegar en la presentación.

**🖥️🌐 Rutas A y B**
Selecciona los datos y pide:
```
Crea un gráfico de líneas con las ventas trimestrales por región.
```
Refina, que es donde está el valor real:
```
Agrega etiquetas a los ejes y muestra los valores de datos.
```
```
Resalta las tres regiones principales y deja el resto en gris.
```
Cuando te guste: **Agregar a una nueva hoja**.

**🔁 Ruta C**
Copilot Chat no dibuja gráficos dentro de tu libro. Dos opciones:
1. Pídele la especificación y créalo tú:
   ```
   Dime exactamente qué gráfico usar para mostrar la tendencia trimestral por
   región: tipo de gráfico, qué va en cada eje, qué series incluir y qué debería
   resaltar visualmente. Justifica la elección.
   ```
2. *Alternativa nativa:* selecciona los datos → **Insertar → Gráficos recomendados**.

---

## Paso 4 — Verificación manual

**Qué buscas:** no quedar mal en la junta.

**Todas las rutas.** Toma **dos** cifras del análisis y compruébalas a mano con una fórmula:

| Cifra que reportó Copilot | Fórmula con la que la verifiqué | Resultado | ¿Coincide? |
|---|---|---|---|
| | | | |
| | | | |

Si no coincide una, revisa las dos siguientes. Un error de agregación nunca viene solo.

> [!IMPORTANT]
> Este paso no es opcional y no tiene ruta alternativa. Verificar dos cifras toma tres minutos; retractarse frente a dirección cuesta mucho más.

---

## Paso 5 — Exponer los supuestos

**Qué buscas:** saber qué tan sólido es lo que vas a afirmar.

**Todas las rutas**, mismo prompt:
```
¿Qué explicación alternativa podría tener la caída de la región con peor
desempeño? Dime qué datos adicionales necesitaría para confirmarla y qué
supuestos estás haciendo al interpretar estos números.
```

Éste es el prompt más valioso de la fase: obliga al modelo a mostrar sobre qué se está parando. Anota los supuestos: van a la sección de riesgos del informe.

**Guarda el archivo.** Fin de la fase 1.

---

# FASE 2 — Word: del hallazgo al informe

**Meta de la fase:** un documento de dos páginas que alguien pueda leer sin ti al lado.

## Paso 6 — Estructura antes que contenido

**Qué buscas:** el esqueleto correcto, no un texto bonito sin forma.

**🖥️ Ruta A — Escritorio con licencia**
Documento en blanco. Aparece el **cuadro de indicaciones de Copilot**. (Cuando ya hay contenido, el icono vive en el **margen izquierdo**.) Pide:

```
Voy a presentar al comité de dirección una recomendación sobre dónde concentrar
el presupuesto comercial del próximo semestre. Dame el índice de un informe de
dos páginas que convenza a un comité escéptico: qué secciones debe tener y qué
tiene que demostrar cada una.
```

**🌐 Ruta B — Navegador**
Igual. Word para la web tiene el cuadro de indicaciones completo. Además, **si usas Copilot Pro personal, la web es la única superficie donde puedes referenciar archivos**.

**🔁 Ruta C — Sin licencia**
Pide el índice en Copilot Chat y escribe los encabezados a mano en Word. Son treinta segundos.
*Atajo útil:* si el chat te devuelve el índice en Markdown, pégalo en Word y aplica estilos con `Ctrl+Alt+1` y `Ctrl+Alt+2`.

---

## Paso 7 — Redactar sección por sección, con las cifras reales

**Qué buscas:** que el informe hable de **tus** datos, no de generalidades del sector.

**🖥️🌐 Rutas A y B**
Aquí está la función más subestimada de Word: **referenciar archivos con `/`**. Escribe la diagonal y busca tu archivo. Copilot admite **hasta 20 elementos** como referencia, en formatos **Word, PowerPoint, PDF o TXT**.

```
Escribe la sección "Situación actual" usando los hallazgos de /Ventas-practica.xlsx.
Tono directo, sin adjetivos, máximo 200 palabras. Cada afirmación debe apoyarse
en una cifra.
```

> [!NOTE]
> El archivo referenciado debe estar en **OneDrive o SharePoint** y tú debes tener permiso sobre él. Un archivo en tu disco local no aparece en la lista de `/`.

Si tu Excel no aparece con `/`, pega el resumen del paso 2 directamente en el prompt. Funciona igual de bien.

**🔁 Ruta C**
En Copilot Chat, adjunta el Excel y pide la sección con el mismo prompt. Copia y pega en Word.
*Mejor todavía:* usa **Páginas de Copilot**. Convierte la respuesta del chat en una página editable, trabaja ahí las secciones, y al final usa el **icono de Word** para convertirla en documento. Te ahorras el copiar y pegar de cada sección.

---

## Paso 8 — La tabla y el tono

**Qué buscas:** que los datos se lean de un vistazo y que el texto suene a ti.

**🖥️🌐 Rutas A y B**
Selecciona el párrafo con los datos y pide:
```
Convierte esto en una tabla con columnas Región, Ventas del periodo, Variación
frente al periodo anterior y Recomendación.
```
Refina:
```
Agrega fila de encabezado, pon los títulos en negrita y ordena de mayor a menor
variación.
```
Y después, el prompt de revisión que casi nadie usa:
```
Revisa todo el documento y señala las tres frases que un director financiero
consideraría poco sustentadas. No las reescribas: solo señálalas.
```

**🔁 Ruta C**
La tabla la armas en Word con **Insertar → Tabla**, y le pides al chat el contenido ya tabulado. Para la revisión crítica, pega el texto completo en el chat con el mismo prompt.
*Alternativa nativa:* el **Editor** de Word (Revisar → Editor) no evalúa argumentos, pero sí claridad, concisión y formalidad.

---

## Paso 9 — Tu voz

**Todas las rutas.** Reescribe a mano **la apertura y el cierre**. Es lo que la gente lee y lo que recuerda, y es lo que hace que el documento suene tuyo y no a máquina.

**Guarda como `Informe-presupuesto.docx` en OneDrive.** Lo vas a necesitar en la fase 3.

---

# FASE 3 — PowerPoint: del informe a la presentación

**Meta de la fase:** seis diapositivas que terminen pidiendo una decisión concreta.

## Paso 10 — Generar la base desde el documento

**Qué buscas:** no volver a escribir lo que ya escribiste.

**🖥️ Ruta A — Escritorio con licencia**
1. Abre PowerPoint **partiendo de la plantilla de tu organización**, no de la presentación en blanco. Es el consejo que da Microsoft y ahorra media hora de maquetación.
2. Selecciona el **icono de Copilot, abajo a la derecha**.
3. **Agregar contenido** → elige **modo agente**.
4. Adjunta el documento de Word.
5. Describe lo que quieres:

```
Crea una presentación de seis diapositivas para un comité de dirección a partir
de este documento. Estructura: problema, evidencia con datos, propuesta, riesgos
y mitigación, costo e impacto esperado, y la decisión que pido hoy.
```

6. Copilot te va a hacer preguntas sobre audiencia y estilo. **Contéstalas con detalle**: cada respuesta aquí te ahorra una ronda de correcciones.
7. Revisa el esquema que propone **antes** de autorizar la generación de las diapositivas.

**🌐 Ruta B — Navegador**
Mismo flujo. Si la plantilla corporativa no está disponible en la web, genera el contenido ahí y aplícale la plantilla al abrirlo en escritorio.

**🔁 Ruta C — Sin licencia**
Éste es el paso donde más se nota la diferencia, y aun así se resuelve bien:

1. En Copilot Chat, adjunta el Word y pide:
   ```
   Convierte este informe en el guion de seis diapositivas. Para cada una dame:
   título de una línea, tres viñetas de máximo doce palabras cada una, y una nota
   del presentador de dos frases. Devuélvelo como texto plano, con el título
   pegado al margen y las viñetas con una sangría de tabulador.
   ```
2. En PowerPoint: **Vista → Esquema**, y pega ahí el resultado. PowerPoint convierte cada título en una diapositiva y cada línea con tabulador en una viñeta. Tienes la presentación armada en un pegado.
3. Vuelve a **Vista → Normal** y usa **Diseñador de PowerPoint** (Inicio → Diseñador) para el diseño visual.

> [!TIP]
> El truco del **Esquema** funciona igual de bien en las tres rutas y es más rápido que cualquier otra cosa cuando ya tienes el contenido escrito. Enséñalo aunque tu grupo tenga licencia.

---

## Paso 11 — Afinar las diapositivas

**🖥️🌐 Rutas A y B**
```
Haz que las viñetas sean concisas y orientadas a la acción, máximo una línea cada una.
```
```
La diapositiva final debe tener una sola pregunta clara: qué necesito que aprueben.
```

Dos límites que conviene conocer:
- La función de **reescritura** trabaja sobre **cuadros de texto, no sobre formas**, y procesa el cuadro completo, no una selección parcial.
- Las **sugerencias de diseño** están oficialmente soportadas en configuración regional **en-US**. En español funcionan, pero la calidad no está garantizada: revísalas.

**🔁 Ruta C**
Afina el texto en el chat y pégalo. Para el diseño, **Diseñador** hace la mayor parte del trabajo.

---

## Paso 12 — Insertar el gráfico

**Todas las rutas.** Copia el gráfico desde Excel y pégalo en la diapositiva de evidencia. Pega **como imagen** si no quieres que se actualice, o **con vínculo** si la presentación se va a repetir cada mes.

---

## Paso 13 — Ensayar las objeciones

**Todas las rutas**, en Copilot Chat o en el panel de Copilot:

```
Actúa como el director financiero del comité. Dame las cinco objeciones más
probables a esta propuesta y qué evidencia pedirías para cada una.
```

Prepara esas cinco respuestas. Este paso es opcional en el curso y obligatorio en la vida real.

---

# FASE 4 — Verificación

## Paso 14 — La lista antes de enviar

- [ ] Verifiqué dos cifras a mano contra una fórmula propia.
- [ ] Cada afirmación numérica del informe tiene su cifra de respaldo.
- [ ] La apertura y el cierre están escritos con mi voz.
- [ ] Los gráficos tienen ejes etiquetados y escala honesta.
- [ ] La última diapositiva pide algo concreto.
- [ ] Revisé que no se haya colado información confidencial que no deba circular.
- [ ] Anoté los supuestos del paso 5 en la sección de riesgos.
- [ ] Puedo defender de dónde salió cada número sin abrir el archivo.

**Y el entregable que de verdad importa:** escribe tu recomendación en **una sola frase**, sin datos y sin matices. Si no te sale, el análisis todavía no está terminado.

---

## Tabla de equivalencias rápida

Para tenerla a la mano mientras trabajas:

| Quiero… | Ruta A / B (con licencia) | Ruta C (sin licencia) | Nativo, sin IA |
|---|---|---|---|
| Explorar datos | Copilot en Excel | Archivo adjunto en Copilot Chat | Analizar datos |
| Tabla dinámica | Se la pides a Copilot | Le pides qué campos usar | Tabla dinámica recomendada |
| Gráfico | Se lo pides y lo refinas | Le pides la especificación | Gráficos recomendados |
| Fórmula | Se la pides en lenguaje natural | Se la pides en el chat | Asistente de fórmulas |
| Estructura de un informe | Cuadro de indicaciones en Word | Chat, y pegas encabezados | Plantillas de Word |
| Redactar con mis datos | `/archivo.xlsx` en Word | Adjunto en el chat, copias y pegas | — |
| Documento colaborativo | Word con Copilot | **Páginas de Copilot** → convertir a Word | Word en línea |
| Presentación desde documento | Agregar contenido → modo agente | Guion en el chat → **Vista Esquema** | Vista Esquema |
| Diseño de diapositivas | Copilot + Diseñador | Diseñador | Diseñador |
| Ensayar objeciones | Panel de Copilot | Copilot Chat | — |

---

## Solución de problemas

| Síntoma | Causa probable | Qué hacer |
|---|---|---|
| El icono de Copilot no aparece en la app | Licencia no asignada, o app en canal de actualización antiguo | Prueba en el navegador; escala a TI |
| "Estado de archivo no admitido" | Archivo desprotegido en SharePoint | Protégelo, o ábrelo en Excel para la web |
| Copilot en Excel aparece pero en gris | Cálculo en Manual, o archivo fuera de OneDrive | Fórmulas → Automático; guarda en OneDrive |
| Copilot no entiende mis datos | Rango sin formato de tabla, encabezados combinados o duplicados | `Ctrl + T`; encabezados únicos en una sola fila |
| El archivo no aparece al escribir `/` en Word | Está en el disco local, no en OneDrive/SharePoint | Súbelo, o pega el contenido en el prompt |
| La presentación ignora mi plantilla | Empezaste desde la presentación en blanco | Parte de la plantilla corporativa y vuelve a generar |
| El diseño en español sale raro | Las sugerencias de diseño se soportan oficialmente en en-US | Revisa a mano o usa Diseñador |
| Copilot dice que el documento es muy grande | Los documentos de Word funcionan mejor por debajo de 24 MB | Divide el documento o quita imágenes pesadas |

---

## Qué debiste aprender

1. **El cuello de botella nunca es el modelo: es la preparación.** Cinco condiciones técnicas en Excel deciden si la práctica fluye o se atora.
2. **Referenciar archivos con `/` es lo que hace que el informe hable de tus datos.** Sin eso, Word escribe generalidades bien redactadas.
3. **La ruta sin licencia llega al mismo entregable**, con dos pasos manuales más. Vista Esquema y Páginas de Copilot son los dos atajos que cierran la brecha.
4. **Copilot te ahorra el arranque y la estructura; el criterio, la verificación y tu voz siguen siendo tuyos.** Los pasos 4, 5, 9 y 13 no tienen atajo.
5. **Encadenar en pasos gana siempre.** Nadie de los que hicieron esta práctica en un solo mega-prompt terminó con algo presentable.

---

## Fuentes

- [Introducción a Copilot en Excel](https://support.microsoft.com/es-es/office/introducci%C3%B3n-a-copilot-en-excel-d7110502-0334-4b4f-a175-a73abdfc118a)
- [Preguntas frecuentes sobre Copilot en Excel](https://support.microsoft.com/en-gb/office/frequently-asked-questions-about-copilot-in-excel-7a13758f-d61e-4a56-8440-f2c9a07802ec)
- [Redactar y agregar contenido con Copilot en Word](https://support.microsoft.com/en-us/word/copilot/draft-and-add-content-with-copilot-in-word)
- [Crear una presentación con Copilot en PowerPoint](https://support.microsoft.com/en-us/office/create-a-new-presentation-with-copilot-in-powerpoint-3222ee03-f5a4-4d27-8642-9c387ab4854d)
- [Preguntas frecuentes sobre Copilot en PowerPoint](https://support.microsoft.com/en-us/office/frequently-asked-questions-about-copilot-in-powerpoint-3e229188-9086-4f4c-9f9f-824cd25ae84f)
