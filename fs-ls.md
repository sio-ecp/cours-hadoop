*** Commande : hadoop fs -ls ***
*********************
> Cette documentation est valable pour HDFS v2.7.3

Description
==
La commande `dfs -ls` permet de lister les fichiers et dossiers présents dans un dossier du système de fichiers **HDFS**.

Utilisation
==
`hadoop fs -ls [-d] [-h] [-R] <args>`

L'argument à passer est l'adresse du dossier à lister, ou aucun pour le dossier courant.

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
`hadoop fs -ls -R .`


Résultat
--
    drwxr-xr-x   - HDPTeacher hadoop   0 2017-01-27 10:20 /user/HDPTeacher/hive
    drwxr-xr-x   - HDPTeacher hadoop   0 2017-01-27 10:24 /user/HDPTeacher/hive/jobs
    drwxr-xr-x   - HDPTeacher hadoop   0 2017-01-27 10:21 /user/HDPTeacher/hive/jobs/hive-job-10-2017-01-27_10-21
    -rw-r--r--   3 HDPTeacher hadoop   0 2017-01-27 10:21 /user/HDPTeacher/hive/jobs/hive-job-10-2017-01-27_10-21/logs
    -rw-r--r--   3 HDPTeacher hadoop  31 2017-01-27 10:21 /user/HDPTeacher/hive/jobs/hive-job-10-2017-01-27_10-21/query.hql
