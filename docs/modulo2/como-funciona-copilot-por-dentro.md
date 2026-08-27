# ¿Cómo funciona internamente Copilot?

Copilot no es "ChatGPT con logo de Microsoft". La diferencia está en lo que pasa entre que tú escribes y el modelo responde. Ese intermedio se llama **orquestación**, y es lo que hace que la respuesta conozca tu trabajo sin exponerlo.

## 1. El recorrido completo de un prompt

```
   TÚ escribes el prompt
        ↓
1. PREPROCESAMIENTO
   Copilot interpreta la intención y decide si necesita datos de trabajo,
   de la web, o ninguno
        ↓
2. FUNDAMENTACIÓN (grounding) vía MICROSOFT GRAPH
   Recupera correos, documentos, chats y reuniones a los que TÚ tienes
   permiso de acceder. Ni uno más.
        ↓
3. CONSTRUCCIÓN DEL PROMPT ENRIQUECIDO
   Tu pregunta + los fragmentos recuperados + las instrucciones del sistema
        ↓
4. EL MODELO DE LENGUAJE (LLM)
   Genera la respuesta a partir de ese paquete
        ↓
5. POSPROCESAMIENTO
   Verificaciones de seguridad y cumplimiento, filtros de contenido,
   revisión de permisos y armado de las CITAS
        ↓
6. RESPUESTA en tu aplicación, con sus fuentes
```

## 2. Las cuatro piezas

### Las aplicaciones de Microsoft 365
Word, Excel, PowerPoint, Outlook y Teams. Son la superficie: donde escribes el prompt y donde aterriza el resultado.

### El modelo de lenguaje grande (LLM)
El motor generativo. **No tiene memoria de tu empresa** ni acceso a tus archivos. Solo ve lo que la orquestación le pone enfrente en ese momento.

### Microsoft Graph
La capa de datos de tu organización: correos, archivos, calendarios, chats, contactos, reuniones. Es el ingrediente que convierte una respuesta genérica en una respuesta tuya.

### El orquestador
El director de orquesta: decide qué recuperar, cuánto meter en el contexto, qué filtros aplicar y cómo armar las citas.

> [!IMPORTANT]
> **La ecuación del examen:**
> `Aplicaciones de Microsoft 365 + LLM + Microsoft Graph = Microsoft 365 Copilot`

## 3. Lo que esta arquitectura garantiza

| Garantía | Por qué se cumple |
|---|---|
| **No ves lo que no puedes ver** | Graph aplica tus permisos en la recuperación. Copilot no "abre puertas": usa las llaves que ya tienes |
| **Tus datos no entrenan el modelo** | El contenido recuperado se usa solo para responderte en ese momento |
| **Las respuestas se pueden auditar** | Las citas apuntan al documento real del que salió cada afirmación |
| **Se respetan etiquetas y políticas** | Las etiquetas de confidencialidad y las políticas de Purview viajan con el contenido |

> [!NOTE]
> Corolario incómodo pero útil: si Copilot te muestra un documento que **no deberías** poder ver, el problema no es Copilot. Es que los permisos de ese documento estaban mal desde antes. Copilot no crea fugas: las hace visibles.

## 4. Por qué a veces "no encuentra" algo que sí existe

Cinco causas, en orden de frecuencia:

1. **No tienes permiso** sobre ese contenido.
2. **No está indexado** en Microsoft Graph (por ejemplo, vive en tu disco local y no en OneDrive/SharePoint).
3. **Estás en el modo equivocado.** Modo Web no ve tus documentos; modo Trabajo no navega la web abierta.
4. **Tu prompt no le dio pistas suficientes** para recuperar el fragmento correcto.
5. **El contenido está en un formato que no procesa** o en una carpeta local que no reconoce.

## 5. Ventana de contexto: por qué importa

El modelo solo puede considerar cierta cantidad de texto a la vez. La orquestación decide qué **cabe** en esa ventana. De ahí salen dos comportamientos que verás seguido:

- Con documentos muy largos, Copilot resume secciones en lugar de leer todo palabra por palabra.
- Los **Cuadernos** limitan las referencias que se usan para fundamentar (se aceptan más de 20, pero solo las primeras 20 se usan). No es un capricho: es la ventana de contexto.

> [!TIP]
> Traducción práctica: **menos fuentes bien elegidas producen mejores respuestas que muchas fuentes revueltas**. Si quieres precisión, referencia el archivo exacto con `/` en lugar de esperar que Copilot adivine.
