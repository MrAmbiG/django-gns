# django-pgns
django, postgresql, nginx, gunicorn, swaggerui. A POC boilerplate template

## run the following to rebuild and run every time...to remove any doublts of caching
- docker compose down -v && docker-compose up -d --no-deps --build djangoapp nginx

# If running for the 1st time then create these users first, create regular users in admin panel
django/django # superuser
user1/djangouser1
user2/djangouser2
user3/djangouser3

# test swagger to be working behind nginx
- 127.0.0.1:5000 Gunicorn is serving the app here. So it should be without any static files. even the /admin panel will be without any static files
- 127.0.0.1:8000 nginx is serving the app here.
    - So it should show the drf with hyperlinkedmodelserializer,
    - /admin should show the rich webpage,
    - /swagger/ should show the swaggerui
    If all 3 are true, then swaggerui is working behind the reverse proxy

