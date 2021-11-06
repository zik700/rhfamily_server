# SI VM

Prepare the Virtual machine described below and we will organize the next interview to do a review of the project prepared by you and in the second part, we'll ask you to do some additional tasks in bash/python/ansible.

Task Description:
Virtual machine with installed OS from RedHat family (RHEL, CentOS, Fedora) with the following software installed:
- python3
- ansible
- docker/podman
- cockpit behind nginx reverse proxy

VM should be prepared and configured using IaaC tools (preferably Vagrant/Terraform, Ansible) - we should be able to recreate this VM with the same configuration in our environment by just using configuration files prepared by the candidate.

# Info

author: dgryn
version: 0.1
state: stable
vagrant: 2.2.16
ansible: 2.9.6

# Dependencies

List of installed packages:
* [ ] python3 == 3.6.8
* [ ] nginx 
* [ ] docker
* [ ] cockpit behind nginx reverse proxy

# Changelog

* [ ] 0.1
    * [ ] basic installation roles
    * [ ] handle purge cache
* [ ] 0.2
    * [ ] install and describe know how about testinfra
    * [ ] test installed roles