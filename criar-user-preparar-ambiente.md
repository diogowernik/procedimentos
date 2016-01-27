Criar novo user:

sudo adduser diogowernik


Create the SSH directory with the ssh command:

ssh diogowernik@159.203.44.1 'mkdir -p ~/.ssh'

Use the scp command to copy the key:

scp ~/.ssh/id_rsa.pub diogowernik@159.203.44.1:~/.ssh/authorized_keys

    how do i disable the password login for the user and only auth on the ssh key.

Edit the /etc/ssh/sshd_config file, find

PasswordAuthentication yes

and set it to no.

na pasta home/diogowernik/.ssh/authorized_keys copiar a chave do digitalocean lá.


------

ruby -v ok
gems -v ok

usar sudo para as coisas

sudo apt-get install ruby-dev
sudo gem install rails-api
sudo gem install bundler