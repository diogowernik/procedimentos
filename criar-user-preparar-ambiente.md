Dicas como criar novo user no ubuntu, como assinar a chave ssh para conectar com C9 e instalar utilizar o ruby:

    sudo adduser username
    visudo
    
add

    username ALL=(ALL:ALL) ALL

ctrl + X
Y

Create a file in the folder root/.ssh

    id_rsa.pub
    paste de big number in this file


Create the SSH directory with the ssh command:

    ssh username@159.203.20.2 'mkdir -p ~/.ssh'

Use the scp command to copy the key:

    scp ~/.ssh/id_rsa.pub username@159.203.20.2:~/.ssh/authorized_keys



Para usar ruby como outro user que não o root:

    ruby -v

    gems -v

E depois usar sudo para as coisas, é possível configurar para não usar o sudo mais, mas tenho que pesquisar como

    sudo apt-get install ruby-dev

    sudo gem install rails-api

    sudo gem install bundler