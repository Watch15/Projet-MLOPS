# Projet Terraform avec intégration Ansible

## Description

Ce projet utilise Terraform pour provisionner des instances EC2 sur AWS et exécuter un playbook Ansible afin de configurer les machines nouvellement créées. Il s'agit d'un exemple d'intégration Infrastructure as Code (IaC) avec des outils comme Terraform et Ansible pour automatiser le déploiement et la gestion des infrastructures cloud.

## Fonctionnalités

- Création d'instances EC2 sur AWS avec Terraform.
- Configuration des instances via un playbook Ansible lancé automatiquement après la création.
- Gestion des inventaires dynamiques AWS pour Ansible.

## Structure du projet

- **main.tf** : Définit l'infrastructure AWS, incluant les instances EC2 et leurs configurations.
- **variables.tf** : Contient les variables utilisées pour personnaliser le déploiement.
- **aws_ec2.yml** : Plugin d'inventaire dynamique Ansible pour récupérer les informations des instances AWS.
- **playbook.yml** : Fichier Ansible contenant les tâches pour configurer les instances EC2.
- **dataset** : contient tout les jeux de données utiliser pour réaliser
- **ML_project**: Contient le programme de machine learning

## Prérequis

- **Terraform** installé sur votre machine.
- **Ansible** installé et configuré pour utiliser un inventaire dynamique.
- **AWS CLI** configurée avec les bonnes informations d'identification.
- Un compte AWS avec les autorisations nécessaires pour créer des ressources EC2.

## Instructions

### Étape 1 : Initialisation de Terraform

1. Initialisez Terraform dans le répertoire du projet :
   ```bash
   terraform init
   ```

### Étape 2 : Vérification du plan

2. Vérifiez le plan d'exécution Terraform pour voir les ressources qui seront créées :
   ```bash
   terraform plan
   ```

### Étape 3 : Création de l'infrastructure

3. Appliquez le plan Terraform pour provisionner les instances EC2 :
   ```bash
   terraform apply
   ```

### Étape 4 : Exécution du playbook Ansible

4. Une fois les instances créées, exécutez Ansible pour configurer les machines :
   ```bash
   ansible-playbook -i aws_ec2.yml playbook.yml
   ```

## Résultats attendus

- Instances EC2 déployées sur AWS.
- Configuration des instances via Ansible (exemple : installation de logiciels, gestion des utilisateurs, etc.).
- Ou peux alors observe le résultat dans l htpp://[IP_de_la_machine]/notebook.html

## Nettoyage

Pour détruire toutes les ressources créées :
```bash
terraform destroy
```

## Auteur

Ce projet a été réalisé dans le cadre d'une intégration entre Terraform et Ansible pour démontrer les capacités d'automatisation de l'infrastructure.

