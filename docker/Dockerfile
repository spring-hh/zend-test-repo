FROM centos:7

RUN yum -y update && yum clean all
RUN yum -y install epel-release
RUN rpm -Uvh http://rpms.famillecollet.com/enterprise/remi-release-7.rpm
RUN yum -y install --enablerepo=remi,remi-php56 php php-devel php-mbstring php-pdo php-gd php-xml php-mcrypt
COPY --from=composer:1 /usr/bin/composer /usr/bin/composer
RUN yum -y install httpd
RUN systemctl enable httpd

CMD ["/sbin/init"]
