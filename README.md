ansible-test
============

The goal of this exercise is to setup a LAMP cluster on ec2/vagrant with Ansible.

##Prerequisites:
* Ansible
* Boto and ~/.boto file configured with your AWS credentials.
* Vagrant

##How to deploy:
* EC2 Cluster

        ansible-playbook -i local ec2-lamp-cluster.yml
    
* EC2 Single Node

        ansible-playbook -i local ec2-lamp-simple.yml

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
        
##Troubleshooting

* You cannot re-execute the ec2 playbooks without killing all the exisiting instances.
* You can re-execute the vagrant playbooks by:

        vagrant provision lb1


