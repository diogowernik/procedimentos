How to connect bluehost shared server with C9 ide.


Is needed some steps:

1) Connect with your bluehost account via terminal

2) Create ssh folder and insert the data from your c9 account

    ssh yourusername@yousite.com 'mkdir -p ~/.ssh'

3) Go to you file manager, in your cpanel, with show hidden files on
find the folder .ssh/

Inside this folder create a file:

    authorized_keys

Paste the ssh number from c9 inside this folder and save

4) download and install node.js in your home directory, via terminal, for example, my home directory is home1/

In my case i had to install node 0.12.9 the new versions were not working with my bluehost account

    wget http://nodejs.org/dist/latest-v0.12.x/node-v0.12.9.tar.gz

    tar -xzf node-v0.12.9.tar.gz

    cd node-v0.12.9

    ./configure --prefix=/home1/yourusername/node/ 
    make  
    make install


5) install python


Download Python

Enter the following commands to download and extract Python 2.7 to your hosting account.

        mkdir ~/python
        
        cd ~/python
        
        wget http://www.python.org/ftp/python/2.7.2/Python-2.7.2.tgz
        
        tar zxfv Python-2.7.2.tgz
        
        find ~/python -type d | xargs chmod 0755
        
        cd Python-2.7.2
        
Install Python

Once extracted you can use the following commands to configure and install Python.

        ./configure --prefix=$HOME/python
        
        make
        
        make install
        
Modify the .bashrc

For your local version of python to load you will need to add it to the .bashrc file.

    vim ~/.bashrc
    i 

Enter:

    export PATH=$HOME/python/Python-2.7.2/:$PATH
        
Write the changes (press ESC) and close vim:

    :wq
        
Press Enter

    source ~/.bashrc
        
Note: You may need to logout for the environment to update. 
Enter python -V to check the version of python installed.

6) In your c9 account put the path to your node instalation:


user : yourusername (from bluehost)

host name: yoursite.com

path to node:  /home1/yourusername/node/bin/node

click create

and thats it...
