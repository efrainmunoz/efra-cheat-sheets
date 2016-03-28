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
## Networking
### Port Forwarding
Edit the Vagrantfile
```ruby
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.provision :shell, path: "bootstrap.sh"
  config.vm.network :forwarded_port, guest: 80, host: 4567
end
```
Run a `vagrant reload` or `vagrant up` so that these changes can take effect.
## Share
### Login to Hashicorp's Atlas
```
$ vagrant login
Username or Email: mitchellh
Password (will be hidden):
You are now logged in!
```
### Share it
```
$ vagrant share
...
==> default: Your Vagrant Share is running!
==> default: URL: http://frosty-weasel-0857.vagrantshare.com
...
```
### Teardown
Use `vagrant suspend`, `vagrant halt`, or `vagrant destroy`.
## Multi-Machine
