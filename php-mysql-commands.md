
commands to install mysql

    sudo apt-get install mysql-server
    sudo mysql_install_db
    sudo mysql_secure_installation

commands to install php

    sudo apt-get install php5-fpm php5-mysql

on the file: /etc/php5/fpm/php
change the cgi.fix_pathinfo

    cgi.fix_pathinfo=0
         
    sudo service php5-fpm restart

    sudo service nginx restart


info.php


    <?php
    phpinfo();
    phpinfo(INFO_MODULES);
    ?>