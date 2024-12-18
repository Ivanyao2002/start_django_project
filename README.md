# Guide de création d'un projet django.

## Introduction
Ce guide vous aidera à créer un projet Django depuis le début, en configurant un environnement virtuel, en installant Django, et en créant votre première application.

## Étapes à suivre
1. Créer le répertoire du projet

Créez un nouveau répertoire pour votre projet et ouvrez-le avec votre éditeur de code.

2. Installer python

Assurer vous d'avoir python installé sur votre machine ; Si ce n'est pas le cas, rendez-vous sur le site de python pour installer une version selon votre système.https://www.python.org/
3. Créer un environnement virtuel

Ouvrez le terminal et exécutez la commande suivante pour créer un environnement virtuel:

```bash
python -m venv nom_de_l_environnement  # Préférez 'venv' ou 'env' ou '.env' ou '.venv'
```
4. Activer l'environnement virtuel

Naviguez vers le dossier Scripts (Windows) ou bin (Unix) et activez l'environnement:

- Pour unix
```bash
source venv/bin/activate
```
- Pour windows
```bash
.\venv\Scripts\activate
```
5. Installer Django

Assurez-vous que l'environnement est activé, puis installez Django:
```bash
pip install django  # Ou spécifiez la version: pip install django==version
```

6. Créer le fichier requirements.txt

Enregistrez les dépendances de votre projet:
```bash
pip freeze > requirements.txt
```

7. Créer le projet Django

Initialisez un nouveau projet Django:
```bash
django-admin startproject nom_du_projet
```
Vous pouvez renommer le dossier principal en src, qui représente la source.

8. Créer une application

Naviguez dans le dossier src (ou dans le dossier de votre projet) et créez une application:
```bash
cd src  # ou cd nom_du_projet
python manage.py startapp nom_de_l_application
```

9. Ajouter l'application aux INSTALLED_APPS

Ouvrez settings.py et ajoutez votre application à la liste INSTALLED_APPS :
```python
INSTALLED_APPS = [
    #...
    'nom_de_l_application.apps.NomDeLaClasseConfig',  # Ou juste 'nom_de_l_application'
]
```

10. Configurer les dossiers templates et static

Créez les dossiers templates et static à la racine de votre projet, puis mettez à jour settings.py:

- Pour les templates :
```python
TEMPLATES = {
    #...
    'DIRS': [BASE_DIR / 'templates'],
}
```
- Pour les fichiers statiques :
```python
STATICFILES_DIRS = [BASE_DIR / 'static']
```

11. Configurer les URL

Dans le fichier urls.py de votre projet, importez include et ajoutez un chemin vers le fichier urls.py de votre application:
```python
from django.urls import path, include

urlpatterns = [
    #...
    path('nom_de_lUrl/', include('nom_de_l_application.urls')),
]
```

12. Créer le fichier urls.py dans votre application

Dans votre application, créez un fichier urls.py et définissez le nom de l'application et les urlpatterns :
```python
app_name = 'nom_de_l_application'

urlpatterns = [
    # Ajoutez vos chemins ici
]
```

13. Créer un fichier de base HTML

Dans le dossier templates, créez un fichier base.html qui servira de modèle pour vos autres fichiers HTML.


14. Organiser le dossier static

Dans le dossier static, créez les sous-dossiers suivants:

- css pour les styles
- js pour les scripts
- images pour les images


15. Configurer la base de données

Modifiez le dictionnaire DATABASES dans settings.py selon votre SGBD et installez le connecteur approprié. Par defaut sqlite3
Exemples :
```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',  # Utilisez 'sqlite3', 'mysql', ou 'oracle' selon votre SGBD
        'NAME': 'nom_de_la_base_de_donnees',        # Nom de votre base de données
        'USER': 'nom_utilisateur',                   # Utilisateur de la base de données
        'PASSWORD': 'votre_mot_de_passe',            # Mot de passe de l'utilisateur
        'HOST': 'localhost',                          # Adresse de l'hôte (utilisez 'localhost' pour une base de données locale)
        'PORT': '5432',                               # Port par défaut pour PostgreSQL
    }
}
```

16. Créer et appliquer les migrations

Effectuez les migrations:
```bash
python manage.py makemigrations
python manage.py migrate
```

17. Lancer le serveur

Démarrez le serveur de développement:
```bash
python manage.py runserver
```

18. Accéder à votre projet

Ouvrez votre navigateur web et accédez à l'URL fournie par le terminal (généralement http://127.0.0.1:8000).


## Conclusion
Vous avez maintenant configuré avec succès un projet Django. Vous pouvez commencer à développer votre application en ajoutant des modèles, des vues et des templates.
Bonne chance pour la suite. La documentation officielle de django : https://docs.djangoproject.com/en/5.1/