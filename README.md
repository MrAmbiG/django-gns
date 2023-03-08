# django-pgns
django, postgresql, nginx, gunicorn, swaggerui. A POC boilerplate template

## run the following to rebuild and run every time...to remove any doublts of caching
- docker compose down -v && docker-compose up -d --no-deps --build djangoapp nginx

# If running for the 1st time then create these users first, create regular users in admin panel
django/django # superuser
user1/djangouser1
user2/djangouser2
user3/djangouser3
