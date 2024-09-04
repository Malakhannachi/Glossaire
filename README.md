# GLOSSAIRE

- [Général](#général)
- [Front-end](#front-end)
- [UX / UI](#ux-ui)
- [Architecture](#architecture)
- [Modélisation / Base de données](#modélisation---base-de-données)
- [Symfony](#symfony)
- [Sécurité](#sécurité)
- [RGPD](#rgpd)
- [SEO](#seo)
- [Gestion de projets / DevOps](#gestion-de-projets---devops)
- [English](#english)

## Général
1.	Quel est l’environnement à installer pour exécuter un script PHP ? Citer 2 exemples de logiciels permettant ce conte
   - laragon et VScode
     
3.	Qu’est-ce qu’un algorithme ?
      - Un algorithme est une série d'étapes claires et précises que l'on suit pour résoudre un problème ou accomplir une tâche
        
4.	Qu’est-ce qu’une variable ? Par quel symbole est préfixée une variable en PHP ?
   - Une variable est un espace de stockage temporaire où l'on peut garder des informations, En PHP, les variables sont par le symbole $.

5.	Qu’est-ce que la portée d’une variable ?
  - La portée d'une variable est la zone de code où elle a été déclarée.

6.	Qu’est-ce qu’une constante ? Quelle est la différence avec une variable ?
  - Constante : Sa valeur est fixe et ne peut pas être modifiée après sa définition.
  -  une constante reste la même, alors qu'une variable peut changer tout au long du programme.

7.	Qu’est-ce qu’une superglobale, combien en existent-ils et donner un exemple d’utilisation 
 - Une superglobale est une variable spéciale en PHP qui est toujours disponible partout dans le script, sans avoir besoin de la déclarer ou de la passer en argument. Il existe 9 superglobales en PHP : $_Get, $_Post, $_REQUEST, $_SESSION, $_COOKIE, $_FILES, $_ENV, $_SERVER, $_GLOBALS

8.	Quels sont les différents types (primitifs) que l’on peut associer à une variable en PHP ? Les citer et en donner des exemples (ne pas oublier le type d’une variable sans valeur)
  -En PHP, les variables peuvent être associées à différents types de données. Voici les principaux types primitifs avec des exemples simples :
    Entier (Integer) :
    Description : Un nombre entier, sans décimales.
    Exemple : $age = 25;
    Flottant (Float) :
    Description : Un nombre avec des décimales.
    Exemple : $prix = 19.99;
    Chaîne de caractères (String) :
    Description : Une séquence de caractères, comme du texte.
    Exemple : $nom = "Marie";
    Booléen (Boolean) :
    Description : Une valeur qui peut être soit true (vrai) soit false (faux).
    Exemple : $estConnecte = true;
    Tableau (Array) :
    Description : Une liste de valeurs, qui peuvent être de n'importe quel type.
    Exemple : $fruits = array("pomme", "banane", "orange");
    Objet (Object) :
    Description : Une instance d'une classe, qui peut contenir des données et des méthodes.
    Exemple : $utilisateur = new Utilisateur();
  	NULL :
    Description : Indique l'absence de valeur ou une variable sans valeur assignée.
    Exemple : $variable = null;

10.	Existe-t-il plusieurs types de tableaux en PHP, si oui lesquels ?
    -Oui, en PHP, il existe deux types principaux de tableaux :Tableau indexé est Un tableau où les éléments sont accessibles via des indices numériques
   	et Tableau associatif est Un tableau où les éléments sont accessibles via des clés nommées (strings) plutôt que des indices numériques .

12.	Quelles sont les différentes structures de contrôles qu’il existe en algorithmie ? Donner un exemple pour chacune d’entre elles
    -En algorithmie, les structures de contrôle sont des mécanismes qui permettent de gérer le flux d'exécution d'un programme. Voici les principales structures de contrôle     avec des exemples simples :
   	If-Else : Pour exécuter du code conditionnellement.
   	Exemple : if ($age > 18) {
            echo "Adulte";
        } else {
            echo "Mineur";
        }

   	For : Pour répéter du code un nombre fixe de fois.
   	Exemple : for ($i = 0; $i < 5; $i++) {
            echo $i; // Affiche 0, 1, 2, 3, 4
              }
    While : Pour répéter du code tant qu'une condition est vraie.
   	Exemple : $i = 0;
              while ($i < 5) {
                  echo $i; // Affiche 0, 1, 2, 3, 4
                  $i++;
              }
    Do-While : Pour répéter du code au moins une fois, puis continuer selon une condition.
   	Exemple : $i = 0;
                do {
                    echo $i; // Affiche 0, 1, 2, 3, 4
                    $i++;
                } while ($i < 5);
    Switch : Pour choisir entre plusieurs options basées sur la valeur d'une variable.
   	Exemple : $jour = "Lundi";
              switch ($jour) {
                  case "Lundi":
                      echo "Début de la semaine";
                      break;
                  case "Vendredi":
                      echo "Fin de la semaine";
                      break;
                  default:
                      echo "Jour normal";
              }

14.	Quelle est la fonction PHP permettant de demander la longueur d’une chaîne de caractères ?
  -La fonction strlen() renvoie le nombre de caractères dans la chaîne donnée.

15.	Qu’est-ce qu’une session ? Quelle fonction permet de démarrer une session en PHP ? Donner un exemple d’utilisation en PHP
 -Une session est un mécanisme qui permet de stocker des informations pour un utilisateur tout au long de sa visite sur un site web. Ces informations peuvent être utilisées pour garder l'utilisateur connecté , Fonction pour démarrer une session :session_start()
Exemple : <?php
          // Démarrer la session
          session_start();
          
          // Stocker une valeur dans la session
          $_SESSION['nom'] = 'Alice';
          
          // Accéder à la valeur stockée
          echo $_SESSION['nom']; // Affiche 'Alice'
          ?>

17.	Qu’est-ce qu’un cookie ? Donner un exemple d’utilisation en PHP
  - Un cookie est un petit fichier stocké sur l'ordinateur de l'utilisateur par le navigateur, qui permet de conserver des informations entre les visites sur un site web.       Les cookies sont souvent utilisés pour mémoriser des préférences, des identifiants de connexion, ou des données de session.
    Exemple : <?php
            // Créer un cookie qui expire dans 1 heure
            setcookie("utilisateur", "Alice", time() + 3600);
            
            // Vérifier si le cookie est défini
            if (isset($_COOKIE["utilisateur"])) {
                echo "Bonjour, " . $_COOKIE["utilisateur"]; // Affiche 'Bonjour, Alice'
            }
            ?>

18.	Quelle est la différence entre les instructions « require » et « include » en PHP
  - la différence entre les instructions "require" et "include" en PHP est "include " Inclut un fichier mais continue en cas d'erreur et "require" nclut un fichier et       
   arrête le script en cas d'erreur

19.	Comment effectuer une redirection en PHP ?
  - Pour effectuer une redirection en PHP, on utilise l'instruction header(). Cela nous permet de rediriger  vers une autre page

20.	Définir la partie « front-end » et « back-end » d’une application
  - Front-end : La partie visible et interactive que vous voyez dans votre navigateur.
  -Back-end : La partie cachée qui gère les données et la logique de l'application.

21.	Définir le contrôle de version ? Qu’est-ce que Git ?
  - Contrôle de version : Système pour suivre et gérer les modifications apportées aux fichiers d'un projet.
  - Git : Un outil populaire pour le contrôle de version, permettant de gérer les versions du code et de collaborer avec d'autres.

22.	Qu’est-ce qu’un CMS ? Citer au moins 2 exemples
    - Un CMS (Content Management System) est un logiciel qui permet de créer, gérer et publier du contenu sur un site web sans avoir besoin de compétences techniques    
     approfondies.
      Exemples :
      WordPress : CMS populaire pour créer des blogs et des sites web avec une interface utilisateur simple.
      Joomla : CMS flexible utilisé pour des sites web variés, des blogs aux sites d'entreprise.
## Front-end
18.	Définir HTML
  -HTML (HyperText Markup Language) est un Langage qui organise et affiche le contenu d'une page web.

19.	Définir CSS
  - CSS (Cascading Style Sheets) est un langage utilisé pour styliser et mettre en forme les pages web.

20.	Définir Javascript
   - JavaScript est un Langage qui rend les pages web interactives et dynamiques.

21.	Définir JSON. Dans quel contexte ce format est-il utilisé ? 
   - JSON est un Format pour échanger des données, souvent utilisé dans les échanges entre serveurs et applications web.

22.	Peut-on interpréter du Javascript côté serveur ? Si oui, comment ?
  - Oui, il est possible d'interpréter du JavaScript côté serveur. Cela se fait principalement avec Node.js, qui est un environnement d'exécution pour JavaScript permettant    d'exécuter des scripts JavaScript sur le serveur, en dehors du navigateur.

23.	Qu’est-ce qu’un sélecteur CSS ?
  - Sélecteur CSS est identifie les éléments HTML auxquels appliquer des styles.

24.	Quelle balise HTML permet de créer un lien hypertexte ?
  - La balise HTML qui permet de créer un lien hypertexte est <a>

25.	Qu’est-ce qu’une requête AJAX ?
  -Requête AJAX est une Technique pour envoyer et recevoir des données sans recharger la page.

26.	Quel sélecteur CSS permet de sélectionner tous les éléments d’une classe spécifique ? D’un identifiant spécifique ?
  - Sélecteur de classe : Utilise un point '.' suivi du nom de la classe.
  - Sélecteur d'identifiant : Utilise un dièse '#' suivi du nom de l'identifiant.

27.	Définir le responsive design
  -Responsive design est une conception de sites web qui s'adaptent automatiquement aux différentes tailles d'écran et appareils.

28.	Qu’est-ce que le templating ?
  - Templating est un Technique qui sépare le design d'une page web de son contenu pour faciliter la création de pages dynamiques et cohérentes

29.	Qu’est-ce qu’une fonction anonyme en Javascript ?
 - Une fonction anonyme en JavaScript est une fonction qui n'a pas de nom, Elle est souvent utilisée pour des tâches temporaires

30.	Quelle méthode JavaScript est utilisée pour ajouter un élément à la fin d'un tableau ?
 - La méthode JavaScript utilisée pour ajouter un élément à la fin d'un tableau est push().

31.	Qu’est-ce qu’un « media query » ?
  - Media query est un Technique CSS pour appliquer des styles différents selon les caractéristiques de l'appareil, comme la taille de l'écran.

32.	Qu’est-ce qu’un pseudo élément en CSS ?
   - Pseudo-élément : Sélectionne et stylise des parties spécifiques d'un élément, comme le premier caractère ou une ligne avant ou après le contenu.

33.	Qu’est-ce que Bootstrap ? Donner d’autres exemples équivalent
  - Bootstrap est un Framework CSS pour concevoir rapidement des sites web avec des styles et des composants préconçus

34.	Quand un formulaire HTML est créé, quelles sont les 2 méthodes qui peuvent lui être associées ? Donner la différence entre ces 2 méthodes
  -  Lorsqu'un formulaire HTML est créé, les deux méthodes qui peuvent lui être associées sont GET : Les données sont envoyées dans l'URL, visible et limitées en taille et
  POST : Les données sont envoyées dans le corps de la requête, pas visible et sans limite stricte de taille.

## UX UI
35.	Quelle est la différence entre UX Design et UI Design ?
  -UX Design : Se concentre sur l'expérience et la facilité d'utilisation du produit.
  - UI Design : Se concentre sur l'apparence visuelle et les éléments interactifs de l'interface.

36.	Qu’est-ce qu’un wireframe ? 
    - Wireframe est un Schéma de la structure d'une page, montrant la disposition des éléments sans design détaillé.

37.	Qu’est-ce qu’un prototype ? 
   - Prototype : Version préliminaire d'un produit pour tester et valider des concepts avant la version finale

38.	Qu’est-ce que la hiérarchie visuelle en UI Design ?
  - Hiérarchie visuelle : Organisation des éléments d'une interface pour guider l'utilisateur et rendre le contenu facile à comprendre et à naviguer

39.	Qu’est-ce que l’accessibilité en UX Design ? 
  - Accessibilité en UX Design se réfère à la conception d'interfaces pour qu'elles soient utilisables par tout le monde, y compris les personnes avec des handicaps.

40.	Qu’est-ce qu’une grille de mise en page ?
  - Grille de mise en page est un Système de lignes pour organiser et aligner le contenu sur une page de manière structurée.

41.	Qu’est-ce que la notion d’affordance en UX Design ?
  - Affordance : Caractéristique d'un élément d'interface qui indique comment il doit être utilisé, par son design et ses caractéristiques visuelles.

42.	Qu’est-ce qu’un « mobile first design » ?
  - Mobile first design : Conception d'abord pour les appareils mobiles, puis adaptation pour les écrans plus grands.

IV. Programmation orientée objet (POO)
43.	Donner une définition de la programmation orientée objet 
  - La programmation orientée objet est une approche où les données et les comportements sont regroupés en objets. Ces objets sont des instances de classes, qui définissent     leurs caractéristiques et leurs actions. Cela permet de structurer le code de manière plus modulaire et réutilisable.

44.	Qu’est-ce qu’une classe ? Comment la déclare-t-on ?
  - une classe est une structure qui définit des attributs et des méthodes pour créer des objets. On la déclare avec le mot-clé class
    Exemple : class NomDeLaClasse {
                public $attribut1;
                public $attribut2;
            
                public function __construct($attribut1, $attribut2) {
                    $this->attribut1 = $attribut1;
                    $this->attribut2 = $attribut2;
                }
            
                public function methode() {
                    // Code de la méthode
                }
            }

45.	Qu’est-ce qu’un objet ?
  - Un objet est une instance d'une classe, contenant des données et des méthodes associées

46.	Définir la notion de propriété / attribut / méthode
  - Propriété / Attribut : C’est une variable définie dans une classe qui stocke des données ou des caractéristiques d'un objet.
  - Méthode : C’est une fonction définie dans une classe qui décrit les comportements ou les actions qu'un objet peut réaliser.

47.	Qu’est-ce que la visibilité d’une propriété ou d’une méthode ? Citer les différents types de visibilité
  - La visibilité détermine qui peut accéder à une propriété ou méthode :
    Public : Accessible de partout.
   Protected : Accessible seulement depuis la classe et ses sous-classes.
   Private : Accessible uniquement depuis la classe elle-même.

48.	Quelle est la méthode spécifique utilisée pour créer un nouvel objet à partir d’une classe ?
  - Pour créer un nouvel objet à partir d'une classe, on utilise un constructeur, une méthode spéciale définie pour initialiser l'objet.

49.	Qu’est-ce que l’encapsulation ?
  - L'encapsulation est la pratique de regrouper les données et les méthodes dans une classe et de contrôler l'accès à ces données en utilisant des niveaux de visibilité          (public, protected, private). Cela protège les données et simplifie l'interaction avec les objets

50.	Que signifie « étendre une classe » ? Quelle est le concept clé mis en œuvre ? Donner un exemple
  - Étendre une classe signifie créer une nouvelle classe qui hérite des attributs et des méthodes d'une classe existante. Le concept clé est l'héritage, qui permet à une 
   sous-classe (ou classe dérivée) de réutiliser et d'étendre les fonctionnalités d'une superclasse
  Exemple : class Animal {
             public function parler() {
                 return "L'animal fait un bruit.";
             }
         }
         
         class Chien extends Animal {
             public function aboyer() {
                 return "Le chien aboie.";
             }
         }
         
         $monChien = new Chien();
         echo $monChien->parler(); // Héritée de la classe Animal
         echo $monChien->aboyer(); // Méthode spécifique à Chien

51.	Définir l’opérateur de résolution de portée
  - L'opérateur de résolution de portée :: permet d'accéder aux membres statiques d'une classe ou d'un espace de noms. Par exemple, Classe::membre en PHP

52.	Définir une méthode / propriété statique
  - Une méthode ou propriété statique appartient à la classe elle-même plutôt qu’à ses instances, et est accessible via le nom de la classe

53.	Définir le polymorphisme en POO
  - Le polymorphisme permet à des objets de types différents d’être traités de manière uniforme en utilisant une interface commune, souvent grâce à des méthodes avec le même nom mais des implémentations différentes

54.	Définir une méthode / classe abstraite ?
  -Méthode abstraite : Déclaration sans implémentation dans une classe abstraite, à définir dans les sous-classes.
  - Classe abstraite : Classe qui ne peut pas être instanciée directement, servant de modèle pour d’autres classes.

55.	Définir le chaînage de méthodes
  - Le chaînage de méthodes est une technique où les méthodes d'un objet renvoient l'objet lui-même (ou un autre objet) pour permettre des appels de méthodes successifs sur 
  la même ligne de code. Cela permet d'exécuter plusieurs opérations en une seule expression fluide

56.	Qu’est-ce que la méthode __toString() ? Existe-t-il d’autres méthodes « magiques »
  - 
La méthode __toString() permet de définir la représentation en chaîne d'un objet lorsqu'il est utilisé comme une chaîne.

Autres méthodes magiques en PHP :

__construct(): Constructeur
__destruct(): Destructeur
__get(): Accès aux propriétés
__set(): Définition des propriétés
__call(): Appel des méthodes non définies
__callStatic(): Appel des méthodes statiques non définies
__isset(): Vérification des propriétés
__unset(): Suppression des propriétés
__clone(): Clonage
__invoke(): Appel d'un objet comme fonction

57.	Qu’est-ce qu’un « autoload » ?
  - L'autoload est une fonctionnalité qui charge automatiquement les classes nécessaires sans avoir à inclure manuellement leurs fichiers. En PHP, cela se fait généralement     avec spl_autoload_register().

58.	Comment appelle-t-on en français les « getters » et les « setters » ?
  - En français, les "getters" sont appelés "accesseurs" et les "setters" sont appelés "mutateurs".
   Accesseurs : Méthodes utilisées pour obtenir la valeur d'un attribut privé ou protégé d'une classe.
   Mutateurs : Méthodes utilisées pour définir ou modifier la valeur d'un attribut privé ou protégé d'une classe

59.	Qu’est-ce que la sérialisation en PHP ? 
  - La sérialisation en PHP convertit un objet ou une structure complexe en une chaîne de caractères pour le stocker ou le transmettre, puis le reconvertit en utilisant 
  serialize() et unserialize().
## Architecture 
60.	Qu’est-ce que l’architecture client / serveur ? Grâce à quel type de requête peut-on interroger le serveur. Définir l’acronyme de ce type de requête. Si on ajoute un « S » à cet acronyme, expliquer la différence
     - L'architecture client/serveur est un modèle où le client (l'utilisateur ou l'application) envoie des requêtes au serveur (qui fournit des ressources ou des services) 
   via un réseau. Le serveur traite ces requêtes et renvoie les réponses au client.
   
   Pour interroger le serveur, on utilise principalement des requêtes HTTP (Hypertext Transfer Protocol).
   
   HTTP : Protocole pour les requêtes et les réponses entre le client et le serveur.
   Acronyme :
   
   HTTP (Hypertext Transfer Protocol) : Protocole standard utilisé pour la communication web.
   Ajout d'un « S » :
   
   HTTPS (Hypertext Transfer Protocol Secure) : Version sécurisée de HTTP, utilisant le chiffrement SSL/TLS pour protéger les données échangées entre le client et le serveur.

61.	Donner la définition d’un design pattern. Citer au moins 3 exemples de design pattern
  - Un design pattern est une solution réutilisable à un problème de conception récurrent en développement logiciel.
   Exemples :
   Singleton : Assure une seule instance d'une classe.
   Observer : Notifie automatiquement les objets dépendants d'un changement d'état.
   Factory Method : Crée des objets sans spécifier la classe concrète.

62.	Qu’est-ce que l’architecture MVC ?
  - L'architecture MVC (Model-View-Controller) est un modèle de conception qui sépare une application en trois composants Model, View, Controller.

63.	Quel est le rôle de chaque couche du design pattern MVC : Model, View, Controller ?
  - Model (Modèle) : Gère les données et la logique métier de l'application. Il récupère, stocke et manipule les données, et peut inclure des règles de validation.

  - View (Vue) : Présente les données au utilisateur. Elle est responsable de l'affichage des informations et de la génération de l'interface utilisateur.

  - Controller (Contrôleur) : Gère les interactions de l'utilisateur. Il reçoit les entrées de l'utilisateur, traite les demandes (en interagissant avec le modèle) et met à 
   jour la vue en conséquence.

64.	Quels sont les avantages de l’architecture MVC ?
  - L'architecture MVC sépare les données (Model), l'affichage (View) et la logique de contrôle (Controller), offrant une meilleure modularité, testabilité et maintenance 
   du code.

65.	Existe-t-il des variantes à l’architecture MVC ?
  - Oui, plusieurs variantes et extensions de l'architecture MVC existent, chacune adaptée à des besoins spécifiques

66.	Qu’est-ce qu’une API ? Définir l’architecture REST
  - API : Interface qui permet à des applications de communiquer entre elles en définissant des règles et des méthodes d'échange de données.
  - REST : Architecture pour les services web utilisant HTTP, avec des principes comme l'absence d'état (stateless), une interface uniforme, et l'utilisation de méthodes       HTTP (GET, POST, PUT, DELETE) pour interagir avec des ressources identifiées par des URL.

## Modélisation - Base de données
67.	Qu’est-ce que la modélisation de données ? Définir la méthode Merise
68.	Quelles sont les 3 étapes principales de la méthode Merise ? 
a.	Analyse, conception et réalisation
b.	Planification, exécution et contrôle
c.	Création, modification et suppression
69.	Qu’est-ce qu’un modèle conceptuel de données (MCD) en Merise ?
70.	Qu’est-ce qu’un modèle logique de données (MLD) en Merise ?
71.	Donner la définition des mots suivants :
a.	Entité
b.	Relation
c.	Cardinalité
d.	Clé primaire / clé étrangère
72.	Que devient une relation de type « Many To Many » dans le modèle logique de données ?
73.	Qu’est-ce qu’une base de données ?
74.	Définir les notions suivantes : 
a.	SQL
b.	MySQL
c.	SGBD (donner 2 exemples de SGBD)
75.	Dans une base de données, les données sont stockées dans des ___. Celles-ci sont constituées de lignes appelées ___ et de colonnes appelées ___
76.	Quelle est la différence entre une base de données relationnelle et non relationnelle ?
77.	Qu’est-ce qu’une jointure dans une base de données ? En existe-t-il plusieurs ? Si oui lesquelles ?
78.	A quoi sert une vue dans une base de données ?
79.	Qu’est-ce que l’intégrité référentielle dans une base de données ?
80.	Quelles sont les fonctions d’agrégation en SQL ?
81.	Qu’est-ce qu’un CRUD dans le contexte d’une base de données ?
82.	Quelles sont les clauses qui permettent de :
a.	Insérer un nouvel enregistrement dans une table
b.	Modifier un enregistrement dans une table
c.	Supprimer un enregistrement dans une table
d.	Supprimer la base de données
e.	Filtrer les résultats d’une requête SQL
f.	Trier les résultats d’une requête SELECT
g.	Regrouper les résultats d'une requête SELECT en fonction d'une colonne spécifique
h.	Concaténer 2 chaînes de caractères 
83.	Comment se connecter à une base de données en PHP ? Quelle est la classe native utilisée ?

## Symfony
84.	Qu’est-ce que Symfony ?
85.	Sur quel langage de programmation et design pattern repose Symfony ? 
86.	Quelle est la dernière version en date de Symfony ?
87.	Qu’est-ce qu’un bundle ? 
88.	Quel est le moteur de template utilisé par défaut dans Symfony ?
89.	Qu’est-ce qu’un ORM ? Quel est son utilité et comment s’appelle-t-il au sein de Symfony ?
90.	Qu’est-ce que l’injection de dépendances ? Quel est l’outil utilisé dans ce contexte et quel fichier contient l’intégralité des dépendances du projet ?
91.	Que permet le bundle Maker au sein de Symfony ? 
92.	Quel est le langage de requêtage exploité au sein d’un projet Symfony ?
93.	Quel est le composant qui garantit l’authentification et l’autorisation des utilisateurs ?

## Sécurité
94.	Qu’est-ce que l’injection SQL ? Comment s’en prémunir ?
95.	Qu’est-ce que la faille XSS ? Comment s’en prémunir ?
96.	Qu’est-ce que la faille CSRF ? Comment s’en prémunir ?
97.	Définir l’attaque par force brute et l’attaque par dictionnaire
98.	Existe-t-il d’autres failles de sécurité ? Citer celles-ci et expliquer simplement leur comportement
99.	A quoi servent l’authentification et l’autorisation dans un contexte d’application web ?
100.	Définir la notion de hachage d’un mot de passe et citer des algorithmes de hachage
101.	Qu’est-ce qu’une politique de mots de passe forts ?
102.	Qu’est-ce que l’hameçonnage ?
103.	Définir la « validation des entrées »

## RGPD
104.	Qu’est-ce que le RGPD ?
105.	Quel est son objectif principal ?
106.	Quelle est la date d’entrée en vigueur du RGPD ?
107.	Quelles sont les sanctions possibles en cas de non-respect du RGPD ?
108.	En France, quel est l’autorité administrative qui s’occupe de faire appliquer le RGPD ?
109.	Quel est le consentement valide selon le RPGD ?
110.	Qu’est-ce qu’une politique de confidentialité ?
111.	Quelle est la durée de conservation maximale des données personnelles selon le RGPD ?
112.	Quels sont les droits des utilisateurs selon le RGPD ?
113.	Qu’est-ce que le principe de minimisation des données selon le RGPD ?

## SEO
114.	Qu’est-ce que le SEO ? 
115.	Quel est l’objectif principal du SEO ?
116.	Existe-t-il plusieurs types de référencement ? Lesquels ?
117.	Qu’est-ce que la densité de mots-clés en SEO ?
118.	Qu’est-ce qu’une balise « alt » ?
119.	Qu’est-ce que la balise « meta description » ?
120.	Qu’est-ce que le « nofollow » en SEO ?
121.	Quelle est l'importance du contenu de qualité pour le référencement d'un site web ?
122.	Pourquoi est-il important d'utiliser des balises de titre (h1, h2, h3, etc.) de manière structurée ?
123.	Quelle est la recommandation pour les URL d'un site web bien référencé ?
124.	Qu'est-ce que le maillage interne et pourquoi est-il important pour le référencement ?
125.	Qu'est-ce que l'optimisation des images pour le référencement ?
126.	Qu'est-ce qu'un plan de site (sitemap) et pourquoi est-il important pour le référencement ?

## Gestion de projets - DevOps
127.	Qu’est-ce que la gestion de projet ?	
128.	Qu’est-ce qu’une méthode Agile de gestion de projet ? 
129.	Expliquer la méthode MoSCoW en quelques lignes et citer ses avantages
130.	A quoi sert la méthodologie MVP ? Citer les caractéristiques clés
131.	Qu’est-ce que la planification itérative ?
132.	Citer 3 méthodes Agiles dans le cadre d’un projet informatique
133.	Qu’est-ce qu’une réunion de revue de projet ?
134.	Qu’est-ce qu’un livrable dans un projet ? 
135.	Quels sont les 3 piliers SCRUM ? Définir chacun d’entre eux
136.	Qu’est-ce que le DevOps et quel est son objectif principal ?
137.	Qu’est-ce que l’intégration continue ? 
138.	Qu’est-ce que Docker ? Et en quoi est-il utile dans le cadre du DevOps ?
139.	Qu’est-ce qu’un test unitaire ? 
140.	Quelle est l'unité de code testée lors d'un test unitaire ?
141.	Quelles sont les caractéristiques d'un bon test unitaire ?
142.	Qu'est-ce qu'une assertion dans un test unitaire ?
 
## English
1)	What does JavaScript enable you to do on a website ?
a.	Add interactive behavior and dynamic content
b.	Define the layout and design of web pages
c.	Handle server-side operations
2)	Which programming language is primarily used for server-side web development ?
a.	PHP
b.	JavaScript
c.	HTML
3)	What is the purpose of a web browser ?
a.	To render and display web pages
b.	To execute serve-side code
c.	To manage databases
4)	What is the difference between GET and POST methods in HTTP ?
a.	GET retrieves data from a server, while POST submits data to a server
b.	GET submits data to a server, while POST retrieves data from a server
c.	GET and POST methods are interchangeable
5)	What is the purpose of version control systems (e.g., Git) in web development ?
a.	To track changes and manage collaborative development
b.	To optimize website loading speed
c.	To handle server-side scripting
6)	What is the purpose of a framework in web development ?
a.	To provide a structured environment for building web applications
b.	To handle network protocols and data transfer
c.	To create visual designs and layouts for websites
7)	What does NoSQL stand for ?
a.	Not Only SQL
b.	Non-Structured Query Language
c.	New Object-Oriented Language
8)	Which of the following is a characteristic of NoSQL databases ?
a.	Strict schema enforcement
b.	Support for complex transactions
c.	Scalability and flexible data models
