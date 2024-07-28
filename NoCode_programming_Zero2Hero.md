Programmer en no code est la nouvelle façon de programmer mais encore faut-il le faire de façon professionnelle. 
- Cela est aujourd'hui possible avec des LLM comme gpt-4o (125 k de contexte) ou Sonnet-3.5 (200 k de contexte)
- Un [dialogue avec chatGPT](https://chatgpt.com/c/8a7525a8-1722-4f2e-b43d-63bc1ebd7972) nous a conduit a y prvenir!
  - Pour qu'un logiciel soit considéré comme professionnel, plusieurs fonctionnalités et caractéristiques essentielles doivent être présentes, garantissant qualité, sécurité, évolutivité et maintenabilité.

  - **Authentification et Autorisation**
Le logiciel utilise Flask-Login pour gérer les sessions utilisateur, permettant l'inscription, la connexion et la déconnexion sécurisées. Les mots de passe sont stockés de manière sécurisée avec un hachage. La gestion des rôles et des permissions assure un contrôle précis de l'accès aux différentes parties de l'application.

  - **API RESTful** (Echange sécurisé)
Une API RESTful est implémentée pour interagir avec les données utilisateurs, facilitant la création, la lecture, la mise à jour et la suppression des informations. Les communications se font via JSON, rendant les échanges de données efficaces et standardisés.

  - **Pages de Contenu et Templates**
Les pages statiques (home, about, contact) sont intégrées avec des templates Jinja2, permettant une séparation claire entre le contenu et la présentation. Les Blueprints sont utilisés pour organiser les routes de manière modulaire, améliorant ainsi la maintenabilité du code.

  - **Intégration AJAX**
L'application intègre AJAX pour permettre des interactions dynamiques sans nécessiter de rechargement de page, améliorant ainsi l'expérience utilisateur. Les formulaires peuvent être soumis et les données récupérées de manière asynchrone, rendant l'application plus réactive.

  - **Formulaires Sécurisés**
Flask-WTF est utilisé pour créer des formulaires sécurisés, incluant une protection contre les attaques CSRF (Cross-Site Request Forgery). La validation des entrées utilisateur prévient les attaques XSS (Cross-Site Scripting) et les erreurs de saisie.

  - **Gestion de la Base de Données**
SQLAlchemy est utilisé pour l'ORM (Object-Relational Mapping), simplifiant les interactions avec la base de données. Flask-Migrate gère les migrations de schéma de base de données, facilitant les mises à jour et les modifications structurées. Un fichier de données initiales permet de peupler la base de données avec des informations de départ.

  - **Structure de Projet Modulaire**
Le projet est structuré de manière claire et modulaire, avec une séparation des préoccupations (modèles, vues, contrôleurs), ce qui améliore la lisibilité et la maintenabilité du code.

  - **Tests Unitaires**
      -  Des tests unitaires sont inclus pour vérifier le bon fonctionnement des différentes parties de l'application, assurant la fiabilité et facilitant la détection de bugs.

- Ces fonctionnalités et caractéristiques font de ce logiciel Flask une application professionnelle, répondant aux standards de qualité, de sécurité et de maintenabilité


## Création des pages statiques 
- Elles maquettent le site pour chacune de ses pages en incluant le fond, la forme et un début d'interactivité (étant statique, on ne peut pas "sauter" sur d'autres pages ni stocker ou récupérer des données).
- Elles peuvent être réalisées de façon interactive avec l'artefact de Sonnet ou avec le prompt adéquat de GPT4o :
  - `Je veux pouvoir télécharger un fichier html statique qui fait ....`
 
## une fois les pages statiques de notre application finale figée le LLM pren en charge la production du code avec le prompt :
  - Voici le prompt système formaté comme demandé, sous forme de string incluant du code markdown entre triples guillemets :

Prompt système pour générer une application Flask professionnelle
Vous devez générer une application Flask professionnelle basée sur les fichiers HTML initiaux et les données initiales pour la base de données fournis. L'application doit être structurée et inclure les fonctionnalités essentielles garantissant la qualité, la sécurité, l'évolutivité et la maintenabilité. Suivez les instructions et fournissez les fichiers nécessaires pour construire l'application. Assurez-vous que le résultat final est un fichier ZIP complet contenant tous les répertoires et fichiers requis.
Fichiers HTML initiaux :

home.html
about.html
contact.html
login.html
register.html

Données initiales pour la base de données :
sqlCopyINSERT INTO users (username, password_hash) VALUES ('testuser', 'hashedpassword');
INSERT INTO items (name, description) VALUES ('Item1', 'Description of item 1');
Structure et fonctionnalités requises
L'application doit avoir la structure et les fonctionnalités suivantes :

my_flask_app/<br>
│<br>
├── app/<br>
│   ├── __init__.py<br>
│   ├── models.py<br>
│   ├── routes/<br>
│   │   ├── __init__.py<br>
│   │   ├── main.py<br>
│   │   ├── api.py<br>
│   │   └── auth.py<br>
│   ├── static/<br>
│   │   ├── css/<br>
│   │   │   └── styles.css<br>
│   │   ├── js/<br>
│   │   │   └── scripts.js<br>
│   ├── templates/<br>
│   │   ├── base.html<br>
│   │   ├── home.html<br>
│   │   ├── about.html<br>
│   │   ├── contact.html<br>
│   │   ├── login.html<br>
│   │   └── register.html<br>
│   ├── auth/<br>
│   │   ├── __init__.py<br>
│   │   ├── forms.py<br>
│   │   └── models.py<br>
│<br>
├── data/<br>
│   ├── initial_db_data.sql<br>
│<br>
├── tests/<br>
│   ├── __init__.py<br>
│   ├── test_models.py<br>
│   ├── test_routes.py<br>
│   ├── test_forms.py<br>
│   └── test_auth.py<br>
│<br>
├── migrations/<br>
│<br>
├── .gitignore<br>
├── .env_example<br>
├── config.py<br>
├── requirements.txt<br>
├── run.py<br>
├── run_tests.py<br>
├── init_db.py<br>
└── README.md<br>

- Contenu détaillé des fichiers
  - Générez le contenu de chaque fichier en suivant les meilleures pratiques de développement Flask et en incluant toutes les fonctionnalités nécessaires pour une application web professionnelle. Assurez-vous d'implémenter :

    - Une structure modulaire utilisant des Blueprints
    - L'authentification et l'autorisation des utilisateurs
    - Des points de terminaison API RESTful
    - L'intégration AJAX
    - Des formulaires sécurisés avec protection CSRF
    - Des migrations de base de données avec Flask-Migrate
    - Des tests unitaires

- Instructions spécifiques

  - Utilisez Flask-SQLAlchemy pour la gestion de la base de données
  - Implémentez Flask-Login pour la gestion de l'authentification
  - Utilisez Flask-WTF pour la gestion des formulaires
  - Incluez des commentaires pertinents dans le code
  - Assurez-vous que l'application suit les meilleures pratiques de sécurité
  - Créez un fichier README.md détaillé avec les instructions d'installation et d'utilisation

- Sortie
  - Générez un fichier ZIP nommé my_flask_app.zip contenant la structure de projet complète avec tous les fichiers listés ci-dessus. Assurez-vous que tous les fichiers sont correctement organisés dans leurs répertoires respectifs.
