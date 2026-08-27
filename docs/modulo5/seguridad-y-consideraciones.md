# Consideraciones de seguridad para el uso de IA

Este es el tema que separa a quien "sabe usar Copilot" de quien puede implementarlo en una organización sin causar un incidente.

## 1. El modelo de seguridad de Microsoft 365 Copilot

| Control | Qué garantiza |
|---|---|
| **Herencia de permisos** | Copilot solo recupera contenido al que **tú ya tienes acceso**. No abre puertas nuevas |
| **Cifrado y aislamiento** | Datos protegidos en reposo y en tránsito |
| **Sin entrenamiento con tus datos** | El contenido de la organización no se usa para entrenar los modelos base |
| **Etiquetas de confidencialidad** | Las etiquetas viajan con el contenido y Copilot las respeta |
| **Cumplimiento regional** | El procesamiento se alinea con las regulaciones locales |
| **Microsoft Purview** | Aplica políticas, etiqueta información sensible y **supervisa las interacciones con la IA** |
| **Protección de datos empresariales** | Marco que cubre incluso a Copilot Chat sin licencia, cuando usas cuenta de trabajo |

## 2. Los cinco riesgos reales

### 2.1 Inyección de instrucciones (*prompt injection*)
Instrucciones maliciosas escondidas en un correo, documento o página web que engañan a Copilot para que ignore sus reglas.

**Mitigación:** desconfía del contenido externo, revisa antes de ejecutar, y nunca automatices acciones irreversibles sin supervisión.

### 2.2 Sobreexposición por permisos mal configurados
Copilot no crea fugas: **revela las que ya existían**. Si media empresa tiene acceso a la carpeta de nómina, Copilot lo va a demostrar en el primer prompt.

**Mitigación:** auditoría de permisos **antes** del despliegue. Es el trabajo aburrido que decide si el proyecto sale bien.

### 2.3 Dependencia excesiva (*overreliance*)
Aceptar la salida sin revisarla. La recomendación oficial: nunca dependas únicamente de Copilot; verifica que no se revelen datos sensibles, que no haya imprecisiones y que las fuentes sean confiables.

### 2.4 Fuga por canal alterno (*shadow AI*)
El riesgo no es Copilot: es la persona que pega un contrato en una herramienta de IA personal porque le resulta más cómoda.

**Mitigación:** habilitar la herramienta corporativa y capacitar. Prohibir sin ofrecer alternativa produce el comportamiento que quieres evitar.

### 2.5 Retención y compartición de conversaciones
Las conversaciones están sujetas a las políticas de retención de la organización. Eliminar el historial **no se puede deshacer**, no afecta los informes de uso y **si compartiste el vínculo de una conversación, esa liga puede seguir accesible**.

## 3. Seguridad específica en reuniones

| Consideración | Por qué importa |
|---|---|
| **La transcripción es un registro** | Queda almacenada y es descubrible en un proceso legal |
| **Consentimiento** | Avisa que se está transcribiendo; en varias jurisdicciones es obligatorio |
| **Reuniones sensibles** | Configura *Solo durante la reunión* o desactiva Copilot |
| **Invitados externos** | Definan de antemano si se graba y quién tendrá acceso al resumen |
| **Citas y atribución** | El resumen dice quién dijo qué: útil, y también delicado |

> [!WARNING]
> Antes de activar transcripción por defecto en toda la organización, revisa con el área legal. Es la decisión con más consecuencias no previstas de todo el despliegue.

## 4. Higiene personal: siete reglas

1. **No pegues** lo que no pondrías en un correo corporativo.
2. **Verifica antes de reenviar.** Si vas a mandarlo a alguien más, ábrele al menos una cita.
3. **Usa chat temporal** para conversaciones que no deban guardarse.
4. **Revisa tus recuerdos** de Copilot cada cierto tiempo y borra los que ya no apliquen.
5. **Nombra tus chats.** Un historial ordenado es un historial que puedes auditar.
6. **No compartas vínculos de conversación** sin revisar todo el hilo.
7. **Reporta lo raro.** Si una respuesta trae información que no deberías ver, avisa a TI: encontraste un permiso mal puesto.

## 5. Lista de verificación antes de un despliegue

- [ ] Auditoría de permisos de SharePoint y OneDrive completada.
- [ ] Etiquetas de confidencialidad definidas y aplicadas al contenido crítico.
- [ ] Políticas de Purview configuradas para las interacciones con IA.
- [ ] Política de transcripción de reuniones revisada con legal.
- [ ] Política de retención de conversaciones definida.
- [ ] Capacitación en prompts **y** en verificación impartida (no solo la primera).
- [ ] Canal claro para reportar respuestas inesperadas.
- [ ] Alternativa corporativa comunicada para desalentar el *shadow AI*.

## 6. La frase que resume el módulo

> Copilot es tan seguro como los permisos de tu organización y tan confiable como el criterio de quien lo usa. La tecnología resuelve la primera mitad; la capacitación resuelve la segunda.
