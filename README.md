# NORMES DE DÉVELOPPEMENT - WORDPRESS

Nous souhaitons livrer à nos clients des sites web « lean » qui sont en d’autres mots, rapides, faciles à modifier et faciles à maintenir sur le long terme. Pour faciliter l’entretient de plusieurs sites sur le long terme, nous désirons qu’ils soient, dans la mesure du possible, programmés de façon uniforme. Ces désirs impact évidemment le choix des technologies et des méthodes de travail.
L’objectif de ce guide est donc de fournir des directives claires au programmeur.

## THÈME WORDPRESS
Le thème WordPress est programmé sur mesure à partir du thème de départ Launchpad. Ce thème est développé à l’interne et il est entre autres inspiré du thème underscores.
Launchpad et les indications pour l’utiliser sont disponibles ici : TBD

## LANGAGES DE PROGRAMMATION
Le thème doit être développé, dans la mesure de ce qui est raisonnable, en utilisant les langages HTML, CSS et Javascript dans leur forme de base, sans l'utilisation de frameworks ou de bibliothèques supplémentaires.
Certaines fonctionnalités peuvent toutefois justifier l'utilisation de bibliothèques tierces. Cependant, ces bibliothèques doivent être bien établies, avoir un historique de mises à jour et être approuvées par l'agence.
Le code doit exclusivement être en anglais (commentaires, variables, classes, etc.).

### HTML
Utiliser les balises sémantiques

### CSS
La feuille de style CSS doit être programmée en suivant les principes ci-bas. L’utilisation de librairie tel que Boostrap ou Tailwind est proscrite.

[CSS Naming Convention](css-naming-convention.md)

https://www.york.ac.uk/pattern-library/about/css.html
https://csswizardry.com/2015/03/more-transparent-ui-code-with-namespaces/
https://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/

### Javascript
Les animations sont programmées à l’aide des librairies GSAP

## EXTENSIONS WORDPRESS
Le recours à des extensions tierces est réduit au minimum. Par défaut, les extensions suivantes sont utilisées :
Meta Box – MetaBox.io
SEOPress Pro – The SEO Guys at SEOPress
Classic Editor – Contributeurs WordPress
Contact Form 7 – Takayuki Miyoshi
Flamingo – Takayuki Miyoshi
Cookie

Selon le besoin, les extensions suivantes peuvent être utilisées :
Polylang – WP SYNTEX

Si des extensions supplémentaires sont nécessaires, elles devront être approuvées par l’agence avant leurs utilisations.


## PERFORMANCE
Nous visons un site qui respecte les standards établis en termes de performance, de référencement et d’accessibilité.
À moins d’exception, le site doit obtenir des résultats de 100% dans l’audit Ligthouse de Google.
SEO

### Accessibilité

### Compatibilité
Le site doit être supporté par tous les navigateurs principaux en utilisation aujourd’hui. Le support pour les anciens navigateurs tel qu’Internet Explorer n’est cependant pas requis.

### Responsive
Le site doit être esthétique sur l’ensemble des écrans, il doit donner l’impression d’avoir été conçu pour l’écran sur laquelle il est affiché, peu importe ça largeur.
Comme les différentes sections d’un site s’adaptent différemment aux largeurs d’écran, des « breakpoints » différents peuvent être spécifiées pour chacune d’elles.

### Animations

### Images
#### SVG
Lorsque possible, les éléments graphiques (logo, icone, texture, forme, etc.) doivent être servies en format vectoriel (SVG) pour assurer un rendu net.

#### WEBP
Les photos et images doivent être servie en format WEBP.
JPEG fallback?
https://stackoverflow.com/questions/77886808/htaccess-deliver-jpg-or-png-if-browser-does-not-accept-webp


https://kinsta.com/blog/wordpress-image-sizes/

### Police
Lorsque possible, les polices utilisées doivent être comprise dans le thème pour être hébergé sur le serveur.

## CONTRÔLE DES VERSIONS DU CODE
La gestion des versions du code doit être assuré sur un répertoire Git sur GitHub. Le développeur est responsable de commettre son code à intervalle régulier pour assurer un contrôle des versions efficaces et, le cas échéant, faciliter la collaboration.
Dans certain cas, l’agence peut contribuer au développement de certaines fonctionnalités précises tel que l’intégration de code de suivi. Le développeur en sera alors avisé.

### Déploiement automatique
https://felipeelia.dev/ftp-no-more-deploying-wordpress-sites-with-github-actions/

## DISTRIBUTION DES RÔLES
### Agence
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

### Développeur
Le développeur est responsable des tâches suivantes :
- Programmation du Thème personnalisé