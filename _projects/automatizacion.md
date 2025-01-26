---
layout: project
title: Automatizar la recolección de datos
description: >
  Recolección de audios de Youtube, transcripción y preprocesamiento de texto
hide_description: false
sitemap: false
date: Dec 2024

image:
  path: /assets/img/yt_app/automatizacion_portada.jpg
  srcset:
    1920w:   /assets/img/yt_app/automatizacion_portada.jpg
    960w:    /assets/img/yt_app/automatizacion_portada_scale_0.5.png
    480w:    /assets/img/yt_app/automatizacion_portada_scale_0.25.png
display_screenshot: "false"

---

# Recolección automatizada de datos de Youtube
<div style="text-align: center;">
  <img src="/assets/img/yt_app/automatizacion_portada.jpg" alt="Portada Análisis Comunidades ML" width="60%" style="border-radius: 30px;">
</div>
<br>

Automatizar la recolección de datos nos ahorra mucho tiempo de trabajo, a la vez que podemos descansar en software de calidad para realizar muchas tareas repetitivas

El proceso que se explica a continuación es una intro al post de [Análisis de discurso en Youtube](./analisis_discurso.md).
Esta intro incluye los siguientes puntos:

1. **Descarga de archivos de audio desde YouTube**  
   Utilizando el paquete **yt_dlp** se automatiza la descarga de audios desde videos de YouTube, una tarea que de otra forma sería manual y repetitiva. Esto permite recolectar datos auditivos relevantes para análisis posteriores.

2. **Transcripción de audio a texto**  
   Con el soporte de la **API Key de GROQ** y el modelo de lenguaje **Whisper**, el programa convierte los archivos de audio en texto de alta precisión. Este paso transforma datos no estructurados (audio) en un formato aún no estructurado, pero más cercano a algo que podemos manejar (texto).

3. **Preprocesamiento del texto para el análisis posterior**  
   Usando la librería **spacy** se prepara el texto para análisis posteriores mediante técnicas como:
   - eliminación de caracteres especiales
   - eliminación de stopwords.
   - lemmatización
   - organización tabulada del texto para su análisis posterior


   Este preprocesamiento, ajustando los parámetros correspondientes, puede preparar los datos obtenidos de esta (u otra) red social para tareas como análisis de sentimientos, comparación de corpus, modelado de tópicos, etc...

### Beneficios de este Enfoque
- **Eficiencia**: la automatización reduce el tiempo y el esfuerzo requeridos en tareas repetitivas.
- **Escalabilidad**: permite manejar grandes volúmenes de datos provenientes de múltiples fuentes.
- **Consistencia**: minimiza errores humanos en la recolección y procesamiento de datos.


<p>Este ejemplo muestra cómo las técnicas automatizadas de recolección y procesamiento son una herramienta esencial en el campo del análisis del discurso.</p>
<p>No hay que desconocer que este tipode herramientas se encuentran limitadas al ámbito de aplicación que les corresponde (las redes, el internet, los chats con los clientes, en suma, los datos de texto digitalizados).</p>
<p>Pero dentro de ese ámbito, resultan ser opciones muy útiles que nos permiten estudiar flujos heterogéneos de información y enriquecer nuestros proyectos con análisis profundos y orientados a resultados.</p>


<div style="margin-top: 20px;">
  <h2>Intro al análisis de audio en Youtube</h2>
  <div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%; background: #000; border-radius: 10px;">
    <iframe src="https://www.youtube-nocookie.com/embed/Tg1MjMIVArc" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
  </div>
</div>