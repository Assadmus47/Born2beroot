*This project has been created as part of the 42 curriculum by mkacemi42.*

# Born2BeRoot

## Description

**Born2BeRoot** est un projet d’administration système de l’école 42 dont l’objectif est de découvrir les bases de la virtualisation, de la gestion d’un système Linux, et des bonnes pratiques de sécurité.

Le projet consiste à installer et configurer une machine virtuelle sous Linux (Debian ou Rocky Linux) en respectant des contraintes strictes de sécurité, de partitionnement, de gestion des utilisateurs et de services système.  
Il permet d’acquérir une compréhension concrète du fonctionnement d’un serveur Linux sécurisé.

---

## Project Description & OS Choice

### Choix du système d’exploitation : Debian

J’ai choisi **Debian** comme système d’exploitation pour ce projet.

#### Avantages de Debian
- Grande stabilité
- Très utilisé dans les environnements serveurs
- Large documentation et communauté
- Gestion simple des paquets avec `apt`
- Léger et performant

#### Inconvénients de Debian
- Versions des logiciels parfois moins récentes
- Moins orienté entreprise que Rocky Linux

---

## Main Design Choices

### Partitionnement
- Utilisation de **LVM (Logical Volume Manager)**
- Séparation des partitions critiques (`/`, `/home`, `/var`, `/tmp`, `/srv`)
- Améliore la sécurité et la flexibilité de gestion du disque

### Politiques de sécurité
- Mot de passe root fort
- Politique de mots de passe stricte (longueur minimale, expiration, complexité)
- Désactivation de la connexion SSH en tant que root
- Utilisation de **sudo** pour les actions administratives

### Gestion des utilisateurs
- Création d’un utilisateur principal non-root
- Utilisation de groupes (`sudo`, `user42`)
- Permissions limitées selon le principe du moindre privilège

### Services installés
- **SSH** : accès distant sécurisé
- **UFW** : pare-feu
- **cron** : tâches planifiées
- **sudo** : gestion des privilèges

---

## Instructions

### Lancement de la machine virtuelle
1. Ouvrir VirtualBox ou UTM
2. Démarrer la machine virtuelle
3. Se connecter avec l’utilisateur configuré

### Connexion SSH
```bash
ssh <username>@<ip_address> -p 4242
