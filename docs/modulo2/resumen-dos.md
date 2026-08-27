# Módulo 2: Emplear Copilot Chat como su asistente de IA

Este es el módulo más importante del examen. Si solo tuvieras tiempo para uno, sería este.

## 2.1 ¿Qué es Copilot Chat?

**Definición:** la experiencia de chat compartida de Microsoft 365 Copilot, con **inteligencia entre aplicaciones**. Su interfaz conversacional entiende la intención del usuario, mantiene un diálogo continuo y sintetiza información de varias fuentes a la vez.

### Copilot Chat vs. Copilot dentro de una aplicación

| | **Copilot Chat** | **Copilot en la app (Word, PowerPoint…)** |
|---|---|---|
| **Acceso** | Aplicación Microsoft 365, Teams o navegador | Dentro de cada aplicación |
| **Alcance** | Trabaja entre varias aplicaciones y contenidos | Diseñado para el contexto de esa app |
| **Uso típico** | Inteligencia entre aplicaciones, síntesis | Word: redactar y editar; PowerPoint: armar la presentación |

### Modo Trabajo y modo Web

| | **Modo Trabajo** | **Modo Web** |
|---|---|---|
| **Se fundamenta en** | Datos de tu organización vía **Microsoft Graph** | Datos públicos vía índice de **Bing** |
| **Alcance** | Archivos, correos, reuniones, chats de Microsoft 365 | Noticias, tendencias, información pública |
| **Casos de uso** | Redactar con contexto interno, resumir reuniones, administrar calendario | Lluvia de ideas, investigación, referencias externas |
| **Disponibilidad** | Requiere **licencia de Microsoft 365 Copilot** | Para todos los usuarios |

Ambos modos comparten seguridad de nivel empresarial, privacidad y cumplimiento normativo.

### Otras capacidades incluidas

- Chat seguro con tecnología GPT-4 / GPT-5.
- Agentes accesibles desde la interfaz de chat.
- Controles de TI (protección de datos empresariales y administración de agentes).
- **Páginas de Copilot**, **Cuadernos**, **carga de archivos** y **generación de imágenes**.

### Memoria de Copilot

Recuerda tus preferencias y tu contexto de trabajo para que no repitas instrucciones ("responde con viñetas", "mantén tono profesional"). Puedes **ver, editar o eliminar** los recuerdos en la configuración, y usar un **chat temporal** cuando no quieras que se guarde nada.

### Chat vs. Búsqueda de Copilot

| | **Copilot Chat** | **Búsqueda de Copilot** |
|---|---|---|
| **Enfoque** | Crear y razonar | Descubrir y localizar |
| **Método** | Conversación | Búsqueda contextual con Microsoft Graph |
| **Cuándo** | Necesitas producir algo | Necesitas encontrar algo rápido |

## 2.2 Escritura de avisos efectivos

Los **cuatro elementos** de un buen prompt (memorízalos, se preguntan):

1. **Contexto** — ¿Por qué lo necesitas y quién está involucrado?
2. **Objetivo** — ¿Qué quieres que haga Copilot?
3. **Origen** — ¿Dónde debe buscar la información?
4. **Expectativas** — ¿Cómo debe entregarte la respuesta?

### Referencias dentro del prompt

| Símbolo | Para qué sirve | Ejemplo |
|---|---|---|
| `/` | Referir una persona, archivo o ubicación | `Resume los puntos clave de /Q4MarketingStrategy.pptx` |
| `#` | Referir un tema, reunión o evento | `¿Cuáles fueron los pendientes de #WeeklyOpsSync?` |
| `@` | Invocar un agente | `@Investigador compara los 3 principales competidores en CRM` |

### Capacidades de voz

**Dictado** (componer con la voz), **Lectura en voz alta** (que Copilot te lea la respuesta en Word y PowerPoint) y **Chat de voz** (conversación hablada bidireccional; `Win + C` en Windows). Además de comodidad, son accesibilidad.

## 2.3 Administración de mensajes y conversaciones

- **Guardar un prompt:** pasa el cursor sobre el prompt → icono de **Marcador** → nómbralo. Queda en **Galería de consultas → Sus mensajes**. No se puede editar en su lugar: se ejecuta, se modifica y se guarda como uno nuevo.
- **Programar un prompt:** pasa el cursor → **Programar este mensaje** → frecuencia → Guardar. **Máximo 10 mensajes programados**, una ejecución al día, 15 ejecuciones totales sobre datos de trabajo. Requiere licencia y que la organización permita experiencias conectadas opcionales.
- **Administrar programados:** menú `...` → **Avisos programados** → Ejecutar ahora / Desactivar / Eliminar.
- **Compartir un prompt:** Galería de consultas → Sus consultas → icono **Compartir** → equipo. Aparece en la pestaña **Equipo**. Usa marcadores como `[Fecha de reunión]` o `[Audiencia]` para reutilizarlos.
- **Conversaciones:** se pueden **buscar**, **renombrar**, **eliminar** y **agregar a un cuaderno**. Para borrar todo el historial: [portal de privacidad de Microsoft](https://account.microsoft.com/privacy) → Historial de actividad de Copilot → Eliminar todo.

> [!WARNING]
> Eliminar conversaciones **no se puede deshacer**, no afecta los informes de uso de la organización, y si compartiste el vínculo de una conversación, esa liga puede seguir siendo accesible.

## 2.4 ¿Qué son los agentes de IA?

**Definición:** asistentes de IA especializados que automatizan tareas, responden preguntas y simplifican procesos. Se comportan como compañeros de equipo expertos en un tipo de trabajo.

| | **Precompilados (tienda de agentes)** | **Personalizados** |
|---|---|---|
| Creación | Ya existen | Los creas tú |
| Configuración | Mínima | Instrucciones, conocimiento, capacidades |
| Orígenes de conocimiento | Predefinidos | Hasta **20** personalizados |
| Licencia | No requieren una aparte | No requieren una aparte |

Los dos precompilados que debes conocer:

- **Investigador (*Researcher*)** — investigación en varios pasos sobre contenido de trabajo y web, con informes estructurados y citas.
- **Analista (*Analyst*)** — análisis de datos con razonamiento de cadena de pensamiento, tendencias, valores atípicos y visuales.

> [!IMPORTANT]
> **Límite combinado: 25 consultas al mes** entre el agente Investigador y el Analista. Es un dato que suele aparecer en el examen.
