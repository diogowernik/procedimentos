Dicas como criar novo user no ubuntu, como assinar a chave ssh para conectar com C9 e instalar utilizar o ruby:

    sudo adduser username


Create the SSH directory with the ssh command:

    ssh username@159.203.44.1 'mkdir -p ~/.ssh'

Use the scp command to copy the key:

    scp ~/.ssh/authorized_keys username@159.203.44.1:~/.ssh/authorized_keys

how do i disable the password login for the user and only auth on the ssh key.

    /etc/ssh/sshd_config

    PasswordAuthentication yes

    and set it to no.

na pasta home/username/.ssh/authorized_keys copiar a chave do cloud9 lá.


------

ruby -v ok
gems -v ok

usar sudo para as coisas

sudo apt-get install ruby-dev
sudo gem install rails-api
sudo gem install bundler