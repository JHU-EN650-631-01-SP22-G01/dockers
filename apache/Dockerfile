FROM httpd:2.4.46
COPY ./httpd.conf /usr/local/apache2/conf/
COPY ./index.html /usr/local/apache2/htdocs/


RUN apt-get update \
    && apt-get install wget gcc make -y\
    && apt-get install libxml2 libxml2-dev -y
RUN mkdir -p /usr/local/bash

RUN wget https://ftp.gnu.org/gnu/bash/bash-4.2.tar.gz \
    && tar -xvzf bash-4.2.tar.gz -C /usr/local/

WORKDIR /usr/local/bash-4.2
RUN ./configure && make && make install

WORKDIR /usr/local/apache2
COPY ./links-status.cgi /usr/local/apache2/cgi-bin/links-status
RUN chmod +x /usr/local/apache2/cgi-bin/links-status
CMD httpd-foreground -c "LoadModule cgid_module modules/mod_cgid.so"

RUN mkdir /usr/local/apache2/ctf/
COPY ./flag.txt /usr/local/apache2/ctf/password.01.flag