# Revisor USCI · Desaladora Coquimbo

Aplicación web para revisar los Informes de Criterio y Bases de Diseño (Fase 1, Rev. A) de la Concesión Planta Desaladora para la Región de Coquimbo, recorriendo los 65 documentos en el orden oficial de Tomos USCI. Versión del 06-11-2026.

## Fuentes

| Fuente | Ubicación |
|---|---|
| Registros de observaciones de la Inspección Fiscal (USCI N°1, 2, 3, 4, 6 y 7) | `DOCUMENTACION / G_PEPID`, archivos `01_` a `06_…_Rev A.xlsx` |
| Registro de observaciones de Medio Ambiente | `DOCUMENTACION / G_PEPID / 07_Criterios y Bases de Diseño_Materias Medioambientales_Rev A.xlsx` |
| Documentos Rev. A (PDF) | `DOCUMENTACION / A_LIBRO_CONSTRUCCION / FOLIO 67 / Adjuntos` (Tomo 1) y `FOLIO 68 / Adjuntos` (Tomos 2 a 6) |
| Revisión complementaria del especialista | BALI refundidas 21.11.25, DS de Adjudicación, Propuesta Técnica Sacyr Agua, vigencia normativa |

## Contenido

| Ruta | Descripción |
|---|---|
| `index.html` | Aplicación completa (HTML, CSS, JS y datos embebidos). Funciona con doble clic o publicada en GitHub Pages. |

## Pestañas

- **Recorrido USCI**: Tomo/USCI → documento. Por cada documento, las observaciones IF de ese USCI por especialidad, con artículo, alcance, severidad, respuesta SC y el recuadro **Dónde está la falta** (páginas, texto del documento en ese punto y enlace al PDF del Folio).
- **Observaciones IF (G_PEPID)**: las 1.652 observaciones (1.571 de los registros USCI y 81 de Medio Ambiente) (matriz USCI × especialidad, filtros por USCI, especialidad, documento y severidad).
- **Revisión especialista**, **Registro normativo**, **Resumen por Tomo**, **Matriz de auditoría**, **Control normativo**, **Brechas y estudios**, **BALI y oferta Sacyr**, **Índice USCI**.

## Imprimir PDF

El botón **Imprimir PDF** de la cabecera genera un PDF A4 con lo que está desplegado en la pestaña activa (en *Recorrido*, el documento abierto; en *Observaciones IF*, todas las filas que cumplen los filtros). Cada PDF lleva la fecha y hora de emisión, la fecha de actualización del registro IF y la de la revisión del especialista, además de los filtros aplicados y la numeración de páginas. Usa jsPDF 2.5.1 y jsPDF-AutoTable 3.8.2 desde cdnjs, por lo que requiere conexión; sin ella se abre la impresión del navegador.

## Notas sobre los datos

- Se incluyen todas las filas con contenido de las 40 hojas; se excluyen 8 filas plantilla sin artículo ni texto.
- Severidad: la del registro (columna *Observado* o prefijo del alcance). 946 filas marcadas solo con "X" figuran como *Sin clasificar*.
- La ubicación en el PDF es automática (sección del artículo, título del alcance y términos citados): exacta 680, probable 353, sección citada 295, solo página 26. 209 observaciones señalan contenido ausente.
- Medio Ambiente (07): todas sus filas indican el código `DCOQ-GSI-CD-C0-EST-BD-0001`, pero la descripción corresponde textualmente a `DCOQ-GSI-CD-C0-ARQ-BD-0001` (Arquitectura y Urbanización, Obras de Conducción y Almacenamiento). Se asocian a ese documento, con una nota de trazabilidad en cada tarjeta. La mayoría pide incorporar normativa ausente, así que se señala la sección donde debe incorporarse (73) o se marcan como contenido ausente (8).
- Al 06-11-2026 ninguna observación tiene respuesta de la Sociedad Concesionaria ni está aprobada.

## Publicar en GitHub Pages

*Settings → Pages → Deploy from a branch*, rama `main`, carpeta `/ (root)`. Queda en `https://lms02025.github.io/RevisorUSCI/`. La página carga fuentes desde Google Fonts; sin conexión usa las del sistema.

## Confidencialidad

El repositorio no contiene los PDF de proyecto: cada observación enlaza al original en Google Drive (FOLIO 67 / FOLIO 68), que solo abre para quien tiene acceso a esa carpeta. El registro de observaciones sí está embebido en `index.html`; si el repositorio es público, cualquiera puede leerlo.
