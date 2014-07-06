FROM smerrill/servicebase
MAINTAINER Steven Merrill <steven.merrill@gmail.com>

RUN yum -y localinstall https://www.softwarecollections.org/en/scls/rhscl/httpd24/epel-6-x86_64/download/rhscl-httpd24-epel-6-x86_64-1-2.noarch.rpm && \
    yum -y install httpd24-httpd && \
    yum -y install php-fpm php-cli php-gd php-mcrypt php-mbstring php-pdo php-mysql php-pecl-memcache php-pecl-apc php-pecl-redis php-drush-drush php-intl php-tidy php-xml php-soap

ENV PHP_MEMORY_LIMIT 196M
ENV PHP_APC_SHM_SIZE 196M
ENV PHP_FPM_PROCS 2

WORKDIR /opt/app
CMD /opt/bin/forego start

# Note that the default docroot is /opt/app/www/build/html.
VOLUME ["/opt/app/log", "/opt/app/www"]

# Copy our configuration files into place.
ADD root /
