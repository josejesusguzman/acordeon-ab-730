# Tutorial: crea tu propio agente de Copilot

**Objetivo:** construir, configurar y compartir un agente personalizado sin escribir una línea de código.

> [!NOTE]
> Requiere una cuenta de trabajo con acceso a la aplicación de Microsoft 365 Copilot. Los agentes **no requieren una licencia aparte**.

## 1. Antes de empezar: ¿qué es un agente?

Un agente es un Copilot especializado: mismas capacidades base, pero con **instrucciones**, **conocimiento** y **capacidades** que tú defines. Piénsalo como contratar a un becario y darle un manual: el modelo es el becario, las instrucciones son el manual.

### Los dos tipos

| **Precompilados** (tienda de agentes) | **Personalizados** |
|---|---|
| Validados para uso empresarial | Los creas para un flujo específico |
| Implementación inmediata | Requieren configuración |
| De Microsoft, socios y equipos internos | Control total sobre comportamiento y fuentes |

Los precompilados estrella: **Investigador** (investigación multipaso con citas) y **Analista** (análisis de datos con visuales).

## 2. Crear el agente — paso a paso

### Paso 1: Abre Copilot Chat
Desde el navegador o la aplicación de Microsoft 365.

### Paso 2: Inicia la creación
Selecciona **Crear agente** en el panel de navegación izquierdo, o entra a la pestaña **Agentes**.

### Paso 3: Descríbelo o parte de una plantilla

**Opción A — plantillas:** Coach de carrera, Idea Coach, Customer Insights.

**Opción B — lenguaje natural:**
```
Un agente que ayude a redactar correos de marketing y a revisar el tono
antes de enviarlos.
```

### Paso 4: Configura
Selecciona **Configurar** para abrir todas las opciones.

## 3. Las cinco secciones de configuración

### 3.1 Detalles
Nombre, descripción e icono. El nombre importa: tus compañeros lo van a buscar por ahí.

### 3.2 Instrucciones — el corazón del agente

Estructura recomendada:

| Aspecto | Qué defines | Ejemplo |
|---|---|---|
| **Quién es** | Identidad o persona | *"Actúa como analista financiero senior"* |
| **Qué hace** | Tareas y objetivos | *"Analiza datos de ventas trimestrales, identifica tendencias y genera reportes"* |
| **Cómo responde** | Tono, formato, nivel de detalle | *"Responde en tono profesional con viñetas. Evita tecnicismos"* |

Ejemplo completo de instrucciones para un agente de propuestas comerciales:

```
Eres un asistente de propuestas comerciales para una empresa de servicios de TI
en México.

Tu trabajo es convertir notas de llamadas de descubrimiento en borradores de
propuesta estructurados con estas secciones fijas: Contexto del cliente,
Necesidad detectada, Solución propuesta, Alcance, Supuestos y Siguientes pasos.

Reglas:
- Usa siempre los precios del documento de tarifas conectado. Nunca inventes cifras.
- Si falta información para llenar una sección, escribe [PENDIENTE: qué falta]
  en lugar de suponer.
- Tono profesional y directo, sin superlativos.
- Máximo dos páginas.
```

> [!TIP]
> La instrucción más valiosa que puedes darle a cualquier agente es qué hacer **cuando no sabe**. Sin ella, inventa.

### 3.3 Conocimiento
Conecta hasta **20 orígenes**: páginas de SharePoint, archivos de OneDrive, chats de Teams y sitios web públicos. Menos fuentes bien elegidas > muchas fuentes revueltas.

### 3.4 Capacidades

| Capacidad | Para qué sirve |
|---|---|
| **Intérprete de código** | Ejecuta Python para cálculos, análisis de datos y tareas repetitivas |
| **Creador de imágenes** | Genera gráficos, diagramas, arte conceptual y mockups |

### 3.5 Avisos sugeridos
Los ejemplos que verá quien abra tu agente por primera vez:
- *"Resume este informe"*
- *"Crea una línea de tiempo del proyecto"*

## 4. Compartir el agente

Por defecto el agente es **privado**. Para compartirlo:

1. Abre el agente en Copilot Chat.
2. Ve a **Configuración → Compartir**.
3. Elige el alcance: **personas o grupos específicos**, o **toda la organización**.
4. Asigna roles:
   - **Visor:** puede usar el agente.
   - **Editor:** puede modificar instrucciones, avisos y orígenes.

> [!IMPORTANT]
> No requiere aprobación del administrador para compartir dentro de la organización. Y ojo: si editas los **avisos sugeridos** después de compartir, quienes ya tienen acceso deben reinstalar el agente para verlos actualizados.

## 5. Ejercicio: construye el tuyo en 20 minutos

Elige uno de estos tres y créalo de verdad:

**a) Revisor de tono corporativo.** Conocimiento: tu guía de estilo o comunicados anteriores. Instrucción: revisa el texto, señala frases fuera de tono y propone la corrección, sin reescribir todo.

**b) Onboarding de área.** Conocimiento: documentos de proceso y preguntas frecuentes de tu equipo. Instrucción: responde dudas de gente nueva citando siempre el documento, y si no está documentado, dilo.

**c) Preparador de juntas.** Conocimiento: minutas anteriores. Instrucción: antes de cada reunión, resume los acuerdos previos, los pendientes y los tres temas que probablemente saldrán.

### Lista de verificación antes de compartirlo

- [ ] ¿Las instrucciones dicen qué hacer cuando falta información?
- [ ] ¿Las fuentes de conocimiento son las mínimas necesarias?
- [ ] ¿Probaste al menos cinco preguntas reales, incluida una que no debería poder contestar?
- [ ] ¿El nombre y la descripción explican de qué sirve sin necesidad de abrirlo?
- [ ] ¿Los avisos sugeridos son ejemplos reales de tu equipo?
