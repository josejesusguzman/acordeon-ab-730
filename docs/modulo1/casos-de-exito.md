# Casos de uso de éxito y ejemplos reales

Los casos que siguen están documentados públicamente por Microsoft. No son ejemplos inventados para el curso: son organizaciones con nombre y apellido que ya operan con estas herramientas.

> [!NOTE]
> Cuando leas cualquier caso de éxito —de Microsoft o de quien sea— busca tres cosas: **qué problema tenían**, **qué cambió en el proceso** y **cómo lo midieron**. Si falta la tercera, es marketing, no un caso.

## 1. Casos documentados por Microsoft

| Organización | País / sector | Qué resolvieron |
|---|---|---|
| **Grupo Bimbo** | México · Alimentos | Estandarizó sus procesos de auditoría global con agentes de IA |
| **Tiendas CUADRA** | México · Retail | Mejoró tiempos de respuesta y habilitó el descubrimiento de productos con IA |
| **A1 Inteligência em Viagens** | Brasil · Turismo corporativo | Aumentó la eficiencia del equipo y la experiencia del cliente |
| **ABN AMRO Bank** | Países Bajos · Banca | Mejoró las interacciones con clientes y empleados |
| **Rabobank** | Países Bajos · Banca | Servicio al cliente con un agente habilitado para texto y voz |
| **Ciudad de Montreal** | Canadá · Gobierno | Mejoró el acceso a información pública y la conexión con la ciudadanía |
| **Singapore Civil Defence Force** | Singapur · Servicios de emergencia | Automatizó procesos manuales con ahorros millonarios |
| **T-Mobile** | EE. UU. · Telecomunicaciones | Dio a sus representantes de servicio información de dispositivos enriquecida |
| **Nexi Group** | Italia · Pagos | Redujo la carga del centro de contacto |
| **La Trobe University** | Australia · Educación | Mejoró la productividad académica y los servicios de apoyo |

Fuente: [Casos de adopción de Copilot Studio — Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/adoption-case-studies)

## 2. Los patrones que se repiten

Si revisas suficientes casos, siempre aparecen los mismos cuatro patrones. Reconocerlos te sirve más que memorizar nombres de empresas:

### Patrón A — El cuello de botella documental
> *"Tenemos la información, pero está regada en mil documentos y nadie la encuentra a tiempo."*

Aparece en auditoría, cumplimiento normativo, legal y soporte técnico. La IA no genera información nueva: la vuelve **localizable y sintetizable**. Es el patrón con el retorno más rápido y más fácil de medir (tiempo de búsqueda antes vs. después).

### Patrón B — La primera línea de atención
> *"El 70% de las preguntas que recibe el centro de contacto son las mismas veinte preguntas."*

Un agente resuelve lo repetitivo y escala a un humano lo que no. El indicador no es "cuántas preguntas contestó el bot", es **cuántas conversaciones humanas se dedicaron a casos complejos**.

### Patrón C — El primer borrador
> *"Mi gente no es lenta escribiendo; es lenta arrancando."*

Propuestas, informes, minutas, comunicados. La ganancia está en el arranque, y por eso es el patrón más fácil de adoptar y el más difícil de medir con precisión.

### Patrón D — El análisis que nadie hacía
> *"Esos datos siempre estuvieron ahí, pero nadie tenía tiempo de cruzarlos."*

No sustituye a un analista: hace que valga la pena hacer análisis que antes no justificaban el esfuerzo.

## 3. Por qué fracasan las implementaciones

Los casos de éxito se publican; los fracasos, no. Estos son los tropiezos más comunes:

1. **Comprar licencias sin rediseñar el proceso.** Si el flujo de trabajo sigue igual, la herramienta solo agrega un paso.
2. **No entrenar en prompts.** Es la diferencia entre una herramienta que la gente usa dos semanas y una que se vuelve costumbre.
3. **Datos desordenados.** Copilot se fundamenta en lo que hay en Microsoft 365. Si los documentos están mal nombrados, duplicados y sin permisos claros, las respuestas heredan ese desorden.
4. **Medir lo que no importa.** "Número de prompts enviados" no es un resultado de negocio. "Horas de cierre mensual" sí lo es.
5. **Saltarse la gobernanza.** Un piloto sin reglas de datos se convierte en un problema de cumplimiento antes que en un caso de éxito.

## 4. Cómo construir tu propio caso

Una plantilla de cuatro renglones que puedes llenar hoy:

```
Proceso:      __________________________  (uno solo, concreto)
Antes:        ____ horas / ____ personas / ____ días de ciclo
Intervención: qué parte del proceso pasa a Copilot y cuál sigue siendo humana
Después:      la misma métrica, medida a las 4 y a las 12 semanas
```

> [!TIP]
> Elige un proceso aburrido, frecuente y medible. Los pilotos que empiezan con lo más vistoso casi siempre mueren en la demo; los que empiezan con lo más repetitivo terminan en producción.
