ansible-test
============

The goal of this exercise is to setup a LAMP stack on EC2 or locally via Vagrant with Ansible.

##Prerequisites:
* Ansible v1.5+
* Boto and ~/.boto file configured with your AWS credentials.
* Vagrant v1.5+

##How to deploy:
* LAMP (EC2)

        ansible-playbook -i local ec2-lamp-simple.yml

* LAMP Cluster (EC2)

        ansible-playbook -i local ec2-lamp-cluster.yml

* LAMP Cluster (Vagrant)

        vagrant up

##How to verify if the setup is working:
* AWS:

        curl http://<aws-lb-ip>

* Vagrant:

        curl http://192.168.33.10

##How to clean up:
* EC2: Terminate all instances created by this playbook, delete hootsuite-test security group.
* Vagrant:

        vagrant destroy -f
        
##Troubleshooting

* You cannot re-execute the ec2 playbooks without terminating all the exisiting instances that were created by this playbook.
* You can re-execute this playbook in Vagrant by:

        vagrant provision lb1


