# Install - Debian based

## Install Ansible

```bash
sudo apt update
sudo apt -y install python3-pip ansible curl sudo
```

## Configure system for playbook run against localhost

```bash
sudo bash -c 'cat << EOF >> /etc/sudoers
# Ansible User Does Not require password
ansible ALL=(ALL:ALL) NOPASSWD: ALL

EOF'
```

```bash
sudo useradd -r -m -s /bin/bash ansible
```

## Run Ansible Playbook from URL against Localhost

Setup Debian Server with basic things:
```bash
sudo -u ansible bash -c "curl https://raw.githubusercontent.com/aaron-imbrock/ansible-playbooks/main/debian-server-common.yaml | ansible-playbook -c local -i "127.0.0.1," /dev/stdin"
```
Install Docker:
```
sudo -u ansible bash -c "curl https://raw.githubusercontent.com/aaron-imbrock/ansible-playbooks/main/docker-server.yaml | ansible-playbook -c local -i "127.0.0.1," /dev/stdin"
```
Install NGINX:
```
sudo -u ansible bash -c "curl https://raw.githubusercontent.com/aaron-imbrock/ansible-playbooks/main/nginx-server.yaml | ansible-playbook -c local -i "127.0.0.1," /dev/stdin"
```
