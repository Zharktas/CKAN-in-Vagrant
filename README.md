# CKAN in Vagrant [![CircleCI](https://circleci.com/gh/Zharktas/CKAN-in-Vagrant.svg?style=svg)](https://circleci.com/gh/Zharktas/CKAN-in-Vagrant)

This is mainly aimed at developing ckan in windows for those who for some reason or other do not want to use docker.

These Ansible scripts install ckan within virtual machine while keeping the code base on host machine for development.

## Usage

```
git clone https://github.com/ckan/ckan.git
cd ckan
git clone https://github.com/Zharktas/CKAN-in-Vagrant.git
vagrant up
```

After installation is done:

```
vagrant ssh
/usr/lib/ckan/default/bin/paster serve /etc/ckan/default/development.ini
```

CKAN is now available in http://192.168.33.10:5000/

### Note

Do not use these scripts in any production environment, the scripts contain many defaults that are not suitable for production.
