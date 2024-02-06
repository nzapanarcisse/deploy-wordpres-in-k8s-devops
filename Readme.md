# Déploiement de WordPress sur un cluster Kubernetes

Ce guide vous explique comment déployer WordPress sur un cluster Kubernetes en suivant les bonnes pratiques. Nous allons utiliser les objets suivants :

## Pour MySQL :

- Utilisation d'un StatefulSet pour créer la base de données et assurer une persistance grâce à l'utilisation de Persistent Volumes (PV).
- Configuration d'un service de type ClusterIP avec un sélecteur pour WordPress et MySQL, permettant ainsi de sélectionner le pod MySQL créé par notre StatefulSet.
- Utilisation d'un objet Secret pour stocker en toute sécurité les mots de passe de l'utilisateur de la base de données et de MySQL.

## Pour WordPress :

- Utilisation d'un Deployment pour créer le pod WordPress.
- Configuration d'un service de type ClusterIP pour exposer le pod à l'intérieur du cluster.
- Utilisation d'un rôle Ingress pour exposer finalement notre pod à l'extérieur du cluster.
- Utilisation de Persistent Volumes (PV) et Persistent Volume Claims (PVC) pour assurer la persistance des données du site.
### commandes pour déployer:
kubectl apply --kustomize .

### suppression des resources
kubectl delete --kustomize .

Veuillez consulter le fichier [wordpress-deployment.yml](wordpress-deployment.yml) pour obtenir des instructions détaillées sur la mise en place de l'environnement de déploiement et les commandes nécessaires pour exécuter les déploiements.

N'hésitez pas à consulter la section "Contributing" (Contribuer) pour savoir comment participer à l'amélioration de ce guide(Par Narcisse **LEPRO**).

---
**Note** : Assurez-vous de suivre toutes les bonnes pratiques de sécurité et de configuration pour votre environnement spécifique avant de déployer WordPress sur un cluster Kubernetes.