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
