# Práctica 2: Rescata el archivo que nadie entiende

Todo el mundo tiene uno: ese Excel que heredaste, con fórmulas enredadas, hojas ocultas y columnas llamadas "Col1", del que depende un proceso real y que nadie se atreve a tocar. Esta práctica lo convierte en algo que otra persona pueda usar sin ti.

**Objetivo:** entender un archivo heredado con Copilot en **Excel**, producir su documentación en **Word** y presentar el diagnóstico en **PowerPoint**.

**Tiempo estimado:** 80 a 100 minutos. Hay una variante de 60 minutos al final.

**Entregables:** el libro documentado y versionado, un documento de traspaso, una hoja **LÉEME** dentro del propio archivo y una presentación de cinco láminas.

> [!IMPORTANT]
> Como en la práctica anterior, cada paso trae **tres rutas**: escritorio con licencia, navegador con licencia, y sin licencia de Copilot. El mapa completo de rutas está en la [Práctica 1](/docs/modulo4/practica1.md#01-qué-ruta-te-toca).

---

## 0. Antes de empezar

![Rescatar un archivo heredado](/images/rescate-archivo-heredado.svg)

### 0.1 Elige bien el archivo

No cualquier Excel sirve para esta práctica. Busca uno que cumpla al menos tres de estas cinco:

- Lo hizo alguien que **ya no está** en el equipo, o tú mismo hace más de un año.
- Tiene **fórmulas que no entiendes al leerlas**.
- Alguien **depende de él** todos los meses.
- Tiene hojas ocultas, columnas sin nombre claro o pestañas llamadas "final", "final2", "final_bueno".
- Si se rompiera hoy, **tardarías más de un día** en arreglarlo.

Si no tienes uno a la mano, en la sección 0.4 te dejo cómo fabricarlo.

### 0.2 La regla de oro: nunca trabajes sobre el original

1. Copia el archivo y renómbralo con fecha: `Reporte-mensual_2026-09-07_trabajo.xlsx`.
2. Guárdalo en **OneDrive o SharePoint** con **autoguardado encendido**.
3. El original no se toca hasta que la copia esté verificada y documentada.

### 0.3 Los totales de control

Esto es lo que hace que la práctica sea seria y no un ejercicio de fe. **Antes de tocar nada**, anota entre tres y cinco cifras que puedas volver a calcular al final:

| # | Qué mido | Dónde está | Valor de hoy |
|---|---|---|---|
| 1 | Suma de la columna principal | | |
| 2 | Número de filas de datos | | |
| 3 | Número de valores únicos de la columna clave | | |
| 4 | El total final que la gente consulta | | |
| 5 | Fecha mínima y máxima del periodo | | |

Estas cifras son tu **Puerta 2**. Si al final del rescate alguna cambió sin que tú lo hayas decidido a propósito, algo se rompió.

### 0.4 Si no tienes un archivo heredado

Pide uno "sucio" en Copilot Chat —funciona en las tres rutas— y pégalo en Excel:

```
Genera una tabla de 60 filas de un reporte de comisiones de vendedores, con los
defectos típicos de un archivo heredado: dos formatos de fecha mezclados, tres
filas duplicadas, cuatro celdas vacías en columnas críticas, una columna llamada
"Col1" sin encabezado claro, nombres de vendedor con espacios de más y con
mayúsculas inconsistentes, y dos importes atípicos. Devuélvela separada por
tabuladores.
```

Después agrega a mano una columna de comisión con esta fórmula, para tener algo que traducir:

```
=SI(Y(D2>0;E2<>"");BUSCARV(B2;Tarifas!$A:$D;4;FALSO)*D2;0)
```

---

# ACTO 1 — Excel: entender qué demonios hace este archivo

## Paso 1 — Inventario del libro

**Qué buscas:** un mapa antes de meter las manos.

**🖥️ Ruta A — Escritorio con licencia**
Abre el archivo y selecciona el **icono de Copilot, abajo a la derecha**:

```
Dame un panorama de este libro: qué contiene cada hoja, qué columnas tiene cada
tabla, qué relaciones hay entre hojas y cuál parece ser el propósito del archivo.
Señala las hojas que parecen borradores o versiones viejas.
```

Sigue con la pregunta que casi nadie hace:

```
¿Qué hoja alimenta a cuál? Dame la cadena de dependencias, de los datos de
entrada al resultado final.
```

**🌐 Ruta B — Navegador**
Idéntico. Y si el archivo estaba desprotegido en SharePoint y te salió *"Estado de archivo no admitido"*, ésta es la salida.

**🔁 Ruta C — Sin licencia**
Adjunta el archivo en **Copilot Chat** con el clip y usa los mismos prompts.
*Alternativas nativas, y son buenas:*
- `Ctrl + ` ` (acento grave) muestra todas las fórmulas de la hoja de un vistazo.
- **Fórmulas → Rastrear precedentes / Rastrear dependientes** dibuja flechas de qué alimenta a qué.
- Si tu edición incluye el complemento **Consultar** (*Inquire*), te da un análisis del libro y un diagrama de relaciones entre hojas. Se activa en Archivo → Opciones → Complementos.

> [!TIP]
> Haz el inventario **con las hojas ocultas visibles**. Clic derecho en cualquier pestaña → Mostrar. Lo que está oculto suele ser justo lo que nadie documentó.

---

## Paso 2 — Traducir las fórmulas

**Qué buscas:** entender qué hace cada fórmula crítica **y bajo qué supuestos**.

**🖥️🌐 Rutas A y B**
Para cada fórmula que no entiendas al leerla, cópiala y pide:

```
Explica paso a paso qué hace esta fórmula, qué supone sobre los datos, y en qué
caso concreto daría un resultado incorrecto sin avisar:
=SI(Y(D2>0;E2<>"");BUSCARV(B2;Tarifas!$A:$D;4;FALSO)*D2;0)
```

Las tres partes de ese prompt importan: *qué hace* es lo fácil, *qué supone* es lo que nadie documentó, y *cuándo falla en silencio* es lo que te va a salvar.

Después, la pregunta de auditoría:

```
Revisa estas fórmulas y señala las frágiles: valores fijos escritos dentro de la
fórmula, referencias a otros libros, búsquedas con coincidencia aproximada,
referencias a columnas completas y rangos que no se ajustan si crecen los datos.
```

**🔁 Ruta C**
Pega la fórmula en Copilot Chat con el mismo prompt. Aquí no pierdes casi nada: traducir fórmulas es texto, y el chat lo hace igual de bien.
*Alternativas nativas:* **Fórmulas → Evaluar fórmula** ejecuta el cálculo paso a paso y te muestra el resultado intermedio de cada parte. Es lenta pero no miente nunca.

### 🚪 Puerta 1 — verificación humana obligatoria

Toma **un caso real que ya conozcas** —una fila cuyo resultado sepas de memoria o puedas calcular a mano— y comprueba que la explicación de Copilot describe lo que realmente pasa con esa fila.

Si no coincide, **la explicación está mal y la documentación que escribas será una mentira con buena redacción**. Vuelve al paso 2 con más contexto.

---

## Paso 3 — Diagnóstico de calidad de datos

**Qué buscas:** la lista de lo que está roto, ordenada por gravedad.

**🖥️🌐 Rutas A y B**
```
Revisa esta tabla e identifica: celdas vacías en columnas críticas, formatos de
fecha inconsistentes, duplicados, valores atípicos y textos con espacios o
mayúsculas inconsistentes. Ordénalos por el impacto que tienen sobre el cálculo
final, no por cantidad.
```

Ese matiz final —**por impacto, no por cantidad**— cambia por completo la utilidad de la respuesta. Doscientas celdas con un espacio de más importan menos que tres fechas mal parseadas dentro del cálculo de comisiones.

**🔁 Ruta C**
Mismo prompt con el archivo adjunto en el chat.
*Alternativas nativas:* **Inicio → Formato condicional → Reglas para resaltar celdas → Valores duplicados**, y **Datos → Validación de datos → Rodear con un círculo datos no válidos**.

---

## Paso 4 — Plan de limpieza (propuesto, no aplicado)

**Qué buscas:** saber qué se puede arreglar y qué riesgo tiene cada arreglo.

**🖥️🌐 Rutas A y B**
```
Con base en los problemas anteriores, propón un plan de limpieza paso a paso.
Para cada paso dime: qué corrige, qué riesgo tiene aplicarlo, y qué cifra debería
comprobar antes y después para saber que no rompí nada.
```

> [!WARNING]
> **No apliques el plan completo de un jalón.** Un paso, una verificación. Si aplicas ocho cambios y el total cambió, no vas a saber cuál lo rompió.

**🔁 Ruta C**
Mismo prompt en el chat. La diferencia es que Copilot Chat no puede ejecutar los cambios en tu hoja, lo cual —seamos honestos— en esta práctica juega **a tu favor**: te obliga a aplicarlos uno por uno.

### 🚪 Puerta 2 — verificación humana obligatoria

Después de **cada** paso de limpieza, recalcula tus totales de control de la sección 0.3:

| Total de control | Antes | Después | ¿Igual? |
|---|---|---|---|
| | | | |

Si alguno cambió y no era el objetivo del paso, **revierte ese paso** antes de seguir. No investigues después: revierte ahora.

---

# ACTO 2 — Word: documentar para que sobreviva sin ti

## Paso 5 — El documento de traspaso

**Qué buscas:** que alguien más pueda hacerse cargo del archivo.

**🖥️ Ruta A — Escritorio con licencia**
Documento en blanco en Word. En el cuadro de indicaciones, **referencia el Excel con `/`** —recuerda: hasta 20 elementos, y el archivo debe estar en OneDrive o SharePoint:

```
Escribe un documento de traspaso para /Reporte-mensual_2026-09-07_trabajo.xlsx
con estas secciones: propósito del archivo, origen de los datos, diccionario de
columnas, fórmulas clave explicadas en lenguaje sencillo, supuestos que hace el
cálculo, advertencias para quien lo modifique, qué hacer si el resultado sale
raro, y quién lo mantiene. Tono directo, para alguien competente que nunca ha
visto este archivo.
```

Refina por secciones, no de golpe:

```
La sección de advertencias es demasiado genérica. Reescríbela con las tres
fórmulas frágiles que identificamos y qué pasa exactamente si alguien inserta
una fila en medio.
```

**🌐 Ruta B — Navegador**
Igual. Word para la web tiene el cuadro de indicaciones completo, y si usas Copilot Pro personal es la **única** superficie donde puedes referenciar archivos.

**🔁 Ruta C — Sin licencia**
Dos caminos, y el segundo es mejor:
1. Pide el documento en Copilot Chat con el Excel adjunto, y pega en Word sección por sección.
2. **Páginas de Copilot:** convierte la respuesta del chat en una página editable, trabaja ahí todas las secciones, y al final usa el **icono de Word** para convertirla en documento. Te ahorras siete pegados.

*Alternativa nativa:* el **Editor** de Word (Revisar → Editor) no evalúa el contenido, pero sí claridad y concisión, que en documentación técnica es justo lo que falla.

---

## Paso 6 — La hoja LÉEME dentro del libro

**Qué buscas:** que la documentación viaje con el archivo, porque el Word se va a perder.

**Todas las rutas.** Pide la versión corta:

```
Resume el documento de traspaso en una versión de media página para pegarla como
primera hoja del libro de Excel. Máximo: propósito en dos líneas, origen de los
datos, tres advertencias y a quién avisar si algo falla.
```

Crea una hoja nueva, ponla **en primer lugar**, nómbrala `LÉEME` y pégala ahí. Dale formato mínimo: título en negrita y texto ajustado.

> [!TIP]
> Este paso vale más que el documento completo. Un Word en una carpeta compartida se pierde en tres meses; una hoja LÉEME dentro del libro la ve todo el que abre el archivo.

---

## Paso 7 — La bitácora de cambios

**Todas las rutas.** En la misma hoja LÉEME, o en una hoja `Bitácora`, registra lo que tocaste:

| Fecha | Qué cambié | Por qué | Total de control antes / después |
|---|---|---|---|
| | | | |

Pídele a Copilot que la redacte a partir de tu plan de limpieza:

```
Con base en el plan de limpieza que aplicamos, redacta las entradas de bitácora:
una fila por cambio, con qué se cambió, por qué, y qué cifra se verificó.
```

### 🚪 Puerta 3 — verificación humana obligatoria

Dale el archivo y el documento a **una persona real** que nunca lo haya visto y pídele que responda tres preguntas sin ayuda tuya:

1. ¿Para qué sirve este archivo?
2. ¿De dónde salen los datos?
3. ¿Qué no debe hacer si no quiere romperlo?

Si no puede con las tres, la documentación todavía no está lista. Y ahora ya sabes exactamente qué sección reescribir.

---

# ACTO 3 — PowerPoint: proponer qué hacer con esto

Documentar el archivo lo hace usable. Pero el archivo sigue siendo frágil, y esa decisión no es tuya: es de quien es dueño del proceso. Esta es la conversación que hay que provocar.

## Paso 8 — El diagnóstico en cinco láminas

**🖥️ Ruta A — Escritorio con licencia**
1. Abre PowerPoint **desde la plantilla de tu organización**, no desde la presentación en blanco.
2. **Icono de Copilot** abajo a la derecha → **Agregar contenido** → **modo agente**.
3. Adjunta el documento de traspaso.
4. Pide:

```
Crea una presentación de cinco diapositivas para el dueño de este proceso, a
partir del documento de traspaso. Estructura: qué hace este archivo y quién
depende de él, en qué estado lo encontré, qué arreglé, qué sigue frágil y qué
decisión necesito. Sin tecnicismos de Excel: el público es de negocio.
```

5. Contesta con detalle las preguntas que te haga sobre audiencia y estilo.
6. Revisa el esquema **antes** de autorizar la generación.

**🌐 Ruta B — Navegador**
Mismo flujo. Si la plantilla corporativa no está en la web, genera ahí y aplica la plantilla al abrirlo en escritorio.

**🔁 Ruta C — Sin licencia**
El atajo del **Esquema**, que funciona igual de bien:

1. En Copilot Chat, adjunta el documento de traspaso y pide:
   ```
   Convierte este documento en el guion de cinco diapositivas. Para cada una:
   título de una línea, tres viñetas de máximo doce palabras y una nota del
   presentador de dos frases. Texto plano, con el título pegado al margen y las
   viñetas con sangría de tabulador.
   ```
2. En PowerPoint: **Vista → Esquema** y pega. Cada título se convierte en diapositiva y cada línea con tabulador en viñeta.
3. **Vista → Normal** y **Inicio → Diseñador** para el diseño.

> [!NOTE]
> Dos límites de Copilot en PowerPoint que conviene conocer: la **reescritura** trabaja sobre cuadros de texto y no sobre formas, y procesa el cuadro completo; y las **sugerencias de diseño** están oficialmente soportadas en configuración regional **en-US**, así que en español conviene revisarlas.

---

## Paso 9 — El riesgo de no hacer nada

**Qué buscas:** el argumento que sí mueve presupuesto.

**Todas las rutas:**
```
Ayúdame a cuantificar el riesgo de dejar este archivo como está. Considera:
cuántas personas dependen de él, cuánto se tarda el proceso cada mes, qué pasa
si la persona que lo entiende se va, y qué costo tendría un error no detectado
en el cálculo. Dame preguntas concretas que deba responder para poner números
a cada punto.
```

Fíjate en el matiz: no le pides que **invente** los números, le pides **qué preguntas** contestar para tenerlos. Los números los pones tú.

Esa lámina es la que decide si te dan tiempo para rehacer el archivo o si sigue viviendo así otro año.

---

## Paso 10 — La decisión que pides

**Todas las rutas.** La última lámina tiene **una sola pregunta**. Tres opciones típicas, elige una:

- *"¿Autorizan dos semanas para migrarlo a una solución con control de versiones?"*
- *"¿Confirman que fulano es el responsable formal de este archivo?"*
- *"¿Aprueban que este proceso deje de depender de un Excel manual?"*

Y ensaya las objeciones:
```
Actúa como el dueño de este proceso, que no tiene presupuesto ni ganas de
cambiar nada. Dame las cinco objeciones que me pondrías y qué evidencia me
pedirías para cada una.
```

---

# Cierre

## Lista final

- [ ] Trabajé sobre una copia versionada, nunca sobre el original.
- [ ] Anoté los totales de control **antes** de tocar nada.
- [ ] Pasé la Puerta 1: verifiqué una explicación de fórmula contra un caso real.
- [ ] Pasé la Puerta 2: los totales cuadran después de cada cambio.
- [ ] Pasé la Puerta 3: alguien más entendió el archivo solo con mi documentación.
- [ ] La hoja LÉEME está como primera pestaña del libro.
- [ ] La bitácora registra qué cambié y por qué.
- [ ] La presentación termina con una sola pregunta concreta.
- [ ] El archivo original sigue intacto hasta que alguien apruebe el reemplazo.

---

## Límites que vas a encontrar

Separo lo que Microsoft documenta de lo que descubres en la práctica, porque no es lo mismo y conviene decirlo:

**Documentado por Microsoft**

| Límite | Detalle |
|---|---|
| Modo de cálculo | La edición con Copilot **solo funciona con el cálculo en Automático** |
| Estado del archivo | Archivos desprotegidos en SharePoint o en formato *Strict Open XML* se rechazan |
| Formato de datos | El módulo del curso indica que los datos deben estar en **formato de tabla o rango admitido** |
| Precisión | Copilot "puede cometer errores, malinterpretar información o producir resultados inexactos" |
| Áreas sensibles | Se desaconseja usarlo para decisiones de finanzas, derecho o medicina |
| Word | Referencias con `/`: hasta **20 elementos**, en Word, PowerPoint, PDF o TXT, alojados en OneDrive o SharePoint |
| PowerPoint | Los documentos de Word funcionan mejor por debajo de **24 MB** |

**Lo que descubres trabajando con archivos heredados**

| Situación | Qué pasa | Cómo lo rodeas |
|---|---|---|
| Encabezados en dos filas o celdas combinadas | Copilot interpreta mal las columnas | Aplana los encabezados a una sola fila antes de empezar |
| Muchas hojas relacionadas entre sí | Razona mejor sobre una hoja que sobre el libro entero | Pregunta hoja por hoja y arma tú la cadena |
| Fórmulas con referencias a otros libros | No puede seguir el vínculo externo | Pega el valor o documenta el vínculo a mano |
| Macros y VBA | Fuera de alcance | Documenta que existen y qué disparan |
| Nombres de columna sin sentido ("Col1") | Las explicaciones salen vagas | Dile en el prompt qué contiene cada columna |

---

## Solución de problemas

| Síntoma | Causa probable | Qué hacer |
|---|---|---|
| Copilot en Excel aparece en gris | Cálculo en Manual, o archivo fuera de OneDrive | Fórmulas → Automático; guarda en la nube |
| "Estado de archivo no admitido" | Archivo desprotegido en SharePoint | Protégelo, o ábrelo en Excel para la web |
| Explica la fórmula pero se equivoca | Le falta contexto de qué contienen las columnas | Descríbele las columnas en el mismo prompt |
| El Excel no aparece al escribir `/` en Word | Está en disco local | Súbelo a OneDrive, o pega el contenido en el prompt |
| El documento sale genérico | No referenciaste el archivo ni diste hallazgos | Pega el diagnóstico del paso 3 dentro del prompt |
| La presentación queda muy técnica | No dijiste quién la va a ver | Agrega *"el público es de negocio, sin tecnicismos de Excel"* |

---

## Qué debiste aprender

1. **Documentar es la tarea que más se pospone y la que la IA resuelve más rápido.** Es el caso de uso con mejor relación esfuerzo/valor de todo el curso.
2. **Copilot explica fórmulas mejor de lo que las escribe.** Úsalo primero como traductor de lo que ya existe, no como generador de lo nuevo.
3. **Las tres puertas no tienen ruta alternativa.** Verificar contra un caso real, cuadrar totales y probar la documentación con una persona: eso es tuyo en las tres rutas.
4. **La ruta sin licencia pierde muy poco aquí**, porque el grueso del trabajo es traducir y redactar texto, y eso Copilot Chat lo hace igual.
5. **El entregable que sobrevive es la hoja LÉEME**, no el documento de Word. La documentación que viaja con el archivo es la única que se lee.
6. **Rescatar un archivo no es arreglarlo:** es dejarlo entendible y poner la decisión sobre la mesa de quien puede tomarla.

---


## Fuentes

- [Introducción a Copilot en Excel](https://support.microsoft.com/es-es/office/introducci%C3%B3n-a-copilot-en-excel-d7110502-0334-4b4f-a175-a73abdfc118a)
- [Preguntas frecuentes sobre Copilot en Excel](https://support.microsoft.com/en-gb/office/frequently-asked-questions-about-copilot-in-excel-7a13758f-d61e-4a56-8440-f2c9a07802ec)
- [Redactar y agregar contenido con Copilot en Word](https://support.microsoft.com/en-us/word/copilot/draft-and-add-content-with-copilot-in-word)
- [Crear una presentación con Copilot en PowerPoint](https://support.microsoft.com/en-us/office/create-a-new-presentation-with-copilot-in-powerpoint-3222ee03-f5a4-4d27-8642-9c387ab4854d)
- [Preguntas frecuentes sobre Copilot en PowerPoint](https://support.microsoft.com/en-us/office/frequently-asked-questions-about-copilot-in-powerpoint-3e229188-9086-4f4c-9f9f-824cd25ae84f)
- [Análisis y visualización de datos con Microsoft 365 Copilot](https://learn.microsoft.com/es-mx/training/modules/analyze-visualize-data-copilot/)
