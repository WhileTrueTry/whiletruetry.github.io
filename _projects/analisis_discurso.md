---
layout: project
title: Análisis de discurso en Youtube
description: >
  Mini-app que sirve como muestra de lo que se puede hacer al integrar herramientas de NLP.
hide_description: false
sitemap: true
date: Jan 2025

image:
  path: /assets/img/yt_app/diagrama.png
  srcset:
    1920w:   /assets/img/yt_app/analisis_discurso_portada.png
    960w:    /assets/img/yt_app/analisis_discurso_portada_scale_0.5.png
    480w:    /assets/img/yt_app/analisis_discurso_portada_scale_0.25.png
display_screenshot: "false"

---
<div style="display: flex;">
  <div style="flex: 0 0 500px; margin-right: 40px; overflow-y: auto; max-height: 500px; border: 1px solid #ccc; border-radius: 10px; padding: 10px;">
    <div style="text-align: center;">
      <img src="/assets/img/yt_app/diagrama.png" alt="Flujo de gestión y procesamiento de la información" width="100%" style="border-radius: 10px;">
    </div>
  </div>
  <div style="flex: 1;">
    <!-- Main content goes here -->
    <h2>Intro</h2>
    <p>Se trata de una app que permite descargar, procesar y visualizar el audio de una lista de videos de Youtube.</p>

    <h2>Software</h2>
    <p>Python (streamlit, langchain, spacy, pandas, ytdlip, subprocess),</p> 
    <p>R (quanteda)</p> 
    <p>Groq API</p> 

  </div>
</div>

<h2>Aplicaciones</h2>
<p>Con los ajustes necesarios, este tipo de mini-apps pueden servir para los casos más variados relacionados con el análisis de texto . Por ejemplo en relación para el análisis de la comunicación con clientes, la identificación de tendencias en internet, la construcción de asistentes personalizados, etc... </p>


<!-- <div style="margin-top: 20px;">
  <h2>Video de Youtube</h2>
  <div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%; background: #000; border-radius: 10px;">
    <iframe src="https://www.youtube-nocookie.com/embed/Tg1MjMIVArc" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
  </div>
</div> -->

<div style="margin-top: 20px;">
  <h2>Demo en video</h2>
  <div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%; background: #000; border-radius: 10px;">
    <video controls style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; border-radius: 10px;">
      <source src="/assets/img/CDPCS/video_clase.mp4" type="video/mp4">
      Mmm... parece que tu navegador no soporta el reproductor de video :(
    </video>
  </div>
</div>