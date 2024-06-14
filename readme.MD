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

* In ansible we cant create functions. we can use existing filters.
