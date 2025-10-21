# Travail par Maika Veilleux
## Attaque (exploit)
Voici les étapes détaillées pour pouvoir modifier le courriel / téléphone sur la page demandée:
1. Vérifier si d'autres ports sont ouverts sur le serveur avec nmap.
![nmap](nmap.png) <br>
2. Se connecter par ssh (le port 22 est ouvert) avec l'adresse IP du serveur.
![ssh](ssh.png) <br>
3. Hacker par force brute avec les informations qu'on a sur bob pour trouver le nom d'utilisateur et le mot de passe. (bob, Sophie2014!)
![login](login.png) <br>
4. Ouvrir le fichier contact.html qui se trouve dans le répertoire /var/www/html dans un éditeur de texte avec la commande "nano /var/www/html/contact.html". Les permissions du fichier sont à 777 donc Bob a les droits d'écriture.
![contact](contact.png) <br>
5. Changer le numéro de téléphone et le courriel dans les balises corrrespondantes et enregistrer les modifications.
![changement](changement.png) <br>
6. Ouvrir le fichier realisation.html qui se trouve dans le répertoire /var/www/html dans un éditeur de texte avec la commande "nano /var/www/html/realisation.html". Supprimer les balises d'image et enregistrer les modifications.
![real](real.png) <br>
En rechargeant la page, on constate que le numéro de téléphone a été modifié, les images supprimées et le courriel changé : <br>
![telephone](telephone.png) <br>
![images](images.png)
## Correctif 1
Configurer un pare-feu local pour limiter l'accès au port 22 uniquement aux adresses IP de confiance et bloquer les autres tentatives de connexions.
## Correctif 2
Utiliser le principe du plus bas privilège en limitant les permissions de l'utilisateur bob.
## Correctif 3
