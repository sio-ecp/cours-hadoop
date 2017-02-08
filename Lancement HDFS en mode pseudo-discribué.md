******************************************
LANCEMENT HDFS EN MODE PSEUDO-DISTRIBUE
******************************************

*************
Vérification des pré-requis
*************

#Java doit être installé. Vous pouvez voir la version recommendée dans HadoopJavaVersions.

#ssh doit être installé et sshd doit être lancé pour utiliser les scripts Hadoop qui gèrent les démons Hadoop à distance.

*************
Installation HFDS
*************

1/ Télécharger la plateforme hadoop sur le lien suivant exemple de version 2.7.3:
http://apache.crihan.fr/dist/hadoop/common/hadoop-2.7.3/hadoop-2.7.3.tar.gz	

2/ décomprésser le fichier tar.gz téléchargé

*************
Configuration
*************

1/ si vous venez d'installer java, Rajouter la variable d'environnement JAVA_HOME à /etc/environnement:
  # set to the root of your Java installation
  $ nano /etc/environnement
  JAVA_HOME="chemin repertoire java"
  # après enregistrement des modifications, recharger les variables d'environnement avec la commande:
  $ source /etc/environnement
  #pour vérifier que la variable JAVA_HOME a été bien définie:
  $ echo $JAVA_HOME

2/Accéder au dossier décompréssé
  $ cd chemindossier
  
3/ Accéder au fichier etc/hadoop/hadoop-env.sh pour modifier la variable JAVA_HOME
  export JAVA_HOME="chemin repertoire java"
  
4/ modifier le fichier etc/hadoop/core-site.xml comme suit:
#vérifier que le port 9000 n'est pas déjà en écoute sinon choisir un autre port
  <configuration>
    <property>
        <name>fs.defaultFS</name>
        <value>hdfs://localhost:9000</value>
    </property>
  </configuration>
  
5/ modifier le fichier etc/hadoop/hdfs-site.xml comme suit: 
#la réplication par défaut vaut 3 alors qua dans notre cas où nous n'avons qu'un seul noeud, la réplication doit être 1 
  <configuration>
    <property>
        <name>dfs.replication</name>
        <value>1</value>
    </property>
  </configuration>
  
6/ configuration de la passphrase ssh
   $ ssh localhost
   #si vous ne pouvez pas accéder à localhost sans passphrase, executer les commandes suivantes:
   $ ssh-keygen -t rsa -P '' -f ~/.ssh/id_rsa
   $ cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
   $ chmod 0600 ~/.ssh/authorized_keys 
   

*************
Lancement HFDS
*************

1/ formatage du filesystem
   $ bin/hdfs namenode -format
   
2/ lancement des daemons de namenode et datanode
   $ sbin/start-dfs.sh

2-bis/ vous pouvez accéder à l'interface graphique via le navigateur:
   http://localhost:50070/
   
3/ Pour arrêter les daemons
    $ sbin/stop-dfs.sh

