# Casperify

[Ghost’s](http://ghost.io) [Casper](https://github.com/TryGhost/Casper) hexo port,
Basic structure from [hexo-theme-ghost-casper](https://github.com/MIKAGMR/hexo-theme-ghost-casper)

![screenshot](http://res.cloudinary.com/djpqkjsmr/image/upload/v1452958974/casperify-screenshot_pp4t7c.png)

## Getting Started

### Installation

Before anything, in the top directory of the project, run:


``` bash
$ git clone https://github.com/agodin3z/hexo-theme-casperify.git themes/casperify
```

> **Note:** You need to change the theme’s name in the configuration file of your project in order to use it with Hexo.

> ```yml
> # file: _config.yml
>
> theme: casperify
> ```

## Configuration

### Global configuration example

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

### Theme’s configuration

We add our information in the theme’s configuration file.

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


### Post configuration

Basic structure required by Post (cover and tags are optional):

``` yml
title: {{ title }}
date: {{ date }}
author: user
#tags: [tag1, tag2, tag3]
#cover: /url-or-path/to/cover.png
---
//Content
```

>Note: The commented parts are optional, won’t affect the site if they'r without information.

For more configuration options read [Hexo’s documentation](http://hexo.io/docs/configuration.html).

## Theme’s custom configuration

### Multi Author configuration

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
> Note: The commented parts are optional, won’t affect the site if they're without information.

> To add more social links, write the id according to te icon’s name [FontAwesome](https://fontawesome.com/v4.7.0/icons/#brand)

> The author's id must be added for each post
``` yml
title: {{ title }}
date: {{ date }}
author: user2 #here
```

### Author’s page

First create a new directory insite the `source/` named `author` and inside of it, create another directory named the user’s name `user` inside of it, we need to create a .md file named `index.md` with the following content:

```
title: "Another user" #author's name
layout: "author"
author: user
#cover:
---
```

### Tag’s page

First create a new directory  inside `source/` named `tags` and inside of this one, we need to create a .md file named `index.md` with the following content:

```
title: "Tags"
layout: "tags"
cover: http://url-to/cover.jpg
---
```

## Copyright & License from original author

Copyright (c) 2013-2016 Ghost Foundation - Released under the MIT License.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
