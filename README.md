#!/bin/sh
# sh docker_setup.sh

# Assuming you’re using zsh and you’ve already installed 
# VirtualBox from MSC

LOGIN=$(whoami)

# Setup Brew
curl -fsSL https://rawgit.com/gcamerli/42brew/master/set.sh
zsh

# Setup docker from Brew
brew install docker
brew install docker-machine

# Check docker version
docker version
docker-machine version

# Create a default docker machine
docker-machine create --driver virtualbox Char
docker-machine ls

# Create symbolic links

#ln -s /goinfre/$LOGIN ~/goinfre 

mv ~/.docker ~/goinfre
mv ~/VirtualBox\ VMs ~/goinfre
ln -s ~/goinfre/.docker ~/.docker
ln -s ~/goinfre/VirtualBox\ VMs ~/VirtualBox\ VMs

# Set docker env variables
vim ~/.zshrc
```
# Set docker env variables
eval $(docker-machine env Char)
```
# Update your rc file
source ~/.zshrc

# https://github.com/Joao-Henrique/Docker_Medium_Tutorial