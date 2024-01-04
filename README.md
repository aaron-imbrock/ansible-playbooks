# Install - Debian based

## Install Ansible

```bash
sudo apt update
sudo apt -y install python3-pip ansible
```

## Configure system for playbook run against localhost

```bash
sudo bash -c 'cat << EOF >> /etc/sudoers
# Ansible User Does Not require password
ansible ALL=(ALL:ALL) NOPASSWD: ALL

EOF'
```

```bash
useradd ansible
```

## Run Ansible Playbook from URL against Localhost

A combination of `curl` and `ansible-playbook` will do ya:
```bash
curl https://raw.githubusercontent.com/aaron-imbrock/ansible-playbooks/main/debian-server-common.yaml | ansible-playbook -c local -i "127.0.0.1," /dev/stdin
```
