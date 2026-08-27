# Módulo 5: Administración de reuniones y colaboración

## 5.1 Preparación y seguimiento de reuniones

### Antes: Copilot en Outlook

Qué puede hacer:
- Resumir hilos largos de correo.
- Programar reuniones con las partes interesadas.
- Crear agendas.
- Bloquear tiempo para trabajo concentrado.

```
Resume este hilo de correo sobre la línea de tiempo de inicio del equipo.
Después crea una agenda para discutir los temas de programación y los pendientes.
```
```
Muestra mis reuniones de hoy y bloquea tiempo para el trabajo del proyecto LaunchPad.
```

### Durante: Copilot en Teams

Capacidades:
- **Resumen en tiempo real**, incluyendo quién dijo qué y dónde hay acuerdo o desacuerdo.
- **Sugerencia de pendientes** y preguntas para avanzar la conversación.
- **Responder preguntas** con base en la transcripción y el chat.
- **Crear formatos**: tablas, listas y resúmenes.
- **Generar contenido de aprendizaje**: cuestionarios, microlearning, incluso juegos.

> [!IMPORTANT]
> **Copilot requiere transcripción** para dar información completa de la reunión. Sin transcripción, se limita a los datos del chat. Este dato aparece en el examen.

**Configuración:** Opciones de reunión → **Permitir Copilot**:
- **Durante y después de la reunión** → requiere transcripción.
- **Solo durante la reunión** → usa conversión de voz a texto sin guardar transcripción.

Habilita **transcripción y grabación en la nube** para funcionalidad completa.

**Prompts dentro de la reunión:**
```
¿Cuáles son las principales ventajas hasta ahora?
```
```
¿Dónde no estamos de acuerdo?
```
```
Resume lo que dijo cada participante.
```
```
Crea una tabla de ventajas y desventajas para cada idea.
```
```
Dime lo que me perdí hasta ahora.
```

> [!TIP]
> Menciona agentes como **@Investigador** o **@Analista** dentro de tus mensajes para profundizar en datos o información durante la reunión.

### Después: resúmenes y seguimiento

Los resúmenes capturan quién contribuyó a cada tema, dónde se alineó o discrepó el equipo y proponen pendientes. Se basan en transcripción y chat, **incluyen citas** y pueden exportarse a Word o Excel.

**Cómo acceder:** pestaña **Resumen** en el chat de la reunión → **Copilot**.

**Seguimiento:**
```
Redacta un correo de seguimiento para el equipo de LaunchPad que resuma las
decisiones de hoy y los pasos siguientes.
```
```
Enumera los pendientes de la transcripción de la reunión para cada miembro del equipo.
```

## 5.2 Colaboración con Copilot Chat, Páginas y Cuadernos

### Copilot Chat para dar seguimiento

```
Resume este hilo de Teams y genera una lista de tareas para la fase de
preparación de inicio.
```
```
Crea una actualización semanal para las partes interesadas con base en los
últimos cambios de la hoja de ruta. Enumera los riesgos o bloqueadores que el
equipo pueda encontrar en los próximos cinco días.
```
```
Revisa los mensajes de Teams y los correos de Outlook relacionados con este
proyecto y agrega pendientes para cada miembro del equipo.
```

### Cuadernos (*Notebooks*)

**Definición:** área de trabajo inteligente dentro de Microsoft 365 que centraliza todo el contenido de un proyecto —archivos, chats, notas de reunión— y entrega información personalizada con IA, sin saltar entre aplicaciones.

**Límites y especificaciones que se preguntan:**

| Aspecto | Detalle |
|---|---|
| Referencias | Puedes agregar más de 20, pero **solo se usan las primeras 20** para fundamentar |
| Tipos de archivo | .docx, .pptx, .xlsx, .pdf, .loop, OneNote |
| Vínculos | Solo a tipos de archivo admitidos en Microsoft 365; los vínculos web **no** se soportan |
| SharePoint | Reconoce actualizaciones y usa la versión actual |
| Carpetas locales | **No** reconoce cambios: solo referencia el contenido original |
| Audio | Introducción de audio disponible en inglés, español, japonés, francés, alemán, portugués, italiano y chino |

### Páginas (*Pages*)

**Definición:** área de trabajo flexible dentro de Copilot Chat que convierte respuestas de IA en contenido **modificable y compartible**. Está construida sobre **Microsoft Loop** y disponible en Teams, Outlook y la aplicación de Microsoft 365.

**Compartir:**

| Opción | Qué hace |
|---|---|
| **Vínculo de página** | Se pega en Teams, Outlook u otras apps. Abre la página en Loop |
| **Copiar el componente** | Se pega como componente Loop; los cambios se actualizan en tiempo real en ambos lados |

**Control de versiones:** Páginas rastrea quién editó qué, muestra la foto de perfil del colaborador junto al contenido y, si fueron varios, muestra "+N". Al pasar el puntero ves el nombre y las partes que editó.

**Convertir a Word:** icono de **Word** en la esquina superior derecha → Copilot prepara el borrador → abre en Word.

> [!NOTE]
> Las páginas se guardan indefinidamente a menos que las elimines manualmente.

## Chuleta: cuál usar cuándo

| Necesito… | Herramienta |
|---|---|
| Ponerme al día de una reunión a la que no fui | Resumen de reunión (requiere transcripción) |
| Convertir una respuesta del chat en documento colaborativo | **Páginas** |
| Reunir 15 archivos de un proyecto y preguntarles cosas | **Cuadernos** |
| Redactar el correo de seguimiento | Copilot en **Outlook** |
| Saber quién dijo qué y dónde hubo desacuerdo | Copilot en **Teams** con transcripción |
| Un documento formal final | **Páginas → convertir a Word** |
