FROM smerrill/servicebase
MAINTAINER Steven Merrill <steven.merrill@gmail.com>

RUN yum -y localinstall https://www.softwarecollections.org/en/scls/rhscl/httpd24/epel-6-x86_64/download/rhscl-httpd24-epel-6-x86_64-1-2.noarch.rpm
RUN yum -y install httpd24-httpd
RUN yum -y install php-fpm php-cli php-gd php-mcrypt php-mbstring php-pdo php-mysql php-pecl-memcache php-pecl-apc

WORKDIR /opt/app
CMD /opt/bin/forego start

# Copy our configuration files into place.
ADD root /
