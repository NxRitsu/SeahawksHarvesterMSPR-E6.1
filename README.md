## 🌐 Présentation du Projet

### 🎯 Objectif du Projet "Seahawks Monitoring"

La société "NFL IT" souhaite améliorer son efficacité opérationnelle en concevant une solution de maintenance à distance. Le projet vise à collecter des informations techniques et à assurer la maintenance à distance des réseaux locaux des franchises de la NFL.

### Seahawks Harvester

Effectue un scan réseau du réseau local du client.
Fournis un tableau de bord avec des informations telles que:
* L'adresse IP locale
* Le nombre de machines connectées en LAN
* Affichage du dernier scan réseau (machines + ports)
* Latence de l’accès à Internet
  
Cette application créée un fichier XML comprenant toutes les informations du dernier scan réseau, ce fichier XML est ensuite envoyé sur le serveur voulu via sFTP.
Présenté sous forme d’une application graphique Python déployée sur un environnement Debian 12.
 
## 🚀 Comment utiliser l’Application Seahawks Harvester ?

⚠️ Uniquemnent sous distribution Debian et Python 3.11 ⚠️

1. Télécharger les fichiers :

```
git clone https://github.com/NxRitsu/SeahawksHarvesterMSPR-E6.1
```

2. Installer les dépendances listées dans le fichier "requirement.txt"

3. Modifier le script Python afin d'indiquer la carte réseau à scanner, l'adresse IP du serveur qui va recevoir le fichier XML, l'utilisateur et le chemin distant où arrivera le fichier XML sur le serveur.

   **Ligne 27, 143, 144, et 145**

4. Générer une paire de clés SSH :
```
ssh-keygen -t rsa -b 4096 -f ~/.ssh/id_rsa -N ""
```
```
ssh-copy-id -i ~/.ssh/id_rsa.pub <user_ssh>@<adresse_ip>
```

5. Exécutez cette commande pour lancer l'application graphique Python :

```
sudo -E python3 ./Harvester.py
```

Cela ouvrira l’application graphique Python, affichant l'adresse IP locale avec un bouton permettant d’effectuer le scan réseau.

En cliquant sur le bouton, le scan se lance, affichant le résultat du scan réseau ainsi que la latence WAN.
