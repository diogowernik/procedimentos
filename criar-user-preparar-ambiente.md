Dicas como criar novo user no ubuntu, como assinar a chave ssh para conectar com C9 e instalar utilizar o ruby:

    sudo adduser portais-front

    sudo adduser portais-front sudo
    
Create the SSH directory with the ssh command:

    ssh portais-front@159.203.20.217 'mkdir -p ~/.ssh'

Use the scp command to copy the key:

    scp ~/.ssh/id_rsa.pub airalien@159.203.20.217:~/.ssh/authorized_keys

Deletar users

    sudo deluser newuser
    visudo

remover os privilegios também!

    
    