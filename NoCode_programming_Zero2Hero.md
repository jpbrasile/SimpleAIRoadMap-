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

- Lorsque vous générez du code pour une application Flask, suivez ces étapes pour éviter les erreurs courantes :

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
    - 18. When rendering boolean values in HTML templates, convert them to human-readable strings like "Enabled" or "Disabled".
    - 19. Ensure that tests are updated to reflect any changes in how data is rendered in templates.
    - 20. Use descriptive assertions in tests to check for the exact output expected in the HTML response.
    - 21.  Always commit the user to the database before adding and committing related preferences or quizzes.
    - 22. Print registered routes for debugging if necessary.
    - 23. Include detailed comments and print statements in tests for better debugging and clarity.

## Points d'étapes

- Ne pas utiliser gpt4-o pour programmer: il est verbeux et détruit tout sur son passage: sous prétexte de résoudre une erreur il supprime allègrement des fichiers qui eux était fonctionnels.
- Le front-end peux être mis en oeuvre avec un dialogue "text2frontend" avec l'artéfact de Sonnet 3.5 (ou avec WebSim.ai qui le met en oeuvre gratuitement actuellement.
- J'ai hacké Le prompt de WebSimai, et même si le prompt équivalent de Sonnet est protégé, il nous a permis [d'améliorer ce prompt](https://claude.site/artifacts/3716969d-b5c0-4fe0-af91-62a06869b68a))
- 💡: Ni WebSim ni Aretefact ne traitent le backend car il demande les ressources d'un serveur. il est toutefois possible d'intégrer à la fin de chaque page html du frontend les directives que le backend devra suivre pour l'intégrer. Le dialogue "text2backend" [obtenu avec Sonnet](https://claude.ai/chat/401d301d-5807-4571-9d1a-758ff3fcc65f) peut donc s'établir une fois que le développeur est satisfait du front. j'ai créé un [prompt côté frontend](https://claude.site/artifacts/67e81ae2-9a7c-455f-8046-17a704926077) et un autre côtés backend ([recommendations](https://claude.site/artifacts/681b749a-17f5-4585-b3b8-770d2eda5c09) qui s'appuie sur un complément structuré, [informations spécifiques](https://claude.site/artifacts/681b749a-17f5-4585-b3b8-770d2eda5c09) à la page traitée.
- **Mode d'emploi** du processus d'automatisation pour la mise en place d'une application full stack professionnelle, en utilisant une approche itérative avec LLM et les artefacts :

  - **Phase Frontend :**
a. Initialisation : Le développeur fournit une description initiale de la page à créer.
b. Génération : Le LLM utilise le prompt système frontend pour générer un artefact HTML initial.
c. Itération : Le développeur examine l'artefact, fournit des commentaires ou des modifications.
d. Raffinement : Le LLM ajuste l'artefact en fonction des commentaires du développeur.
e. Finalisation : Le processus se répète jusqu'à ce que le développeur soit satisfait de la page frontend.
Prompt utilisé : "Prompt Système pour la Génération de Page HTML avec Directives Backend Intégrées"

  - **Intégration des Directives Backend :**
a. Le LLM ajoute automatiquement la section <backend> à chaque page HTML finalisée.
b. Cette section inclut les spécifications, routes, modèles, logique, et structure de fichiers pour le backend.
Prompt utilisé : Le même que pour la phase frontend, avec focus sur la section backend.

  - **Phase Backend :**
a. Récupération : Le développeur backend récupère les pages HTML avec les directives intégrées.
b. Analyse : Un script ou le LLM analyse les sections <backend> de chaque page.
c. Génération de la Structure : Création de l'arborescence du projet backend selon les directives.
d. Implémentation : Le LLM génère le code Python pour chaque fichier spécifié.
e. Révision : Le développeur backend examine et ajuste le code généré si nécessaire.
Prompt utilisé : "Prompt pour le Développement Backend Flask"

- **Intégration et Tests :**
a. Le développeur intègre le frontend et le backend.
b. Des tests automatisés sont générés et exécutés pour valider l'application.

- **Itération Globale :**
Si des ajustements sont nécessaires, le processus peut être répété pour des composants spécifiques.

Cette approche permet une création rapide et cohérente d'une application full stack, en utilisant l'intelligence du LLM pour la génération de code et les connaissances du développeur pour la validation et les ajustements fins.

### Développement Backend
- Lors de nos précédentes tentatives nous avons perdu beaucoup de temps à des tâcheS qui pourraient être automatiséeS
  -  💡 La création du repository local (arbrescence et fichiers vides) a pu être automatisé en donnant à Sonnet d'image (copie d'écran) de l'arborescence souhaitée et en demandant au llm le code python qui l'implémente : Sonnet lit l'image et produit le code suivant.

```
import os

def create_directory_structure(base_path):
    directories = [
        "myapp",
        "myapp/app",
        "myapp/app/blueprints",
        "myapp/app/static",
        "myapp/app/static/js",
        "myapp/app/templates",
        "myapp/tests",
        "myapp/tests/unit",
        "myapp/tests/integration"
    ]
    
    files = [
        "myapp/app/__init__.py",
        "myapp/app/blueprints/auth.py",
        "myapp/app/blueprints/preferences.py",
        "myapp/app/blueprints/quiz.py",
        "myapp/app/static/js/preferences.js",
        "myapp/app/static/js/quiz.js",
        "myapp/app/templates/inscription.html",
        "myapp/app/templates/preferences.html",
        "myapp/app/templates/frontend_base.html",
        "myapp/app/templates/dashboard.html",
        "myapp/app/models.py",
        "myapp/app/utils.py",
        "myapp/app/config.py",
        "myapp/tests/unit/test_auth.py",
        "myapp/tests/unit/test_preferences.py",
        "myapp/tests/unit/test_quiz.py",
        "myapp/tests/unit/test_utils.py",
        "myapp/tests/integration/test_registration_login_flow.py",
        "myapp/tests/integration/test_quiz_flow.py",
        "myapp/tests/conftest.py",
        "myapp/.gitignore",
        "myapp/.env_example",
        "myapp/README.md",
        "myapp/requirements.txt",
        "myapp/run.py"
    ]
    
    for directory in directories:
        os.makedirs(os.path.join(base_path, directory), exist_ok=True)
    
    for file in files:
        open(os.path.join(base_path, file), 'a').close()

if __name__ == "__main__":
    base_path = os.getcwd()  # You can change this to any path you want
    create_directory_structure(base_path)
    print("Directory structure created successfully!")
```

- Maintenant muni des instructions backend et du contenu à intégrer dans les divers fichiers, la mise en place du répertory peut être automatisée
- Nous avons ensuite passé beaucoup de temps (outre la mauvaise prestation de GPT-4o ) à faire du couper/coller pour prendre en compte les suggestions du LLM au cours du débug
- La gestion des historiques nous aurait également été bien utile pour figer chaque étape franchie
- MAis ces tâches peuvent être elles aussi automatisée grace à l'assistant au codage opensource [AIDER](https://github.com/paul-gauthier/aider). Sa mise en oeuvre se fait en quelques clicks
```
$ pip install aider-chat

# Change directory into a git repo
$ cd /to/your/git/repo

# Work with Claude 3.5 Sonnet on your repo
$ export ANTHROPIC_API_KEY=your-key-goes-here
$ aider

# Work with GPT-4o on your repo
$ export OPENAI_API_KEY=your-key-goes-here
$ aider --sonnet 
```   
## Après la théorie la pratique avec la création de LearnAnythingV3
- Nous partons des 3 html que nous avons créés avec Sonnet : dossier HTML_ini
- Attention au crl V : Sonnet ne colle que ce qu'il veut si on ne dit pas "coller en texte brut"
- Le prompt front end est trop lié à l'application qui a servi d'exemple il faut le reprendre, à la main car tous les LLM semblent être devenus idiot ce matin.
- Plutôt que décrire ici ma démarche dans le détail, je vous renvoie au [chat avec Sonnet](https://claude.ai/chat/662e2394-657b-4cf9-8ad1-c4e14a47e28e):
  - Mon pompt fonctionne  : conclusion reprendre la main quand l'IA devient trop bête
  - Le droit à l'erreur dans un chat avec Sonnet: reprendre là où ça a dérappé , faire edit, reformulez, save  et on repart d'un bon pied. Le LLM n'a plus la souvenance des passage vaseux !
  - Je demande une sortie en HTML à couper/coller : ça le motive à tout écrire et on peut facilement télécharger le document 
  - Finalement j'ai chargé Sonnet  d'assurer la cohérence d'ensemble et de compléter les manquant. Il a fait du bon boulot:
   ![image](https://github.com/user-attachments/assets/1c0999d7-4aa4-4877-b884-f746a6b131e2)


aider --model deepseek/deepseek-coder
.gitignore : ``# Aider tool related files
.aider.tags.cache.v3
aider-env/
.aider.chat.history.md
.aider.input.history

# Environment and configuration files
.env

# Ignore node_modules (if applicable)
node_modules/

# Ignore log files and temporary files
*.log
*.tmp

# Ignore compiled code and dependency directories
dist/
build/

# Ignore system files
.DS_Store
Thumbs.db```` 
   
## Le prncipe MISS (make it simple and stupid
- L'idée de départ, d'avoir des spécificatons parfates d'abord puis coder ensuite ne fonctionnnne pas vraiment car on en met trop dans la gueule du LLM .
- Par contre commencer à partir d'un répertoire vide et demander à AIDER d'afficher une page.html "Hello Word" fonctionne parfaitement, puis on lui demande de faire une page log up , puis de conserver le résultat dans une base de données...
- Il ira mêeme à traduire un cours en anglais et l'affiche en foncton des préféences
- Tout ça en quelques minutes, mais avec le coût de l'API Sonnet (4 € quand même) DeepSeek_coder est un peu moins bon mais 50 fois moins cher.
- AIDER est vraiment efficace il fait tourner les codes corrige les erreurs et gère github 

## les bases de l'apprentissage 3 phse : le tuto , la démonstration interactive et les exercices interactifs
- les prompts ont été générés par [Sonnet]
  - Pour le tutoriel avec présentation animée :

    "Créez une page HTML unique pour un tutoriel sur les équations du premier degré, destiné aux élèves de collège (12-15 ans). La page doit inclure une introduction, une explication de l'importance des équations du premier degré, et un tutoriel pas à pas avec des analogies simples. Utilisez HTML5, CSS3 et JavaScript (ES6+) pour créer une présentation animée des équations. La page doit être responsive, utiliser des couleurs vives mais non agressives, et inclure des animations subtiles pour l'engagement. Assurez-vous que le code est bien structuré et commenté."

  - Pour la démonstration interactive :

"Créez une page HTML unique pour une démonstration interactive des équations du premier degré, adaptée aux élèves de collège. La page doit permettre aux utilisateurs d'entrer une équation du premier degré ou d'en générer une aléatoirement. Implémentez une fonction pour résoudre l'équation pas à pas, affichant chaque étape individuellement. Utilisez HTML5, CSS3 et JavaScript (ES6+) pour créer cette expérience interactive. Assurez-vous que la page est responsive, utilise un design attrayant, et inclut des vérifications pour éviter les résultats NaN. Le code doit être bien structuré et commenté."

  - Pour les exercices interactifs :

"Créez une page HTML unique pour des exercices interactifs sur les équations du premier degré, destinés aux élèves de collège. La page doit présenter une série d'exercices de difficulté croissante, avec un champ de saisie pour la réponse de l'utilisateur, une vérification immédiate, et des options pour obtenir des indices ou voir la solution complète. Implémentez un suivi des progrès de l'utilisateur. Utilisez HTML5, CSS3 et JavaScript (ES6+) pour créer cette expérience interactive. Assurez-vous que la page est responsive, utilise un design attrayant et encourageant. Le code doit être modulaire, bien commenté et inclure un système de stockage local pour sauvegarder les progrès."    

""  [Métaprompting](https://claude.ai/chat/73ae7e7f-6c11-4c81-8c8d-17d03d24be3d) : 
- On passe à un tuo interactif sur Magellan en rajoutant simplement : "adapte les 3 prompts suivant pour "la vie de Magellan":  - Pour le tutoriel avec présentation animée :..." , puis applique les 3 prompts
on obtient (en demandant d'utiliser mermaid : [le tuto](https://claude.site/artifacts/46812f3a-e262-4c00-a0be-3e727f80a431), [la démonstratin animée](https://claude.site/artifacts/5aaf2e0c-fb37-4429-b939-ac3d64283b52) et [les quizz](https://claude.site/artifacts/5138d4be-88ce-4ee9-b62c-226b5bdf0a09)
- la généralisation à tous les cours de 5ième estpossible mais artefact ne gère pas facilement les fichiers de gros volume: s'il donne bine la [strcuture générale]( des cours de 5ième, il ne rempli pas le détail de chaque cours
- Nous avons contourné l'obstacle, e nlui demandant [de ne générer que le prompt qui génèrera le cours](https://claude.site/artifacts/02c006cb-67d0-46db-b957-e4de04e0f506) , pour chaque cas particulier
- Nous nous sommes attaché ensuite à améliorer les cours correspondants, en particulier pour les exercices interactifs, que nosu avons, après de nombreuse itérations, en jeu interactif. Le codetrop lourd, ne tourne pas sur Artefact mais sonnet nous permet de le décomposer en plusieurs fichiers qui compilé localement tournent parfaitement. La bonne nouvelle est que le code est bien structuré avec un fichier json pour les questions. Ce sera le fichier à changer pour passer d'un thème à un autre. 
- Voici l'[arborecence](https://claude.site/artifacts/4ef389ba-d7d7-4679-8464-c63cc66b1614) des fichiers correspondants.
- Une autre issue détect est la difficulté de prendre en compte uen réponse ouverte de l'élève car elle sera déclarée fausse même en cas d'un formatage qui n'est pas celui attendu. La solution la plus performante serait de laisser traiter par n llm la cohérence, question, réponse attendue, préférences et historique des réponses.  

## Point d'avancement au 8 Août 2024
- La réalisation d'une application full stack en no code a été réalisée avec un backend streamlit
- Nous avons déployé l'applications sur https://learnanything.streamlit.app/ en traitant les problèmes de secrets. Cette application est maintenant synchronisée via github 
- nous avons créé un compte admin qui a accès à tous les échanges et qui peut chatter avec chatgpt-4o-mini 
