ansible-test
============

##Prerequisites:
* Ansible
* Boto + ~/.boto file configured.
* Vagrant

##How to deploy:
* EC2 Cluster

    ansible-playbook -i local provision-ec2-instances.yml
    
* A EC2 Node


* Locally using Vagrant

    vagrant up

##How to clean up:
* EC2: Shut down all instances, delete hootsuite-test security group.
* Vagrant:

    vagrant destroy -f
