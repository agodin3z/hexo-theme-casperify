# Casperify

Hexo port del tema [Casper](https://github.com/TryGhost/Casper) de [Ghost](http://ghost.io)

Estructura base: [hexo-theme-ghost-casper](https://github.com/MIKAGMR/hexo-theme-ghost-casper)

![screenshot](http://res.cloudinary.com/djpqkjsmr/image/upload/v1452958974/casperify-screenshot_pp4t7c.png)

## ¿Como instalarlo?

### Instalación

Antes de todo, nos situamos en el directorio principal de nuestro proyecto y ejecutamos:


``` bash
$ git clone https://github.com/AGodinez/hexo-theme-casperify.git themes/casperify
```

> **Nota:** Es necesario cambiar el nombre del tema en el archivo de configuración de nuestro proyecto.

> ```yml
> # file: _config.yml
>
> theme: casperify
> ```

## Configuración

### Ejemplo del archivo de configuración del proyecto

``` yml
# file: _config.yml

# Hexo Configuration
## Docs: http://hexo.io/docs/configuration.html
## Source: https://github.com/hexojs/hexo/

# Site
title: Titulo del sitio web o blob
subtitle: Eslogan
description: Pequeña descripción del sitio web o blob
logo: /ruta-al/logo.png
language: es
timezone: #Conocer nuestra timezone: https://timezonedb.com/
since: # Año que sera mostrado en la sección de copyright.

# URL
## If your site is in a subdirectory, set url as 'http://yoursite.com/child' and root as '/child/'
url: http://mywebsite.com
root: /
permalink: :title/
permalink_defaults:
#permalink info: https://hexo.io/docs/permalinks.html

# Directory
source_dir: source
public_dir: public
tag_dir: tags
archive_dir: archives
category_dir: categories
code_dir: downloads/code
i18n_dir: :lang
#skip_render:

# Writing
new_post_name: :title.md # File name of new posts
default_layout: post
titlecase: false # Transform title into titlecase
external_link: true # Open external links in new tab
filename_case: 0
render_drafts: false
post_asset_folder: false
relative_link: false
future: true
highlight:
  enable: true
  line_number: true
  auto_detect: true
  tab_replace:

# Category & Tag
default_category: uncategorized
category_map:
tag_map:

# Date / Time format
## Hexo uses Moment.js to parse and display dates
## You can customize date format as defined in
## http://momentjs.com/docs/#/displaying/format/
date_format: LL
time_format: HH:mm:ss

# Pagination
## Set per_page to 0 to disable pagination
per_page: 5
pagination_dir: page

# Extensions
## Plugins: http://hexo.io/plugins/
## Themes: http://hexo.io/themes/
theme: casperify

# Feed
feed:
  type: atom
  path: atom.xml
  limit: 20

# Disqus
disqus_shortname: myShortname

# Deployment
## Docs: http://hexo.io/docs/deployment.html
deploy:
  type: git
  repo: https://url-a/mi/repo.git
  branch: miRama
  message: "Mensaje de despliegue"
```

### Configuración del tema

Agremamos nuestra información al archivo de configuración del tema:

``` yml
# file: themes/casperify/_config.yml

# main cover
cover: http://url/al/background.jpg

# authors config
authors:
  user:
    name: Nombre del autor
    username: user
    avatar: /ruta-o-url/del/avatar.png
    shortbio: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.'
    longbio: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam feugiat in purus non posuere. Fusce nibh erat, ullamcorper sit amet dui sed, vehicula euismod velit.'
    location: Algun Lugar
    website: http://mywebsite.com
    cover: /ruta-o-url/del/author-cover.png
    social: # social network profile links
      facebook: https://facebook.com/myUser
      twitter: https://twitter.com/myUser
      google-plus: https://plus.google.com/+myUser
      github: https://github.com/myUser
      instagram: https://instagram.com/myUser
      flirck: https://www.flickr.com/photos/myUser
      linkedin: https://linkedin.com/in/myUser
      steam: https://steamcommunity.com/id/myUser
      tumblr: http://myUser.tumblr.com
      pinterest: https://www.pinterest.com/myUser

#opengraph config
twitter_profile:
googleplus_profile:
fb_admins:
fb_app_id:

# Magnific Popup (lightbox): http://dimsemenov.com/plugins/magnific-popup/
# FitVids: http://fitvidsjs.com/
lightbox: true
fitvids: true

excerpt_link: Read More

#analytics
google_analytics: myID

# Miscellaneous
rss: /atom.xml

```


### Configuración del Post

Estructura básica requerida por post:

``` yml
title: {{ title }}
date: {{ date }}
author: user
#tags: [tag1, tag2, tag3]
#cover: /ruta-o-url/del/cover.png
---
//Content
```

> **Nota:** Las partes comentadas son opcionales, no afectarán al sitio si no se llena con información.

Para mas opciones de configuración leer la [Documentación de Hexo](http://hexo.io/docs/configuration.html).

## Configuración personalizada del tema

### Configuración Multi Autor

``` yml
# file: themes/casperify/_config.yml

# authors config
authors:
  user: #identificador del autor 1
    name:
    username: user
    avatar:
    shortbio: #Se mostrara al final del post
    longbio:  #Se mostrara en la página del autor
    #location:
    #website:
    #cover:
    social: # social network profile links
      #facebook:
      #twitter:
      #google-plus:
      #github:
      #instagram:
      #flirck:
      #linkedin:
      #steam:
      #tumblr:
      #pinterest:
  user2: #identificador del autor 2
    name:
    username: user2
    avatar:
    shortbio:
    longbio:
    #location:
    #website:
    #cover:
    social: # social network profile links
      #facebook:
      #twitter:
      #google-plus:
      #github:
      #instagram:
      #flirck:
      #linkedin:
      #steam:
      #tumblr:
      #pinterest:

```
> **Nota:** Las partes comentadas son opcionales, no afectarán al sitio si no se llena con información.

> Para agregar mas links sociales, escribir el nombre de la red social de acuerdo al nombre del icono de [FontAwesome](http://fontawesome.io/icons/#brand)

> El identificador del autor se debe agregar en cada post
``` yml
title: {{ title }}
date: {{ date }}
author: user2 #aqui
```

### Página del Autor

Primero creamos un directorio nuevo dentro de `source/` y lo nombramos `author` luego, dentro de este, creamos un directorio con el nombre del identificador del autor `user` por ultimo, dentro de este directorio creamos un archivo .md con nombre: `index.md` que debera contener lo siguiente:

```
title: "My name" #nombre del autor
layout: "author"
author: user #identificador del autor
#cover:
---
```

### Página de Tags

Creamos un directorio nuevo dentro de `source/` y lo nombramos `tags` luego, dentro de este, creamos un archivo .md con nombre `index.md` que debera contener lo siguiente:

```
title: "Tags"
layout: "tags"
cover: http://url-o-ruta/del/cover.jpg
---
```

## Copyright & Licencia de la obra original

Copyright (c) 2013-2016 Ghost Foundation - Released under the MIT License.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
