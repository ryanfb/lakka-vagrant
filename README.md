# lakka-vagrant

This repository contains a [Vagrant](https://www.vagrantup.com/) build environment for [Lakka](http://www.lakka.tv/).

**WARNING:** this `Vagrantfile` provisions a large amount of memory/disk resources, as without them I encountered failing builds.

# Usage

* Install/configure Vagrant and VirtualBox
* `vagrant plugin install vagrant-disksize`
* `vagrant up`
* `vagrant ssh`
* Follow the instructions on the [Compiling Lakka](http://www.lakka.tv/doc/Compiling-Lakka/) page 
