# Start Django Project
Guide de création d'un projet django.
- Céer le repertoire du projet puis ouvrer le avec votre éditeur
- Ouvrer le terminal puis créer un environnement virtuel  ( python ou python3 pour Unix -m venv nom_de_lenvironnement de prefence venv ou env)
- Naviguer vers le fichier activate.bat soit dans scripts ou bin, puis activer l'environnement (source activate ou activate pour windows)
- Revener au repertoire de votre projet puis installer django (pip ou pip3 install django ou preciser la version django==version)
- Créer le fichier requirements.txt en freesant les dépendances (pip ou pip3 freeze > requirements.txt)
- Créer le projet django (django-admin startproject nom_du_projet); Vous pouvez renommer le premier dossier par src qui represente source
- Naviguer à l'interieur de src si vous l'avez renommé sinon à l'interieur de votre projet puis créer une application  (python manage.py startapp nom_de_lApplication)
- Rajouter l'application à la suite de la liste INSTALLED_APPS ('nom_de_lApplication.apps.nom_de_la_classeConfigu'g ou 'nom_de_lApplication')
- Créer un dosier templates et un dossier static à la racine de votre projet puis rajouter les à settings.py
- Dans TEMPLATES à la clé DIRS ajouter la liste des dossiers template créer ([BASE_DIR / 'templates']) ; BASE_DIR reprensentant la racine du projet
- Pour le dossier static, créer une liste STATICFILES_DIRS puis ajouter la liste des dossiers static créer ([BASE_DIR / 'static'])
- Dans le fichier urls.py dans le dossier portant le nom de votre projet, d'abord importer le module include de django.urls puis ajouter un chemin pointant vers le fichier urls.py que vous aller créer dans votre application (path('nom_de_lUrl/', include('nom_de_lApplication.urls'))
- Créer un fichier urls.py dans votre application puis donner lui un nom dans le fichier (app_name = 'nom_de_lApplication') puis definisser la liste urlpatterns
- Dans le dossier templates créer un fichier base.html qui sera le fichier html de base à étendre pour toute nos fichiers html 
- Configurer le dictionnaire DATABASES si vous avez une base de donnée et en fonction de votre SGBD installer le connecteur approprié
- Créer les migratrions (python manage.py makemigrations)
- Appliquer les migrations (python manage.py migrate)
- Lancer le server (python manage.py runserver)
- Puis lancer le projet a travers le lien générer sur le navigateur
 
