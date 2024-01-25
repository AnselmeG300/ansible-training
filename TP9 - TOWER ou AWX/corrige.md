### Objectif du TP
Il est question de déployer Tower et refaire le TP5

- Lancer un client et une image franela/dind sur le labs eazytrainning

### Cloner le repos https://github.com/diranetafen/cursus-devops.git 
```bash
git clone https://github.com/diranetafen/cursus-devops.git
```

### Se deplacer à l'intérieur dans le dossier tower 
```bash
cd cursus-devops/tower
```

### Desarchiver l'archive contenue dans le répertoire personnel: 
```bash
tar -xzvf awx.tar.gz -C ~/
```

### Lancer le docker compose
```bash
cd ~/.awx/awxcompose/
docker compose up -d
```

### Se connecter à l'IHM via le port 80 
```
  login: admin 
  password: password
```

### Mettez à jour l'IP de l'hote client 
* Faites un fork du projet https://github.com/diranetafen/tower-ansible-demo
* Mettez à jour la propriéte ansible_host dans le fichier hosts.yml

### Lancement de notre playbook avec tower
* Creer le projet 
* Definir l'inventaire
* Definir les credentials
* Definir le job

- mot de passe vault du repos pour le déploiement via tower
