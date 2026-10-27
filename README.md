# Estudio UNED

App web de estudio y repaso del Grado en Filosofía (UNED, curso 2026/27):
Introducción al Pensamiento Científico (IPC), Antropología Social I (AS1) y Antropología Social II (AS2).

- Portada con las tres asignaturas: porcentaje de lectura y de repaso, ritmo frente al plan
  («al día», «3 por detrás»…) y la siguiente lectura, que se marca con un toque.
- Cuenta atrás de exámenes y entregas, aviso de temas atrasados y gráfico de lo marcado cada semana.
- Dos fases por asignatura: **Lectura** y **Repaso** (segunda vuelta), cada una con su progreso.
- Fechas editables: exámenes y entregas (botón del calendario) y fechas objetivo de lectura y repaso de cada tema (Editar).
- **Avisos**: genera un archivo de calendario (.ics) con alarmas para el Calendario del iPhone.
- Cada asignatura tiene sus temas (agrupables por bloques) y, dentro, lecturas y tareas.
- Cada lectura o tarea lleva una categoría (Manual, Lectura, Material, Vídeo, Test, Entrega…), editable en Ajustes, y se puede filtrar por ella.
- El porcentaje se actualiza al marcar cada elemento como hecho.
- Modo **Editar** para añadir, renombrar, mover o borrar temas y lecturas.
- Funciona sin conexión y se instala en el iPhone como una app.

## Instalar en el iPhone

1. Abre la web de la app en **Safari**.
2. Botón **Compartir** → **Añadir a pantalla de inicio**.

## Avisos

iOS no permite que una web programe notificaciones sin un servidor propio, así que los avisos se delegan
en el Calendario del iPhone: **Fechas → Avisos en el iPhone → Crear archivo de avisos → Guardar en Archivos**,
y desde la app Archivos, abrir `avisos-estudio.ics` → **Añadir todo**. Si cambian las fechas, se vuelve a generar.

## Contenido y actualizaciones

Las asignaturas, temas, lecturas, fechas objetivo (`due`, `revDue`), categorías (con `review` si entran en el repaso)
y fechas clave (`milestones`) están en **`content.json`**. Cada tema y cada lectura tiene un `id` fijo
(por ejemplo `as1-t03-02`) que no debe cambiarse nunca: es lo que une la lectura con lo marcado en el iPhone.

Para publicar cambios de contenido:

1. Edita `content.json` (añadir, renombrar, cambiar categoría o nota, quitar).
2. Sube el número de **`contentVersion`** (1 → 2…).
3. Al abrir la app aparece el aviso **«Contenido nuevo disponible» → Actualizar**
   (o en **Ajustes → Buscar actualizaciones**).

Al actualizar, la app:
- añade las lecturas y temas nuevos en su sitio;
- actualiza títulos, categorías, notas y fechas, **salvo lo que hayas editado tú** en la app;
- retira lo que ya no esté en `content.json`, **salvo lo que esté marcado como hecho o editado**;
- no vuelve a añadir lo que hayas borrado tú;
- **nunca toca lo marcado como leído o repasado** ni tus lecturas o fechas propias.

## Datos

El progreso se guarda **solo en el dispositivo** (almacenamiento local del navegador), no en este repositorio.
En **Ajustes → Exportar** puedes guardar una copia de seguridad en JSON y recuperarla con **Importar**.

Todo está en `index.html`, sin dependencias externas.
