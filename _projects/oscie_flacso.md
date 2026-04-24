---
layout: project
title: Recopilación automatizada de información web
description: >
  Desarrollo de herramientas para el relevamiento de organizaciones sociales mediante scraping y LLMs
hide_description: false
date: Feb 2026
sitemap: true

image:
  path: /assets/img/oscie_flacso/flacso.jpg
  srcset:
    1920w:   /assets/img/oscie_flacso/flacso.jpg
    960w:    /assets/img/oscie_flacso/flacso_0.5.png
    480w:    /assets/img/oscie_flacso/flacso_0.25.png
display_screenshot: "true"

---
 
# Recopilación automatizada de información para investigación de FLACSO
<br>

La tarea de relevar manualmente la información disponible en decenas de sitios web resulta costosa en tiempo. Estas herramientas buscan resolver ese problema de forma sistemática y reproducible, permitiendo automatizar el análisis de organizaciones sociales.

<!-- <div style="text-align: center; margin-top: 20px; overflow-y: scroll; max-height: 500px;">
  <img src="/assets/img/oscie_flacso/diagrama_flujo_ScrapAndAnalyze.png" alt="Flujo de recolección y procesamiento de datos" width="100%" style="border-radius: 10px;">
</div> -->

El proceso desarrollado para este proyecto de investigación se divide en los siguientes puntos clave:

1. **Rastreo y navegación automática (Crawling)** El sistema parte de la dirección web de una organización y recorre automáticamente las páginas del sitio siguiendo los enlaces internos. Es posible controlar la profundidad del rastreo y el número máximo de páginas a procesar para asegurar una captura eficiente.

2. **Extracción de contenido y procesamiento con LLM** Todo el contenido textual relevante es extraído y procesado por un modelo de lenguaje (LLM). Mediante un *prompt* específico, se le indica al modelo qué campos de información debe detectar, tales como:
   - Nombre de la organización y misión.
   - Áreas temáticas de trabajo.
   - Fuentes de financiamiento.
   - Productos y publicaciones.

3. **Generación de perfiles institucionales estructurados** Como resultado final, se obtiene un perfil estructurado generado a partir del contenido real del sitio, con intervención manual sólo en la etapa final de consolidación. El sistema es flexible, permitiendo adaptar el *prompt* a distintos tipos de organizaciones o necesidades de relevamiento.

### Detalles Técnicos y Código Abierto
Las herramientas fueron construidas sobre el paquete de Python **crawl4AI** y la **API de Groq Cloud**. El código se encuentra documentado y disponible para la comunidad en GitHub:
- [WhileTrueTry/scrape_and_analyze](https://github.com/WhileTrueTry/scrape_and_analyze): Herramienta para escrapear información y analizar los resultados mediante LLMs.

### Beneficios de este Enfoque
- **Eficiencia Operativa**: Permite obtener perfiles de manera automatizada con un costo reducido y en una fracción del tiempo manual.
- **Valor Analítico**: Libera tiempo para que los investigadores se dediquen a tareas de validación y análisis comparativo.
- **Flexibilidad**: El sistema puede adaptarse fácilmente a nuevas categorías de información o tipos de sitios web.

<p>Este avance implica que, para cada organización de la muestra, es posible escalar el relevamiento de datos de manera sistemática.</p>

<p>Siempre es importante destacar que los resultados obtenidos con estas herramientas deben ser siempre reconsiderados por humanos con experiencia específica en el objeto de estudio. Esto es especialmente relevante al utilizar modelos de lenguaje gratuitos y open-source, que si bien son eficaces, pueden presentar limitaciones en comparación a los modelos más potentes del mercado.</p>

<br>
<hr style="border: 1px solid #000; margin: 20px 0;">