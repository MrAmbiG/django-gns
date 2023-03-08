# Pull base image
FROM python:3.8-slim

# Set environment varibles
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

RUN mkdir /djangoapp
RUN apt update && \
    # apk add --no-cache --virtual .gyp python3 make g++ \
    # apk add postgresql-dev tree
    apt-get install -y build-essential python3.8-dev libpq-dev
WORKDIR /djangoapp

# copy code
ADD djangoapp /djangoapp
ADD requirements.txt /djangoapp/requirements.txt

# install our dependencies
RUN pip install -r /djangoapp/requirements.txt

# expose the port 8000
EXPOSE 8000

# define the default command to run when starting the container
RUN python manage.py collectstatic --no-input
CMD ["gunicorn", "--bind", ":8000", "djangoapp.wsgi:application"]
