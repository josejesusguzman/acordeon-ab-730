# Módulo 6: Definir el rol de Copilot en tu flujo de trabajo

Este módulo no enseña funciones nuevas: te pone a decidir. La idea central que se repite en las tres unidades es esta:

> **No hay una única forma "correcta" de usar Copilot.** Hay escenarios, restricciones y criterio.

Antes de cada escenario, el módulo te invita a preguntarte:
- ¿Tu equipo prefiere una introducción rápida o un desglose detallado?
- ¿Necesitas información respaldada con datos o resúmenes visuales?
- ¿Importa la consistencia de formato para las partes interesadas?

---

## Escenario 1 — Informe de estado semanal

**Personaje:** Camden, coordinador de proyecto.
**Situación:** lunes por la mañana, el informe vence en dos horas y la información está regada en correos, chats de `#project-status`, un Excel compartido y las notas del viernes.

### Flujo de trabajo

**Paso 1 — Outlook.** Abre Copilot Chat, selecciona **Datos** y los tipos de trabajo conectados.
```
Resume las actualizaciones del proyecto de los correos etiquetados como "Estado"
o de [miembros del equipo] durante la semana pasada.
```
Copilot filtra por etiquetas o remitentes y extrae progreso, bloqueadores y decisiones.

> [!TIP]
> Si las actualizaciones se ven incompletas, revisa si hay correos archivados o en carpetas fuera del alcance de Copilot. Los filtros de búsqueda manuales ayudan a validar.

**Paso 2 — Word.**
```
Crea un informe de estado semanal con las actualizaciones de Outlook. Formatea
con secciones de Progreso, Bloqueadores y Pasos siguientes.
```

**Ajustes:** si el formato queda desalineado, pide una plantilla profesional o viñetas; si el contenido sale genérico, refina el prompt con más detalle.

**Lección:** las etiquetas y la organización previa del correo determinan la calidad del resumen. **La higiene de datos es parte del prompt.**

---

## Escenario 2 — Mazo de propuesta para cliente

**Personaje:** Shane, asociado de desarrollo de negocio.
**Situación:** 12:45 p.m., el gerente pide una presentación de propuesta para una reunión a las 3:00 p.m. Solo hay notas dispersas de una llamada de descubrimiento, un archivo `Pricing.xlsx` y correos con preferencias del cliente.

### Flujo de trabajo

**Paso 1 — Outlook:**
```
Resume las preferencias del cliente y los puntos de discusión clave de los correos
con [Nombre del cliente] de las últimas dos semanas.
```

**Paso 2 — Refinar con preguntas de seguimiento:**
```
¿Qué dijo el cliente sobre la flexibilidad de precios?
```
```
¿Hay alguna preocupación sobre los tiempos de implementación?
```
Si Copilot omitió algo, busca manualmente palabras clave: *presupuesto*, *tiempos*, *preocupaciones*.

**Paso 3 — PowerPoint:**
```
Crea un conjunto de propuestas para [Nombre del cliente] usando el resumen de
correo. Incluye diapositivas para las necesidades del cliente, nuestra solución,
precios y pasos siguientes.
```

Después: personalización de marca, ajuste de tono, visuales y logotipos —eso sigue siendo tuyo.

**Lección:** Copilot resuelve la estructura y el contenido base; **la personalización y el criterio comercial son humanos**.

---

## Escenario 3 — Resumen ejecutivo

**Personaje:** Hunter, analista de estrategia.
**Situación:** 4:15 p.m., el director pide por Teams un resumen ejecutivo sobre adopción de IA en servicios financieros para el consejo de mañana. Sin plantilla, tema amplísimo y contenido disperso.

### Flujo de trabajo (interno → externo)

**Paso 1 — Comunicaciones internas:**
```
Resume las discusiones internas sobre la adopción de inteligencia artificial en
servicios financieros desde correos, chats de Teams y notas de reuniones de los
últimos 3 meses.
```

**Paso 2 — Documentos de apoyo:**
```
Busca archivos o presentaciones internos que mencionen inteligencia artificial en
servicios financieros.
```
Copilot busca en SharePoint y OneDrive.

**Paso 3 — Validación externa:**
```
Busca informes o artículos externos recientes sobre la adopción de IA en servicios
financieros. Céntrate en tendencias y desafíos.
```

**Paso 4 — Word:**
```
Crea un resumen ejecutivo con la información interna y la investigación externa.
Incluye secciones para perspectiva interna, tendencias del sector y recomendaciones
estratégicas.
```

**Lección:** dividir una tarea enorme en pasos manejables es lo que convierte el pánico en un plan. El orden **interno → externo** hace que el documento hable de tu organización y no de generalidades del sector.

---

## Los tres patrones detrás de los tres escenarios

| Escenario | Patrón | Cuándo lo reconoces |
|---|---|---|
| Informe semanal | **Consolidar** información dispersa en un formato fijo y recurrente | La tarea se repite cada semana igual |
| Propuesta de cliente | **Producir** un entregable a contrarreloj con información incompleta | Hay fecha límite y falta contexto |
| Resumen ejecutivo | **Sintetizar** interno + externo para una decisión | El tema es amplio y alguien va a decidir con eso |

> [!IMPORTANT]
> Si en el examen te dan un escenario, identifica primero cuál de estos tres patrones es. La respuesta correcta casi siempre se deduce del patrón: consolidar → Outlook + Word; producir → resumen + PowerPoint; sintetizar → interno primero, luego externo, luego Word.
