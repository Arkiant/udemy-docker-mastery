# create your custom drupal image here, based of official drupal
FROM drupal:8.2

RUN apt-get update && apt-get install -y git \
        && rm -rf /var/lib/apt/lists/*

COPY default.settings.php sites/default/settings.php

RUN chown www-data:www-data sites/default/settings.php

WORKDIR /var/www/html/themes

RUN git clone --branch 8.x-3.x --single-branch --depth 1 https://git.drupal.org/project/bootstrap.git  \
        && chown www-data:www-data -R bootstrap

WORKDIR /var/www/html