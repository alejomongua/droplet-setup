droplet-setup
=============

In my local host, add remote host IP to hosts file:

    xx.xx.xx.xx remote_host

Then i login on my new machine:
    
    ssh root@remote_host

Scripts to setup my droplet for development

    apt-get update
    apt-get upgrade -y
    apt-get install -y emacs git-core language-pack-es
    dpkg-reconfigure locales
    localedef -i es_CO -c -f UTF-8 es_CO.UTF-8
    cd $HOME
    git clone https://github.com/startup-class/dotfiles.git
    ln -sb dotfiles/.screenrc .
    ln -sb dotfiles/.bash_profile .
    ln -sb dotfiles/.bashrc .
    ln -sb dotfiles/.bashrc_custom .
    mv .emacs.d .emacs.d~
    ln -s dotfiles/.emacs.d .
    
I also have to add my ssh key to authorized_keys

    # In my local host
    scp ~/.ssh/id_rsa.pub root@remote_host:~/.ssh/authorized_keys
