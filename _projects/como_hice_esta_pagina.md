---
layout: project
title: Cómo hice esta página
description: >
  Cómo hice esta página usando Hydejack y las instrucciones que encontré en internet.
hide_description: true
order: 3
sidebar: true
permalink: projects/como_hice_esta_pagina

sitemap: true
date: Jan 2025

image:
  path: /assets/img/webpage/web_page_portada.png
  srcset:
    1920w:   /assets/img/webpage/web_page_portada.png
    960w:    /assets/img/webpage/web_page_portada_scale_0.5.png
    480w:    /assets/img/webpage/web_page_portada_scale_0.25.png
  
display_screenshot: "false"

---
<span style="display:none;">Cómo hice esta página</span>
# 🚀 Configuración de Jekyll >4 en GitHub Pages

Guía para configurar y desplegar una página en GitHub Pages con la última versión de Jekyll y los plugins más nuevos

GitHub Pages te permite levantar y alojar gratuitamente un sitio creado con Jekyll, pero para ello utiliza por defecto la gem de Ruby `github-pages`, que tiene restricciones en las versiones de Jekyll, temas y plugins compatibles, lo que puede limitar la personalización y funcionalidad del sitio. Y lo va a hacer incluso si no tenés esa gem en tu archivo local.

¿Es posible usar las últimas versiones de Jekyll, cualquier tema y plugin, y aún aprovechar el hosting gratuito de GitHub?
Sí, configurando el workflow de GitHub Actions con el que se levanta el sitio de manera adecuada.

Para esto necesitamos una rama del proyecto que llamaremos gh-pages, desde la que construiremos el sitio.
Y los archivos resultantes quedarán guardados en la rama main, desde la cual lo levantaremos con todas las funcionalidades.

Si querés entender mejor cómo funciona todo esto, te dejo a mano el tutorial original 😉


<div style="margin-top: 20px;">
  <h2>Paso a paso</h2>
  <div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%; background: #000; border-radius: 10px;">
    <iframe src="https://www.youtube-nocookie.com/embed/Tg1MjMIVArc" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
  </div>
</div>

---
---

## Recursos

- Tutorial original: [Moncef Belyamani](https://www.moncefbelyamani.com/making-github-pages-work-with-latest-jekyll/#fnref1)
- Instrucciones oficiales de Jekyll:
  - [Instalación](https://jekyllrb.com/docs/installation/)
  - [Jekyll basics](https://jekyllrb.com/docs/)
- Más sobre Jekyll:
  - [Techno Tim](https://www.youtube.com/watch?v=F8iOU1ci19Q&t=874s)
  - [Code Voyage with Iman](https://www.youtube.com/watch?v=GKiqZL1pA_M&t=2739s)
- El tema que usé: [Hydejack v9.2.1](https://hydejack.com/blog/hydejack2024-09-04-service-release-for-9-1/)
<br>(este es el tema sobre el que trabajé una vez que estuve seguro de que iba a poder utilizar su versión más nueva)

### Prerrequisitos

- Una cuenta de GitHub.
- Ruby versión 3.2.6
- Y su respectivo entorno de desarrollo Ruby, con un administrador y conmutador de versiones como `chruby`.
- Git y la CLI de GitHub (gh) para trabajar en consola
- y el entorno de Git configurado, con tu nombre, mail, editor y main como tu rama predeterminada.



---
---

## 💻 Configuración inicial (en consola)


**Creamos el directorio y definimos dependencias**
```bash
git init keeptrying && cd keeptrying
```

**Nos aseguramos de estar usando la versión correcta de ruby**
```bash
chruby 3.2.6
```

**Instalamos bundler y jekyll**
```bash
gem install bundler jekyll
```

**Iniciamos el proyecto**
```bash
jekyll new .
```

**Y re-aseguramos la versión correcta, para cuando entremos más adelante en nuestro directorio `jekyll-github-actions`**
```bash
echo 'ruby-3.2.6' >> .ruby-version
```

---
---


## ✏️ Empezamos a modificar archivos


**Actualizamos el `Gemfile` de ruby**

Agregamos las siguientes líneas al archivo `Gemfile`:

```ruby
...
ruby "3.2.6"
...
group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.12"
  gem "jekyll-timeago", "~> 0.13.1"
end
...
```

**Instalamos dependencias (en consola)**
```bash
bundle install
```

**Actualizamos el `Gemfile.lock` (si "ruby" no aparece entre "Platforms" en ese archivo) (en consola)**
```bash
bundle lock --add-platform ruby
bundle lock --add-platform x86_64-linux
```

**Verificamos la versión de Jekyll**

Para asegurarnos de que Jekyll >3.9 esté funcionando, actualizamos el archivo `index.markdown` con contenido de prueba.
El plugin `timeago` no funciona con la carga default de GitHub Pages

```liquid
### Ejemplo de uso:
## 🛠️ Probando el plugin `timeago`
{% assign fecha = '2020-04-13T10:20:00Z' %}

- Fecha original: {{ fecha }}
- Con el filtro de timeago: {{ fecha | timeago }}


Dale las gracias a [Moncef Belyamani](https://www.moncefbelyamani.com) por este hack  🙌

```


---
---

## ⚙️ Definimos el proceso de GitHub Actions


**Creamos directorios y archivos necesarios para GitHub Actions** (en consola)
```bash
mkdir -p .github/workflows
touch .github/workflows/jekyll-github-pages.yml
```

**Establecemos el flujo de trabajo en el archivo `jekyll-github-pages.yml` que acabamos de**
```yaml
name: Contruir y levantar la página con Jekyll y GitHub Pages

on:
  push:
    branches:
      - gh-pages # o "main" si se trata de una project page

jobs:
  jekyll:
    runs-on: ubuntu-latest
    steps:
      - name: 📂 setup
        uses: actions/checkout@v2

        # Descomenta las líneas siguientes si usas jekyll-last-modified-at
        # o necesitas obtener todo el historial de commits:
        # with:
        # fetch-depth: '0'

      - name: 💎 setup ruby
        uses: ruby/setup-ruby@v1
        with:
          ruby-version: 3.2

      - name: 🔨 install dependencies & build site
        uses: limjh16/jekyll-action-ts@v2
        with:
          enable_cache: true

      - name: 🚀 deploy
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./_site
          # Si estás desplegando en <username>.github.io, descomenta:
          publish_branch: main ## o gh-pages si se trata de una project page
```

---
---

## 📂 Configuramos el acceso de la url en `_config.yml`

Actualizamos según el tipo de página:
- Para **user pages** (nuestro caso) modificamos el campo `url`.
- Para **project pages** (el caso del tutorial original) modificamos el campo `baseurl` (y el flujo de trabajo `jekyll-github-pages.yml` de recién)

Ejemplo:
```yaml
baseurl: "" 
url: "https://<nombre-usuario>.github.io"
```

---
---


## 🚀 Deployamos en GitHub Pages

**Inicializamos el repositorio:**
   ```bash
   git add .
   ```
   ```bash
   git commit -m "Allá vamos"
   ```
   ```bash
   gh auth login --scopes repo,workflow ## Acá vas a tener que seguir las instrucciones para conectar con GitHub
   ```
   ```bash
   gh repo create <nombre-repositorio> --public --push -r origin -s . -d "Dalee"
   ```

**Configuramos la rama `gh-pages`:**

```bash
git checkout -b gh-pages
```
```bash
git add .
```
```bash
git commit -m "Levantamos en gh-pages para ponerlo a funcionar"
```
```bash
git push origin gh-pages
```

---
---

## ☝️ Chequeamos la configuración de GitHub Actions: 

**En la página de GitHub checkeamos la configuración establecida de cómo ejecutar el workflow de GitHub Actions.**

**También nos aseguramos de que la rama establecida para el deploy de la página sea main.**



**¡Y listo! Cuando se complete el workflow de GitHub Actions ya vamos a tener la página de Jekyll funcionando alojada en GitHub Pages. 🎉**
