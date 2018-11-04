# lhblog-theme
Theme for LibreHealth (librehealth.io) Blog.

A Blog theme for LibreHealth's Website (librehealth.io).

## Context
- [Post](#post) 
  - [Example Front Matter](#example-front-matter)
  - [Adding Post Image](#adding-post-image)
  - [Taxonomy](#taxonomy) 
  - [Post Description](#post-description)
- [Index Page](#index-page)
  - [Carousel](#carousel)
  - [Showcase](#showcase)
  - [Blog Description](#blog-description)
- [Navbar](#navbar)
  - [Logo](#logo)
  - [Menus](#menus)
- [Social Media](#social-media)
- [Footer](#footer)
- [Parallax](#parallax)
- [Open Graph](#open-graph)

## Post
### Example Front Matter
The following is an ideal front matter of a post. It should ATLEAST include a date, an author and a post for the image. If no image is added, a default blue background will be used to display the post instead. The following example is in YAML.
```
---
title: "LibreHealth Radiology"
date: 2018-10-26T13:54:30+07:00
author: "Mark Jones"
image: "radiology2.jpg"
tags: ["hello", "super"]
categories: ["sports",'games']
description: "A description on the technology of LibreHealth Radiology"
---
```

### Adding Post Image
To add an image to a the post, add the image to the static folder of the site and specify the directory of the image **RELATIVE TO THE STATIC FOLDER**. 
This post image will be used on the index page and as a parallax.

### Taxonomy
The two supported taxonomies are categories and tags. Add them to the post's front matter. Example.
```

---
title: "LibreHealth-EHR"
date: 2018-10-26T12:39:41+07:00
tags: ["fdf", "fede", "djfkjkd"]
categories: ["gaming",'hello']
---
```

### Post Description
To edit the description of the post, edit the params of the post's front matter. This is optional. If no description is set, the site will run.
```
---
title: "LibreHealth Radiology"
date: 2018-10-26T13:54:30+07:00
image: "radiology2.jpg"
description: "A description on the technology of LibreHealth Radiology"
---
```


## Index Page
### Carousel
The content used in the frontpage carousel is pulled directly from the data/carousel directory of the site. 
To turn on carousel, add the following line to the config file's params.

```
[params]
    carouselon = false
```

The file should be in toml, yaml or json and specify the following as a data:
title: Title of the carousel slide
description: Description of the carousel slide
image: Url relative to /static dir which will be displayed on the slide

```
title: "LibreHealth EHR"
description:
    The LibreHealth EHR application is a clinically-focused electronic health record (EHR) system designed to be both easy to use "out of the box" and also customizable for use in a variety of health care settings.
image: "img/carousel/librehealth-EHR.png"
```

### Showcase
To choose the showcased post, set showcase as its relative URL in the params of the site's config file.

```
[params]
    showcase = "/posts/librehealth-radiology"
```

### Blog Description
On the index page of the site, there will be a description of the site. To set this, set the blogdescription variable in the params of the config file.
```
[params]
    blogdescription = "Read new stories, follow our project"
    siteDescription = "The Blog of LibreHealth. Read new stories, follow our project"
```

## Navbar
### Logo
The logo in the navbar has to specified in the params of the config file. Eg. IN TOML
``` 
[params]
    logo = "logo.png"
```

### Menus
The Menus of the navbar is specified in the config file of the site. To add menus to the navbar, specify the menus under 
[[menu.main]] in the config file. If the menu does not have any children, specify content in the following format. The urls MUST BE ABSOLUTE.
```
[[menu.main]]
    name = "Home"
    url  = "librehealth.io"
    weight = 1
```
If the section does have children, specify the content in this format. 
```
[[menu.main]]
    name = "Projects"
	identifier = "projects"
    url  = "../projects/"
    weight = 2

    [[menu.main]]
        name = "LibreHealth Radiology"
        parent = "projects"
        identifier="lh-radiology"
        url = "../projects/lh-radiology"
        pre = "fa fa-heartbeat"
```
## Social Media
The 4 social medias supported are twitter, github, gitlab and linkedin. To make sure that social media buttons link to the website, specify the links in the params of the config file. 

```
IN TOML
[params]
    twitter = "https://twitter.com/librehealthio?lang=en"
    github = "https://github.com/LibreHealthIO"
    gitlab = "https://gitlab.com/librehealth"
    linkedin = "https://www.linkedin.com/company/librehealth"*
```

## Footer
The two things which are important about the footer is the copyright text and the about description.
These are specified in the params of the config file.

```
[params]
    copyrighttext = "2014 LibreHealth Copyright"
    footerabout = "LibreHealth is collaborative community for free & open source software projects in Health IT, and is a member project of Software Freedom Conservancy."
```

## Parallax
On all blog posts, there will be a parallax which contains an image. To add the image to the parallax, specify the url of the image in the params of the config file. Specify by using the url RELATIVE to the static folder in the bannerimage parameter.

```
[params]
    bannerimage = "bannerimage.png
```


## Open Graph
When the blog will be shared, there will be a description of the website, to set this, change the siteDescription parameter. of the blog config
```
[params]
    siteDescription = "The Blog of LibreHealth. Read new stories, follow our project"
```
To set the default image shown on the website, set shareLogo in the param to the relative of the image (from the static folder)
```
[params]
    shareLogo = "share-logo.png" 
```

