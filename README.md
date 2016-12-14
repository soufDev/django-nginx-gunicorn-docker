# django-docker
Deploy Django with NGINX  Gunicorn and Docker

# 1- make you project on web/ folder

# 2- you should have all the requiments at this folder on requirments.txt ( in my example I should add gunicorn==2.6.0 to the requirements )

# 3- with you Terminal go to folder ~/django-docker and run
	 docker-compose build

	 docker-compose up (-d additional if you want to launch docker in background )

# 4- launch http://your_ip_adress and than you have your django project launched with docker

# 5- also if you need to add static files or migrate your migrations you can launch

	 docker-compose run web python manage.py staticfiles

	 docker-compose run web python manage.py migrate.py
Or

# launch your container: choose your container like djangodocker_web_1 than go on your terminal and write

	docker exec -ti djangodocker_web_1 bash

# then you can do every thing you want like

	python manage.py makemigrations

	python manage.py migrate

	python manage.py staticfiles ( to get your admin panel )

	python manage.py createsuperuser ( create super user for your admin panel )

and to create your database with postgresql you have to go to your terminal and then go to your postgres container, launch your postgres container with this commande:

	docker exec -ti djangodocker_postgres_1 bash

then you can create your database and set it to your setting.py file, then you have to launch a

	python manage.py migrate

with djangodocker_web_1 container

and for nginx configration your can choose another configuration or just set this configuration for your case
