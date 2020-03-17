# vagrant and virtualbox 101

this repo  setup a simple ubuntu machine

## what is vagrant?

allows us to manage and provision virtual machines.

it also allows us to pull images of vm from its marketplace

## what is virtual box?

is the sw that does the heavy lifting of creating said machines

## find out basic commands

# create a ubuntu 18.04 server
using vagrant:

vagrant init

atom .

open vagrantfile and change base to the selected package you want to install. in this case it will be 'ubuntu/bionic64'. save it then do next step

vagrant up

vagrant ssh

# how to update packages
sudo apt-get update -y

# how to install packages
sudo apt-get instal <package name> -y

in this case sudo apt-get nginx -y

once installed to run nginx type:
sudo systemctl start nginx

type:
ps aux | grep nginx to check it is running

type exit to exit ubuntu.

now go into config file and type:
config.vm.network "private_network", ip: '192.168.10.100'

once thats in save the file and run vagrant reload in terminal

this will reload your vm without destroying it and will update the ip address.

once this is done type in the ip address into the browser and it will give you a welcome page for nginx.
