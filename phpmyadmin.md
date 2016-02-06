Step One — Install phpMyAdmin

    sudo apt-get update
    sudo apt-get install phpmyadmin

    sudo php5enmod mcrypt
    sudo service php5-fpm restart

    http://server_domain_or_IP/phpmyadmin

Step Two — Secure your phpMyAdmin Instance

    cd /usr/share/nginx/html
    ls -l
    sudo mv phpmyadmin nothingtosee
    ls -l

php.ini max files

    /etc/php5/php.ini

-----

Maximum allowed size for uploaded files.

    upload_max_filesize = 40M

Must be greater than or equal to upload_max_filesize

    post_max_size = 40M



    etc/nginx/nginx.config



    http:{

    client_max_body_size 50M;

    }



    sudo service php5-fpm restart