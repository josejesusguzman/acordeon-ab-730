# Copilot público vs. Copilot empresarial

Uno de los errores más caros en las organizaciones: creer que "ya tenemos Copilot" porque la gente usa el chat gratuito desde el navegador. Aquí está la diferencia, que además se pregunta en el examen.

## 1. Los tres Copilot que existen

| | **Copilot con cuenta personal** | **Copilot Chat** (cuenta de trabajo, sin licencia) | **Microsoft 365 Copilot** (con licencia) |
|---|---|---|---|
| **Cuenta** | Personal (@outlook.com, @hotmail.com) | Profesional o educativa | Profesional o educativa |
| **Fundamentación** | Web pública | Web pública | Web **y** datos de trabajo vía Microsoft Graph |
| **Modo Trabajo** | ❌ | ❌ | ✅ |
| **Protección de datos empresariales** | ❌ | ✅ | ✅ |
| **Copilot dentro de Word/Excel/PowerPoint/Outlook/Teams** | ❌ | ❌ | ✅ |
| **Agentes Investigador y Analista** | ❌ | ❌ | ✅ |
| **Avisos programados** | ❌ | ❌ | ✅ |
| **Páginas y Cuadernos** | Limitado | ✅ | ✅ |
| **Carga de archivos y generación de imágenes** | ✅ | ✅ | ✅ |
| **Costo** | Gratuito | **Sin costo adicional** con la suscripción a Microsoft 365 | Licencia de pago por usuario |

## 2. La distinción que de verdad importa: la protección de datos empresariales

Cuando inicias sesión con tu **cuenta de trabajo**, aunque no tengas licencia de pago, Copilot Chat opera bajo el **marco de protección de datos empresariales de Microsoft**:

- Tus mensajes **no se usan para entrenar los modelos base**.
- El contenido queda cubierto por los compromisos de privacidad, seguridad y cumplimiento de tu organización.
- Tu administrador tiene controles de TI y administración de agentes.

Cuando alguien de tu equipo pega el borrador de un contrato en un chat de IA **con su cuenta personal**, nada de lo anterior aplica. Ese es el riesgo real, y no se resuelve con una política escrita: se resuelve dándole a la gente una herramienta corporativa que sea igual de cómoda.

> [!WARNING]
> "Shadow AI" es el nombre del problema: gente usando herramientas de IA no autorizadas porque las autorizadas no existen o son incómodas. La mitigación más efectiva no es prohibir, es habilitar.

## 3. Qué gana exactamente quien paga la licencia

1. **Modo Trabajo.** El salto cualitativo. Copilot puede responder *"¿qué acordamos con el proveedor en la junta de marzo?"* porque ve tus correos, chats, archivos y reuniones —solo los que tú puedes ver.
2. **Copilot dentro de las aplicaciones.** El panel en Word para redactar, en Excel para analizar, en PowerPoint para armar la presentación, en Outlook para resumir hilos, en Teams para las reuniones.
3. **Los agentes de razonamiento.** Investigador y Analista, con su límite de 25 consultas combinadas al mes.
4. **Automatización ligera.** Avisos programados (hasta 10, una ejecución diaria, 15 ejecuciones sobre datos de trabajo).
5. **Resúmenes de reunión con transcripción**, con citas y atribución de quién dijo qué.

## 4. Cómo decidir a quién darle licencia

No se la des a todos de golpe. Prioriza por **densidad de trabajo con información**:

| Perfil | Prioridad | Por qué |
|---|---|---|
| Dirección y mandos medios | 🔴 Alta | Viven en juntas y correos; el resumen con citas les devuelve horas |
| Ventas y preventa | 🔴 Alta | Propuestas, seguimientos y minutas: el patrón "primer borrador" puro |
| Finanzas y análisis | 🟠 Media-alta | Excel + agente Analista |
| Legal y cumplimiento | 🟠 Media-alta | Búsqueda documental con citas verificables |
| Operación en piso o campo | 🟢 Baja | Poco trabajo documental; el retorno tarda más |

> [!TIP]
> Métrica sencilla para justificar la compra: *horas al mes que esa persona pasa leyendo o redactando documentos y correos*. Si son más de 20, la licencia se paga sola.

## 5. Preguntas frecuentes que te van a hacer

**¿Copilot lee mis correos?**
Recupera únicamente el contenido al que tú ya tienes acceso, y solo cuando tu prompt lo requiere. No hay un proceso que "lea todo" en segundo plano.

**¿Mis documentos entrenan al modelo?**
No. Los datos de la organización no se usan para entrenar los modelos base.

**¿Mi jefe puede ver mis chats de Copilot?**
Los chats están sujetos a las políticas de retención y cumplimiento de la organización, igual que tu correo corporativo. No es un espacio privado personal.

**¿Sirve si mi empresa no tiene todo en la nube?**
Parcialmente. Copilot se fundamenta en lo que vive en Microsoft 365. Los archivos en discos locales o en servidores no indexados quedan fuera de su alcance.
