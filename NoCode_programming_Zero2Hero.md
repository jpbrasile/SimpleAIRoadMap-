Programmer en no code est la nouvelle façon de programmer mais encore faut-il le faire de façon professionnelle. 
- Cela est aujourd'hui possible avec des LLM comme gpt-4o (125 k de contexte) ou Sonnet-3.5 (200 k de contexte)
- Un [dialogue avec chatGPT](https://chatgpt.com/c/410d9165-1dea-4c6d-b042-0fcfd5cb00cf) nous a conduit a y prvenir!
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
