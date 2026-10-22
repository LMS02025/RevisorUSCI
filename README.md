# Revisor USCI · Desaladora Coquimbo

Visor web de la revisión de las bases de diseño (Entrega 1, Rev. A) de la Concesión Planta Desaladora para la Región de Coquimbo, contra BALI Cap. 2.2, normativa vigente y Oferta Técnica Sacyr. Versión del 22-10-2026.

## Contenido

| Ruta | Descripción |
|---|---|
| `index.html` | Visor completo (HTML, CSS, JS y datos embebidos). |
| `docs/` | 31 PDF de bases de diseño que el visor abre y marca página a página. Los nombres deben conservarse. |

## Pestañas

- **Visor**: navegación por Tomo/USCI → documento → página, con las observaciones resaltadas sobre el PDF.
- **Por hoja**: 510 observaciones con página, frase ancla, «debe decir» y fundamento.
- **Registros**: registros de auditoría REG-001 a REG-040.
- **Normas por USCI**: hallazgos validados y registro de 426 normas y criterios, ordenados según el orden USCI.
- **65 USCI**: dedicación de contenido por asignación USCI–documento.
- **BALI 2.2.2**: cumplimiento por sub-cláusula.

## Publicar en GitHub Pages

1. Crear un repositorio y subir `index.html`, `README.md` y la carpeta `docs/` completa.
2. En *Settings → Pages*, elegir *Deploy from a branch*, rama `main`, carpeta `/ (root)`.
3. Abrir `https://<usuario>.github.io/<repositorio>/`.

El visor carga pdf.js y las fuentes desde CDN (cdnjs, Google Fonts), por lo que requiere conexión a internet. Abrir `index.html` con doble clic (`file://`) no permite cargar los PDF; usar GitHub Pages o un servidor local (`python3 -m http.server`).

## Confidencialidad

Los PDF son documentos de proyecto. Si el repositorio es público, cualquier persona podrá descargarlos; usar un repositorio privado (GitHub Pages en repos privados requiere plan de pago u organización) o retirar `docs/` si corresponde.
