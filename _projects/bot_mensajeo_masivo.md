---
layout: project
title: Spam-bot de Whatsapp
description: >
  Diseño, desarrollo y puesta en producción de un spam-bot en Whatsapp.
hide_description: false
date: Sep 2024
sitemap: true

image:
  path: /assets/img/bot_WA/bot_WA_portada.png
  srcset:
    1920w:   /assets/img/bot_WA/bot_WA_portada.png
    960w:    /assets/img/bot_WA/bot_WA_portada_scale_0.5.png
    480w:    /assets/img/bot_WA/bot_WA_portada_scale_0.25.png
display_screenshot: "false"


---

## Spam-bot de Whatsapp
<div style="text-align: center;">
  <img src="/assets/img/bot_WA/bot_WA_portada.png" alt="Portada Análisis Comunidades ML" width="60%" style="border-radius: 30px;">
</div>
<br>
 
Este proyecto es un bot de WhatsApp desarrollado en **JavaScript/TypeScript**. Está diseñado para permitir a los usuarios interactuar y programar envíos masivos de mensajes de manera sencilla. El bot puede ser fácilmente alojado en la nube. El proyecto original se desplegó en **AWS** utilizando **PM2** para garantizar que el servicio se mantenga operativo.

<div style="text-align: center; margin-top: 20px; overflow-y: scroll; max-height: 500px;">
  <img src="/assets/img/bot_WA/diagrama_de_flujo.png" alt="Flujo de programación de un mensaje" width="100%" style="border-radius: 10px;">
</div>


## Funcionalidades Principales

1. **Programación de Mensajes Personalizados**:
   - Mensajes de texto con variables dinámicas personalizadas para cada cliente.
   - Envío de imágenes, videos, archivos, y mensajes de audio.
   - Organización flexible de los contenidos del mensaje
   - Interfaz integrada al propio chat de Whatsapp

2. **Gestión por Chat**:
   - Toda la configuración y operación del bot se realiza a través de una única ventana de chat en WhatsApp.
   - Los usuarios pueden programar mensajes simplemente indicando un archivo **CSV** o **Excel** con la lista de números destinatarios.

3. **Mecanismos de Seguridad**:
   - Implementación de técnicas para evitar bloqueos por parte de WhatsApp.
   - Simulación de comportamiento humano para minimizar riesgos.

<br>

## Algunos casos de Uso

- Campañas publicitarias automatizadas.
- Recordatorios y notificaciones para eventos.
- Comunicación masiva con clientes o usuarios de servicios.

<br>

Construir este bot fue de lo más atractivo. Desde la comunicación con el cliente final, el diseño de la arquitectura, su desarrollo, testeo y puesta en producción. Llevé adelante todo el proceso.
<br>
Y yo siempre me sentí cómodo con Python, bases de datos, análisis de datos... pero este proyecto fue un poco una aventura. Meterme tan a fondo a programar un asistente, por completo en otro lenguaje, organizar el desarrollo del producto, levantarlo y retocarlo y después la satisfacción de que quede corriendo en la nube y funcione todo como tiene que funcionar... Fantástico!

<div style="margin-top: 20px;">
  <h2>Video demostración</h2>
  <div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%; background: #000; border-radius: 10px;">
    <iframe src="https://www.youtube-nocookie.com/embed/Tg1MjMIVArc" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
  </div>
</div>