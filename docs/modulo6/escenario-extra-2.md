# Escenario de uso extra 2: Tickets de soporte y voz del cliente

**Personaje:** Marco, coordinador de mesa de servicio.
**Situación:** cada semana entran alrededor de 400 tickets. Marco sabe que hay patrones —problemas que se repiten, clientes que escalan siempre, un producto que genera más carga que los demás— pero nunca ha tenido tiempo de demostrarlo con datos. El viernes tiene comité de operaciones y quiere llegar con una propuesta, no con una queja.

**Lo que tiene:**
- Una exportación en CSV de los tickets del último trimestre (folio, fecha, cliente, categoría, descripción, tiempo de resolución, satisfacción).
- Chats de Teams del equipo de soporte.
- Correos de escalamiento de los clientes más ruidosos.

---

## Flujo de trabajo 1 — Entender el volumen (agente Analista)

### Paso 1: Panorama
Copilot Chat → **Agentes** → **Analista** → adjunta el CSV.
```
Analiza estos tickets de soporte del último trimestre. Dame el panorama: volumen
por categoría, tiempo promedio de resolución por categoría, y las tres categorías
que consumen más tiempo total del equipo.
```

### Paso 2: Encontrar lo que duele
```
¿Qué categorías tienen el peor tiempo de resolución en relación con su volumen?
Visualiza el crecimiento de tickets por categoría a lo largo del trimestre.
```

### Paso 3: El prompt que cambia la conversación
```
Si pudiera eliminar la causa raíz de una sola categoría de tickets, ¿cuál
liberaría más horas del equipo? Muestra el cálculo.
```

> [!TIP]
> Pedir el cálculo es lo que convierte un dato en un argumento. En el comité te van a preguntar exactamente eso.

---

## Flujo de trabajo 2 — Entender el contenido (voz del cliente)

### Paso 4: Temas en el texto libre
```
Revisa la columna de descripción e identifica los temas principales que reportan
los clientes. Agrúpalos y dime cuántos tickets caen en cada tema. Señala los
temas que NO están bien representados por la categoría asignada.
```

Ese último matiz es oro: casi siempre la taxonomía de categorías está desactualizada respecto a lo que la gente realmente reporta.

### Paso 5: Contrastar con el equipo
En Copilot Chat, modo Trabajo:
```
Revisa los chats de Teams del equipo de soporte del último trimestre. ¿Qué
problemas mencionan con más frecuencia que NO aparecen reflejados en los tickets?
```

### Paso 6: Escalamientos
```
Resume los correos de escalamiento de los últimos tres meses. ¿Qué tienen en
común los casos que escalaron? ¿Se pudieron haber prevenido según lo que dicen
los tickets previos de esos clientes?
```

---

## Flujo de trabajo 3 — Convertirlo en propuesta

### Paso 7: El cuaderno del proyecto
Crea un **cuaderno** llamado "Comité de operaciones — propuesta soporte" y agrega como referencias el análisis del Analista, el resumen de escalamientos y el documento de procesos actual. Luego pregunta:
```
¿Qué contradicciones hay entre nuestro procedimiento documentado y lo que
realmente está pasando según los tickets y los chats del equipo?
```

### Paso 8: La presentación
En PowerPoint:
```
Crea seis diapositivas para un comité de operaciones: situación actual con
números, las tres causas raíz principales, la propuesta, el costo estimado, el
impacto esperado en horas liberadas y la decisión que pido hoy.
```

### Paso 9: Anticipar la resistencia
```
Actúa como el director de operaciones. Dame las cinco objeciones más probables a
esta propuesta y qué evidencia pedirías para cada una.
```

### Paso 10: Un agente para el equipo
Con lo aprendido, crea un **agente personalizado** de primer nivel:
```
QUIÉN ERES: asistente de primer nivel de la mesa de servicio de [empresa].
QUÉ HACES: cuando alguien describe un problema, identificas la categoría, propones
los pasos de diagnóstico de nuestro procedimiento documentado y redactas la
respuesta al cliente.
CÓMO RESPONDES: pasos numerados, lenguaje sencillo, sin tecnicismos hacia el
cliente. Si el problema no está en el procedimiento documentado, dilo y sugiere
escalar. Nunca prometas tiempos de resolución.
```
Conecta como conocimiento el procedimiento de SharePoint y la base de casos resueltos.

---

## Dónde está la línea humana

| Copilot sí | Humano siempre |
|---|---|
| Clasificar y agrupar tickets | Decidir la taxonomía oficial |
| Detectar patrones y calcular impacto | Validar la causa raíz con el equipo técnico |
| Redactar respuestas estándar | Responder a un cliente molesto |
| Proponer la reestructura del proceso | Aprobarla y ejecutarla |

> [!WARNING]
> Cuidado con los datos personales de los clientes en las descripciones de los tickets. Antes de subir una exportación completa, anonimiza o confirma que la política de tu organización lo permite.

## Preguntas de reflexión

1. ¿Qué pasa con la calidad del análisis si la categorización original de los tickets está mal hecha?
2. ¿Cómo mides que la propuesta funcionó: menos tickets, o los mismos tickets resueltos más rápido?
3. Si un agente de primer nivel contesta el 40% de los tickets, ¿qué debería hacer el equipo con ese tiempo?
