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
   - Pour exécuter un script PHP il faut un serveur Apache . les logiciels sont laragon et WAMP ( Windows ).
     
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
 - Une superglobale est une variable spéciale en PHP qui est toujours disponible partout dans le script, sans avoir besoin de la déclarer ou de la passer en argument. Il existe 9 superglobales en PHP : 
 $_GET : Récupère les données envoyées via l'URL (méthode GET).
$_POST : Récupère les données envoyées via un formulaire (méthode POST).
$_REQUEST : Combine les données des superglobales $_GET, $_POST, et $_COOKIE.
$_FILES : Gère les fichiers téléchargés via un formulaire.
$_SESSION : Stocke les données utilisateur pour maintenir une session.
$_COOKIE : Contient les cookies envoyés par le navigateur.
$_SERVER : Fournit des informations sur le serveur et l'environnement d'exécution.
$_ENV : Contient les variables d'environnement.
$_GLOBALS : Accède à toutes les variables globales du script.
$_PHP_SELF : Renvoie le chemin du fichier actuellement exécuté.

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
La modélisation de données consiste à organiser et représenter les données d’un système pour montrer comment elles sont liées, souvent avec des schémas. Cela aide à créer et gérer les bases de données plus facilement.
La méthode Merise est une méthode d'analyse et de conception de systèmes d'information. Elle permet de modéliser les données et les traitements d'une application en séparant deux aspects : le modèle conceptuel (données) et le modèle organisationnel (traitements). Utilisée surtout pour la conception de bases de données, Merise emploie des diagrammes (comme les MCD, Modèle Conceptuel de Données) pour représenter les entités, les relations et les processus du système. Cette méthode est couramment utilisée pour structurer et formaliser le développement de projets informatiques.
69.	Quelles sont les 3 étapes principales de la méthode Merise ? 
a.	Analyse, conception et réalisation X
b.	Planification, exécution et contrôle
c.	Création, modification et suppression
70.	Qu’est-ce qu’un modèle conceptuel de données (MCD) en Merise ?
 MCD : Représentation abstraite des données et de leurs relations.
71.	Qu’est-ce qu’un modèle logique de données (MLD) en Merise ?
MLD : Détails sur la structure des données sous forme de tables et de colonnes, prêt pour la mise en œuvre.
72.	Donner la définition des mots suivants :
a.	Entité
Un objet ou concept identifiable dans un système, comme un client ou un produit.
b.	Relation
Un lien entre deux ou plusieurs entités, montrant comment elles interagissent.
c.	Cardinalité
Le nombre d'occurrences d'une entité associées à une autre dans une relation, indiquant des types de relations (un à un, un à plusieurs, etc.).
d.	Clé primaire / clé étrangère
Clé primaire : Identifie uniquement chaque enregistrement dans une table.
Clé étrangère : Lien vers la clé primaire d'une autre table, établissant une relation entre elles.
74.	Que devient une relation de type « Many To Many » dans le modèle logique de données ?
Dans le modèle logique de données (MLD), une relation de type « Many To Many » devient généralement une table d'association ou table de jointure. Cette table contient des clés étrangères qui font référence aux clés primaires des deux entités impliquées dans la relation.
75.	Qu’est-ce qu’une base de données ?
Une base de données est un système organisé pour stocker et gérer des données, permettant d'y accéder et de les manipuler facilement.
76.	Définir les notions suivantes : 
a.	SQL (Structured Query Language) est un langage utilisé pour gérer et manipuler des bases de données relationnelles.
b.	MySQL est un SGBD relationnel open source qui utilise SQL, souvent utilisé pour des applications web
c.	SGBD (donner 2 exemples de SGBD)
Un SGBD (Système de Gestion de Bases de Données) est un logiciel pour créer et gérer des bases de données.
Exemples :
PostgreSQL
Oracle Database
77.	Dans une base de données, les données sont stockées dans des tables. Celles-ci sont constituées de lignes appelées enregistrements et de colonnes appelées attributs.
78.	Quelle est la différence entre une base de données relationnelle et non relationnelle ?
79.	Qu’est-ce qu’une jointure dans une base de données ? En existe-t-il plusieurs ? Si oui lesquelles ?
Une jointure dans une base de données est une opération qui combine des lignes de deux ou plusieurs tables basées sur une condition de correspondance, généralement une clé primaire et une clé étrangère. Les jointures permettent d'extraire des données liées dans une seule requête.

Types de jointures
Il existe plusieurs types de jointures, notamment :

Jointure interne (INNER JOIN) : Récupère uniquement les lignes qui ont des correspondances dans les deux tables.

Jointure externe : Peut être subdivisée en trois types :

Jointure externe gauche (LEFT JOIN) : Récupère toutes les lignes de la table de gauche et les lignes correspondantes de la table de droite. Si aucune correspondance n'est trouvée, les résultats de la table de droite contiendront des valeurs NULL.
Jointure externe droite (RIGHT JOIN) : Récupère toutes les lignes de la table de droite et les lignes correspondantes de la table de gauche. Si aucune correspondance n'est trouvée, les résultats de la table de gauche contiendront des valeurs NULL.
Jointure externe complète (FULL JOIN) : Récupère toutes les lignes des deux tables, avec des valeurs NULL pour les lignes qui n'ont pas de correspondance dans l'autre table.
Jointure croisée (CROSS JOIN) : Produit le produit cartésien des deux tables, c'est-à-dire toutes les combinaisons possibles de lignes des deux tables.
80.	A quoi sert une vue dans une base de données ?
Une vue dans une base de données est une table virtuelle qui affiche le résultat d'une requête SQL.
81.	Qu’est-ce que l’intégrité référentielle dans une base de données ?
 l'intégrité référentielle aide à maintenir la cohérence et la fiabilité des données dans une base de données relationnelle.
82.	Quelles sont les fonctions d’agrégation en SQL ?
les fonctions d'agrégation permettent de résumer et d'analyser les données dans une base de données.
83.	Qu’est-ce qu’un CRUD dans le contexte d’une base de données ?
Un CRUD dans une base de données désigne les quatre opérations fondamentales pour manipuler les données :
Create : Ajouter des données (insertion).
Read : Lire des données (consultation).
Update : Mettre à jour des données (modification).
Delete : Supprimer des données.
Ces opérations sont essentielles pour gérer efficacement les données dans les applications.
84.	Quelles sont les clauses qui permettent de :
a.	Insérer un nouvel enregistrement dans une table: INSERT INTO
b.	Modifier un enregistrement dans une table: UPDATE
c.	Supprimer un enregistrement dans une table:DELETE
d.	Supprimer la base de données: DROP DATABASE
e.	Filtrer les résultats d’une requête SQL: WHERE
f.	Trier les résultats d’une requête SELECT: ORDER BY
g.	Regrouper les résultats d'une requête SELECT en fonction d'une colonne spécifique:GROUP BY
h.	Concaténer 2 chaînes de caractères : CONCAT()
85.	Comment se connecter à une base de données en PHP ? Quelle est la classe native utilisée ?
Pour se connecter à une base de données en PHP, vous pouvez utiliser la classe PDO (PHP Data Objects) ou mysqli (MySQL Improved).
Classe native utilisée
PDO : Idéale pour travailler avec plusieurs types de bases de données.
mysqli : Spécifique à MySQL.
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
L'injection SQL est une attaque où un pirate insère des commandes SQL malveillantes dans les champs d'entrée d'une application web pour manipuler la base de données.
Comment s'en protéger :
Requêtes préparées : Utiliser des requêtes paramétrées pour séparer le code SQL des données.
Échapper les entrées : Utiliser des fonctions qui échappent les caractères spéciaux dans les entrées utilisateur.
Valider les entrées : Restreindre les données soumises par l'utilisateur (types, formats).
Limiter les privilèges : Réduire les permissions des comptes de la base de données.
Utiliser un ORM : Les ORM génèrent des requêtes SQL sécurisées automatiquement.
95.	Qu’est-ce que la faille XSS ? Comment s’en prémunir ?
La faille XSS (Cross-Site Scripting) permet à un attaquant d'injecter du code malveillant dans une page web, qui s'exécute ensuite dans le navigateur des utilisateurs, compromettant leurs données.
Comment s'en protéger :
Échapper les entrées utilisateur : Traiter toutes les données avant de les afficher.
Valider les entrées : Limiter les données acceptées à des formats précis.
Utiliser des en-têtes de sécurité : CSP, HttpOnly et Secure pour les cookies.
Sanitiser les données : Nettoyer les données soumises.
Utiliser des frameworks sécurisés : React, Angular, etc.
Désactiver le HTML là où il n'est pas nécessaire.

96.	Qu’est-ce que la faille CSRF ? Comment s’en prémunir ?
La faille CSRF (Cross-Site Request Forgery) permet à un attaquant de forcer un utilisateur authentifié à exécuter des actions non souhaitées sur un site web à son insu.
Comment s'en protéger :
Jetons CSRF : Ajouter des jetons uniques aux formulaires et requêtes sensibles.
Vérification du Referer ou Origin : S'assurer que la requête provient du bon site.
Limiter la durée de session : Réduire le temps d'authentification.
Cookie SameSite : Empêcher l'envoi des cookies vers des sites externes.
MFA : Ajouter une authentification multifactorielle pour des actions critiques.

97.	Définir l’attaque par force brute et l’attaque par dictionnaire
Force brute : Teste toutes les combinaisons possibles.
Dictionnaire : Teste une liste de mots de passe courants.

98.	Existe-t-il d’autres failles de sécurité ? Citer celles-ci et expliquer simplement leur comportement
oui il existe des nombreuses autres failles :
Déni de service (DoS) : Surcharge un serveur pour le rendre indisponible.

Man-in-the-Middle (MITM) : Interception des communications entre deux parties pour voler des données.

Escalade de privilèges : Un utilisateur obtient des permissions non autorisées.

Phishing : Tromperie pour obtenir des informations sensibles via des messages frauduleux.

Configuration de sécurité : Mauvaises configurations exploitables par les attaquants.

Injection de commandes : Exécution de commandes système via des entrées non sécurisées.

Ransomware : Logiciel qui chiffre des données et exige une rançon pour les déchiffrer.

Zero-day : Vulnérabilité inconnue exploitée avant qu'un correctif soit disponible.

Buffer Overflow : Écriture excessive dans un espace mémoire, permettant l'exécution de code malveillant

99.	A quoi servent l’authentification et l’autorisation dans un contexte d’application web ?
Authentification : Vérifie qui vous êtes.
Autorisation : Détermine ce que vous pouvez faire

100.	Définir la notion de hachage d’un mot de passe et citer des algorithmes de hachage
Le hachage de mots de passe est une technique essentielle pour sécuriser les informations d'identification des utilisateurs. L'utilisation d'algorithmes de hachage robustes et adaptés, comme bcrypt, scrypt ou Argon2, est recommandée pour protéger les mots de passe contre les attaques.

101.	Qu’est-ce qu’une politique de mots de passe forts ?
Une politique de mots de passe forts est essentielle pour réduire le risque de compromission des comptes utilisateurs. En encourageant les bonnes pratiques de création et de gestion des mots de passe, les organisations peuvent protéger les données sensibles et renforcer la sécurité globale de leur système.

102.	Qu’est-ce que l’hameçonnage ?
L’hameçonnage est une menace sérieuse pour la sécurité des données personnelles et financières, et la vigilance est essentielle pour s'en protége

103.	Définir la « validation des entrées »
La validation des entrées est une pratique essentielle pour sécuriser les applications et assurer l'intégrité des données. Elle doit être mise en œuvre de manière rigoureuse tant côté client que côté serveur pour maximiser la protection contre les menaces potentielles.

## RGPD
104.	Qu’est-ce que le RGPD ?
Le RGPD est une réglementation européenne qui protège les données personnelles des citoyens en imposant des règles strictes aux entreprises sur leur collecte et utilisation.
105.	Quel est son objectif principal ?
L'objectif principal du RGPD est de protéger les données personnelles et de donner aux citoyens plus de contrôle sur leurs informations
106.	Quelle est la date d’entrée en vigueur du RGPD ?
Le RGPD est entré en vigueur le 25 mai 2018.
107.	Quelles sont les sanctions possibles en cas de non-respect du RGPD ?
En cas de non-respect du RGPD, les sanctions peuvent être sévères et incluent :
En cas de non-respect du RGPD, les sanctions peuvent être sévères et incluent :

Amendes : Jusqu'à 20 millions d'euros ou 4 % du chiffre d'affaires mondial annuel de l'entreprise, selon le montant le plus élevé.
Avertissements : En cas de première infraction sans dommage important.
Interdiction temporaire ou définitive de traiter des données.
Obligation de rectifier ou supprimer des données.
Poursuites judiciaires : Les individus concernés peuvent également engager des actions en justice pour obtenir des réparations.
Amendes : Jusqu'à 20 millions d'euros ou 4 % du chiffre d'affaires mondial annuel de l'entreprise, selon le montant le plus élevé.
Avertissements : En cas de première infraction sans dommage important.
Interdiction temporaire ou définitive de traiter des données.
Obligation de rectifier ou supprimer des données.
Poursuites judiciaires : Les individus concernés peuvent également engager des actions en justice pour obtenir des réparations.
108.	En France, quel est l’autorité administrative qui s’occupe de faire appliquer le RGPD ?
En France, l'autorité administrative chargée de faire appliquer le RGPD est la CNIL (Commission Nationale de l'Informatique et des Libertés). La CNIL veille à la protection des données personnelles et au respect des droits des citoyens en matière de vie privée. Elle peut également sanctionner les entreprises en cas de non-respect du RGPD
109.	Quel est le consentement valide selon le RPGD ?
Selon le RGPD, un consentement valide doit être libre, spécifique, éclairé, univoque et facilement révocable
110.	Qu’est-ce qu’une politique de confidentialité ?
Une politique de confidentialité est un document qui explique comment une entreprise ou une organisation collecte, utilise, stocke et protège les données personnelles de ses utilisateurs. Elle informe également les utilisateurs de leurs droits concernant leurs données et des mesures prises pour assurer leur sécurité. Cette politique est essentielle pour garantir la transparence et la conformité avec des réglementations comme le RGPD.
111.	Quelle est la durée de conservation maximale des données personnelles selon le RGPD ?
Selon le RGPD, les données personnelles doivent être conservées uniquement aussi longtemps que nécessaire pour les finalités pour lesquelles elles sont traitées
112.	Quels sont les droits des utilisateurs selon le RGPD ?
Selon le RGPD, les utilisateurs ont les droits suivants concernant leurs données personnelles :

Droit d'accès
Droit de rectification
Droit à l'effacement
Droit à la limitation du traitement
Droit à la portabilité des données
Droit d'opposition
Droit de ne pas faire l'objet d'une décision automatisée
113.	Qu’est-ce que le principe de minimisation des données selon le RGPD ?
Le principe de minimisation des données selon le RGPD exige que seules les données personnelles nécessaires soient collectées et conservées, afin de réduire les risques pour la vie privée
## SEO
114.	Qu’est-ce que le SEO ? 
Le SEO (Search Engine Optimization) est l'ensemble des techniques visant à améliorer la visibilité d'un site web dans les résultats des moteurs de recherche pour attirer du trafic organique.
115.	Quel est l’objectif principal du SEO ?
L'objectif principal du SEO est d'augmenter la visibilité d'un site web dans les résultats des moteurs de recherche afin d'attirer un trafic organique de qualité.
116.	Existe-t-il plusieurs types de référencement ? Lesquels ?
Oui, il existe plusieurs types de référencement, principalement :

SEO (Search Engine Optimization) : Optimisation pour les moteurs de recherche afin d'améliorer le classement organique d'un site web.

SEA (Search Engine Advertising) : Publicité sur les moteurs de recherche, comme Google Ads, qui permet de payer pour apparaître en haut des résultats.

SMO (Social Media Optimization) : Optimisation des contenus sur les réseaux sociaux pour augmenter leur visibilité et engagement.

SEM (Search Engine Marketing) : Marketing sur les moteurs de recherche, englobant le SEO et le SEA.

Référencement local : Optimisation pour apparaître dans les résultats de recherche locaux, souvent utilisée par les entreprises ayant une présence physique
117.	Qu’est-ce que la densité de mots-clés en SEO ?
La densité de mots-clés en SEO est le pourcentage de fois qu'un mot-clé apparaît dans un texte par rapport au nombre total de mots. Elle aide à évaluer l'optimisation du contenu pour les moteurs de recherche. Une densité idéale se situe généralement entre 1 et 3 %.
118.	Qu’est-ce qu’une balise « alt » ?
Une balise « alt » est un attribut HTML qui décrit le contenu d'une image. Elle améliore l'accessibilité pour les utilisateurs malvoyants, aide au référencement des images par les moteurs de recherche, et s'affiche en cas de problème de chargement de l'image.
119.	Qu’est-ce que la balise « meta description » ?
La balise « meta description » est un élément HTML qui résume le contenu d'une page web et apparaît dans les résultats des moteurs de recherche. Elle incite les utilisateurs à cliquer sur le lien, bien qu'elle n'affecte pas directement le classement SEO. Il est conseillé de la limiter à 150-160 caractères.
120.	Qu’est-ce que le « nofollow » en SEO ?
Le « nofollow » est un attribut HTML qui indique aux moteurs de recherche de ne pas suivre un lien et de ne pas transmettre d'autorité à la page cible. Il est souvent utilisé pour contrôler le référencement, réduire le spam dans les commentaires et gérer les liens payants.
121.	Quelle est l'importance du contenu de qualité pour le référencement d'un site web ?
Le contenu de qualité est essentiel pour le référencement car il améliore le classement dans les moteurs de recherche, engage les utilisateurs, génère des backlinks, optimise les mots-clés et favorise la fidélisation des visiteurs
122.	Pourquoi est-il important d'utiliser des balises de titre (h1, h2, h3, etc.) de manière structurée ?
Utiliser des balises de titre de manière structurée améliore la lisibilité, aide au référencement et optimise l'expérience utilisateur en clarifiant la hiérarchie du contenu
123.	Quelle est la recommandation pour les URL d'un site web bien référencé ?
our des URL bien référencées, il est recommandé de :

Être claires et pertinentes.
Inclure des mots-clés.
Être simples et courtes.
Utiliser des tirets pour séparer les mots.
Éviter les paramètres excessifs.
124.	Qu'est-ce que le maillage interne et pourquoi est-il important pour le référencement ?
Le maillage interne est la structure des liens entre les pages d'un site web. Il est important pour le référencement car il améliore l'indexation, répartit l'autorité des pages, optimise l'expérience utilisateur et augmente le temps passé sur le site.
125.	Qu'est-ce que l'optimisation des images pour le référencement ?

L'optimisation des images pour le référencement consiste à améliorer les images d'un site en utilisant des balises « alt », en compressant les fichiers, en utilisant des noms de fichiers descriptifs, en choisissant des formats appropriés et en incluant les images dans les sitemaps. Cela améliore la visibilité, réduit le temps de chargement et offre une meilleure expérience utilisateur.
126.	Qu'est-ce qu'un plan de site (sitemap) et pourquoi est-il important pour le référencement ?
Un plan de site (sitemap) est un fichier XML qui liste toutes les pages d'un site web pour aider les moteurs de recherche à les indexer. Il est important pour le référencement car il améliore l'indexation, clarifie la structure du site, gère les erreurs et permet de prioriser certaines pages.
## Gestion de projets - DevOps
127.	Qu’est-ce que la gestion de projet ?	
La gestion de projet consiste à planifier, organiser et suivre les étapes nécessaires pour atteindre un objectif spécifique, tout en respectant les délais, le budget et les ressources disponibles.

128.	Qu’est-ce qu’une méthode Agile de gestion de projet ? 
La méthode Agile est une approche de gestion de projet basée sur des cycles courts appelés "sprints", qui favorise la flexibilité et l'adaptation rapide aux changements, avec des livrables fréquents et une collaboration étroite avec les parties prenantes

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
