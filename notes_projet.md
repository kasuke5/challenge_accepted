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


* Voir de quoi l'utilisateur a besoin pour se connecter aux machines
* ~~Savoir comment gérer la destruction de machine et/ou d'infrastructure (comment identifier celle qui faut destroy)~~ des dossiers seront créés à chaque terraform plan il suffira d'aller dessus et de faire `terraform destroy` ou `terraform plan -destroy`
* ~~Faire serveur web~~
* Premiere maquette du site (trouver un theme bootstrap)
* Faire infrastructure avec au moins 2 machines avec terraform
* Avoir une liste des TP (demander à eric)

* Liste des truc a installer pour les users/tache ansible :
  * Utilisateur (eleve) avec mdp par defaut (eleve)
  * vim
  * php 7 ?
  * nginx sans config il se demerde apres
  * postfix sans config
  * djbdns sans config
