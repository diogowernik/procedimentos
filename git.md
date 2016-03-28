Instlar git

    apt-get install git
    
Comandos mais utilizados!

    git init

    git add -A .


    git config --global user.email "diogowernik@gmail.com"
    git config --global user.email "diogowernk"


    touch .gitignore

    git log

    git reset --hard HEAD

    git status
    
remove .c9 from git and add to gitgnore, from terminal (if already saved .c9 on git)

    git rm --cached .c9/ -r

Ignore all .c9 specific files, on .gitgnore file

    /.c9/
    
Exemplos de gitgnore:

    /configuration.php
    /images/*
    /templates/*
    /carvalho-diogo/*
    /tmp/*


Compiled source

    *.com
    *.class
    *.dll
    *.exe
    *.o
    *.so
    *.gif
    *.png
    *.jpg

Packages

    *.7z
    *.dmg
    *.gz
    *.iso
    *.jar
    *.rar
    *.tar
    *.zip

Logs and databases

    *.log
    *.sql
    *.sqlite

OS generated files

    .DS_Store
    .DS_Store?
    ._*
    .Spotlight-V100
    .Trashes
    ehthumbs.db
    Thumbs.db

#### Issue

**insufficient permission for adding an object to repository database .git/objects**

    cd .git/objects
    ls -al
    sudo chown -R yourname:yourgroup *

**remove folder cache**

    git rm -r --cached some-directory

**force remove file**

    git rm -f sample.txt

**create new branch**

    git checkout -b feature/users_controller

