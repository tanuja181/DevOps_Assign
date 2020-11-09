Directory Structure:
1. configs - contain environment specific variable
2. inventories - contains inventory file for each environment
3. roles - This will have subfolders like java,tomcat

a) tomcat - this folder will have files related to the installation of tomcat

     - files (This will contain files which you want to copy to to your destination servers)

     - handlers ( This is used to start/stop the services)

     - tasks ( playbook to install the software)

b) add_devops_user - This folder will have files related to the setup of initial user

5.main.yml - This is the main file which will execute roles in 

Creating Encrypted File:

$ ansible-vault create filename.yaml

Editing Encrypted Files:

$ ansible-vault edit secrets.txt

How to run Playbook

ansible-playbook main.yml -i inventories/dev/hosts --user ec2-user --key-file /home/ec2-user/playbooks/ansible_aut.pem -e '@configs/dev.yml'
ansible-playbook main.yml -i inventories/dev/hosts --user devops --key-file /home/devops/.ssh/id_rsa -e '@configs/dev.yml'