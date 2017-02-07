*** Commande : hadoop fs -ls ***
*********************
> Cette documentation est valable pour HDFS v2.7.3

Description
==
La commande `dfs -ls` permet de lister les fichiers et dossiers présents dans le dossier founri du système de fichier **HDFS**. 

Utilisation
==
`hadoop fs -ls [-d] [-h] [-R] <args>`

L'argument à passer est l'adresse du dossier à lister, ou aucun pour le

Paramètres
--
* _-d :_ liste les dossiers comme des fichiers
* _-h :_ convertit les tailles de fichiers en nombres lisibles par l'homme
* _-R :_ liste tous les sous-dossiers et leur contenu de manière récursive

Retour
--
Le résultat de la commande est une liste des fichiers et dossiers et leurs caractéristiques.


| Caractéristique       |   Fichier   |   Dossier  |
| --------------------- |:-----------:|:----------:|
| Permissions           |      X      |      X     |
| Nombre de réplicas    |      X      |            |
| Utilisateur ID        |      X      |      X     |
| Groupe ID             |      X      |      X     |
| Taille                |      X      |            |
| Date de modification  |      X      |      X     |
| Heure de modification |      X      |      X     |
| Nom                   |      X      |      X     |

Exemple
==

Commande
--

Résultat
--
