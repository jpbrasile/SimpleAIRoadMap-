## Introduction au No Code
- Le no code est une approche de développement logiciel qui permet aux utilisateurs de créer des applications sans écrire de code. 
Cette méthode consiste à demander sous forme de texte ce que l'assistant codage doit réaliser, rendant ainsi le développement accessible à ceux qui n'ont pas de compétences en programmation. 
Les outils no code permettent de concevoir des sites web, des applications mobiles, des bases de données et bien plus encore avec une courbe d'apprentissage réduite.

- A titre d'exemple : la Création d’une Application Full Stack avec Streamlit, Firebase et Google Auth

    - Ce guide vous explique comment créer et déployer une application web complète (full stack) en utilisant Streamlit pour le front-end, Firebase pour le back-end, et Google Auth pour l'authentification. Vous utiliserez également Aider pour le débogage et Streamlit Cloud pour le déploiement.

## Pourquoi Utiliser Streamlit, Firebase et Google Auth ?
- Streamlit : Permet de créer des interfaces utilisateur simples et interactives en Python, idéal pour des prototypes et des tableaux de bord.
- Firebase : Plateforme Google offrant des services comme Firestore (base de données en temps réel) et Firebase Authentication, facilitant le développement d'applications.
- Google Auth : Facilite l'authentification sécurisée avec des comptes Google, offrant une expérience utilisateur fluide.

## Étape 1 : Configuration de l'Environnement
1. Créer et Activer un Environnement Virtuel
- Pourquoi ? Un environnement virtuel isole les dépendances spécifiques de votre projet des autres projets sur votre machine, garantissant que les versions des bibliothèques restent cohérentes et évitant les conflits.
- Commandes :
```
python -m venv venv
source venv/bin/activate  # Sur Windows, utilisez `venv\Scripts\activate`
```

2. Installer les Dépendances
- Pourquoi ? Installer les bibliothèques nécessaires pour votre projet, à savoir Streamlit, Pyrebase (pour interagir avec Firebase), et python-dotenv (pour gérer les variables d'environnement).
- Commandes :
```
pip install streamlit pyrebase4 python-dotenv
```
3. Créer un Fichier .env
- Pourquoi ? Les variables d'environnement stockent des informations sensibles (comme les clés API) en dehors du code source, améliorant ainsi la sécurité et facilitant la gestion de différentes configurations pour différents environnements.
- Contenu du fichier .env :
```
API_KEY=your_api_key
AUTH_DOMAIN=your_project_id.firebaseapp.com
DATABASE_URL=https://your_project_id.firebaseio.com
PROJECT_ID=your_project_id
STORAGE_BUCKET=your_project_id.appspot.com
MESSAGING_SENDER_ID=your_messaging_sender_id
APP_ID=your_app_id
```
4. Créer un Fichier .gitignore
- Pourquoi ? Un fichier .gitignore indique à Git quels fichiers ou répertoires ne pas inclure dans le contrôle de version, évitant de versionner des fichiers sensibles ou spécifiques à l'environnement.
- Contenu du fichier .gitignore :
```
venv/
.env
__pycache__/
*.pyc
*.pyo
serviceAccountKey.json
.aider*
```
5. Créer un Fichier requirements.txt
- Pourquoi ? Liste les dépendances de votre projet, permettant à d'autres développeurs de les installer facilement en recréant exactement le même environnement.

- Commande :
```
pip freeze > requirements.txt
```
6. Créer un Fichier README.md
- Pourquoi ? Documentez votre projet pour expliquer son but, comment le configurer et l'utiliser.
- Contenu du fichier README.md :

### Mon Application Full Stack avec Streamlit et Firebase

Cette application est un exemple d'application full stack utilisant Streamlit pour le front-end, Firebase pour le back-end, et l'authentification Google.

### Configuration

1. Clonez le dépôt :
   ```
   git clone https://github.com/votre_nom_utilisateur/votre_depot.git
   cd votre_depot
   ```
- Créez et activez un environnement virtuel :
```
python -m venv venv
source venv/bin/activate  # Sur Windows, utilisez `venv\Scripts\activate`
```
- Installez les dépendances :
```
pip install -r requirements.txt
```
- Configurez les variables d'environnement en créant un fichier .env :
```
API_KEY=your_api_key
AUTH_DOMAIN=your_project_id.firebaseapp.com
DATABASE_URL=https://your_project_id.firebaseio.com
PROJECT_ID=your_project_id
STORAGE_BUCKET=your_project_id.appspot.com
MESSAGING_SENDER_ID=your_messaging_sender_id
APP_ID=your_app_id
```
- Ajoutez le fichier de clé de service Firebase :
    - Téléchargez le fichier serviceAccountKey.json depuis la console Firebase, sous Project Settings > Service accounts > Generate new private key, et placez-le dans votre répertoire de projet.
- Lancez l'application :
```
streamlit run app.py
```
- Déploiement
    - Le déploiement se fait via Streamlit Cloud. Connectez votre dépôt GitHub à Streamlit Cloud et suivez les instructions pour déployer l'application.


## Étape 2 : Configuration Firebase

### Créer un Projet

**Créer un Projet Firebase** : Rendez-vous sur [Firebase](https://firebase.google.com/).

- **Actions sur le site Firebase (console.firebase.google.com) :**
    - Cliquez sur "Ajouter un projet".
    - Donnez un nom au projet.
    - Configurez Google Analytics (optionnel).
    - Cliquez sur "Créer le projet".

### Ajouter une Application
- **Ajouter une Application** :
    - Sur la page d'accueil du projet, cliquez sur l'icône de la plateforme (Web, iOS, Android).
    - Enregistrez l'application en lui donnant un nom.
    - Copiez la configuration Firebase générée.

### Configurer l'Authentification
- **Configurer l'Authentification** :
    - Dans le menu latéral, cliquez sur "Authentication".
    - Dans l'onglet "Sign-in method", activez les méthodes d'authentification souhaitées (par exemple, Google Auth).

### Configurer Firestore
- **Configurer Firestore** :
    - Dans le menu latéral, cliquez sur "Firestore Database".
    - Cliquez sur "Créer une base de données".
    - Choisissez le mode (production ou test).
    - Sélectionnez la région.

### Gérer les Règles de Sécurité

- **Gérer les Règles de Sécurité** :
    - Dans Firestore ou Storage, allez dans l'onglet "Règles".
    - Modifiez les règles selon vos besoins.
### Télécharger le Fichier de Configuration
- **Télécharger le Fichier de Configuration** :
    - Dans les paramètres du projet, section "Vos applications".
    - Cliquez sur l'icône de téléchargement pour obtenir le fichier JSON (serviceAccountKey.json).

## Étape 3 : Développement de l'Application
### Créer un Fichier `app.py`
- Utilisez un LLM pour générer le code nécessaire pour votre application. Voici un exemple simplifié :
```python
import streamlit as st
import pyrebase
from dotenv import load_dotenv
import os
import firebase_admin
from firebase_admin import credentials, firestore
```
### Charger les variables d'environnement
```
load_dotenv()
```
### Configuration Firebase
```
config = {
    "apiKey": os.getenv("API_KEY"),
    "authDomain": os.getenv("AUTH_DOMAIN"),
    "databaseURL": os.getenv("DATABASE_URL"),
    "projectId": os.getenv("PROJECT_ID"),
    "storageBucket": os.getenv("STORAGE_BUCKET"),
    "messagingSenderId": os.getenv("MESSAGING_SENDER_ID"),
    "appId": os.getenv("APP_ID")
}
```
### Initialiser Firebase avec Pyrebase
```
firebase = pyrebase.initialize_app(config)
auth = firebase.auth()
```
### Initialiser Firebase Admin SDK
```
cred = credentials.Certificate("serviceAccountKey.json")
firebase_admin.initialize_app(cred)
db = firestore.client()
st.title("Mon Application Full Stack")
```
### Interface d'authentification
```
email = st.text_input("Email")
password = st.text_input("Mot de passe", type="password")
if st.button("Se connecter"):
    try:
        user = auth.sign_in_with_email_and_password(email, password)
        st.success("Connecté avec succès!")
    except:
        st.error("Erreur d'authentification. Veuillez vérifier vos identifiants.")
if st.button("Ajouter des données"):
    data = {"name": "Streamlit", "type": "web application"}
    db.collection("apps").add(data)
    st.success("Données ajoutées!")
if st.button("Voir les données"):
    apps = db.collection("apps").stream()
    for app in apps:
        st.write(app.to_dict())
```

## Étape 4 : Utilisation de Aider pour le Débogage
- Pourquoi ? Aider peut analyser votre code et fournir des suggestions et des solutions pour résoudre les problèmes, rendant le processus de débogage plus efficace.
- Si vous rencontrez des erreurs, utilisez Aider pour obtenir des suggestions et des solutions de débogage.

## Étape 5 : Déploiement avec Streamlit Cloud
### Initialiser un Dépôt Git
- Pourquoi ? Git est un système de contrôle de version qui vous permet de suivre les modifications apportées à votre code, facilitant la collaboration et la gestion des versions.
- Commandes :
```
git init
git add .
git commit -m "Initial commit"
```
### Créer un Dépôt GitHub et Ajouter l'Origine Distante
- Pourquoi ? GitHub héberge vos dépôts Git et facilite la collaboration avec d'autres développeurs.
- Commandes :
```
git remote add origin https://github.com/votre_nom_utilisateur/votre_depot.git
git push -u origin master
```
### Configurer Streamlit pour le Déploiement
- Installer Streamlit CLI : Si ce n'est pas déjà fait.
    - Pourquoi ? La CLI de Streamlit est nécessaire pour lancer et déployer votre application sur Streamlit Cloud.
    - Commande :
```
pip install streamlit
```
- Connecter votre dépôt GitHub à Streamlit :
    - Pourquoi ? Cela permet à Streamlit Cloud de surveiller votre dépôt pour les modifications et de déployer automatiquement la version la plus récente de votre application.
    - Rendez-vous sur Streamlit Cloud.
        - Connectez-vous avec votre compte GitHub.
        - Suivez les instructions pour lier votre dépôt GitHub contenant votre projet Streamlit.
- Déployer l'Application :
    - Pourquoi ? Streamlit Cloud gère l'infrastructure nécessaire pour héberger votre application, vous permettant de vous concentrer sur le développement.
        - Sélectionnez le dépôt et la branche que vous souhaitez déployer.
        - Streamlit va automatiquement déployer votre application et vous fournir une URL publique.

### Mini Cheat Sheet : Développement et Déploiement
- **Commandes de Base (venv et git)**
```
# Créer un environnement virtuel :
python -m venv venv
# Activer l'environnement virtuel :
source venv/bin/activate  # Sur Windows, utilisez `venv\Scripts\activate`
# Installer les dépendances :
pip install streamlit pyrebase4 python-dotenv firebase-admin
# Initialiser un dépôt Git :
git init
# Ajouter tous les fichiers :
git add .
# Faire un commit :
git commit -m "Initial commit"
# Ajouter une origine distante :
git remote add origin https://github.com/votre_nom_utilisateur/votre_depot.git
# Pousser vers GitHub :
git push -u origin master
```
- **Utilisation de Streamlit**
    - Lancer l'application Streamlit en local :
```
streamlit run app.py
```
- **Configuration Firebase**
    - Créer un Projet Firebase : Rendez-vous sur Firebase, créez un projet.
    - Activer Google Auth : Dans la console Firebase, allez dans Authentication > Sign-in method, activez Google.
    - Configurer Firestore : Allez dans Firestore Database, suivez les étapes pour configurer.
- **Fichier .env**
Le fichier .env contient les configurations sensibles que vous ne souhaitez pas versionner :
```
API_KEY=your_api_key
AUTH_DOMAIN=your_project_id.firebaseapp.com
DATABASE_URL=https://your_project_id.firebaseio.com
PROJECT_ID=your_project_id
STORAGE_BUCKET=your_project_id.appspot.com
MESSAGING_SENDER_ID=your_messaging_sender_id
APP_ID=your_app_id
```
- **Fichier .gitignore**
Le fichier .gitignore pour exclure les fichiers non nécessaires au versionnement :
```
venv/
.env
__pycache__/
*.pyc
*.pyo
serviceAccountKey.json
.aider*
```
- **Fichier requirements.txt**
    - Liste les dépendances de votre projet :
```
streamlit
pyrebase4
python-dotenv
firebase-admin
``` 
###  Cheat Sheet Firebase
- **Initialisation de Firebase dans votre code**
    - Charger les variables d'environnement :
```
from dotenv import load_dotenv
import os
load_dotenv()
```
- **Configuration Firebase :**
```
import pyrebase
import firebase_admin
from firebase_admin import credentials, firestore
config = {
    "apiKey": os.getenv("API_KEY"),
    "authDomain": os.getenv("AUTH_DOMAIN"),
    "databaseURL": os.getenv("DATABASE_URL"),
    "projectId": os.getenv("PROJECT_ID"),
    "storageBucket": os.getenv("STORAGE_BUCKET"),
    "messagingSenderId": os.getenv("MESSAGING_SENDER_ID"),
    "appId": os.getenv("APP_ID")
}
# Initialiser Firebase avec Pyrebase
firebase = pyrebase.initialize_app(config)
auth = firebase.auth()
# Initialiser Firebase Admin SDK
cred = credentials.Certificate("serviceAccountKey.json")
firebase_admin.initialize_app(cred)
db = firestore.client()
```
- **Authentification avec Firebase:**
```
# Inscription d'un utilisateur :
email = "user@example.com"
password = "password"
user = auth.create_user_with_email_and_password(email, password)
# Connexion d'un utilisateur :
user = auth.sign_in_with_email_and_password(email, password)
# Déconnexion d'un utilisateur :
auth.current_user = None
```

- **Gestion de la base de données Firestore**
```
# Ajouter des données :
data = {"name": "Streamlit", "type": "web application"}
db.collection("apps").add(data)
#  Lire des données :
apps = db.collection("apps").stream()
for app in apps:
    print(app.to_dict())
```

### Cheat Sheet Streamlit
- **Commandes de base Streamlit**
```
# Afficher un titre :
import streamlit as st
st.title("Mon Application Full Stack")
# Afficher du texte :`
st.write("Bienvenue sur mon application créée avec Streamlit et Firebase!")
#  Champs de texte et boutons :
email = st.text_input("Email")
password = st.text_input("Mot de passe", type="password")
if st.button("Se connecter"):
    st.success("Connecté avec succès!")
```

### Cheat Sheet Aider
- Aider est un assistant de programmation basé sur l'IA qui utilise des modèles de langage pour aider au développement de logiciels. Voici ses principales fonctionnalités :
- Commandes clés :
    - /help : Affiche la liste des commandes disponibles
    - /edit : Modifie un fichier existant
    - /new : Crée un nouveau fichier
    - /run : Exécute une commande shell
    - /diff : Affiche les modifications apportées
    - /undo : Annule la dernière modification
    - /add : Ajoute un fichier au projet
    - /ls : Liste les fichiers du projet
    - /chat : Démarre une conversation avec l'IA
- Bonnes pratiques :
    - Fournissez des instructions claires et concises
    - Divisez les tâches complexes en étapes plus petites
    - Utilisez /diff pour vérifier les changements avant de les valider
    - Profitez de la fonction de chat pour des explications détaillées
- Astuces :
    -  Aider peut générer du code, déboguer et refactoriser
    - Il peut expliquer des concepts de programmation
    - Utilisez-le pour explorer de nouvelles idées ou approches
    - Combinez les commandes pour un flux de travail efficace
    - Aider s'intègre à votre environnement de développement existant, offrant une assistance IA pratique tout au long du processus de codage.

### Conclusion
En suivant ce guide, vous pouvez créer, déboguer et déployer une application full stack utilisant Streamlit, Firebase et Google Auth. L'utilisation de Aider pour le développement et Streamlit Cloud pour le déploiement simplifie le processus et vous permet de vous concentrer sur la création de fonctionnalités utiles. Ce guide couvre les aspects essentiels, depuis la configuration de l'environnement jusqu'au déploiement, en passant par la gestion des dépendances et des variables d'environnement. En utilisant ces outils et pratiques, vous pouvez développer des applications web robustes et évolutives de manière efficace.
