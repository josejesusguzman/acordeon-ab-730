# Preguntas rápidas para repasar

Banco de repaso por módulo. Léelas, contéstalas de memoria y **después** despliega la respuesta.

> [!NOTE]
> Estas preguntas no son del examen oficial ni pretenden reproducirlo. Son un repaso de los datos que más se confunden.

---

## Módulo 1 — IA generativa e IA responsable

<details><summary><b>1. ¿Cuál es la diferencia entre un modelo de clasificación y uno generativo?</b></summary>

El de clasificación **identifica y ordena** información existente (mandar un correo a Spam). El generativo **crea contenido nuevo** a partir de patrones aprendidos (redactar la respuesta a ese correo).
</details>

<details><summary><b>2. ¿Cuáles son los seis principios de IA responsable de Microsoft?</b></summary>

Equidad, confiabilidad y seguridad, privacidad y seguridad, inclusión, transparencia y responsabilidad.
</details>

<details><summary><b>3. ¿Se usan tus datos de trabajo para entrenar el modelo?</b></summary>

No. Los datos de la organización no se usan para entrenar los modelos base.
</details>

<details><summary><b>4. ¿Qué es la inyección de instrucciones (*prompt injection*)?</b></summary>

Instrucciones maliciosas ocultas en la entrada del usuario o en contenido externo que engañan al sistema para que ignore sus reglas y ejecute acciones no deseadas.
</details>

<details><summary><b>5. ¿Cuál es la ecuación de Microsoft 365 Copilot?</b></summary>

`Aplicaciones de Microsoft 365 + LLM + Microsoft Graph = Microsoft 365 Copilot`
</details>

<details><summary><b>6. ¿Qué aporta Microsoft Graph?</b></summary>

Acceso al contexto de tu organización —correos, documentos, calendarios y chats— **respetando tus permisos**.
</details>

<details><summary><b>7. ¿Por qué Copilot entrega citas?</b></summary>

Por el principio de **transparencia**: permiten verificar que la respuesta se fundamentó en documentos reales.
</details>

---

## Módulo 2 — Copilot Chat, prompts y agentes

<details><summary><b>8. ¿Cuáles son los cuatro elementos de un buen prompt?</b></summary>

**Contexto**, **objetivo**, **origen** y **expectativas**.
</details>

<details><summary><b>9. ¿Para qué sirven `/`, `#` y `@`?</b></summary>

`/` referencia una persona, archivo o ubicación. `#` referencia un tema, reunión o evento. `@` invoca un agente.
</details>

<details><summary><b>10. Diferencia entre modo Trabajo y modo Web</b></summary>

**Trabajo** se fundamenta en datos de la organización vía Microsoft Graph y requiere licencia de Microsoft 365 Copilot. **Web** se fundamenta en datos públicos vía el índice de Bing y está disponible para todos.
</details>

<details><summary><b>11. ¿Cuántos avisos programados puedes tener y con qué frecuencia corren?</b></summary>

Máximo **10** mensajes programados, **una ejecución al día**, con un total de **15 ejecuciones** sobre datos de trabajo.
</details>

<details><summary><b>12. ¿Se puede editar un prompt guardado en su lugar?</b></summary>

No. Debes ejecutarlo o copiarlo, modificarlo en el chat, guardarlo como uno nuevo y eliminar el original.
</details>

<details><summary><b>13. ¿Cuál es el límite de los agentes Investigador y Analista?</b></summary>

**25 consultas combinadas al mes** entre ambos.
</details>

<details><summary><b>14. ¿A cuántos orígenes de conocimiento puede conectarse un agente personalizado?</b></summary>

Hasta **20**.
</details>

<details><summary><b>15. ¿Qué capacidades opcionales puede tener un agente?</b></summary>

**Intérprete de código** (ejecuta Python) y **creador de imágenes**.
</details>

<details><summary><b>16. ¿Se requiere aprobación del administrador para compartir un agente dentro de la organización?</b></summary>

No.
</details>

<details><summary><b>17. ¿Qué pasa si eliminas tu historial de conversaciones?</b></summary>

No se puede deshacer, no afecta los informes de uso de la organización, y si compartiste el vínculo de una conversación, esa liga puede seguir siendo accesible.
</details>

<details><summary><b>18. ¿Qué diferencia hay entre Copilot Chat y Búsqueda de Copilot?</b></summary>

Chat está centrado en **crear y razonar**; Búsqueda, en **descubrir y localizar** información usando Microsoft Graph.
</details>

---

## Módulo 3 — Redactar y refinar contenido

<details><summary><b>19. ¿Cómo referencias un documento de Word desde PowerPoint?</b></summary>

Con `/` seguido del nombre del archivo, por ejemplo `/InformeQ3.docx`. También puedes pegar el contenido directamente.
</details>

<details><summary><b>20. ¿En qué se diferencia el agente Investigador de Copilot Chat estándar?</b></summary>

Chat está optimizado para **redacción y edición**; el Investigador, para **detección, síntesis y generación de información**, con investigación multipaso y citas.
</details>

<details><summary><b>21. ¿Qué hace el Investigador antes de entregar el informe?</b></summary>

Puede **hacer preguntas aclaratorias** para refinar el encargo.
</details>

<details><summary><b>22. ¿Qué dos tipos de datos puedes elegir al redactar en Word?</b></summary>

Datos **basados en trabajo** (Microsoft 365) y datos **basados en web** (Bing).
</details>

---

## Módulo 4 — Datos y visualización

<details><summary><b>23. ¿Qué requisito tiene Copilot en Excel sobre los archivos?</b></summary>

El archivo debe estar guardado en **OneDrive** (o SharePoint) y los datos deben estar en formato de **tabla o rango admitido**.
</details>

<details><summary><b>24. ¿Cómo importas datos de la web dentro de Excel con Copilot?</b></summary>

Panel de Copilot Chat → icono de **globo** → elegir contenido conectado a la web → pedir los datos → **Insertar en nueva hoja**.
</details>

<details><summary><b>25. ¿Qué tipos de archivo acepta el agente Analista?</b></summary>

Excel, CSV, JSON, .txt, .doc y .pdf.
</details>

<details><summary><b>26. ¿Qué distingue al agente Analista de Copilot Chat?</b></summary>

Está optimizado para análisis de datos, visualización y generación de información, con **razonamiento de cadena de pensamiento**.
</details>

<details><summary><b>27. ¿Copilot puede explicar una fórmula existente?</b></summary>

Sí. Genera fórmulas y también las explica en lenguaje sencillo.
</details>

---

## Módulo 5 — Reuniones y colaboración

<details><summary><b>28. ¿Qué necesita Copilot para dar información completa de una reunión de Teams?</b></summary>

**Transcripción.** Sin ella se limita a los datos del chat.
</details>

<details><summary><b>29. ¿Qué opciones hay al habilitar Copilot en una reunión?</b></summary>

**Durante y después de la reunión** (requiere transcripción) o **solo durante la reunión** (usa voz a texto sin guardar transcripción).
</details>

<details><summary><b>30. ¿Cuántas referencias usa realmente un cuaderno para fundamentar?</b></summary>

Puedes agregar más de 20, pero **solo se usan las primeras 20**.
</details>

<details><summary><b>31. ¿Qué tipos de archivo admiten los cuadernos?</b></summary>

.docx, .pptx, .xlsx, .pdf, .loop y OneNote. **Los vínculos web no se soportan.**
</details>

<details><summary><b>32. ¿Qué pasa con las carpetas locales referenciadas en un cuaderno?</b></summary>

El cuaderno **no reconoce cambios** posteriores: se queda con el contenido original. En SharePoint sí reconoce las actualizaciones.
</details>

<details><summary><b>33. ¿Sobre qué tecnología están construidas las Páginas de Copilot?</b></summary>

**Microsoft Loop**.
</details>

<details><summary><b>34. ¿Cuáles son las dos formas de compartir una página?</b></summary>

**Vínculo de página** (abre la página en Loop) y **copiar el componente** (se pega como componente Loop y se actualiza en tiempo real).
</details>

<details><summary><b>35. ¿Cuánto tiempo se guardan las páginas?</b></summary>

Indefinidamente, a menos que las elimines manualmente.
</details>

---

## Módulo 6 — Escenarios

<details><summary><b>36. ¿Cuál es la idea central del módulo 6?</b></summary>

Que **no hay una única forma correcta** de usar Copilot: hay escenarios, restricciones y criterio.
</details>

<details><summary><b>37. En el escenario del resumen ejecutivo, ¿en qué orden se recopila la información?</b></summary>

Primero lo **interno** (correos, chats, notas, documentos de SharePoint y OneDrive), después la **validación externa**, y al final la redacción en Word.
</details>

<details><summary><b>38. En el escenario del informe semanal, ¿qué hace que el resumen de Outlook salga incompleto?</b></summary>

Correos archivados o en carpetas fuera del alcance de Copilot. Se valida con filtros de búsqueda manuales.
</details>

---

## Trampas frecuentes

| Suena parecido | Pero |
|---|---|
| **Copilot Chat** vs **Copilot en la app** | Chat trabaja entre aplicaciones; el de la app, dentro de su contexto |
| **Investigador** vs **Analista** | Investigador = información y síntesis con citas; Analista = datos, cálculos y visuales |
| **Páginas** vs **Cuadernos** | Páginas = producir contenido colaborativo; Cuadernos = consultar un conjunto de fuentes |
| **Modo Trabajo** vs **Modo Web** | Graph vs Bing; licencia vs sin licencia |
| **Guardar** un prompt vs **Programar** un prompt | Guardar lo deja disponible; programar lo ejecuta solo |
| **10** avisos programados vs **20** referencias vs **25** consultas de agentes | Tres límites distintos que se confunden entre sí |
