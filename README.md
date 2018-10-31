# lhblog-theme
Theme for LibreHealth (librehealth.io) Blog.

A Blog theme for LibreHealth's Website (librehealth.io).

## Context
- [Post](#post) 
  - [Adding Post Image](#adding-post-image) 
- [Index Page](#index-page)
  - [Carousel](#carousel)
- [Navbar](#navbar)
  - [Logo](#logo)
  - [Menus](#menus)
- [Social Media](#social-media)
- [Footer](#footer)

## Post
### Adding Post Image
To add an image to a the post, add the image to the static folder of the site and specify the directory of the image **RELATIVE TO THE STATIC FOLDER**. 
This post image will be used on the index page and as a parallax.

## Index Page
### Carousel
The content used in the frontpage carousel is pulled directly from the data/carousel directory of the site. The file should be in 
toml, yaml or json and specify the following as a data:
title: Title of the carousel slide
description: Description of the carousel slide
image: Url relative to /static dir which will be displayed on the slide

`Example:
title: "LibreHealth EHR"
description:
    The LibreHealth EHR application is a clinically-focused electronic health record (EHR) system designed to be both easy to use "out of the box" and also customizable for use in a variety of health care settings.
image: "img/carousel/librehealth-EHR.png"`

## Navbar
### Logo
The logo in the navbar has to specified in the params of the config file. Eg. IN TOML
``` 
[params]
    logo = "logo.png"
```

### Menus
The Menus of the navbar is specified in the config file of the site. To add menus to the navbar, specify the menus under 
[[menu.main]] in the config file. If the menu does not have any children, specify content in the following format.
```
[[menu.main]]
    name = "Home"
    url  = "../"
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
copyrighttext = "2014 LibreHealth Copyright"
footerabout = "LibreHealth is collaborative community for free & open source software projects in Health IT, and is a member project of Software Freedom Conservancy."
```
