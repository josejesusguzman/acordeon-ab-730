# Práctica 2: Automatiza tu lunes con avisos programados
**Objetivo:** Configurar, administrar y compartir prompts guardados y programados.

> [!IMPORTANT]
> Requiere licencia de Microsoft 365 Copilot y que tu organización tenga habilitadas las experiencias conectadas opcionales. Límites: **10 mensajes programados**, una ejecución al día, **15 ejecuciones** sobre datos de trabajo.

## Paso a Paso:

1. **Diseña el prompt del lunes.** En Copilot Chat, escribe y ejecuta:
   ```
   Resume los correos sin leer de los últimos tres días agrupados por proyecto.
   Marca con 🔴 los que esperan respuesta mía y con 🟡 los informativos.
   Termina con las tres cosas que debería atender hoy.
   ```

2. **Verifica que la salida sirva.** Si no, refínalo antes de programarlo: un prompt malo programado es ruido semanal automatizado.

3. **Prográmalo.** Pasa el puntero sobre el texto de tu prompt → **Programar este mensaje** → elige *Diariamente a las 8:00 a.m.* o *Semanalmente los lunes* → **Guardar**.

4. **Adminístralo.** Ve al menú de tres puntos `...` → **Avisos programados**. Practica las tres acciones:
   - **Ejecutar ahora** (para no esperar al lunes).
   - **Desactivar** (temporalmente).
   - **Eliminar**.

   Observa que los programados aparecen en **negrita** dentro de Conversaciones.

5. **Crea un segundo programado distinto.** Por ejemplo, viernes a las 4:00 p.m.:
   ```
   Revisa mi calendario y mis correos de esta semana y redacta un resumen de
   cierre: qué se cerró, qué quedó pendiente y qué se movió a la próxima semana.
   ```

6. **Comparte un prompt con tu equipo.** Abre la **Galería de consultas → Sus consultas** → icono **Compartir** → elige el equipo → **Compartir**. Verifica que aparezca en la pestaña **Equipo**.

7. **Hazlo reutilizable con marcadores de posición:**
   ```
   Resume el avance del proyecto [NOMBRE] para [AUDIENCIA] con corte al [FECHA].
   ```

8. **Documenta tus límites.** Anota cuántos programados llevas de los 10 disponibles y con qué frecuencia corre cada uno.

## Qué debiste aprender

- Programar un prompt convierte una tarea recurrente en un entregable que te espera.
- Los prompts guardados **no se editan en su lugar**: se ejecutan, se modifican en el chat y se guardan como nuevos (y conviene borrar el viejo).
- Compartir prompts es la forma más barata de estandarizar la calidad de un equipo.
