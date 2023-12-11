# MODDLE INSTALATION
```
$ cd /opt 
$ git clone https://github.com/moodle/moodle.git
$ cd moodle
$ git branch --track MOODLE_403_STABLE origin/MOODLE_403_STABLE
$ git checkout MOODLE_403_STABLE
$ cp -R /opt/moodle/* /var/www/moddle
$ chmod -R 0777 /var/www/moddle
```
——————————— END ———————————

## DATABASE MARIADB
=====================
```
$ mkdir /var/moodledata
$ chown -R www-data /var/moodledata
$ chmod -R 0777 /var/moodledata >> mysql -u farel -p
$ MYSQL >> CREATE DATABASE moodle DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```



## MOODLE FINAL INSTALATION 
```
$ systemctl reload apache2
$ sudo a2enmod rewrite
$ systemctl restart apache2
$ cd /var/www/moddle
```

```
$ nano .htaccess
\->> add text:: php_value max_input_vars 5000
$ systemctl restart apache2
```

## SSL CONFIG WITH CERTBOT
=============================

#update snap app on ubuntu
```
$ snap install core && snap refresh core 
$ snap install --classic certbot 
```

# download certificate from certbot
```
$ certbot --apache
```
# Enable Auto Renewal Certificate
```
$ certbot renew --dry-run
```
# Config modle to https
```
$ cd /var/www/moddle
$ nano config.php
```

=============================================================
## Path Certificates
=============================================================

# e-learning.farel.jarkom.my.id
Certificate is saved at: /etc/letsencrypt/live/e-learning.farel.jarkom.my.id/fullchain.pem \
Key is saved at:         /etc/letsencrypt/live/e-learning.farel.jarkom.my.id/privkey.pem \
————————————————————————————————————————————

# farel.jarkom.my.id

Certificate is saved at: /etc/letsencrypt/live/farel.jarkom.my.id/fullchain.pem \
Key is saved at:         /etc/letsencrypt/live/farel.jarkom.my.id/privkey.pem \
————————————————————————————————————————————

