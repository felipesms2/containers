FROM felipesms/liga:1.0
# Set environment variables
ENV DEBIAN_FRONTEND=noninteractive \
    LANG=en_US.UTF-8 \
    LANGUAGE=en_US.UTF-8 \
    LC_ALL=en_US.UTF-8
RUN mkdir /app && chmod -R 777 /app && \ 
apt-get update; apt upgrade -y; \
apt install \
zsh \
sudo \
wget \
curl \
sqlite3 \
apache2 \
php \
php-mongodb \
phpunit \
php-gd \
php-sqlite3 \
php-bcmath \
php-redis \
php-gmp \
php-interbase \
php-odbc \
php-mysql \
php-curl \
php-xml \
php-intl \
php-mbstring \
mariadb-server \
ssh \
composer \
git \
nodejs \
npm \
nano \
php-zip \
php-pear \
php-dev \
nmap \
neofetch \
python3-pip \
python3-tk \
python3-dev \
net-tools \
iproute2 -y ; \
useradd -m -s /usr/bin/zsh -G sudo sites; \
sudo -u sites sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)" && \
cd /app && \
wget https://files.phpmyadmin.net/phpMyAdmin/5.2.2/phpMyAdmin-5.2.2-all-languages.zip && \
unzip phpMyAdmin-5.2.2-all-languages.zip && \
mv phpMyAdmin-5.2.2-all-languages pma && \
rm -rf phpMyAdmin-5.2.2-all-languages.zip && \
chmod -R 777 /app;
WORKDIR /app
COPY ./envvars /etc/apache2/envvars
COPY ./000-default.conf /etc/apache2/sites-enabled/000-default.conf
COPY ./ports.conf /etc/apache2/ports.conf
COPY ./config.inc.php /app/pma/config.inc.php

# docker build -t phpmyadmin:1.0 .
# docker run --name phpmyadmin --network host -it -v $(pwd):/app phpmyadmin:1.0
# docker tag phpmyadmin:1.0 felipesms/phpmyadmin:1.0
# docker push felipesms/phpmyadmin:1.0
# docker run -d -v $(pwd):/app --network host --name liga felipesms/phpmyadmin:1.0
# docker container run --name digi_art_worker -it -p 3500:5000 -v $(pwd):/root/digi-art --entrypoint /bin/bash digilivro/digi_art_python3.9:1.0
# gunicorn --bind 127.0.0.1:5000 wsgi:app

