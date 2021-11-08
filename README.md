# Info

![Version v.0.1](https://img.shields.io/badge/version-v0.1-orange?style=flat-square)
![Version v.2.9.6](https://img.shields.io/badge/ansible-v2.9.6-blue?style=flat-square)
![Version v.2.2.16](https://img.shields.io/badge/vagrant-v2.2.16-blue?style=flat-square)
![Build passed](https://img.shields.io/badge/build-passed-40ab26?style=flat-square)

# SI VM

Prepare the Virtual machine described below and we will organize the next interview to do a review of the project prepared by you and in the second part, we'll ask you to do some additional tasks in bash/python/ansible.

Task Description:
Virtual machine with installed OS from RedHat family (RHEL, CentOS, Fedora) with the following software installed:
- python3
- ansible
- docker/podman
- cockpit behind nginx reverse proxy

VM should be prepared and configured using IaaC tools (preferably Vagrant/Terraform, Ansible) - we should be able to recreate this VM with the same configuration in our environment by just using configuration files prepared by the candidate.

# Dependencies

List of installed packages:
* [x] python3
* [x] nginx 
* [x] docker
* [x] cockpit behind nginx reverse proxy

# Changelog

* [x] 0.1
    * [x] basic installation roles
* [ ] 0.2
    * [ ] test roles installation