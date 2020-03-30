# Vagrant OrchardCore with Linux

This repository will install the [OrchardCore](http://www.orchardcore.net/) docker container.


## Vagrant and Ansible
Do a simple `vagrant up` by using [Vagrant](https://www.vagrantup.com)'s [Ansible provisioner](https://www.vagrantup.com/docs/provisioning/ansible.html). All you need is a working [Vagrant installation](https://www.vagrantup.com/docs/installation/) (2.2.4+ but the latest version is always recommended), a [provider](https://www.vagrantup.com/docs/providers/) (tested with the latest [VirtualBox](https://www.virtualbox.org) version), and 3GB of RAM.

If more than the default 10GB disk space is needed
- run `vagrant plugin install vagrant-disksize` to install the vagrant plugin
- add `ubuntu.disksize.size = "25GB"` to the Vagrantfile.

## OrchardCore

Access at [http://127.0.0.1:8077](http://127.0.0.1:8077).

## Postgres DB Connection

Access at [http://127.0.0.1:5432](http://127.0.0.1:5432).

Default password containted in the `vars.yml` [file](https://raw.githubusercontent.com/ojw713/vagrant-orchardcore/master/orchardcore/vars.yml).

If the default settings are not changed this conneciton string can be used:

`Server=db;Port=5432;Database=orchard;User Id=postgres;Password=bshpassword`