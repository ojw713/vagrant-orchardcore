# Vagrant OrchardCore with Linux

This repository will install the [OrchardCore](http://www.orchardcore.net/) docker container.


## Vagrant and Ansible
Do a simple `vagrant up` by using [Vagrant](https://www.vagrantup.com)'s [Ansible provisioner](https://www.vagrantup.com/docs/provisioning/ansible.html). All you need is a working [Vagrant installation](https://www.vagrantup.com/docs/installation/) (2.2.4+ but the latest version is always recommended), a [provider](https://www.vagrantup.com/docs/providers/) (tested with the latest [VirtualBox](https://www.virtualbox.org) version), and 3GB of RAM.

If more than the default 10GB disk space is needed
- run `vagrant plugin install vagrant-disksize` to install the vagrant plugin
- add `ubuntu.disksize.size = "25GB"` to the Vagrantfile.

## OrchardCore

Access at [http://127.0.0.1:8077](http://127.0.0.1:8077).
