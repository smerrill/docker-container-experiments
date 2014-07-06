FROM centos
MAINTAINER Steven Merrill <steven.merrill@gmail.com>

# Set up the default CentOS SCLs as well as some handy packages.
# ruby is here for the erb binary and templates.
# Forego is used as a zero-dependency way to run two commands (such as in a combined Apache/php-fpm container.)
RUN yum -y localinstall https://dl.fedoraproject.org/pub/epel/6/x86_64/epel-release-6-8.noarch.rpm && \
    yum -y update && \
    yum -y install centos-release-SCL && \
    yum -y install tar wget curl unzip vim less ruby && \
    mkdir -p /opt/bin && \
    wget https://godist.herokuapp.com/projects/ddollar/forego/releases/current/linux-amd64/forego -O /opt/bin/forego && \
    chmod +x /opt/bin/forego

# Also run a newer libselinux, per https://bugzilla.redhat.com/show_bug.cgi?id=1098120#c12.
ADD root /
RUN yum -y update libselinux-*

CMD /bin/bash
