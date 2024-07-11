# DEVELOPMENT STANDARDS FOR WORDPRESS

We aim to deliver lean websites to our clients, which means they should be fast, easy to edit, and easy to maintain over the long term. Also, to facilitate the maintenance of multiple sites, we want them to be programmed uniformly as much as possible. These desires obviously impact the choice of technologies and working methods.

The goal of this guide is therefore to provide clear guidelines to the programmer.

## WORDPRESS THEME
The WordPress theme is custom-built based on the Launchpad starter theme. This starter theme is developed internally and is inspired, among other things, by the [underscores](https://underscores.me/) theme. 

Launchpad and instructions for its use are available here: [Lunchpad](https://github.com/NavirInc/Launchpad)

No visual builders are used.

## PROGRAMMING LANGUAGES
The theme should be developed, to the extent that is reasonable, using vanilla HTML, CSS, and Javascript without the use of additional frameworks or libraries.

Certain features, however, may justify the use of third-party libraries. These libraries must be well-established, have a history of updates, and be approved by the agency.

All code must be exclusively in English (comments, variables, classes, etc.).

### HTML
Use semantic HTML tags.

### CSS
The CSS stylesheet is writen using Sass and following the principles in this [CSS Naming Convention](css-naming-convention.md). The use of libraries such as Bootstrap or Tailwind is prohibited.

The *style.scss* file must be placed in the *src/scss* folder. The file is then compiled and minified using the command below and placed in the theme's base folder.

```sass src/scss/style.scss style.min.css --style compressed --no-source-map```

### Javascript
Compress - TBD

The use of jQuery is prohibited.

## EXTENSIONS WORDPRESS
The use of third-party extensions is minimized. By default, the following extensions are used:
- **Meta Box AIO** (premium) – MetaBox.io
- **SEOPress Pro** (premium) – The SEO Guys at SEOPress
- **Classic Editor** – Contributeurs WordPress
- **Contact Form 7** – Takayuki Miyoshi
- **Flamingo** – Takayuki Miyoshi
- **Beautiful and responsive cookie consent** (premium) - Beautiful Cookie Banner

As needed, the following extensions can be used:
- **Polylang** – WP SYNTEX

If additional extensions are needed, they must be approved by the agency before use.

## Files handling

TBD

## PERFORMANCE
We aim for a site that adheres to established standards in terms of performance, accessibility, best pratices and SEO. Unless otherwise specified, the site must achieve 100% scores in Google Lighthouse audits.


### Accessibility
Le site doit respecter les bonnes pratiques en terme d'accessibilité.

### Compatibility
The site must be supported by all major browsers in current use today. Support for older browsers such as Internet Explorer is not required.

### Responsive
The site should look aesthetically pleasing on all screens, giving the impression that it was designed for the screen it is displayed on, regardless of its width.

Since different sections of a site adapt differently to screen widths, different breakpoints can be specified for each of them.

### Animations
Animations are programmed using the GSAP library.

### Pictures
#### SVG
When possible, graphic elements (logo, icon, texture, shape, etc.) must be served in vector format (SVG) to ensure clear rendering.

#### WEBP
Photos and images must be served in WEBP format.

For further consideration : JPEG fallback? Deliver scaled image?

[htaccess: deliver jpg or png if browser does not accept webP](https://stackoverflow.com/questions/77886808/htaccess-deliver-jpg-or-png-if-browser-does-not-accept-webp)

[Wordpress image sizes](https://kinsta.com/blog/wordpress-image-sizes/)

### Fonts
Whenever possible, the fonts used should be included in the theme for hosting on the server.

## CODE REPOSITORY
Code version control must be managed using a Git repository on GitHub. Developers are responsible for committing their code at regular intervals to ensure effective version control and, where applicable, facilitate collaboration.

The code repository will be created by the agency.

In some cases, the agency may contribute to the development of specific features, such as integrating tracking code. The developer will be notified accordingly.

### Automatic deployment
Currently, the agency does not use automatic deployment.

For further consideration :

[FTP No More: Deploying WordPress sites with GitHub Actions](https://felipeelia.dev/ftp-no-more-deploying-wordpress-sites-with-github-actions/)

## ROLES DISTRIBUTION
### Agency
Avant le début du mandat, l’agence fournira au développeur les éléments suivants.
- Serveur de développement avec accès administrateur (Hébergement, FTP, PHPmyadmin, etc.)
- Installation Wordpress avec extensions installées
- Répertoire Git avec thème de base
- Librairies et licences nécessaires
- Maquette Figma du site web complet
- Images exportées en format WEBP et SVG
- Textes

Après le développement, l’agence sera responsable des tâches suivantes :
- Configuration et intégration de Google Tag Manager
- Configuration de Google Search Console
- Configuration et intégration du compte SMTP
- Intégration des Méta-titre et Méta description
- Redirection des anciens URL
- Mise en ligne du site web sur le serveur du client

### Web developer
Le développeur est responsable des tâches suivantes :
- Programmation du Thème personnalisé

