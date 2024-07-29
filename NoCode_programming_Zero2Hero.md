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
Vous devez générer une application Flask professionnelle basée sur les fichiers HTML initiaux et les données initiales pour la base de données fournis. L'application doit être structurée et inclure les fonctionnalités essentielles garantissant la qualité, la sécurité, l'évolutivité et la maintenabilité. Suivez les instructions et fournissez les fichiers nécessaires pour construire l'application. .
Fichiers HTML initiaux : joints en attachés
Données initiales pour la base de données : incluses dans un des html
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


## Un big problème : l'IA est incontrôlée : 
Elle génère beaucoup de codes (les limites permises en tokens sont vite dépassée) et quand il y a une erreur elle en génère de nouveaux, voire écrase les anciens! 

Pourtant, comme le montre webSim.ai elel est capable de produire des sites web statique avec du html, du css et du javascript en faisant évoluer le design en fonction des remarques de l'utilisateur. Rien de mystérieux, il suffit d'ailleurs de demander à websim.ai son prompt système qu'elle nou fournit aimablement et que [Sonnet 3.5 se permet d'améliorer](https://claude.ai/chat/365bbadf-9210-4e96-99de-3146dfbaeb44)   

Les valeurs ajoutées de websim.ai par rapport à l'artefact de Sonnet sont
- d'être gratuit
- de pouvoir afficher des images dont on donne l'url (pour sonnet il faut télécharger le html pour que l'image apparaîsse)
- de pouvoir sauvegarder l'url du site ce qui la rend disponible pour tous, (et en particulier pour réaliser un site multipage)

Des solutions d'hébergement gratuit de sites statiques existent (GitHub Page par exemple) . Faire un clone de websim.ai est donc possible.

J'ai demandé es fonctionnalité d'artefact à Sonnet 3.5 (il ne veut pas donner le verbatim) . Il apparaît que deux fonctionnalité (react et mermaid) non impmémentées dans websim.ai sont disponible. Je les ai intégré dans le [system prompt final](https://claude.site/artifacts/3716969d-b5c0-4fe0-af91-62a06869b68a) qui cumule les fonctionnalité de websim et d'artefact. 
- On peut toujours améliorer le prompt pour le cas où des erreurs apparaîtraient: [prompt amélioré](https://claude.site/artifacts/b85576c3-0d24-4e7c-8416-2a2e7bfab096) après [cette erreur](https://claude.ai/chat/541a6094-780e-4b45-a92c-204d33aaff85)

## Du statique au dynamique:
- Revenons à notre objectif principal de faire du no code pour développer ue application complexe : nous avons pris le cas d'école (mais important) visant à disposer d'un outil apte à nous apprendre n'importe quel sujet.
- L'utilisation d'artefact de sonnet nous a permis de créer 3 templates pour [l'inscription](https://htmlpreview.github.io/?https://github.com/jpbrasile/images/blob/main/inscription.html), les [preférences](https://htmlpreview.github.io/?https://github.com/jpbrasile/images/blob/main/preferences.html) et [un exemple de sessions](https://htmlpreview.github.io/?https://raw.githubusercontent.com/jpbrasile/images/main/frontend_base.html)
- Avant de nous lancer dans la création de code il faut établir la façon dont nous voulons que tout cela fonctionne. Un [chat](https://chatgpt.com/c/02c9e062-35f3-4b62-b2a6-abc716af3864) nous montre le chemin. Et un [autre](https://chatgpt.com/c/87bad5b1-706d-4460-9be8-77ac048e8f1a) nous permet de créer l'arborescence via python.
- Les bugs proviennent de difficultés au llm de résoudre certains problèmes: voilà une façon de les y aider:
- When generating Flask application code:

  When generating Flask application code:

  - 1. Use a single SQLAlchemy instance defined in the app's init.py file.
  - 2. In models.py, import the db instance from the parent package, not re-declare it.
  - 3. Use relative imports within the application package (e.g., from .. import db).
  - 4. Ensure blueprint imports in init.py match the actual file structure.
  - 5. Configure the database URI in a config file, preferably loaded from environment variables.
  - 6. In test files, use the testing configuration and an in-memory SQLite database.
  - 7. Always consider the project's directory structure when writing import statements.
  - 8. Use a create_app factory function for application initialization.
  - 9. Register blueprints in the create_app function.
  - 10.Separate configuration classes (Development, Testing, Production) in a config.py file.
  - 11. Maintain a comprehensive requirements.txt file, including all direct and indirect dependencies.
  - 12. When writing tests in subdirectories, add the parent directory of the app to sys.path to ensure the app can be imported correctly.
  - 13. Use absolute imports for app modules in test files located in subdirectories.
  - 14. Consider using a setup.py file to make your app installable and resolve import issues.
  - 15. When using environment variables, ensure they are loaded before the app configuration (consider using python-dotenv).
  - 16. Ensure Proper Handling of Boolean Values in Templates: When rendering boolean values in HTML templates, convert them to human-readable strings like "Enabled" or "Disabled".
  - 17. Update Tests Accordingly: When modifying how data is rendered in templates, ensure the tests are updated to reflect these changes.
  - 18. Use Descriptive Assertions: When writing assertions in tests, ensure they check for the exact output expected in the HTML response.
  - 19. Always Commit User Before Preferences or Quizzes: Ensure that the user is committed to the database before adding and committing related preferences or quizzes.
  - 20. Print Registered Routes for Debugging: If necessary, print registered routes for debugging to ensure routes are correctly set up.
  - 21. Include Detailed Comments and Print Statements in Tests: For better debugging and clarity, include detailed comments and print statements in tests.
