# IaC-Ansible
That is documentation for creation jenkins with slave and wildfly instances on AWS


# Setup emvironment

GUIDES:
Ansible instalation:
https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html
Terraform instalation:
https://developer.hashicorp.com/terraform/install
Git instalation:
https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

# Setup infrastructure

Start by cloning the repository!
```
git clone https://github.com/YevheniiHryshkovets/IaC-Ansible.git
```

Now you can create instances on aws by terraform:
```
terraform init

terraform apply
```

Then you need to update hosts on file: hosts.ini
Place ip addreses from console output like this way:

```
[jenkins]
"jenkins_ip" ansible_ssh_user=example_user ansible_ssh_private_key_file=/example/path/key.pem

[jenkins_slave]
"jenkins_slave_ip" ansible_ssh_user=example_user ansible_ssh_private_key_file=/example/path/key.pem

[wildfly]
"wildfly_ip" ansible_ssh_user=example_user ansible_ssh_private_key_file=/example/path/key.pem
```

Now you cat start execute your playbooks:
For Jenkins:
```
ansible-playbook -i hosts.ini jenkins.yml

ansible-playbook -i hosts.ini setup_jenkins_apache.yml
```
For jenkins-slave:
```
ansible-playbook -i hosts.ini jenkins_slave.yml
```
For wildfly:
```
ansible-playbook -i hosts.ini setup_wildfly.yml

ansible-playbook -i hosts.ini setup_wildfly_apache.yml
```

For remove your infrastructure use terraform:
```
terraform destroy
```

