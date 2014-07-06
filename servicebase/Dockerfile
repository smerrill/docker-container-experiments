FROM centos
MAINTAINER Steven Merrill <steven.merrill@gmail.com>

RUN yum -y update && \
    yum -y install centos-release-SCL && \
    yum -y install tar wget curl unzip vim less && \
    mkdir -p /opt/bin && \
    wget https://godist.herokuapp.com/projects/ddollar/forego/releases/current/linux-amd64/forego -O /opt/bin/forego && \
    chmod +x /opt/bin/forego

# Set up the default CentOS SCLs as well as some handy packages.
# Also run a newer libselinux, per https://bugzilla.redhat.com/show_bug.cgi?id=1098120#c12.
ADD root /
RUN yum -y update libselinux-*

CMD /bin/bash
