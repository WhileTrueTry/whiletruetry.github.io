---
layout: project
title: Comunidades de Twitter
description: >
  Un análisis de las comunidades de discusión en Twitter en torno a Mercado Libre
  <br>Ene 2023 - Abr 2023
hide_description: false
date: May 2023
sitemap: true

image:
  path: /assets/img/ML/portada_analisis_comunidades_ml.png
  srcset:
    1920w:   /assets/img/ML/portada_analisis_comunidades_ml.png
    960w:    /assets/img/ML/portada_analisis_comunidades_ml_scale_0.5.png
display_screenshot: "false"

carousels:
  - images: 
    - image: /assets/img/ML/ML_NLP_1.jpg
    - image: /assets/img/ML/ML_NLP_2.jpg
    - image: /assets/img/ML/ML_NLP_3.jpg
    - image: /assets/img/ML/ML_NLP_4.jpg
    - image: /assets/img/ML/ML_NLP_5.jpg
    - image: /assets/img/ML/ML_NLP_6.jpg
    - image: /assets/img/ML/ML_NLP_7.jpg
    - image: /assets/img/ML/ML_NLP_8.jpg
    - image: /assets/img/ML/ML_NLP_9.jpg
    - image: /assets/img/ML/ML_NLP_10.jpg
    - image: /assets/img/ML/ML_NLP_11.jpg
    - image: /assets/img/ML/ML_NLP_12.jpg
    - image: /assets/img/ML/ML_NLP_13.jpg
    - image: /assets/img/ML/ML_NLP_14.jpg
    - image: /assets/img/ML/ML_NLP_15.jpg
    - image: /assets/img/ML/ML_NLP_16.jpg
---

## Análisis de comunidades en Twitter
<div style="text-align: center;">
  <img src="/assets/img/ML/portada_analisis_comunidades_ml.png" alt="Portada Análisis Comunidades ML" width="60%" style="border-radius: 30px;">
</div>
<br>
 
Este estudio estuvo centrado en la observación de las comunidades de discusión relacionadas con Mercado Libre en Twitter.
El proceso completo incluyó la definición de un diseño metodológico, la recolección de datos, su pre-procesamiento, el análisis y la presentación de los resultados en las diapositivas que se adjuntan a continuación   

## Presentación de resultados
{% include carousel.html height="50" unit="%" duration="11" number="1" %}


### **Metodología aplicada**  
- **Recolección de tweets**: Mediante el uso de snscrape, una libraría de web scraping, se obtuvieron los tweets que se adjuntan en el repositorio  de github **tweets_mercado_libre_23** .  
- **Preprocesamiento de datos**: Utilicé Python, con librerías como **spacy**, **gensim** y **transformers** para limpiar y estructurar la información. Preparé el texto para ser analizado y armé las redes de relaciones por menciones que sirven de insumo para las redes de Gephi  
- **Preparación para análisis de redes**: Los datos se adaptaron para ser procesados con **Gephi** (para el modelado de las redes) y la librería **quanteda** en **R** (para el análisis del texto).  

### **Análisis realizado**  
- Apliqué técnicas como el **modelado de tópicos** y el **análisis de sentimiento** para identificar los temas centrales de las discusiones.  
- Y  **modelos de lenguaje (LLMs)** para tareas de clasificación de texto
- Aproveché los algoritmos de clusterización y análisis que vienen pre-configurados en Gephi.
- Incluí el diseño de indicadores propios para detectar influencers y figuras de autoridad en la conversación.
- etc...
    

En este proyecto se combinan herramientas avanzadas y métodos específicos para ofrecer una visión detallada de cómo se desarrolla el intercambio de ideas en esta red social en el contexto de referencia a una marca grande con presencia en la conversación social

<div style="background-color: black; padding: 20px; border-radius: 10px; text-align: center; margin: 20px auto; width: fit-content;">
  <a href="/assets/img/ML/comunidades_ML_NLP.pdf" class="button-63" role="button" style="background-image: linear-gradient(144deg,#AF40FF, #5B42F3 50%,#00DDEB); border: 0; border-radius: 8px; box-shadow: rgba(151, 65, 252, 0.2) 0 15px 30px -5px; box-sizing: border-box; color: #FFFFFF; display: flex; font-family: Noto sans, sans-serif; font-size: 23px; justify-content: center; line-height: 1em; max-width: 100%; min-width: 140px; padding: 19px 24px; text-decoration: none; user-select: none; -webkit-user-select: none; touch-action: manipulation; white-space: nowrap; cursor: pointer; margin-bottom: 20px;">
    Descargar presentación en PDF
  </a>
  <a href="https://github.com/WhileTrueTry/tweets_mercado_libre_23" class="button-63" role="button" style="background-image: linear-gradient(144deg,#AF40FF, #5B42F3 50%,#00DDEB); border: 0; border-radius: 8px; box-shadow: rgba(151, 65, 252, 0.2) 0 15px 30px -5px; box-sizing: border-box; color: #FFFFFF; display: flex; font-family: Noto sans, sans-serif; font-size: 23px; justify-content: center; line-height: 1em; max-width: 100%; min-width: 140px; padding: 19px 24px; text-decoration: none; user-select: none; -webkit-user-select: none; touch-action: manipulation; white-space: nowrap; cursor: pointer;">
    Descargar el dataset original
  </a>
</div>
