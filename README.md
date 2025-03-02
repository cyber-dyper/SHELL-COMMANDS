# 🐚 **SHELL-COMMANDS : Maîtriser les Commandes Shell Essentielles !**  

## 🎯 **Objectif du Dépôt**  
Ce dépôt est conçu pour t'aider à comprendre et utiliser les principales **commandes Shell** sous Linux.  
Tu apprendras à manipuler des fichiers, gérer des processus, automatiser des tâches et bien plus encore !  

---

## 📚 **Table des Matières**  

- [🧠 Qu'est-ce qu'un Shell ?](#-quest-ce-quun-shell-)  
- [💻 Les Commandes de Base](#-les-commandes-de-base)  
  - [📁 Gestion des Fichiers & Répertoires](#-gestion-des-fichiers--répertoires)  
  - [🔍 Navigation dans le Système de Fichiers](#-navigation-dans-le-système-de-fichiers)  
  - [🛠️ Gestion des Utilisateurs & Permissions](#️-gestion-des-utilisateurs--permissions)  
  - [📦 Gestion des Logiciels](#-gestion-des-logiciels)  
  - [🚦 Contrôle des Processus](#-contrôle-des-processus)  
  - [🧹 Nettoyage & Maintenance du Système](#-nettoyage--maintenance-du-système)  
- [🧪 Utiliser les Commandes Shell dans un Scénario Réel](#-utiliser-les-commandes-shell-dans-un-scénario-réel)  
- [📚 Ressources Utiles](#-ressources-utiles)  

---

## 🧠 **Qu'est-ce qu'un Shell ?**  

Un **Shell** est une interface en ligne de commande qui permet de communiquer avec ton système d'exploitation.  
Il interprète les commandes que tu saisis et exécute les tâches demandées, comme :  

- 📂 **Créer ou supprimer des fichiers**  
- 🔍 **Naviguer dans les dossiers**  
- 🚀 **Lancer des programmes**  
- 🛠️ **Automatiser des tâches avec des scripts**  

> 🧠 **Astuce** : Si tu es débutant et que des termes comme *terminal*, *SSH* ou *rsync* te semblent flous, consulte le dépôt [PROJET-RSYNC](https://github.com/cyber-dyper/PROJET-RSYNC) pour un projet pratique !  

---

## 💻 **Les Commandes de Base**  

### 📁 **Gestion des Fichiers & Répertoires**  

| Commande          | Description                                | Exemple                                |  
|-------------------|--------------------------------------------|---------------------------------------|  
| `ls`             | Lister les fichiers d'un dossier            | `ls -l /home`                          |  
| `mkdir`          | Créer un nouveau dossier                    | `mkdir mon_dossier`                    |  
| `rmdir`          | Supprimer un dossier vide                   | `rmdir mon_dossier`                    |  
| `touch`          | Créer un fichier vide                       | `touch fichier.txt`                    |  
| `rm`             | Supprimer un fichier                        | `rm fichier.txt`                       |  
| `cp`             | Copier des fichiers ou dossiers             | `cp source.txt destination.txt`        |  
| `mv`             | Déplacer ou renommer des fichiers/dossiers  | `mv ancien_nom.txt nouveau_nom.txt`    |  

📦 **Scénario :**  
Tu veux préparer des dossiers pour un projet :  

```bash
mkdir /home/utilisateur/projet
cd /home/utilisateur/projet
touch notes.txt
ls -l
```

### 🔍 **Navigation dans le Système de Fichiers**  

| Commande | Description                                | Exemple                  |  
|----------|--------------------------------------------|--------------------------|  
| `cd`     | Changer de répertoire                       | `cd /home/utilisateur`   |  
| `pwd`    | Afficher le répertoire courant              | `pwd`                    |  
| `tree`   | Afficher la structure d'un dossier en arbre | `tree /home/projet`      |  

🚦 **Astuce :** Utilise `cd ..` pour revenir au **dossier parent** !  


### 🛠️ **Gestion des Utilisateurs & Permissions**  

| Commande | Description                                   | Exemple                     |  
|----------|-----------------------------------------------|-----------------------------|  
| `sudo`   | Exécuter une commande en tant qu'administrateur | `sudo apt update`           |  
| `chmod`  | Modifier les permissions d'un fichier           | `chmod 755 script.sh`       |  
| `chown`  | Changer le propriétaire d'un fichier            | `sudo chown utilisateur fichier` |  

---

🔐 **Expliquer les Permissions :**  

- `r` : Lecture (*Read*)  
- `w` : Écriture (*Write*)  
- `x` : Exécution (*Execute*)  

---

📋 **Exemple : `chmod 755 fichier.sh`**  

| Rôle          | Permissions       | Valeur |  
|---------------|-------------------|--------|  
| **Propriétaire** | Lecture, Écriture, Exécution | `7`    |  
| **Groupe**       | Lecture, Exécution            | `5`    |  
| **Autres**       | Lecture, Exécution            | `5`    |  



### 📦 **Gestion des Logiciels**  

| Commande       | Description                                 | Exemple                     |  
|----------------|---------------------------------------------|-----------------------------|  
| `apt update`   | Mettre à jour la liste des paquets disponibles | `sudo apt update`           |  
| `apt install`  | Installer un logiciel depuis les dépôts       | `sudo apt install wget`     |  
| `apt remove`   | Désinstaller un logiciel                      | `sudo apt remove wget`      |  

---

📥 **Scénario : Installation de `curl`**  

```bash
sudo apt update
sudo apt install curl -y
curl --version
```

### ✅ **Explication :**

- `sudo apt update` : Met à jour la **liste des paquets disponibles**.
- `sudo apt install curl -y` : Installe **curl** sans demander de **confirmation** (`-y`).
- `curl --version` : Vérifie que l'installation a bien fonctionné en **affichant la version** de **curl**.


### 🚦 **Contrôle des Processus**

| Commande       | Description                             | Exemple        |
|----------------|-----------------------------------------|----------------|
| `ps`          | Lister les processus en cours            | `ps aux`       |
| `top`         | Afficher les processus en temps réel     | `top`          |
| `kill`        | Terminer un processus                    | `kill 1234`    |

---

🔍 **Astuce :**  
Utilise `kill -9 1234` pour **forcer l'arrêt** d'un processus récalcitrant !  

📋 **Explication :**  
- `ps aux` : Affiche tous les processus en cours avec des détails complets.  
- `top` : Montre en temps réel l'utilisation CPU, mémoire et la charge système.  
- `kill 1234` : Envoie un signal de terminaison au processus d'ID 1234.  
- `kill -9 1234` : Utilise le signal **-9 (SIGKILL)** pour arrêter immédiatement le processus.  

### 🧹 **Nettoyage & Maintenance du Système**

| Commande       | Description                                 | Exemple               |
|----------------|---------------------------------------------|-----------------------|
| `df -h`       | Afficher l'espace disque disponible          | `df -h`               |
| `du -sh`      | Connaître la taille d'un dossier             | `du -sh /home`        |
| `free -h`     | Voir la mémoire disponible                   | `free -h`             |
| `apt autoremove` | Supprimer les paquets inutilisés            | `sudo apt autoremove` |

---

💡 **Scénario :**  
**Nettoyer le système** pour libérer de l'espace disque :  

```bash
sudo apt update
sudo apt upgrade -y
sudo apt autoremove -y
```

### 📋 **Explication :**

- `df -h` : Affiche l'**espace disque utilisé** et disponible sur chaque **partition** en format lisible (`-h` pour *human-readable*).
- `du -sh /home` : Calcule la **taille totale** du dossier **/home** avec un affichage **simplifié**.
- `free -h` : Montre la **mémoire RAM disponible**, utilisée et le **swap** (`-h` pour *human-readable*).
- `sudo apt autoremove` : Supprime automatiquement les **paquets obsolètes** ou non utilisés après des mises à jour.

🧠 **Astuce :**  
Utilise `sudo apt clean` pour **effacer le cache** des paquets téléchargés !


### 🧪 **Utiliser les Commandes Shell dans un Scénario Réel**

🎲 **Pour un projet pratique**, consulte le dépôt **[PROJET-RSYNC](https://github.com/cyber-dyper/PROJET-RSYNC)** où tu pourras appliquer ces commandes pour **automatiser des sauvegardes et restaurations de données** !

---

### 📚 **Ressources Utiles**

- 🌍 [Documentation des Commandes Shell](https://doc.ubuntu-fr.org/commande_shell)  
- 📄 [Guide des Expressions Régulières](https://wiki.ubuntu.com/kmezhoud/Bioinformatics?action=AttachFile&do=get&target=Shell-Regex.pdf)  
- 📁 [PROJET-RSYNC : Utilisation avancée de rsync](https://github.com/cyber-dyper/PROJET-RSYNC)  




