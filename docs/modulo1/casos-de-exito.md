# Casos de uso de éxito y ejemplos reales

Todos los casos de esta página están documentados públicamente por Microsoft, con nombre de la organización, nombre y cargo de las personas que hablan, y cifras publicadas. No son ejemplos inventados para el curso.

> [!IMPORTANT]
> **Cómo leer un caso de éxito sin tragártelo entero.** Busca siempre cuatro cosas:
> 1. **Qué problema tenían** — descrito en términos de proceso, no de tecnología.
> 2. **Qué construyeron** — y con qué piezas, para saber si tú puedes replicarlo.
> 3. **Cómo lo midieron** — la métrica y el antes/después. Si no está, es marketing.
> 4. **Qué siguió siendo humano** — todos los casos serios lo dicen. Los que no lo dicen, mienten por omisión.

---

# Parte 1 — Casos con Microsoft 365 Copilot

Estos son los más cercanos a lo que evalúa el AB-730: gente de negocio usando Copilot dentro de sus aplicaciones de siempre.

## 1.1 Grupo Bimbo — México · Alimentos

**El caso más útil para este curso**, porque es mexicano, es un proceso aburrido y medible, y combina Microsoft 365 Copilot con agentes.

### El problema

El equipo de **auditoría interna global** de Grupo Bimbo son más de **100 auditores repartidos por el mundo**. Su trabajo depende de metodologías, plantillas y estándares que viven en SharePoint. Cuatro dolores concretos:

- **Búsqueda manual en SharePoint.** Los auditores no lograban confirmar rápido si la plantilla que estaban usando era la versión aprobada más reciente. Cuando descubrían tarde que no lo era, había retrabajo.
- **Un equipo de calidad convertido en cuello de botella.** El equipo de QA era pequeño y debía responder todas las dudas de metodología. Con auditores en varias zonas horarias, una pregunta podía tardar horas o días en resolverse.
- **Trabajo manual pesado.** Armar la **matriz de riesgo y control** de una auditoría tomaba **hasta 2 días**.
- **Inconsistencia entre regiones.** Cada región interpretaba las guías a su manera, con el riesgo de cumplimiento que eso implica en una empresa global.

### La solución

Dos agentes construidos en **Copilot Studio**, entregados a los auditores **dentro de Microsoft 365 Copilot y Teams**, conectados directamente a la documentación de SharePoint:

| Agente | Fase de auditoría | Qué hace |
|---|---|---|
| **Comatrix** | Planeación | Genera la matriz inicial de riesgo y control a partir de los procedimientos globales aprobados. El auditor la revisa y la ajusta al alcance específico |
| **Audit Assist** | Ejecución y reporte | Responde preguntas de metodología en lenguaje natural, recupera plantillas aprobadas y ayuda a estructurar los hallazgos según el estándar de reporte |

Tres decisiones de diseño que explican por qué funcionó:

1. **SharePoint como única fuente de verdad, sin base de conocimiento paralela.** Cuando el equipo de calidad actualiza un procedimiento, el agente usa la versión nueva automáticamente.
2. **Orquestación determinística en Audit Assist.** En auditoría no se vale improvisar: eligieron un comportamiento estricto y predecible sobre uno creativo.
3. **Iteración larga sobre el *system prompt*.** Ahí definieron cómo se recupera, se estructura y se presenta la información.

El proyecto nació de un **hackathon interno** donde auditores de distintas regiones detectaron el problema común. Esos mismos auditores fueron los usuarios de prueba durante el desarrollo, y luego los *champions* de la adopción.

### Los resultados

| Métrica | Antes | Después |
|---|---|---|
| Fase de planeación de la auditoría | — | **~20% menos tiempo** |
| Matriz de riesgo y control | ~2 días | **menos de medio día** (≈75% menos) |
| Adopción entre auditores | — | **50–60%** activos a principios de 2026 |
| Tiempo de entrega de la solución | ~6 meses | **1–2 meses** |

> "Si un auditor tiene una pregunta fuera del horario laboral, ya no tiene que esperar hasta el día siguiente. Puede preguntarle a Audit Assist y obtener la respuesta de inmediato."
> — **Eduardo Arenas**, Data Analyst, Grupo Bimbo

> "Lo que más nos importaba era lo fácil que era conectar nuestros agentes directamente a nuestra documentación de SharePoint. Cada vez que nuestro equipo de calidad actualiza un procedimiento o plantilla, el agente usa automáticamente la versión más reciente. Ya no tenemos que mantener una base de conocimientos separada."
> — **Mauricio Imenez**, Director of Data Analytics and AI, Global Internal Audit, Grupo Bimbo

### La lección

El valor no vino de un modelo más inteligente: vino de **conectar el agente al repositorio que ya era la fuente oficial**. Y el equipo de QA no desapareció — dejó de contestar preguntas repetidas para dedicarse a mejorar la metodología y a los casos complejos. Ese traslado de trabajo, no la desaparición de trabajo, es el resultado real.

Fuentes: [Caso de estudio en Microsoft Learn](https://learn.microsoft.com/en-us/power-platform/guidance/case-studies/grupo-bimbo-global-audit) · [Historia de cliente de Microsoft](https://www.microsoft.com/en/customers/story/26762-grupo-bimbo-microsoft-365-copilot)

---

## 1.2 Vodafone — Reino Unido / global · Telecomunicaciones

### El problema
Vodafone quería aterrizar su estrategia de transformación digital: liberar eficiencia interna y usar IA generativa para mejorar la experiencia del cliente. El reto no era técnico, era demostrar **beneficio de negocio medible** antes de comprometer miles de licencias.

### La solución
Un despliegue por fases, que es el patrón correcto:

1. **Piloto de 300 usuarios** en un programa de acceso temprano, con el objetivo explícito de evaluar el beneficio.
2. **Expansión a 68,000 usuarios** en los dos meses siguientes, una vez validado.

### Los resultados

- **4 horas ahorradas por usuario, por semana.**
- Casos de uso reportados por los propios equipos: revisión de documentos legales más rápida, redacción y análisis.

> "Copilot nos ha ayudado a revisar documentos más rápidamente."
> — **Hazel Butler**, equipo Legal, Vodafone

> "Evolucionó de escribir documentos a usarlo como un Copilot, como un experto al lado tuyo."
> — **Federico Frumento**, Senior Data Governance Manager, Vodafone

### La lección
Fíjate en la secuencia: **300 → medir → 68,000**. No al revés. Y ojo con la cifra de "4 horas por semana": es tiempo *percibido* como liberado, no dinero ahorrado. Sirve para justificar la licencia, no para prometer un recorte de plantilla.

Fuente: [Historia de cliente de Microsoft](https://www.microsoft.com/en/customers/story/19346-vodafone-microsoft-365-copilot)

---

## 1.3 Lumen Technologies — EE. UU. · Telecomunicaciones

### El problema
El equipo comercial gastaba horas investigando antes de cada contacto con un cliente. Ese tiempo salía directo del tiempo de venta. Y la empresa quería crecer **sin contratar más gente**.

### La solución
Copilot para ventas desplegado en varios miles de empleados, con tres tácticas de adopción que vale la pena copiar:

- **Adopción desde arriba** con *champions* designados por departamento.
- **Biblioteca de prompts** construida entre todos.
- **Acceso inmediato en vez de capacitación larga**: primero que lo usen, después la teoría.

### Los resultados

| Tarea | Antes | Después |
|---|---|---|
| Investigación previa a contactar un cliente | **4 horas** | **15 minutos** |

Y la traducción a dinero que hizo la propia empresa:

> "Devolver cuatro horas cada semana vale 50 millones de dólares en ingresos a lo largo de 12 meses."
> — **Ashley Haynes-Gaspar**, Chief Revenue Officer, Lumen Technologies

### La lección
Este es el mejor ejemplo de **cómo se convierte tiempo en dinero**: no dijeron "ahorramos horas", dijeron "estas horas, en manos de un vendedor, producen ingresos". Si vas a pedir presupuesto, esta es la conversión que tienes que saber hacer con tus propios números.

Fuente: [Historia de cliente de Microsoft](https://www.microsoft.com/en/customers/story/1771760434465986810-lumen-microsoft-copilot-telecommunications-en-united-states)

---

# Parte 2 — Casos con agentes de IA (Copilot Studio)

El AB-730 te presenta a los agentes en el Módulo 2. Estos casos muestran hasta dónde llega un agente bien construido, y también dónde está el trabajo real: los datos y el proceso, no el modelo.

## 2.1 Tiendas CUADRA — México · Retail de calzado y piel

### El problema

CUADRA es una marca mexicana premium de botas artesanales de piel, nacida en León. Vendía por teléfono, chat, correo, redes sociales y WhatsApp… **solo en horario de oficina**, y con un equipo de servicio al cliente de **cuatro personas** para todo el universo de clientes.

En temporadas pico —El Buen Fin y Navidad— simplemente no daban abasto. Y la mayoría de las preguntas eran siempre las mismas: dónde va mi pedido, hay talla, cuánto tarda, qué promociones hay.

> "Necesitábamos estar disponibles 24/7. Los clientes quieren saber dónde está su orden, si un producto está en stock o dónde pueden comprarlo, en cualquier momento. Antes, todo dependía de personas respondiendo teléfonos, correos o mensajes de chat."
> — **Diego Olvera**, Director de Tecnologías de la Información, Tiendas CUADRA

### La solución

Un **"Asistente CUADRA"** construido en dos fases, con el socio implementador Algoritmo:

**Fase 1 — Automatización operativa.** Un agente principal (*Atlas*) integrado con Shopify para estatus de pedido, disponibilidad y promociones, con escalamiento estructurado a Dynamics 365 Customer Service cuando hace falta un humano.

**Fase 2 — Inteligencia multimodal.** Un segundo agente que **reconoce imágenes de producto y sugiere outfits completos**, generando imágenes con Azure OpenAI y enviándolas por correo.

Piezas: Copilot Studio (conversación y orquestación), Power Automate (datos de Shopify, creación de casos, notificaciones a Teams), Dynamics 365 (gestión de casos), Dataverse (datos y contexto), y PDF/Excel/sitio web como fuentes de conocimiento.

Un detalle honesto que casi nadie cuenta: las primeras versiones **consumían demasiados créditos**. Lo resolvieron optimizando prompts, aplicando IA generativa solo donde aportaba, y acortando las respuestas.

### Los resultados

| Métrica | Antes | Después |
|---|---|---|
| Satisfacción del cliente (CSAT) | **3.9 / 5** | **5.0 / 5** |
| Calidad de las respuestas | **57%** | **95.5%** |
| Disponibilidad | Horario de oficina | **24/7** |
| Casos creados automáticamente | — | **Cientos por semana** |

> "El equipo de servicio al cliente tiene solo cuatro personas apoyando a todo un universo de clientes. La carga de trabajo ha disminuido significativamente con el asistente virtual."
> — **Carlos Damian**, Technology Manager, Tiendas CUADRA

### La lección

**El orden de las fases es la enseñanza.** Empezaron por lo aburrido y de alto volumen (¿dónde está mi pedido?) y solo después construyeron lo vistoso (recomendación de outfits por imagen). Si lo hubieran hecho al revés, habrían tenido una demo bonita y un equipo de cuatro personas igual de saturado.

Fuente: [Caso de estudio en Microsoft Learn](https://learn.microsoft.com/en-us/power-platform/guidance/case-studies/tiendas-cuadra-customer-service)

---

## 2.2 A1 Inteligência em Viagens — Brasil · Agencia de viajes corporativa

### El problema

Una agencia con más de 30 años, donde los agentes de viaje **buscaban manualmente en sitios de gobierno y llamaban a embajadas** para confirmar requisitos de visa, documentación y vacunas de cada destino. Durante la pandemia, con reglas cambiando cada semana, el proceso se volvió lento y propenso a errores, y la información que llegaba al cliente no siempre era completa ni confiable.

### La solución

Tres automatizaciones encadenadas, construidas por una empresa pequeña sin equipo de desarrollo:

1. **Coordinación de viaje automática.** Llega el PDF de confirmación de reserva a un buzón compartido → Power Automate extrae el destino → busca códigos de país y aeropuerto en Dataverse → consulta APIs de autoridades para los requisitos actuales → traduce del inglés al portugués con Microsoft Translator → envía el correo formateado al agente y al cliente.
2. **Facturación automática** con Azure AI Document Intelligence leyendo los PDF de factura.
3. **"Fifi", un agente con personalidad propia** en Copilot Studio, publicado en el sitio web y en Teams. Además de responder, **genera políticas de viaje completas**: hace una serie de preguntas al cliente, llena una plantilla de Word con Power Automate, la guarda en SharePoint y la envía por correo.

### Los resultados

- **55% de aumento en la eficiencia** de la coordinación de viajes.
- Información más completa, oportuna y confiable para el cliente.
- Tráfico alto en el blog de la empresa por las políticas de viaje generadas.

> "Power Platform cambió nuestro negocio de formas que nunca esperamos. Antes, nunca pensamos que fuera posible para nosotros crear software. Nos dio el poder de poner nuestras ideas a trabajar, fácil y de forma accesible para una empresa pequeña."
> — **Daniel Schaurich de Oliveira**, CEO, A1 Inteligência em Viagens

> "Crea una persona para el agente. Fifi no es solo un bot, es una colega de trabajo, y eso ayuda al equipo a aceptar y asimilar sus contribuciones más rápido."
> — **Daniel Schaurich de Oliveira**, CEO

### La lección

Dos cosas. Primera: **este es el caso que demuestra que no necesitas ser una corporación**. Segunda, y más interesante: darle personalidad al agente fue una decisión de **gestión del cambio**, no de tecnología. El equipo adoptó a "Fifi" más rápido de lo que habría adoptado a "el chatbot".

Fuente: [Caso de estudio en Microsoft Learn](https://learn.microsoft.com/en-us/power-platform/guidance/case-studies/boost-efficiency-experience-case-study)

---

## 2.3 Dunaway — EE. UU. · Ingeniería civil y planeación

**El caso con el número más brutal de toda esta lista.**

### El problema

Dunaway diseña y planea obra civil en **más de 100 ciudades de Texas**. Cada ciudad tiene su propio código regulatorio: documentos de entre 100 y 3,000 páginas, que se actualizan seguido y viven en sitios web distintos con formatos distintos.

Sus ingenieros gastaban **más de 10,000 horas al año** buscando, consultando e interpretando esos documentos a mano. Y el riesgo no era solo el tiempo: citar la versión equivocada de un código significa rediseños caros y meses de retraso.

### La solución

**ATLAS**, un agente en Copilot Studio dentro de Teams, con tres capas:

1. **Ingesta de conocimiento:** un Excel con el manifiesto de **más de 200 fuentes regulatorias**, Power Automate recolectando el contenido y SharePoint como fuente única de verdad, indexado en Azure AI Search.
2. **Experiencia de usuario:** conversación en Teams, respuestas estructuradas en *Adaptive Cards*, acceso filtrado por ciudad o condado.
3. **Capa de citas:** Azure Functions que mapea cada respuesta al **párrafo exacto del PDF** de origen. La precisión de las citas empezó en 70% y mejoró con esta capa.

### Los resultados

| Métrica | Resultado |
|---|---|
| Reducción del tiempo de investigación normativa | **90%** |
| Horas liberadas al año | **más de 10,000** |
| Reducción de tickets de TI (con su segundo agente, *DAVE*) | **80%** |

> "La velocidad para obtener la respuesta fue el objetivo de crear el bot. Antes, si un cliente hacía una pregunta en una reunión, nuestros ingenieros tenían que decir: 'lo investigamos y te avisamos'. Ahora pueden consultar al bot en la reunión y responder de inmediato."
> — **Brian Bowden**, Vice President of Technology, Dunaway

### La lección

Observa dónde pusieron el esfuerzo de ingeniería: **en las citas**. En un contexto regulado, una respuesta sin la referencia exacta al párrafo del código no sirve de nada, por más bien redactada que esté. Es exactamente el principio de **transparencia** de la IA responsable, convertido en requisito técnico.

Fuente: [Caso de estudio en Microsoft Learn](https://learn.microsoft.com/en-us/power-platform/guidance/case-studies/dunaway-streamlines-city-code-research)

---

## 2.4 Nexi Group — Italia · Pagos y servicios de tarjetas

### El problema

Nexi opera en **25 países** y representa cerca del **65% del consumo con tarjeta en Europa**. Miles de productos de tarjeta, cada uno con condiciones contractuales, servicios y requisitos regulatorios distintos. La documentación de soporte estaba **dispersa en múltiples fuentes**, así que los agentes humanos tenían que buscarla manualmente mientras el cliente esperaba. Resultado: tiempos de atención largos y respuestas inconsistentes.

### La solución

Un agente conversacional con tres componentes:

1. **Recuperación inteligente de documentos (RAG).** Documentos en Azure Storage, indexados en Azure AI Search **con metadatos personalizados** (nivel de tarjeta, reglas de elegibilidad) y estrategias de fragmentación a la medida.
2. **Integración segura con sistemas internos** vía Azure Functions, para ejecutar acciones reales: bloquear tarjeta, reemitir tarjeta, listar transacciones. Con Key Vault para secretos y Cosmos DB para bitácora y auditoría.
3. **Analítica extendida** hacia Power BI.

El detalle que más vale la pena copiar: **la sesión empieza sin autenticación** para información general, y **exige autenticarse en el momento en que la conversación requiere algo personal**. Después de autenticarse, el cliente con tarjeta Gold solo ve documentación de tarjeta Gold. Toda acción sobre sistemas internos exige autenticación previa.

### Los resultados

- **Más de 3,000 interacciones diarias** atendidas.
- **70% de satisfacción**.
- **Reducción significativa de escalamientos** a agente humano.
- Los equipos de negocio actualizan los mensajes del agente por su cuenta; TI mantiene control con roles de seguridad personalizados.

> "Al usar respuestas de IA generativa y habilitar el autoservicio, esta solución redujo significativamente las tasas de escalamiento. No solo mejoró nuestra reputación de marca en servicios digitales: también mejoró la experiencia de usuario mientras reducía costos operativos."
> — **Clemente Pescatore**, Global Head of Contact Center & RPA Factory, Nexi Group

### La lección

**El diseño de permisos es parte del diseño del agente.** Aquí no hay un agente que "sabe todo y decide qué contar": hay una recuperación que se filtra por los derechos reales del cliente autenticado. Es la misma idea que Copilot aplica con Microsoft Graph, llevada a un producto externo.

Fuente: [Caso de estudio en Microsoft Learn](https://learn.microsoft.com/en-us/power-platform/guidance/case-studies/nexi-revolutionizes-customer-support)

---

## 2.5 Rabobank — Países Bajos · Banca

### El problema

Tenían chatbot, pero mal montado: los sistemas de **chat y de voz se actualizaban por separado** aunque usaran la misma información, el mantenimiento dependía de proveedores externos, y cualquier cambio requería desarrolladores especializados. La consecuencia no era técnica sino de negocio: **no podían iterar rápido**.

> "Necesitábamos una plataforma flexible que pudiera integrarse con APIs externas, para transformar nuestro chatbot en un verdadero asistente financiero. Queríamos una sola plataforma conversacional para administrar todos los chatbots y optimizarla nosotros mismos."
> — **Chris den Arend**, Solution Architect, Rabobank

### La solución

Tres agentes en Copilot Studio: **uno de voz y dos de texto** (banca empresarial y clientes minoristas), sobre una arquitectura con Genesys Cloud (contacto y escalamiento), Azure Speech Services, Azure AI Search y Azure AI Foundry **dentro de su propia suscripción de Azure, por cumplimiento normativo**.

Dos prácticas destacables:

- Un proceso nocturno en Python que reindexa **más de 8,000 URLs** del sitio del banco, limpia los datos y reconstruye el índice de búsqueda. La base de conocimiento nunca envejece.
- **300 a 400 temas** por agente de texto, validados contra conversaciones reales anonimizadas con una herramienta propia de verificación de exactitud.

### Los resultados

| Métrica | Resultado |
|---|---|
| Llamadas atendidas al día | **20,000** |
| Chats atendidos al día | **7,000** |
| Chats resueltos **sin** escalar a humano | **62%** |
| Tiempo de construcción de los agentes de texto | **3 meses** |

Y el resultado organizacional: ahora pueden actualizar los agentes **sin ayuda externa**.

### La lección

La métrica que eligieron es la correcta: **62% de autoservicio**, no "cuántos mensajes contestó el bot". Y fíjate que el mayor beneficio no fue de atención al cliente, sino de **autonomía**: dejaron de depender de un proveedor para cambiar una respuesta.

Fuente: [Caso de estudio en Microsoft Learn](https://learn.microsoft.com/en-us/power-platform/guidance/case-studies/rabobank-conversational-banking)

---

## 2.6 Ciudad de Montreal — Canadá · Gobierno municipal

### El problema

Un sitio web con **más de 40,000 páginas**, **50,000 visitantes diarios** y **1.7 millones de ciudadanos** que no encontraban lo que buscaban. El centro de llamadas se saturaba con preguntas básicas —horarios de recolección de basura, pago de impuestos, retiro de nieve— y eso reducía su capacidad para atender emergencias reales.

### La solución

Un asistente virtual en Copilot Studio, con una decisión de arquitectura muy sensata:

> "Una razón clave por la que elegimos Copilot Studio fue la opción de combinar fácilmente respuestas predefinidas de un chatbot clásico con respuestas generadas por IA. Esta opción híbrida nos permitió lograr un nivel de precisión más alto que usando solo IA generativa."
> — **Mohamed Arhab**, Solution Architect, Departamento de TI, Ciudad de Montreal

Pero el trabajo pesado no estuvo en el agente. Estuvo en **arreglar el contenido**:

- Optimizaron `robots.txt` e indexación: pasaron de menos de 15,000 a **más de 45,000 documentos indexados en 3 meses** (lo triplicaron).
- Eliminaron contenido oculto en secciones colapsadas y lo convirtieron en HTML visible.
- Usaron **HTML semántico** (H1, H2) y formatos explícitos y legibles para la IA (por ejemplo, escribir los horarios línea por línea en vez de en una tabla ambigua).
- Crearon **entidades personalizadas** para código postal y para los 19 municipios, con sus sinónimos y variantes.

### Los resultados

- **90% de eficiencia** en las consultas ciudadanas atendidas con respuestas generativas.
- **85% de las conversaciones** resueltas solo con respuestas generativas conectadas al sitio web.
- Satisfacción de **más de 4 sobre 5**.
- Menos preguntas básicas en el centro de llamadas, y por lo tanto más capacidad para emergencias.

### La lección

**Este es el caso que hay que citar cuando alguien dice "solo enciendan la IA".** La mayor parte del proyecto fue higiene de contenido: hacer que la información existente fuera legible para una máquina. Es exactamente lo que le va a pasar a tu organización con SharePoint y OneDrive.

Fuente: [Caso de estudio en Microsoft Learn](https://learn.microsoft.com/en-us/power-platform/guidance/case-studies/city-montreal-citizen-engagement)

---

## 2.7 Singapore Civil Defence Force — Singapur · Servicios de emergencia

**El caso con el mejor retorno documentado de la lista.**

### El problema

Procesos manuales en una organización de emergencias: gestión de roles de turno, mantenimiento de vehículos, gestión de alimentos en una academia que sirve **más de 3,000 comidas diarias**. Los oficiales tenían que entrar a la intranet a buscar turnos disponibles y frecuentemente perdían la ventana para reservarlos. Para averías menores de vehículos dependían de proveedores externos.

Y sobre todo: los proyectos de TI tradicionales **tardaban de 2 a 3 años** en entregar una solución. Inaccesible para una organización de primera línea.

### La solución

Un equipo interno de **Digital Factory** (creado en 2023, en alianza con la agencia HTX) que construyó **8 aplicaciones** en Power Platform y Copilot Studio, entre ellas:

- **NEXA**, agente conversacional que da acceso a directrices y procedimientos operativos, con gamificación tipo quiz.
- **ADA**, que asigna bomberos a turnos cruzando habilidades y licencias de conducir.
- **DORA**, para roles de turno del personal no operativo, con intercambio de turnos.
- **ITA**, guías interactivas de diagnóstico que permiten resolver fallas sin llamar al proveedor.
- **FICA**, gestión de comidas en tiempo real, que además reduce desperdicio.

### Los resultados

| Métrica | Resultado |
|---|---|
| Valor de las soluciones entregadas | **~20 millones de USD** |
| Costo de desarrollo | **menos de 50,000 USD** |
| Retorno | **400:1 como mínimo** |
| Tiempo por proyecto | de **2–3 años** a **1–3 meses** |
| Alcance de NEXA | **6,000 oficiales** |
| Alcance de ADA + ITA | **2,100 operativos en 23 estaciones** |

Dato revelador: **FICA la desarrolló una sola persona en 3 meses.**

### La lección

El resultado no vino de la IA: vino de **cambiar quién construye el software**. Al poner la herramienta en manos de la gente que conoce el proceso, el ciclo de entrega pasó de años a semanas. La IA fue la última capa, no la primera.

Fuente: [Caso de estudio en Microsoft Learn](https://learn.microsoft.com/en-us/power-platform/guidance/case-studies/scdf-implements-digital-solutions)

---

## 2.8 T-Mobile — EE. UU. · Telecomunicaciones

### El problema

Los representantes de servicio necesitaban, en medio de una conversación con el cliente, información de promociones, descuentos, valores de equipo a cambio y especificaciones técnicas de dispositivos. Esa información estaba en sistemas internos **y** en los sitios de los fabricantes.

El proceso previo era un **reporte diario en PDF**, cada vez más largo y difícil de buscar, que los empleados terminaban **imprimiendo** para consultarlo rápido. Y para lo técnico, había que navegar a mano a los sitios de los fabricantes, cambiando de app en el iPad mientras el cliente esperaba.

### La solución

**PromoGenius**: una app de Power Apps con un agente de Copilot Studio dentro, disponible en los iPads de tienda y en línea para el call center.

- El agente se conecta a **más de 20 sitios de fabricantes** y recupera especificaciones automáticamente.
- Los datos de promociones se transforman cada noche con pipelines de Microsoft Fabric hacia Dataverse, desde Oracle, SAP y hojas de Excel.
- Usaron **Bing Custom Search** en lugar de conectar los sitios como fuente de conocimiento directa, porque así podían **excluir páginas de promociones vencidas** por cumplimiento regulatorio.
- Le instruyeron al agente formatear comparaciones de equipos en **tablas lado a lado**, para poder mostrárselas al cliente directamente.

### Los resultados

| Métrica | Resultado |
|---|---|
| Usuarios únicos | **más de 83,000** |
| Aperturas mensuales | **500,000** |
| Posición interna | **2ª app más usada** de T-Mobile |
| Tiempo de la primera versión | de **9–12 meses estimados** a **unas pocas semanas** |

Y el beneficio que importa: el representante **ya no abandona la conversación con el cliente** para ir a buscar un dato.

> "La diseñé intencionalmente para aprovechar las capacidades de IA generativa, buscando un enfoque más conversacional para obtener respuestas. Como resultado, la organización empezó a replantear cómo se puede consolidar la información."
> — **Brian Hodel**, Solution Architect and Developer, T-Mobile

### La lección

La restricción regulatoria **moldeó la arquitectura**: eligieron Bing Custom Search precisamente porque les permitía bloquear contenido vencido. Cuando alguien te pregunte "¿por qué no simplemente conectamos el sitio?", esta es la respuesta.

Fuente: [Caso de estudio en Microsoft Learn](https://learn.microsoft.com/en-us/power-platform/guidance/case-studies/tmobile-empowers-customer-service)

---

## 2.9 La Trobe University — Australia · Educación superior

### El problema

Personal académico y administrativo buscando información repartida entre RR. HH., Finanzas y TI, con **más de 10,000 artículos de base de conocimiento en ServiceNow** como repositorio principal. La gente gastaba "minutos valiosos navegando artículos" para encontrar una respuesta.

Además, el conector estándar de ServiceNow no era suficiente: solo devolvía fragmentos breves, no accedía a instrucciones paso a paso, y no soportaba enrutamiento por intención ni recuperación semántica.

### La solución

**Troby**, un agente en Teams con un RAG propio de bajo código:

- **Procesos nocturnos** que extraen de 10 a 30 preguntas de ejemplo por artículo para poblar una tabla de intenciones en Dataverse, y otro que limpia el HTML y guarda el contenido estructurado por categoría.
- **Clasificación con AI Builder**: si la confianza supera 0.80, enruta al tema correspondiente (TI, RR. HH., Finanzas).
- Respuestas generativas renderizadas en *Adaptive Cards* con enlaces.

### Los resultados

- **71% de las consultas resueltas** por el agente.
- **10,000+ artículos** integrados.
- Alternativa más barata que la plataforma de chatbot anterior.
- Retroalimentación de los usuarios que llevó a **corregir artículos de la base de conocimiento** — es decir, el agente mejoró la documentación original.

### La lección

Ese último punto es el más interesante y el que menos se comenta: **un buen agente expone la mala documentación**. Cuando la gente le pregunta al agente y la respuesta es mala, descubres qué artículo estaba mal escrito. Es un efecto secundario que vale casi tanto como el agente.

Fuente: [Caso de estudio en Microsoft Learn](https://learn.microsoft.com/en-us/power-platform/guidance/case-studies/latrobe-supercharges)

---

## 2.10 Otros casos del catálogo

Documentados por Microsoft, con menos detalle en esta página:

| Organización | País / sector | Qué resolvieron |
|---|---|---|
| [ABN AMRO Bank](https://learn.microsoft.com/en-us/power-platform/guidance/case-studies/abn-amro-enhances-ai) | Países Bajos · Banca | Interacciones con clientes y empleados con Copilot Studio y Azure |
| [Holland America Line](https://learn.microsoft.com/en-us/power-platform/guidance/case-studies/holland-america-customer-experience) | EE. UU. · Cruceros | Conserje virtual en su sitio web |
| [mobilezone](https://learn.microsoft.com/en-us/power-platform/guidance/case-studies/mobilezone-modernizes-service-delivery) | Suiza · Retail de telefonía | Modernización del servicio con Copilot Studio, Dynamics 365 y servidores MCP |
| [Signetic](https://learn.microsoft.com/en-us/power-platform/guidance/case-studies/signetic-transforms-healthcare) | Salud | Eficiencia de flujos de trabajo y atención al paciente |

---

# Parte 3 — Qué nos enseñan todos juntos

## 3.1 Tabla comparativa de resultados

| Organización | Métrica principal | Cifra |
|---|---|---|
| Dunaway | Tiempo de investigación normativa | **−90%** (10,000+ h/año) |
| Singapore Civil Defence Force | Retorno de inversión | **400:1** |
| Lumen | Investigación previa a venta | **4 h → 15 min** |
| Grupo Bimbo | Matriz de riesgo y control | **2 días → medio día** |
| Ciudad de Montreal | Consultas resueltas por el agente | **85–90%** |
| La Trobe University | Consultas resueltas | **71%** |
| Rabobank | Chats sin escalamiento | **62%** |
| A1 Inteligência em Viagens | Eficiencia en coordinación | **+55%** |
| Vodafone | Tiempo liberado por persona | **4 h/semana** |
| Tiendas CUADRA | Satisfacción del cliente | **3.9 → 5.0** |
| Nexi Group | Interacciones diarias | **3,000+**, 70% de satisfacción |
| T-Mobile | Adopción | **83,000 usuarios**, 500,000 aperturas/mes |

## 3.2 Los cuatro patrones que se repiten

Reconocer el patrón te sirve más que memorizar nombres de empresas. En el examen, y en tu trabajo.

### Patrón A — El cuello de botella documental
> *"Tenemos la información, pero está regada en mil documentos y nadie la encuentra a tiempo."*

**Casos:** Dunaway, Grupo Bimbo, Nexi, La Trobe, Montreal.

Es el patrón más común y el de retorno más rápido, porque el antes/después se mide fácil: tiempo de búsqueda. La IA no genera información nueva, la vuelve **localizable y sintetizable**. Requisito indispensable: una fuente de verdad ordenada y con permisos correctos.

### Patrón B — La primera línea de atención
> *"El 70% de las preguntas que llegan son las mismas veinte preguntas."*

**Casos:** Tiendas CUADRA, Rabobank, Nexi, Montreal, T-Mobile.

El indicador correcto **no** es "cuántas preguntas contestó el bot", es **qué porcentaje se resolvió sin escalar** (Rabobank: 62%) y **en qué se ocupó el tiempo humano liberado**.

### Patrón C — El primer borrador
> *"Mi gente no es lenta escribiendo; es lenta arrancando."*

**Casos:** Vodafone, Lumen, Grupo Bimbo (Comatrix).

Propuestas, informes, minutas, matrices. El más fácil de adoptar y el más difícil de medir con precisión, porque el ahorro es difuso. Por eso Lumen hizo bien en traducirlo a ingreso por vendedor en vez de dejarlo en "horas ahorradas".

### Patrón D — El proceso que nadie rediseñaba
> *"Siempre lo hemos hecho así porque cambiarlo tomaba dos años."*

**Casos:** Singapore Civil Defence Force, A1 Inteligência em Viagens.

El más subestimado. Aquí el valor no viene del modelo, viene de que **construir se volvió barato**, y por lo tanto se volvió razonable arreglar procesos que antes no justificaban un proyecto de TI.

## 3.3 Los seis denominadores comunes

Lo que hicieron **todos** los casos que funcionaron:

1. **Conectaron el agente a la fuente de verdad que ya existía**, en vez de crear una base de conocimiento paralela (Bimbo con SharePoint, Dunaway con sus 200 fuentes, La Trobe con ServiceNow).
2. **Arreglaron los datos antes que el modelo.** Montreal triplicó su indexación; Rabobank reindexa 8,000 URLs cada noche; T-Mobile transforma sus datos cada noche con Fabric.
3. **Empezaron por lo aburrido y de alto volumen**, y dejaron lo vistoso para la fase 2 (CUADRA es el ejemplo de manual).
4. **Involucraron a los usuarios reales desde el diseño.** Bimbo salió de un hackathon de auditores; T-Mobile diseñó la interfaz sentado con los representantes; Montreal dejó que el área de negocio administrara las entidades y frases de activación.
5. **Definieron qué se escala a un humano y cuándo.** Ninguno construyó un agente que decidiera solo.
6. **Midieron una métrica de negocio, no de uso.** Horas, escalamientos, ciclo de auditoría, satisfacción — nunca "número de prompts enviados".

## 3.4 Cómo leer estas cifras con sano escepticismo

Vas a usar estos casos para convencer a alguien. Antes, ten claro lo siguiente:

| La cifra dice | Lo que en realidad significa |
|---|---|
| "4 horas ahorradas por semana" | Tiempo **percibido** como liberado por el usuario, normalmente por encuesta. No es dinero ni plantilla. |
| "−90% en tiempo de investigación" | Sobre **esa tarea específica**, no sobre la jornada completa del ingeniero. |
| "ROI 400:1" | Compara el costo de desarrollo contra el **valor estimado** de las soluciones, no contra ingreso real cobrado. |
| "85% de consultas resueltas" | De las consultas que **entraron al agente**. No dice cuántas personas prefirieron llamar por teléfono. |
| "Satisfacción 5.0 / 5" | Muestra pequeña y autoseleccionada. Ve la tendencia, no el valor absoluto. |

Nada de esto invalida los casos. Solo significa que, cuando presentes tu propio piloto, **la cifra honesta te va a servir más que la impresionante**: la primera resiste una pregunta del director financiero, la segunda no.

## 3.5 Por qué fracasan las implementaciones

Los éxitos se publican; los fracasos, no. Estos son los tropiezos más comunes, y fíjate cómo cada uno es el reverso exacto de un denominador común de arriba:

1. **Comprar licencias sin rediseñar el proceso.** Si el flujo de trabajo sigue igual, la herramienta solo agrega un paso más.
2. **No capacitar en prompts.** Es la diferencia entre una herramienta que la gente usa dos semanas y una que se vuelve costumbre.
3. **Datos desordenados.** Copilot se fundamenta en lo que hay en Microsoft 365. Documentos mal nombrados, duplicados y sin permisos claros producen respuestas que heredan ese desorden.
4. **Medir lo que no importa.** "Número de prompts enviados" no es un resultado de negocio; "días de cierre mensual" sí.
5. **Saltarse la gobernanza.** Un piloto sin reglas de datos se vuelve un problema de cumplimiento antes que un caso de éxito.
6. **Empezar por el caso más vistoso.** Los pilotos que arrancan con la demo bonita mueren en la demo; los que arrancan con lo repetitivo llegan a producción.
7. **No definir quién mantiene la solución.** Un agente sin dueño queda obsoleto en un trimestre.

## 3.6 Cómo construir tu propio caso

### La plantilla mínima

```
PROCESO:      __________________________  (uno solo, concreto y aburrido)
FRECUENCIA:   ____ veces por semana / mes
ANTES:        ____ horas · ____ personas · ____ días de ciclo
INTERVENCIÓN: qué parte pasa a Copilot y qué parte sigue siendo humana
DESPUÉS:      la misma métrica, medida a las 4 y a las 12 semanas
RIESGO:       qué pasa si la IA se equivoca, y quién responde
```

### Las cinco preguntas antes de arrancar

1. ¿Este proceso se repite lo suficiente como para que el ahorro sea visible?
2. ¿La información que necesita **ya existe** en un lugar ordenado y con permisos correctos?
3. ¿Puedo medir el antes **hoy**, antes de tocar nada? (Si no, esa es la primera tarea.)
4. ¿Quién revisa la salida antes de que tenga efecto?
5. ¿Quién va a mantener esto dentro de seis meses?

### Cómo convertirlo en dinero, al estilo Lumen

```
Horas liberadas por persona por semana   ×
Número de personas                       ×
52 semanas                               =  horas al año

Horas al año × valor de una hora de esa persona en su actividad principal
```

Lo importante no es el número final: es **poder defender cada factor** cuando te pregunten de dónde salió.

> [!TIP]
> Elige un proceso aburrido, frecuente y medible. Y mide el "antes" **antes**. La razón número uno por la que un piloto exitoso no consigue presupuesto para escalar no es que haya fallado: es que nadie registró cómo estaban las cosas al inicio.

---

## Fuentes

- [Casos de adopción de Copilot Studio — Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/adoption-case-studies) — índice completo de casos.
- [Historias de clientes de Microsoft](https://www.microsoft.com/en/customers/) — buscador de casos por producto e industria.
