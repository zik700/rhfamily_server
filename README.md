# SI VM

![Version v.0.1](https://img.shields.io/badge/version-v0.1-orange?style=flat-square)
![Version v.2.9.6](https://img.shields.io/badge/ansible-v2.9.6-blue?style=flat-square)
![Version v.2.2.16](https://img.shields.io/badge/vagrant-v2.2.16-blue?style=flat-square)
![Build passed](https://img.shields.io/badge/build-passed-40ab26?style=flat-square)

Prepare the Virtual machine described below and we will organize the next interview to do a review of the project prepared by you and in the second part, we'll ask you to do some additional tasks in bash/python/ansible.

Task Description:
Virtual machine with installed OS from RedHat family (RHEL, CentOS, Fedora) with the following software installed:
- python3
- ansible
- docker/podman
- cockpit behind nginx reverse proxy - administration web application available on port specified in vagrant-config.yml ex.(http://localhost:8080)

VM should be prepared and configured using IaaC tools (preferably Vagrant/Terraform, Ansible) - we should be able to recreate this VM with the same configuration in our environment by just using configuration files prepared by the candidate.

# Dependencies
### Host

For proper operation, you must have the following tools:
1. https://www.vagrantup.com/downloads - Vagrant [2.2.16]
2. https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html - Ansible [2.9.6]

### VM
List of installed packages on the machine:
* [x] python3
* [x] nginx 
* [x] docker
* [x] cockpit behind nginx reverse proxy

# Usage example

Run bellow command in project directory for build machine
```bash
$ vagrant up  
```

Run bellow command in project directory for re-provision
```bash
$ vagrant provision  
```

Run bellow command in project directory for remove built machine
```bash
$ vagrant destroy  
```

# Changelog

* [x] 0.1
    * [x] basic installation roles
* [ ] 0.2
    * [ ] test roles installation