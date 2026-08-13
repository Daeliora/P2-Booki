# Booki

Intégration responsive de la plateforme **Booki**, un site de planification de vacances permettant de consulter des hébergements et des activités à Marseille.

Ce projet a été réalisé à partir de maquettes fournies pour les versions **desktop, tablette et mobile**, avec pour objectif de reproduire fidèlement l’interface tout en respectant les contraintes d’intégration HTML et CSS du projet.

## Aperçu

Booki propose une interface permettant de :

* consulter une sélection d’hébergements ;
* parcourir les hébergements les plus populaires ;
* découvrir des activités à Marseille ;
* utiliser une barre de recherche et des filtres ;
* naviguer rapidement entre les sections « Hébergements » et « Activités ».

La page HTML met notamment en place le header, la recherche, les filtres, les cartes d’hébergements, les contenus populaires et la section activités.

> **Remarque :** la recherche et les filtres constituent une première version d’interface et ne sont pas reliés à une logique de recherche réelle. Les cartes utilisent actuellement `href="#"` afin de simuler leur caractère cliquable.

## Objectifs du projet

Le travail consistait à transformer les maquettes UI en une interface web cohérente, responsive et conforme aux spécifications fournies.

Les principales contraintes étaient :

* utiliser **HTML et CSS** ;
* ne pas utiliser de framework CSS ;
* respecter les maquettes desktop, tablette et mobile ;
* utiliser une structure HTML sémantique ;
* produire un code valide selon les validateurs W3C ;
* assurer la compatibilité avec les dernières versions de Chrome et Firefox.

## Fonctionnalités

### Navigation

Le header contient le logo Booki ainsi qu’un menu permettant d’accéder directement aux sections **Hébergements** et **Activités** grâce aux ancres HTML.

L’effet de survol du menu est réalisé avec le pseudo-élément CSS `::before`, permettant de conserver un HTML propre tout en gérant la barre bleue décorative directement en CSS.

### Recherche

La zone de recherche comprend :

* une icône de localisation ;
* un champ de saisie ;
* un bouton « Rechercher » ;
* une adaptation en version mobile avec une icône loupe.

La recherche est volontairement non fonctionnelle dans cette version du projet : elle sert à valider l’intégration de l’interface.

### Filtres

Quatre filtres sont proposés :

* **Économique**
* **Familial**
* **Romantique**
* **Nos pépites**

Un effet de survol modifie leur apparence. Là encore, les filtres sont visuels et ne déclenchent pas de recherche réelle.

### Hébergements

La section « Hébergements à Marseille » présente des cartes contenant :

* une image ;
* le nom de l’établissement ;
* le prix par nuit ;
* une notation.

Chaque carte est conçue pour être entièrement cliquable, conformément aux spécifications.

### Les plus populaires

Une section dédiée aux hébergements les plus populaires permet de présenter une sélection complémentaire sous forme de cartes horizontales.

### Activités

La section « Activités à Marseille » est construite avec **CSS Grid** afin de reproduire la disposition en quatre colonnes imposée par la maquette desktop.

Ce choix permet notamment de gérer simplement les espacements entre les cartes grâce à la propriété `gap`.

## Responsive Design

L’intégration repose sur trois catégories d’affichage :

| Support  | Résolution         |
| -------- | ------------------ |
| Desktop  | `> 1024 px`        |
| Tablette | `768 px à 1024 px` |
| Mobile   | `< 768 px`         |

La largeur maximale de l’interface est fixée à **1440 px**, avec une largeur minimale de **320 px**.

### Adaptations tablette

Sur tablette :

* les hébergements occupent toute la largeur ;
* la section « Populaires » passe sous les hébergements ;
* les cartes populaires sont réorganisées horizontalement ;
* les cartes de la section activités sont redimensionnées ;
* le footer est adapté à l’espace disponible.

### Adaptations mobile

Sur mobile :

* le header est réorganisé verticalement ;
* la navigation occupe toute la largeur ;
* la barre de navigation passe sous le menu ;
* le bouton « Rechercher » devient une icône loupe ;
* les filtres passent sur plusieurs lignes ;
* l’ordre des sections « Populaires » et « Hébergements » est adapté ;
* les cartes d’hébergement passent sur une colonne ;
* la section activités devient verticale ;
* le footer passe lui aussi en disposition verticale.

## Technologies utilisées

* **HTML5**
* **CSS3**
* **Flexbox**
* **CSS Grid**
* **Media Queries**
* **Font Awesome**
* **Google Fonts — Raleway**

Le projet repose volontairement uniquement sur HTML et CSS, conformément aux contraintes initiales.

## Charte graphique

Les couleurs principales du projet sont centralisées dans des variables CSS :

```css
:root {
    --main-color: #0065FC;
    --main-bg-color: #F2F2F2;
    --filter-bg-color: #DEEBFF;
}
```

### Couleurs

* **Bleu principal** : `#0065FC`
* **Bleu clair** : `#DEEBFF`
* **Gris de fond** : `#F2F2F2`

### Typographie

* **Raleway**

La centralisation des couleurs dans `:root` facilite la maintenance et permet de conserver une charte graphique cohérente dans l’ensemble du projet.

## Structure du projet

```text
P2-Booki/
├── css/
│   └── style.css
├── images/
│   ├── activites/
│   ├── hebergements/
│   └── logo/
├── index.html
└── README.md
```

Le dépôt est actuellement public sur GitHub, avec `master` comme branche par défaut.

## Installation

Aucune dépendance particulière n’est nécessaire pour lancer le projet.

```bash
git clone https://github.com/Daeliora/P2-Booki.git
cd P2-Booki
```

Il suffit ensuite d’ouvrir `index.html` dans un navigateur récent ou d’utiliser un serveur local.

## Bonnes pratiques appliquées

Le projet met en œuvre plusieurs principes d’intégration :

* utilisation de balises HTML sémantiques ;
* utilisation de classes CSS pour cibler les éléments ;
* centralisation des couleurs dans des variables CSS ;
* limitation de la duplication des styles ;
* utilisation d’attributs `alt` pour les images ;
* prise en compte de l’accessibilité pour les informations de notation.

## Validation

Le projet avait pour objectif de respecter les validateurs **W3C HTML et CSS** et d’être compatible avec les dernières versions de **Google Chrome** et **Mozilla Firefox**.

## Retour sur le projet

Ce projet a permis de travailler concrètement sur la transformation d’une maquette UI en interface web responsive.

Les principaux défis ont concerné notamment :

* l’alignement précis des cartes ;
* la gestion des filtres et de la barre de recherche ;
* la navigation entre les sections ;
* l’adaptation de la mise en page aux différents écrans ;
* la conservation d’une architecture cohérente au fur et à mesure de l’intégration.

Une évolution importante dans la méthode de travail a été de commencer par poser l’architecture globale avant d’affiner chaque section. Cette approche permet d’éviter de devoir refaire des parties déjà intégrées lorsqu’elles ne s’accordent pas avec le reste du projet.

## Statut

**Projet d’intégration front-end finalisé**

Interface responsive disponible pour :

* Desktop
* Tablette
* Mobile

## Auteur

**Elodie**

Projet réalisé dans le cadre du projet d’intégration **Booki**.

### Repository

https://github.com/Daeliora/P2-Booki

