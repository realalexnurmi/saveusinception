#Base image
FROM debian:buster
#I'm author of this and I DNK why you should know this
LABEL maintainer="Eiji Nena <enena@student.21-school.ru>"
#UPDATE!UPGRADE!PRAY FOR VIM! HTOP to find out PID! [MAIN LAYER]
RUN apt-get update && apt-get -y upgrade && apt-get -y install vim htop
#All things for PHP
RUN apt-get -y install php7.3 php7.3-fpm php7.3-mysql php7.3-xml
#And wget for CLI(that setup WP easy)
RUN apt-get	-y install wget
#Script for up this container
ADD up.sh ./
#Template configuration file wordpress
ADD wp-config.php ./
#Give user permission for all:)
RUN chmod 777 wp-config.php up.sh
#Of course, if you need to raise it, you need to run UP-SCRIPT
ENTRYPOINT [ "./up.sh" ]