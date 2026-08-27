# Escenario de uso extra 1: Conciliación de facturas de proveedores

**Personaje:** Daniela, analista de cuentas por pagar.
**Situación:** cierre de mes. Llegan 180 facturas de proveedores por correo, en PDF, con formatos distintos. Daniela tiene que verificar que cada una corresponda a una orden de compra, detectar diferencias de monto y armar el reporte de excepciones antes del jueves. Hoy es martes.

**Lo que tiene:**
- Una bandeja de Outlook con las facturas adjuntas.
- Un Excel en OneDrive con las órdenes de compra abiertas.
- Un procedimiento de tres páginas en SharePoint que casi nadie lee.

---

## Flujo de trabajo 1 — Triaje desde Outlook

### Paso 1: Ordenar la bandeja
```
Revisa mis correos de la última semana con facturas adjuntas y dame una tabla con
proveedor, número de factura, monto, fecha y si menciona una orden de compra.
Marca los que no traigan número de orden.
```

### Paso 2: Detectar lo urgente
```
De esa lista, ¿cuáles tienen fecha de vencimiento en los próximos 10 días y
cuáles vienen de proveedores con los que hemos tenido diferencias antes según
mis correos?
```

> [!TIP]
> La segunda parte de ese prompt es la que ningún proceso manual hace: cruzar la factura de hoy con el historial de fricción del proveedor.

---

## Flujo de trabajo 2 — Conciliación en Excel

### Paso 3: Comparar contra órdenes de compra
Abre el Excel de órdenes de compra en OneDrive, pega la tabla de facturas en una hoja nueva y pide:
```
Compara la hoja "Facturas" contra la hoja "OrdenesCompra" usando el número de
orden. Genera una tabla de excepciones con: facturas sin orden, órdenes sin
factura, y diferencias de monto mayores a 1%. Ordena por monto de la diferencia,
de mayor a menor.
```

### Paso 4: Entender el patrón, no solo la lista
```
De las excepciones, ¿hay algún patrón por proveedor, por tipo de gasto o por
periodo? Dime qué tres causas podrían explicar la mayoría de las diferencias.
```

### Paso 5: Verificar a mano
Toma las tres excepciones de mayor monto y compruébalas tú. Si el cruce automático falló en una, falló en todas las de ese tipo.

---

## Flujo de trabajo 3 — El entregable

### Paso 6: Reporte para el jefe de área
```
Redacta un resumen ejecutivo del cierre de conciliación: total de facturas
procesadas, monto total, número de excepciones, monto en excepción y las tres
causas principales. Máximo 200 palabras. Termina con la decisión que necesito
de mi jefe.
```

### Paso 7: Correos a proveedores
```
Redacta un correo estándar para solicitar aclaración de diferencia de monto a un
proveedor. Tono cordial y firme, con marcadores de posición para [PROVEEDOR],
[FACTURA], [MONTO FACTURADO], [MONTO ESPERADO] y [ORDEN DE COMPRA].
```
Guárdalo como prompt reutilizable y compártelo con tu equipo desde la Galería de consultas.

### Paso 8: Automatizar el lunes
```
Cada lunes a las 8 a.m.: revisa los correos con facturas adjuntas recibidos la
semana anterior y dame la tabla de proveedor, factura, monto, fecha y orden de
compra, marcando los que no traigan orden.
```
Prográmalo (recuerda: máximo 10 avisos programados).

---

## Dónde está la línea humana

| Copilot sí | Humano siempre |
|---|---|
| Extraer y tabular datos de correos | Autorizar el pago |
| Cruzar dos listas y detectar diferencias | Decidir si una diferencia se acepta |
| Proponer causas de las excepciones | Confirmar la causa con el proveedor |
| Redactar los correos de aclaración | Revisar antes de enviarlos |
| Armar el reporte | Firmar el reporte |

> [!WARNING]
> Nunca automatices la **autorización** de un pago con base en una conciliación generada por IA. Automatiza la detección, no la decisión.

## Preguntas de reflexión

1. ¿Qué parte de este proceso tiene el mayor costo si la IA se equivoca?
2. ¿Los PDF de las facturas contienen datos personales o bancarios que no deban viajar en un prompt?
3. Si el proceso se automatiza, ¿en qué se ocupa el tiempo que se libera: en más facturas o en mejor análisis de proveedores?
