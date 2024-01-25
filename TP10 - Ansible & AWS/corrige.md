# Module 10: Ansible et AWS

L'objectif de ce tp est de vous montrer comment est ce que nous pouvons
provisionner des machines sur aws à l'aide de Ansible 

Pour realiser ce tp il vous faudra realiser un certains nombres d'etapes:

Prerequis:
- Creation d'un compte AWS (NB: Bien vouloir creer un second compte , l'utilisation du compte root est proscrite!!!!!)
- Creation de Secret_key et Access pour votre compte
- Creation d'une paire de cles avec un nom personnaliser, dans notre cas: devops.pem (NB: .pem est l'extension de votre fichier )
- Recuperer l'id d'un subnet sur votre compte 

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
export AWS_ACCESS_KEY_ID='PUT YOUR OWN'
export AWS_SECRET_ACCESS_KEY='PUT YOUR OWN'
```

### Installer les roles ansibles dans le requirements.yml
```bash
cd ansible-aws-ec2 
ansible-galaxy install -r roles/requirements.yml
```

### Modifier le fichier all.yaml qui se trouve dans le repertoire group_vars en fonction de votre configuration
    dans notre cas nous nous trouvons dans la region "us-east-1 et notre subnet se trouve dans la zone de disponibilite 1a (us-east-1a)

### Lancez votre playbook et verifier que tout se passe bien
```bash
ansible-playbook deploy.yml
```

N'hesiter pas a activer la versobité pour un meilleur Deboggage  (Pour l'activer rajouter juste cette option "-vvv" à la suite de votre commande)

Patienter quelques instant que le processus s'acheve puis recuperer l'ip qui s'affiche a l'ecran que rentrer le dans un navigateur