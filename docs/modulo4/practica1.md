# Práctica 1: De hoja cruda a decisión, con el agente Analista
**Objetivo:** Ejecutar un análisis iterativo completo y convertirlo en un entregable de negocio.

> [!IMPORTANT]
> Consume consultas de tu límite de **25 mensuales combinadas** con el agente Investigador. Diseña el análisis antes de empezar.

## Paso a Paso:

1. **Prepara el archivo.** Un Excel o CSV con datos reales (anonimizados) o el de práctica del tutorial. Formato de tabla, encabezados limpios.

2. **Abre el agente.** Copilot Chat → **Agentes** → **Analista** → icono **+** → adjunta el archivo.

3. **Consulta principal.** No preguntes "analiza esto": dile qué decisión estás tratando de tomar.
   ```
   Resalta las tendencias clave del rendimiento de ventas por región y trimestre.
   Me interesa decidir en qué región concentrar el presupuesto del próximo semestre.
   ```

4. **Itera con tres seguimientos**, uno a la vez:
   ```
   Identifica los productos de alto rendimiento según métricas de participación
   del cliente.
   ```
   ```
   Visualiza el crecimiento de ventas en los últimos cuatro trimestres.
   ```
   ```
   ¿Qué explicación alternativa podría tener la caída de la región con peor
   desempeño? Dime qué datos adicionales necesitaría para confirmarla.
   ```

   El tercer prompt es el importante: obliga al agente a exponer sus supuestos.

5. **Verifica manualmente.** Toma **dos** cifras del análisis y compruébalas en Excel con una fórmula. Anota si coinciden.

   | Cifra reportada por el agente | Cifra verificada por mí | ¿Coincide? |
   |---|---|---|
   | | | |
   | | | |

6. **Convierte el análisis en entregable:**
   ```
   Resume los resultados en tres viñetas para una diapositiva de liderazgo.
   ```
   ```
   Escribe un resumen ejecutivo de este informe.
   ```
   ```
   Redacta una actualización por correo que resuma estas conclusiones.
   ```

7. **Escribe tu recomendación en una sola frase.** Sin datos, sin matices: la decisión que tomarías. Ese es el único entregable que a dirección le interesa.

## Qué debiste aprender

- La calidad del análisis depende de que hayas nombrado **la decisión**, no solo los datos.
- El razonamiento de cadena de pensamiento es útil precisamente porque puedes auditarlo: pídele que exponga sus supuestos.
- Verificar dos cifras a mano toma tres minutos y es la diferencia entre presentar y quedar mal presentando.
