# Vagrant Cheat Sheet
## Project Setup
```
$ mkdir vagrant_getting_started
$ cd vagrant_getting_started
$ vagrant init
```
## Boxes
### Installing a box
```
$ vagrant box add ubuntu/trusty64
```
### Using a box
```ruby
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"
end
```
## Up and SSH
```
$ vagrant up
...
$ vagrant ssh
...
vagrant@trusty64:~$
```
## Synced Folders
```
$ vagrant up
...
$ vagrant ssh
...
vagrant@trusty64:~$ ls /vagrant
Vagrantfile
```
## Provisioning
Create the following shell script and save it as `bootstrap.sh`
```
#!/usr/bin/env bash

apt-get update
apt-get install -y apache2
if ! [ -L /var/www ]; then
  rm -rf /var/www
  ln -fs /vagrant /var/www
fi
```
Edit the Vagrantfile
```ruby
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.provision :shell, path: "bootstrap.sh"
end
```
