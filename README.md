"# Heroku-django-bk001"

Token : 0b01f9d120ef265975712b2855062ecf40200570

Use this token for our API by setting a request header called Authorization, followed by Token <token>, eg:
	
import requests
username = 'bkablam10'
token = '0b01f9d120ef265975712b2855062ecf40200570'

response = requests.get(
    'https://www.pythonanywhere.com/api/v0/user/{username}/cpu/'.format(
        username=username
    ),
    headers={'Authorization': 'Token {token}'.format(token=token)}
)
if response.status_code == 200:
    print('CPU quota info:')
    print(response.content)
else:
    print('Got unexpected status code {}: {!r}'.format(response.status_code, response.content)) 


# git

$ git init
Initialized empty Git repository in ~/djangogirls/.git/
$ git config --global user.name "Your Name"
$ git config --global user.email you@example.com 
$ git status
$ git add .
$ git commit -m "My Django Girls app, first commit"
$ git branch -M main
$ git remote add origin https://github.com/<your-github-username>/my-first-blog.git
$ git push -u origin main (master)
....
# pythonAnyWhere
Configurer votre site sur PythonAnywhere
Allez sur le Panneau de Contrôle de PythonAnywhere en cliquant sur le logo, et choisissez l'option de démarrer un terminal "Bash". C'est comme votre terminal à vous, mais chez PythonAnywhere.
..
$ pip3.8 install --user pythonanywhere
$ pa_autoconfigure_django.py --python=3.8 https://github.com/<your-github-username>/my-first-blog.git (or pa_autoconfigure_django.py --python=3.8 https://github.com/bkablam11/Heroku-django-bk001.git --nuke
)
(ola.pythonanywhere.com) $ python manage.py createsuperuser
(ola.pythonanywhere.com) $ ls
(ola.pythonanywhere.com) $ ls blog/
## link
https://tutorial.djangogirls.org/fr/django_urls/


## Commiter et pusher votre code sur GitHub a nouveau
$ git status
$ git add .
$ git status
$ git commit -m "Modification du HTML du site"
$ git push

## Puller les modifications sur PythonAnywhere et recharger son appli web
$ cd ~/<your-pythonanywhere-domain>.pythonanywhere.com
$ git pull

## shell python testing query set
python manage.py shell

> Créer des objets et les manipuler et filter les objets; Classer les objets; Requêtes complexes grâce au chaînage des méthodes

orm to sql

>>> queryset = MyModel.objects.all()
>>> print(queryset.query)
SELECT "myapp_mymodel"."id", ... FROM "myapp_mymodel"

Sql vers QuerySet Django
SELECT * FROM movie as m INNER JOIN similarity as s ON m.`movie_id` = s.first_movie WHERE `movie_id` = 1 ORDER BY `s`.`similarity_score` DESC

similarities = Similarity.objects.filter(
    first_movie__id=1
).order_by(
    "-similarity_score"
).select_related(
    'first_movie'
)

movies = Movie.objects.all().prefetch_related(
    'first_movie'
).filter(
    first_movie__id=1
).order_by(
    "-similarity_score"
)

Une solution pourrait être la suivante :

s = Similarity.objects.filter(first_movie__id=1).order_by("-similarity_score")
# and access to first_movie
for movie in s:
    movie.first_movie

# mise a jour des fichier static css
$ workon <your-pythonanywhere-domain>.pythonanywhere.com
(ola.pythonanywhere.com)$ python manage.py collectstatic
[...]

# token pythonanywhere
https://www.pythonanywhere.com/user/bkablam10/consoles/#
https://www.pythonanywhere.com/user/bkablam10/webapps/#tab_id_bkablam10_pythonanywhere_com

# Nous allons donc une nouvelle fois suivre le processus suivant et créer : un lien vers la page, une URL, une vue et un template

# lien utils django gils
https://tutorial.djangogirls.org/fr/whats_next/


Django
Notre autre livre, Django Girls Tutorial: Extensions
Tutoriel officiel de Django
Vidéos Getting Started With Django
La spécialisation Python de Coursera – vous pouvez accéder gratuitement à certains cours et vous pouvez obtenir un certificat Coursera à la fin
HTML, CSS et JavaScript
Cours de développement web de la Codecademy
freeCodeCamp
Python
Cours Python de la Codecademy
Cours Python de Google
Le livre Learn Python The Hard Way – les premiers exercices sont gratuits
New Coder tutorials – c'est une série d'exemples pratiques illustrant comment Python peut vous servir
edX – vous pouvez accéder à la plupart des cours gratuitement, mais si vous voulez un certificat ou des crédits pour une qualification supérieure, cela coûtera de l'argent
La spécialisation Python de Coursera – vous pouvez accéder gratuitement à certains cours et vous pouvez obtenir un certificat à la fin
Python for Everybody – une version gratuite et ouverte de la spécialisation de Coursera "Python for Everybody"
Travailler avec les données
Cours de science des données de la Codecademy
edX – vous pouvez accéder à la plupart des cours gratuitement, mais si vous voulez un certificat ou des crédits pour une qualification supérieure, cela coûtera de l'argent
Dataquest – les 30 premières « missions » sont gratuites
On a hâte de voir votre prochaine création !
