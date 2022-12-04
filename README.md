# Deploy a Web application with Ansible

### Project Prerequisites

1. Working Knowledge of git
2. knowledge of AWS management console
3. Knowledge of AWS Service (EC2, security groups)

### Steps to follow

1. Login to your aws management console
2. Create the first sg (main-sg), enable ssh from your IP
3. Create the second sg (ec2-sg), enable ssh from main-sg, and enable HTTP from port 80
   Launch the ansible-ec2
4. ssh into the ansible-ec2
5. Create key pairs on the ansible-ec2
6. import the public key into the ec2 console (ansible-ec2-pub-key)
7. launch the remaining 3 servers. keypair: ansible-ec2-pub-key | Security group: ec2-sg
8. test your connection -> ssh into other ec2 servers using their specific private IPs while on the ansible-ec2

#### On Ansible master controller (ansible-ec2)

1. Instll python 3.7.x
2. Install pip
3. install virtualenv (if you are using virtual environment)
4. Install and configure aws cli
5. Install ansible on the ansible-ec2
6. Clone this repository to your project directory
7. Within your project directory, create and activate a virtual environment
8. Install project dependencies
9. Within the etc/ansible directory run this query to get server tags ``
10. Update the hosts in the main.yml file to reflect your desried tag
11. Run the playbook `ansible-playbook --ask-vault-password --key-file ~/.ssh/id_rsa main.yml`
