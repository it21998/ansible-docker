# Prerequisites
* Installs on local machine that runs the playbooks
* Ansible install
```bash
sudo apt update
sudo apt install software-properties-common
sudo apt-add-repository --yes --update ppa:ansible/ansible

sudo apt update
sudo apt install ansible
```
* roles install
```bash
ansible-galaxy install geerlingguy.docker
ansible-galaxy install geerlingguy.pip
```
* to test if a group of hosts are accesible, run
```bash
ansible -m ping all <group-name>
```
# Possible tweaking code
* hosts.yml
```yaml
deploymentdocker:
  hosts:
    deploy2:
      ansible_host: 20.58.117.204
      ansible_port: 22
      ansible_ssh_user: azureuser    
      #ansible_ssh_private_key_file= ~/.ssh/id_rsa.pub
```


# Open ports on azure
* 8000
* 9000
* 80
* 8025
* 100
* 5432

# If remote machine has no docker
```bash
ansible-playbook playbooks/docker-install.yml
```



# Ready to run playbooks
```bash
ansible-playbook playbooks/django-app-docker.yml
ansible-playbook playbooks/django2-app-docker.yml
```
