FROM nginx:1.19.0-alpine


RUN rm /etc/nginx/conf.d/default.conf
COPY conf.d/local.conf /etc/nginx/conf.d

RUN set -x ; \
  addgroup -g 82 -S www-data ; \
  adduser -u 82 -D -S -G www-data www-data && exit 0 ; exit 1

RUN apk --no-cache add shadow && usermod -aG www-data nginx
# # Change ownership of static files directory to Nginx user
# RUN chown -R nginx:nginx /djangoapp/staticfiles

# # Change ownership of media files directory to Nginx user
# RUN chown -R nginx:nginx /djangoapp/media

