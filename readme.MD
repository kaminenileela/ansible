# Adhoc command to run:
connect with SSH
* ansible -i <inventory> -e ansible_user=ec2-user -e ansible_password=DevOps321

# examples of adhoc commands:
* ansible -i <ip-address>, all -e ansible_user=ec2-user -e ansible_password=DevOps321 -m ping
* ansible -i <ip-address>, all -e ansible_user=ec2-user -e ansible_password=DevOps321 -m dnf -a "name=nginx state=installed" -b
* ansible -i <ip-address>, all -e ansible_user=ec2-user -e ansible_password=DevOps321 -m service -a "name=nginx state=started" -b

# play books
* keep all adhoc commands in one single file to run. It is called playbook.
# example
* ping-01.yaml

* run playbook as below
- ansible -i inventory.ini web --list-hosts (to list all available hosts)
- ansible -i inventory.ini all --list-hosts (to list all hosts available in group all)
- ansible-playbook -i inventory.ini -e ansible_user=ec2-user -e ansible_password=DevOps321 <yaml-file-name> 

* In ansible we cant create functions. we can use existing filters. filter is represented by | (pipe)

# Ansible Shell vs Ansible comand module
* shell module - it will use shell environment, means we can use redirections >, pipes | and other shell variables. If you want to run shell script ansible or comples commands with redirections then use shell module. 
* command module - it will just run the commands, but can't use shell environment like >, pipe | or variables.
If simple plain command without variables, redirections, pipes etc. we can use command module

