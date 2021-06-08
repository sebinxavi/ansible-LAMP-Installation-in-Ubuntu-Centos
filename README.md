# Ansible Playbook for Installing LAMP in both CentOS and Ubuntu

This Ansible Playbook will helps you to Install LAMP in both CentOS and Ubuntu at a time. Ansible is an open source IT Configuration Management, Deployment & Orchestration tool. It aims to provide large productivity gains to a wide variety of automation challenges.

## Features of Ansible

- Infrastructure Provisioning
- Configuration Management
- IT automation
- Continuous deployment
- Application Development
- Network Automation
- Security Automation
- Infrastructure Orchestration 

## Prerequisites
- Ansible version - 2.9
- Linux Master Server 
- Two Client Servers - CentOS, Ubuntu
- SSH PEM key for Remote Servers
- SSH User with sudo privilege

### Usage

This script will perform following operations;

- Update all Packages
- Install LAMP in CentOS and Ubuntu Servers
- Create sample index.html file in Apache Document root
- Restart and Enable Apache, MySQL services

# Ansible Installation

```sh
$ yum -y install ansible
```

## How to configure

With Ansible installed, you are ready to provision the remote server by following the below steps.

```sh
$ git clone https://github.com/sebinxavi/ansible-LAMP-Installation-in-Ubuntu-Centos.git
$ cd ansible-LAMP-Installation-in-Ubuntu-Centos
```

Open the file 'hosts' and edit the Remote hosts details

The Sample format is provided below,
```sh
[ubuntu]
172.31.43.55  ansible_user=ec2-user ansible_port=22 ansible_ssh_private_key_file="ubuntu.pem"
```

- Add a Group name for the remote hosts. Example: centos/ubuntu
- Add the Remote Host IP addresse. Example: 172.31.43.55
- Add the Remote SSH User. Example: ec2-user
- Add the SSH port number: Example: 22
- Import the SSH key file to the same location in which we are going to run the Ansible command and add the key name to the file hosts

Run the ansible-playbook from the master server by below command,

```sh
$ ansible-playbook -i hosts apache.yml
```

## Results:
Access the IP address of the Remote Host servers in Browser and you can see the sample html page.
