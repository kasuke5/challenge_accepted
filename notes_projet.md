# Notes pr projet

* se connecter aux serveur aws :
récup la clé ssh au format .pem (chmod 400 je crois)
`ssh -i /home/flo/Téléchargements/Essai.pem ubuntu@ec2-54-194-185-113.eu-west-1.compute.amazonaws.com`

+ charte : methode travail, save, reunion, nomenclature etc...
+ spec : ce que veux le client, mission, objectifs (de la mission  4 5 6 SMART), fonctionnalités
+ planning : fcontionnalités en taches.
+ script terraform + script ansibe de test pour it1


+ comment acceder aux machine avec config pété

* Ansible
  * lancer le playbook `ansible-playbook -i hosts playbook.yml`

* types de tp proposé
  * routage
  * ARP
  * NAT Port forwarding
  * DHCP
  * DNS
  * Serveur web
  * Serveur mail
  * SSH



Objectif :
Créer des machines virtuelles avec des configurations réseau corrompu et le but est de résoudre les différents problèmes pour avoir une/des machine avec un réseau fonctionnel

Creation d'infrastructure en ligne pour chaque chapitre des cours réseaux d'openclassroom.

# Fonctionnalités

* Creation de compte utilisateur (inscription/connexion)
* Utilisateur avec suivi de cours et de tp (comme sur openclassroom)
* Serveur web avec base de données
* Creation de machines virtuelles automatisées avec terraform + ansible pour AWS
* Creation machine virtuelles routeur
* Creation d'infrastructure
* Création d'exercices personnalisés
* Script permettant de voir si l'utilisateur a réussi l'exercice
* Cacher un tuto dans les VM
* Script ajout de machines
* Machines fantomes pour tester (empecher requete icmp + fige table arp donc acces que via certaine machine)
* Script pour récupérer toutes les infos pour accéder aux VM
* Serveur mail pour envoyer infos aux utilisateurs
* Lister les fonctionnalités par rapport aux exercices pour ansible. (lister ce quil faut installer/configurer)



*faire tuto ajout de machine AWS via terraform*

---
# tâches à réaliser avant IT2:

* Pour la charte :
  * ~~sauvegarde (à quelle fréquence)~~
  * ~~nomenclature (nommage des fichiers)~~
  * planning à faire


* Pour les specs :
  * Mission à retoucher
  * Objectifs à SMARTER
  * Details sur la machine de supervision (machine fantome)
  * Comment on se connecte aux différentes machines


* ~~Voir de quoi l'utilisateur a besoin pour se connecter aux machines~~ adresse ip de la machine qu'on recupere izi, et log par defaut eleve:eleve
* ~~Savoir comment gérer la destruction de machine et/ou d'infrastructure (comment identifier celle qui faut destroy)~~ des dossiers seront créés à chaque terraform plan il suffira d'aller dessus et de faire `terraform destroy` ou `terraform plan -destroy`
* ~~Faire serveur web~~
* ~~Premiere maquette du site (trouver un theme bootstrap)~~
* ~~Faire infrastructure avec au moins 2 machines avec terraform~~
* ~~BDD~~
* ~~Connexion/ Inscription~~
* Avoir une liste des TP (demander à eric) Faire 3 machines, chacun son réseau, elle passe toutes par un routeur qui va leur fournir internet, une des machines sera serveur web
* Faire machine de supervision (pour savoir si l'exo a été réussi)

* Liste des truc a installer pour les users/tache ansible :
  * ~~Ajouter utilisateur (eleve) avec mdp par defaut (eleve)~~
  * ~~vim~~
  * ~~Aller dans `/etc/ssh/sshd_config` et changer par `PasswordAuthentication yes
` et `systemctl reload sshd`~~
  * ~~Autoriser eleve dans sudoers~~
  * Créer plusieurs interfaces réseaux et leur attribué une adresse + mask

---
# Le tp à faire :
* 1 machine serveur :
  * Table de routage à faire
  * Créer plusieurs interfaces réseaux (3)
  * Faire en sorte que la machine devienne routeur avec `echo 1 > /proc/sys/net/ipv4/ip_forward`
  * Prendre les requêtes et donner l'accès à internet aux autres machines
* 1 machine web sur son réseau
* 1 autre machine sur son réseau différents des autres

---
# Changement car on avance pas
## TP à faire pour IT2/3
* Script pour vérifier DNS, dig @IP_Instance challenge-accepted.com (A/MX/NS)
* Le tp sera de faire un DNS pour le nom de domaine challenge-accepted.com NS, MX et A
* De base, création de la machine pour 48h, et bouton quand on s'approche de la fin pour redemander 48h, bouton pour detruire l'instance.
* Pour l'instance, activer ICMP port web et SSH
