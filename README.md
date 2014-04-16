ansible-test
============

The goal of this exercise is to setup a LAMP cluster on ec2/vagrant with Ansible.

##Prerequisites:
* Ansible
* Boto and ~/.boto file configured with your AWS credentials.
* Vagrant

##How to deploy:
* EC2 Cluster

        ansible-playbook -i local provision-ec2-instances.yml
    
* EC2 Single Node

        wip

* Locally using Vagrant

        vagrant up

##How to test if load balancer is working:
* AWS:

        curl http://<aws-lb-ip>

* Vagrant:

        curl http://192.168.33.10

##How to clean up:
* EC2: Shut down all instances, delete hootsuite-test security group.
* Vagrant:

        vagrant destroy -f
