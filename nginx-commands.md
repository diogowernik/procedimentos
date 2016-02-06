nginx commands

simple nginx install

    sudo apt-get install nginx



    sudo service nginx restart

nginx verify troubles

    nginx -t

complete remove nginx

    sudo apt-get purge nginx nginx-common
    sudo apt-get autoremove

nginx page speed - dont know yet how to use:

    https://github.com/Levantado/ngx_pagespeed-install-script/releases/download/1a/page-speed.sh 

    bash page-speed.sh

    ip addr show eth0 | grep inet | awk '{ print $2; }' | sed 's/\/.*$//'