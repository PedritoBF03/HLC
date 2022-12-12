FROM ubuntu
RUN apt-get update && apt-get install -yq --no-install-recommends \
    apache2
# Copy taller /var/www/html
ADD taller.tgz /var/www/html
CMD apachectl -D FOREGROUND