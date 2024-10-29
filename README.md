# Ansible-Basics <a href="https://www.ansible.com/" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/ansible/ansible-icon.svg" alt="ansible" width="40" height="40"/> </a>
![ansible](https://github.com/harshitsahu2311/Ansible-Basics/blob/main/ansible.jpg)

# Installing Steps
```sh
sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install ansible
```
# Configure SSH Private Key
Go to the folder in windows, where your private key is there and open terminal and run this command:
```sh
scp -i "new-key.pem" new-key.pem ubuntu@ec2-54-169-226-225.ap-southeast-1.compute.amazonaws.com:/home/ubuntu/keys
```
`scp -> Secure Copy through SSH` <br>
`-i "new-key.pem" -> Private Key` <br>
`new-key.pem -> source` <br>
`ubuntu@ec2-54-169-226-225.ap-southeast-1.compute.amazonaws.com:/home/ubuntu/keys -> Destination` <br>


# For Adding Server
```sh
vim /etc/ansible/hosts
```
Paste the below code 
```sh

[servers] # Name of your group
server-1 ansible_host=47.129.221.7 #<paste your servers public ip>
server-2 ansible_host=18.143.143.75
server-3 ansible_host=54.169.226.225

[all:vars] # Variables required for servers
ansible_python_interpreter=/usr/bin/python3
ansible_user=ubuntu
ansible_ssh_private_key_file=/home/ubuntu/keys/new-key.pem

```
