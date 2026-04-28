# Projet SAE 2.03 Equipe V3

## Titre du projet

- Site GitLab avec docker et HTML/CSS

## Membres de l'équipe
_(**Format :** Demi-groupe - NOM Prénom)_

- C1 - ACHAFIK Abdellah
- C1 - BASLEY Max-Malo
- C1 - COFFARD Alexis
- C2 - SALMON William

## Liens vers le site web du projet


[Site web GitLab](https://levan06.github.io/docker-sae203/html/)

## Liens vers le dépôt github du projet

[Dépôt sur GitHub](https://github.com/levan06)


## Instructions pour lancer l'application

- Vérifiez si docker est installé :
```shell
ca250645@di-docker:~$ docker --version
Docker version 29.4.1, build 055a478
```

- Cloner le référentiel :
 ```shell
ca250645@di-docker:~$ git clone git@github.com:levan06/docker-sae203.git
Clonage dans 'docker-sae203'...
remote: Enumerating objects: 27, done.
remote: Counting objects: 100% (27/27), done.
remote: Compressing objects: 100% (19/19), done.
remote: Total 27 (delta 0), reused 27 (delta 0), pack-reused 0 (from 0)
Réception d'objets: 100% (27/27), 8.21 Kio | 2.74 Mio/s, fait.
```

- Aller au référentiel :
```shell
ca250645@di-docker:~$ cd exempleDockerfile
```

- Construisez l'image décrite dans dockerfile avec docker build : 
```shell
ca250645@di-docker:~$ docker build -t equipev3-img .
```

- Lancer le serveur web :
```shell
ca250645@di-docker:~$ docker run -d -p 8200:80 equipev3-img
```

- Vérifier que l'application est en cours d'exécution. Pour ce faire, ouvrez un navigateur et tapez ```di-docker:8200```

- Vérifier que le conteneur associé est actif :
```shell
ca250645@di-docker:~$ docker ps
```

- La sortie de ```docker ps``` doit être similaire à :
```shell
CONTAINER ID   IMAGE          COMMAND                  CREATED          STATUS          PORTS                  NAMES
0e5224a399fe   equipev3-img   "/usr/sbin/apache2ct…"   3 seconds ago    Up 2 seconds    0.0.0.0:8200->80/tcp   wizardly_lamport

```

- Finalement, arrêtez le conteneur avec la commande suivante (les dernières chiffres sont le code de hachage affiché par docker ps):
```shell
ca250645@di-docker:~$ docker stop 0e5224a399fe
```

- Encore, si on souhaite supprimer le conteneur, on peut taper :
```shell
ca250645@di-docker:~$ docker rm 0e5224a399fe
```
