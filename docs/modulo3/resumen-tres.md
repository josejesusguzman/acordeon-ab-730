# Módulo 3: Redactar y refinar contenido empresarial con Copilot

Este módulo es el patrón "primer borrador" llevado a Word, Outlook y PowerPoint.

## 3.1 Borrador de contenido con Microsoft 365 Copilot

**Lo que Copilot puede hacer con contenido:**

1. Partir de un aviso o de unos puntos clave y crear un **borrador estructurado**.
2. Dar comentarios y sugerencias en tiempo real sobre **tono, claridad y coherencia**.
3. Incorporar datos, referencias y conocimiento organizacional.
4. **Iterar rápido** hasta que el texto cumpla el objetivo.
5. Trabajar tanto con contenido nuevo como con material existente.

### Redactar en Word

1. Abre Word → icono de **Copilot** en la cinta **Inicio** → se abre Copilot Chat.
2. Elige el tipo de recurso: **datos de trabajo** o **datos de la web**.

| Tipo de datos | Qué contiene | Cuándo usarlo |
|---|---|---|
| **Basados en trabajo** | Correos, documentos, reuniones y chats de Microsoft 365 | Necesitas contexto interno de tu organización |
| **Basados en web** | Información pública vía Bing | Investigación externa, tendencias, datos actualizados |

Prompts de ejemplo:
```
Escribe una introducción profesional para nuestro informe de desempeño del
tercer trimestre.
```
```
Haz que el tono sea más optimista y con visión de futuro.
```
```
Agrega una frase que resalte los logros del equipo.
```

> [!TIP]
> Iterar es la clave. Los mensajes de seguimiento para ajustar tono, longitud o enfoque valen más que un primer prompt perfecto.

### Tendencias: trabajo vs. web

**Con datos de trabajo:**
```
Resume la información interna reciente sobre tendencias de tecnología portátil
de mis documentos y correos.
```

**Con datos de la web:**
```
Resume las tendencias actuales del sector de tecnología portátil usando
orígenes web recientes.
```

Prueba ambos y combínalos: la mezcla de contexto interno con referencia externa produce el contenido más sólido.

### Convertir texto en tabla

1. Selecciona el párrafo.
2. Pide:
   ```
   Convierte este párrafo en una tabla con columnas para nombre del equipo,
   KPI y resultado.
   ```
   O usa **Visualizar como tabla** en el panel de chat.
3. Refina:
   ```
   Agrega una fila de encabezado y pon en negrita los títulos de columna.
   ```
4. Guarda el documento.

### De Word a PowerPoint

1. Abre PowerPoint → icono de **Copilot** en la cinta **Inicio**.
2. Referencia el documento de Word con `/`:
   ```
   /InformeQ3.docx
   ```
3. Prompt inicial:
   ```
   Resume este contenido en cinco viñetas para una presentación de liderazgo.
   ```
4. Refina:
   ```
   Haz que las viñetas sean concisas y orientadas a la acción.
   ```
5. Guarda.

### Comunicar en Outlook

1. Pide a Copilot que resuma el hilo largo.
2. Redacta el correo a partir del resumen:
   ```
   Envía un correo al equipo directivo con base en el resumen del hilo.
   Mantén el tono profesional y conciso.
   ```

### El flujo completo

```
WORD: redactar el informe  →  WORD: convertir datos en tabla
   →  POWERPOINT: crear la presentación desde el documento
   →  OUTLOOK: resumir las conversaciones del equipo
   →  OUTLOOK: comunicar el avance a dirección
```

## 3.2 El agente Investigador (*Researcher*)

**Definición:** agente de razonamiento integrado en Microsoft 365 Copilot, optimizado para **detección, síntesis y generación de información** —a diferencia de Copilot Chat estándar, que está centrado en redacción y edición.

**Qué hace:**
1. Investigación en **varios pasos** combinando contenido de trabajo interno y orígenes web públicos.
2. Entrega resúmenes estructurados **con citas**.
3. **Hace preguntas aclaratorias** para afinar el encargo, como lo haría un colega.
4. Genera contenido listo para usar en Word, PowerPoint u Outlook.

**Acceso:** licencia de Microsoft 365 Copilot → aplicación Microsoft 365 (navegador o escritorio) → sección **Agentes**.

> [!IMPORTANT]
> **25 consultas combinadas al mes** entre el agente Investigador y el Analista. Úsalas en preguntas que de verdad lo ameriten.

**Prompt inicial de ejemplo:**
```
Investiga las últimas tendencias de IA para minoristas y redacta un informe de
análisis de mercado basado en datos de la competencia.
```

**Prompts de refinamiento:**
```
Incluye información sobre comportamiento del consumidor y tasas de adopción.
```
```
Resume los movimientos clave de los principales competidores en los últimos 12 meses.
```
```
Resalta los riesgos o desafíos del mercado.
```

**Reformatear el resultado:**
```
Resume esto en tres viñetas para una diapositiva de liderazgo.
```
```
Escribe un resumen ejecutivo para este informe.
```
```
Redacta una actualización por correo que resuma estos resultados.
```

## Errores comunes en este módulo

| Error | Consecuencia | Arreglo |
|---|---|---|
| Pedir el documento final en un solo prompt | Texto genérico | Encadena: estructura → contenido → tono → formato |
| No decir para quién es | Registro equivocado | Nombra siempre a la audiencia |
| Usar el Investigador para tareas simples | Gastas tus 25 consultas | Copilot Chat basta para resumir y redactar |
| Aceptar el borrador tal cual | Suena a máquina | Reescribe al menos la apertura y el cierre con tu voz |
