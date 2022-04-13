FROM httpd
COPY ./httpd.conf /usr/local/apache2/conf/
RUN apt-get update \
    && apt-get install libxml2 libxml2-dev -y