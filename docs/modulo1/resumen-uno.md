# Módulo 1: ¿Qué es la inteligencia artificial generativa?

Resumen rápido de las unidades del módulo en Microsoft Learn. Si vas con prisa, esto es lo que tienes que saber.

## 1.1 ¿Qué es la inteligencia artificial generativa?

- **Definición:** rama de la IA diseñada para **producir contenido nuevo** —imágenes, video, texto o audio— a partir de una descripción sencilla en lenguaje natural.
- Gracias al avance del **procesamiento de lenguaje natural**, los resultados son de calidad similar a la humana: artículos, resúmenes, imágenes realistas, voces sintéticas, animaciones.
- Está pensada para **usuarios de negocio sin perfil técnico**: interfaces conversacionales, plantillas predefinidas y funcionalidades precompiladas. No necesitas programar.

### Modelos que clasifican vs. modelos que generan

| Tipo de modelo | Qué hace | Ejemplo cotidiano |
|----------------|----------|-------------------|
| **Clasificación** | Identifica y ordena información existente | Mandar un correo a Spam, Promociones o Principal |
| **Generativo** | Crea contenido nuevo a partir de patrones aprendidos | La respuesta que te escribe Copilot Chat |

### Para qué sirve en una empresa

1. **Automatizar lo tedioso:** redactar correos, resumir documentos, generar informes, sintetizar notas de reunión.
2. **Detonar ideas:** campañas de marketing, nombres de producto, guiones, propuestas de diseño.
3. **Acelerar el flujo de trabajo:** producir borradores en minutos para dedicar el tiempo a lo que sí requiere criterio humano.

> [!NOTE]
> La frase que conviene memorizar: la IA generativa **no sustituye el criterio**, libera el tiempo que estabas gastando en el primer borrador.

## 1.2 Descripción de la inteligencia artificial responsable

Microsoft define **seis principios** de IA responsable. Aparecen en el examen; apréndetelos por nombre:

| Principio | Qué significa |
|-----------|---------------|
| **Equidad** | El sistema no discrimina y da resultados equitativos para todos los usuarios |
| **Confiabilidad y seguridad** | Se mitigan riesgos como generar contenido dañino o que el sistema sea explotado |
| **Privacidad y seguridad** | Los datos del usuario se protegen y se cumple la normativa de privacidad |
| **Inclusión** | Se diseña para no perpetuar los sesgos presentes en los datos de entrenamiento |
| **Transparencia** | Los procesos de IA son comprensibles y accesibles para el usuario |
| **Responsabilidad** | Desarrolladores y organizaciones responden por el impacto del sistema |

### Cómo aterriza esto en Microsoft 365 Copilot

- **Respuestas fundamentadas:** Copilot se apoya en fuentes confiables y **entrega citas** para que puedas verificar.
- **Moderación de contenido:** clasificadores y filtros bloquean contenido dañino o inadecuado.
- **Privacidad por diseño:** tus datos están protegidos y **no se usan para entrenar el modelo**.
- **Cifrado y aislamiento** de datos en reposo y en tránsito, **controles de acceso** que respetan permisos y etiquetas de confidencialidad, y **cumplimiento regional**.
- **Microsoft Purview** aplica políticas de cumplimiento, etiquetas de confidencialidad y supervisa las interacciones con la IA para evitar el uso compartido excesivo de información confidencial.

### Riesgos que sí debes tener presentes

- **Inyección de instrucciones (*prompt injection*):** instrucciones maliciosas escondidas en un correo, un archivo o una página web que engañan a Copilot para que ignore sus reglas.
- **Dependencia excesiva:** nunca dependas únicamente de la respuesta de Copilot. Revisa siempre que no se hayan expuesto datos sensibles, que no haya imprecisiones y que las fuentes sean documentos o sitios conocidos.
- **Supervisión humana:** el humano sigue siendo el árbitro final en decisiones críticas, y los mecanismos de retroalimentación existen para reportar problemas.

## 1.3 Microsoft 365 Copilot como compañero de flujo de trabajo

**Definición:** asistente con IA generativa incrustado en las aplicaciones de Microsoft 365 (Word, Excel, Outlook, Teams y PowerPoint).

La ecuación que hay que saber de memoria:

```
Aplicaciones de Microsoft 365  +  LLM  +  Microsoft Graph  =  Microsoft 365 Copilot
```

- **LLM:** el motor generativo.
- **Microsoft Graph:** la capa que le da contexto de tu organización —correos, documentos, calendarios y chats— **respetando tus permisos**.

### Lo que Copilot puede hacer

1. **Generar** contenido nuevo: correos, documentos, presentaciones.
2. **Resumir** información: reuniones, hilos de chat, documentos largos.
3. **Analizar y visualizar** datos.
4. **Automatizar** flujos de trabajo y tareas repetitivas.
5. **Apoyar decisiones** con recomendaciones contextuales.

> [!IMPORTANT]
> La diferencia entre Copilot y cualquier chatbot público es **Microsoft Graph**. Sin Graph tienes un modelo listo; con Graph tienes un modelo que conoce tu trabajo.
