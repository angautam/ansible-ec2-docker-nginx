# ansible-ec2-docker-nginx

The playbook lets you provision EC2 instance on AWS cloud and install docker.

The image I am using here is of Red Hat distribution AMI image from AWS cloud.

Instruction :

1) as prerequisites install below and ensure its done in order on the control node of ansible.

#Pre-requisite

#Pip is not available in RHEL core repositories. To install pip we need to enable the EPEL repository:

#sudo yum install epel-release

#Once the EPEL repository is enabled we can install pip and all of it’s dependencies with the following command:

#sudo yum install python-pip

#Install development tools

#sudo yum install python-devel

#Development tools are required for building Python modules, you can install them with:

#sudo yum groupinstall 'development tools'

#sudo pip install --upgrade pip

#sudo pip install boto3

#sudo pip install boto

#sudo yum install ansible

2) under /etc/ansible/hosts file. place below entry:
[local]
localhost

[webserver]

3) export the secret key and access key of AWS account on terminal.

4) run "ansible-playbook launchec2-ansible.yml -vvv"

5) after this is done, ensure your hosts entry gets updated with public ip and user key details just under tag [webserver]

6) run "ansible-playbook docker-install.yml" to install docker on newly provisioned ec2 instance.

7) then run "ansible-playbook rundockercontainer-curl.yml" to build the docker image and run it.

The Solution task and detailed steps and technical arguments are attached.

