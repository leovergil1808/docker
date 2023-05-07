FROM centos:7

# update yum
RUN yum update -y && \
    yum clean all

# Cài đặt Apache HTTP Server
RUN yum install -y httpd httpd-tools 

# Cài đặt module SSL cho Apache.
RUN yum install -y mod_ssl

# Cài đặt thư viện mã hóa OpenSSL.
RUN yum install -y openssh-server openssh-clients

# Cài open ssl
RUN yum install -y openssl

# Cài sudo để có thể thực thi các lệnh với quyền root
RUN yum install -y sudo

# Cài which để tìm kiếm đường dẫn của một tệp tin.
RUN yum install -y which

#  Cài wget để tải các tệp tin từ Internet.
RUN yum install -y wget

# Cài Git để quản lý mã nguồn
RUN yum -y install git

# Cài Unzip để giải nén các tệp tin
RUN yum -y install unzip

# Cài trình soạn thảo Vim
RUN yum -y install vim

# Làm sạch các bộ đệm của
RUN yum clean all

# Cài Php 8.2.5
# 1. Cài kho lưu trữ phụ EPEL
# 2. Cài kho lưu trữ Remi để cài đặt PHP
# 3. Cài gói yum-utils để quản lý các kho lưu trữ.
# 4. Bật kho lưu trữ Remi phiên bản 8.0 để cài đặt PHP 8.0.
# 5. Cài các module PHP và các gói phụ trợ
RUN yum -y install epel-release
RUN yum -y install http://rpms.remirepo.net/enterprise/remi-release-7.rpm
RUN yum -y install yum-utils
RUN yum-config-manager --enable remi-php82
RUN yum -y install php php-cli php-fpm php-mysqlnd php-zip php-devel php-gd php-mbstring php-curl php-xml php-pear
# Hết phần cài Php 8.2.5

# Tải composer
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"

# Cài composer
RUN php composer-setup.php
RUN mv composer.phar /usr/local/bin/composer

# Cài node 16
RUN curl -sL https://rpm.nodesource.com/setup_16.x | sudo bash -
RUN sudo yum install -y nodejs

# Cài trình biên dịch scss
RUN npm install -g sass

# Tạo và cấp quyền thư mục chứa source custom ( mẫu ko dc xóa )
# RUN mkdir /data
# RUN chmod 0777 data
# RUN mkdir /data/mo2
# RUN chmod 0777 /data/mo2
# RUN mkdir /data/log
# RUN mkdir /data/log/nginx
# RUN chmod 0777 /data/log/nginx
# RUN mkdir /data/log/www
# RUN chmod 0777 /data/log/www


# Mở port
EXPOSE 22 80 3306

# Khởi động apache
CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]
