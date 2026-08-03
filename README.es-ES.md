

# Casperify

Adaptación para Hexo del tema [Casper](https://github.com/TryGhost/Casper) de [Ghost](http://ghost.io),
Estructura básica basada en [hexo-theme-ghost-casper](https://github.com/MIKAGMR/hexo-theme-ghost-casper)

![screenshot](http://res.cloudinary.com/djpqkjsmr/image/upload/v1452958974/casperify-screenshot_pp4t7c.png)

## Empezando

### Instalación

Antes de nada, en el directorio raíz del proyecto, ejecuta:


``` bash
$ git clone https://github.com/agodin3z/hexo-theme-casperify.git themes/casperify
```

> **Nota:** Debes cambiar el nombre del tema en el archivo de configuración de tu proyecto para poder usarlo con Hexo.

> ```yml
> # file: _config.yml
>
> theme: casperify
> ```

## Configuración

### Ejemplo de configuración global

``` yml
# file: _config.yml

# Hexo Configuration
## Docs: http://hexo.io/docs/configuration.html
## Source: https://github.com/hexojs/hexo/

# Site
title: Some Title
subtitle: Slogan
description: website or blog description
logo: /path-to/logo.png
language: en
timezone: #Get your timezone: https://timezonedb.com/
since: # The start year shown in your copyright section.

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
  repo: https://url-to/my/repo.git
  branch: myBranch
  message: "My deploy message"
```

### Configuración del tema

Agregamos nuestra información en el archivo de configuración del tema.

``` yml
# file: themes/casperify/_config.yml

# main cover
cover: http://url/to/background.jpg

# authors config
authors:
  user:
    name: Another User
    username: user
    avatar: /path-or-url/to/avatar.png
    shortbio: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.'
    longbio: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam feugiat in purus non posuere. Fusce nibh erat, ullamcorper sit amet dui sed, vehicula euismod velit.'
    location: Milky Way
    website: http://mywebsite.com
    cover: /path-or-url/to/author-cover.png
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


### Configuración de publicaciones

Estructura básica requerida para la publicación (la portada y las etiquetas son opcionales):

``` yml
title: {{ title }}
date: {{ date }}
author: user
#tags: [tag1, tag2, tag3]
#cover: /url-or-path/to/cover.png
---
//Content
```

> Nota: Las partes comentadas son opcionales, no afectarán al sitio si se dejan sin información.

Para más opciones de configuración, lee la [documentación de Hexo](http://hexo.io/docs/configuration.html).

## Configuración personalizada del tema

### Configuración para múltiples autores

``` yml
# file: themes/casperify/_config.yml

# authors config
authors:
  user: #Author id 1
    name:
    username: user
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
  user2: #Author id 2
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
> Nota: Las partes comentadas son opcionales, no afectarán al sitio si se dejan sin información.

> Para agregar más enlaces sociales, escribe el id según el nombre del ícono en [FontAwesome](https://fontawesome.com/v4.7.0/icons/#brand)

> El id del autor debe agregarse en cada publicación
``` yml
title: {{ title }}
date: {{ date }}
author: user2 #here
```

### Página del autor

Primero, crea un nuevo directorio dentro de `source/` llamado `author` y, dentro de él, crea otro directorio con el nombre de usuario `user`. En su interior, debemos crear un archivo `.md` llamado `index.md` con el siguiente contenido:

```
title: "Another user" #author's name
layout: "author"
author: user
#cover:
---
```

### Página de etiquetas

Primero, crea un nuevo directorio dentro de `source/` llamado `tags` y, dentro de este, debemos crear un archivo `.md` llamado `index.md` con el siguiente contenido:

```
title: "Tags"
layout: "tags"
cover: http://url-to/cover.jpg
---
```

## Copyright y Licencia del autor original

Copyright (c) 2013-2016 Ghost Foundation - Publicado bajo la Licencia MIT.

Por la presente se concede permiso, sin cargo, a cualquier persona que obtenga una copia de este software y los archivos de documentación asociados (el "Software"), para tratar el Software sin restricciones, incluidos, entre otros, los derechos de usar, copiar, modificar, fusionar, publicar, distribuir, sublicenciar y/o vender copias del Software, y para permitir a las personas a quienes se les proporcione el Software hacerlo, sujeto a las siguientes condiciones:

El aviso de copyright anterior y este aviso de permiso se incluirán en todas las copias o porciones sustanciales del Software.

EL SOFTWARE SE PROPORCIONA "TAL CUAL", SIN GARANTÍA DE NINGÚN TIPO, EXPRESA O IMPLÍCITA, INCLUIDAS PERO NO LIMITADAS A LAS GARANTÍAS DE COMERCIABILIDAD, APTITUD PARA UN PROPÓSITO PARTICULAR Y NO INFRACCIÓN. EN NINGÚN CASO LOS AUTORES O TITULARES DEL COPYRIGHT SERÁN RESPONSABLES DE NINGUNA RECLAMACIÓN, DAÑOS U OTRAS RESPONSABILIDADES, YA SEA EN UNA ACCIÓN DE CONTRATO, ILÍCITO CIVIL O CUALQUIERA OTRA, QUE SURJA DE, FUERA DE O EN CONEXIÓN CON EL SOFTWARE O EL USO U OTROS TRATOS EN EL SOFTWARE.
