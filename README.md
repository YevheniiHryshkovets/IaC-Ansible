# IaC-Ansible

https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html


Ansible instalation:
```
python3 -m pip install --user ansible
```

```
python3 -m pip install --user ansible-core
```

```
python3 -m pip install --user ansible-core==2.12.3
```
Ansible update:
```
python3 -m pip install --upgrade --user ansible
```

add path 
```
export PATH=/path/to/ansible/bin:/Users/y.hryshkovets/Library/Python/3.11/bin
```
```
export PATH=/Users/y.hryshkovets/Library/Python/3.11/bin:$PATH
```

```
terraform init
```

```
terraform apply
```

```
ansible-playbook -i hosts.ini jenkins.yml
```

```
terraform apply -target=aws_instance.wildfly-server
```

```
terraform apply -target=aws_instance.jenkins-server
```

```
terraform apply -target=aws_instance.jenkins-server

ansible-playbook -i hosts.ini setup_jenkins_apache.yml

ansible-playbook -i hosts.ini setup_jenkins.yml
```

```
terraform apply -target=aws_instance.wildfly-server

ansible-playbook -i hosts.ini setup_wildfly.yml

ansible-playbook -i hosts.ini setup_wildfly_apache.yml
```