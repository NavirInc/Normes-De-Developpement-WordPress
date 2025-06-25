> [!WARNING]
> This document is currently under development. Suggestions for improvements are welcome.

# DEVELOPMENT STANDARDS FOR WORDPRESS

We aim to deliver lean websites to our clients, which means they should be fast, easy to edit, and easy to maintain over the long term. Also, to facilitate the maintenance of multiple sites, we want them to be programmed uniformly as much as possible. These desires obviously impact the choice of technologies and working methods.

The goal of this guide is therefore to provide clear guidelines to the programmer.

## WORDPRESS THEME
The WordPress theme is custom-built based on the [Lunchpad](https://github.com/NavirInc/Launchpad) starter theme. This starter theme is developed internally and is inspired, among other things, by the [underscores](https://underscores.me/) starter theme. 

### Componnent
Website sections that are used or likely to be used in multiple locations must be programmed as components. This modular approach ensures code reusability, maintainability, and consistency across the site.

### Visual builder
No visual builders are used; all code is written manually to ensure full control and optimization.


## PROGRAMMING LANGUAGES
The theme should be developed, to the extent that is reasonable, using vanilla HTML, CSS, and JavaScript without the use of additional frameworks or libraries.

Certain features, however, may justify the use of third-party libraries. These libraries must be well established, have a history of updates, and be approved by the agency.

All code must be exclusively in English (comments, variables, classes, etc.).

### HTML
Use semantic HTML tags.

### CSS
The CSS stylesheet is written using Sass and following the principles in this [CSS Naming Convention](css-naming-convention.md). The use of libraries such as Bootstrap or Tailwind should be avoided.

The *style.scss* file must be placed in the *src/scss/* folder. The file is then compiled, minified and placed in the theme's base folder using the command below.

```sass src/scss/style.scss style.min.css --style compressed --no-source-map```

*Both files are uploaded to the server.*

### JavaScript
The use of jQuery and other frameworks should be avoided. Some library for specific functionality may be used with the agency's approbation.

The main JavaScript file is placed in the *src/js/* folder. The file is then minified and placed in the *assets/js/* folder using the command below.

```terser src/js/main.js --output assets/js/main.min.js --compress --mangle```

*Both files are uploaded to the server.*

####  Approved libraries
These JavaScript libraries can be used.

- [**GSAP**](https://gsap.com/) (premium) - Animation 
- [**Splide**](https://splidejs.com/) - Slider/carousel


## WORDPRESS PLUGIN GUIDELINES
The use of third-party extensions is minimized. By default, the following extensions are used:
- **Meta Box AIO** (premium) – MetaBox.io
- **SEOPress Pro** (premium) – The SEO Guys at SEOPress
- **Classic Editor** – Contributeurs WordPress
- **Contact Form 7** – Takayuki Miyoshi
- **Flamingo** – Takayuki Miyoshi
- **Beautiful and responsive cookie consent** (premium) - Beautiful Cookie Banner

As needed, the following extensions can be used:
- **Polylang** – WP SYNTEX
- **WooCommerce** - Automattic

If additional extensions are needed, they must be approved by the agency.


## PERFORMANCE
We aim for a site that adheres to established standards in terms of performance, accessibility, best practices and SEO. Unless otherwise specified, the site must achieve 100% scores in Google Lighthouse audits.


### Accessibility
The site must adhere to best practices in terms of accessibility.

### Compatibility
The site must be supported by all major browsers in current use today. Support for older browsers such as Internet Explorer is not required.

### Responsive
The site should look aesthetically pleasing on all screens, giving the impression that it was designed for the screen it is displayed on, regardless of its width.

Since different sections of a site adapt differently to screen widths, different breakpoints can be specified for each of them.


### Pictures
#### SVG
When possible, graphic elements (logo, icon, texture, shape, etc.) must be served in vector format (SVG) to ensure a clear rendering.


#### WEBP
Photos and images must be served in WEBP format.

### Fonts
Whenever possible, the fonts used should be included in the theme for hosting on the server.

## LICENSES
TBD

## CODE REPOSITORY
Code version control must be managed using a Git repository on GitHub. Developers are responsible for committing their code at regular intervals to ensure effective version control and, where applicable, facilitate collaboration.

The code repository will be created by the agency.

In some cases, the agency may contribute to the development of specific features, such as integrating tracking code. The developer will be notified accordingly.

## DEPLOYMENT
All theme files are committed to the Git repository and manually uploaded to the production server. Currently, the agency does not use automatic deployment.


## ROLE DISTRIBUTION
### Agency
At the project beginning, the agency will provide the developer with the following:
- Development server with admin access (Hosting, FTP, PHPmyadmin, etc.)
- WordPress installation with necessary plugins installed
- Git repository with base theme
- Required libraries and licenses
- Figma mockup of the complete website
- Images exported to WEBP and SVG formats
- Text content

After development, the agency will be responsible for the following tasks:
- Configuration and integration of Google Tag Manager
- Configuration of Google Search Console
- Configuration and integration of SMTP account
- Integration of Meta titles and Meta descriptions
- Redirection of old URLs
- Deployment of the website on the client's server


### Web developer
The developer is responsible for the following tasks:
- Programming the custom theme
- Performance optimization