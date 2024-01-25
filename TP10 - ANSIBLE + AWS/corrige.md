#### Versions sur eazytraining/ansible
```bash
OS: Centos7
ansible 2.9.25
  config file = /etc/ansible/ansible.cfg
  configured module search path = [u'/home/admin/.ansible/plugins/modules', u'/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/lib/python2.7/site-packages/ansible
  executable location = /bin/ansible
  python version = 2.7.5 (default, Oct 14 2020, 14:45:30) [GCC 4.8.5 20150623 (Red Hat 4.8.5-44)]
```

### Cloner le repos https://github.com/eazytrainingfr/ansible-aws-ec2 
```bash
git clone https://github.com/eazytrainingfr/ansible-aws-ec2.git
```

### Creer le fichier devops.pem
```bash
vi devops.pem
```

### Creer les variables d'environnement AWS_ACCESS_KEY_ID et AWS_SECRET_ACCESS_KEY 
```bash
export AWS_ACCESS_KEY_ID=""
export AWS_SECRET_ACCESS_KEY="secret -key"
```

### Installer les roles ansibles dans le requirements.yml
```bash
cd ansible-aws-ec2 
ansible-galaxy install -r roles/requirements.yml
```

### Lancez votre playbook et verifier que tout se passe bien
```bash
ansible-playbook --ask-become-pass deploy.yml
```
