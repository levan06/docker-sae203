# docker-sae203

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
ca250645@di-docker:~$ docker build -t <choisir-un-nom-pour-l'image> .
```

- Lancer le serveur web :
```shell
ca250645@di-docker:~$ docker run -d -p 8080:80 <nom-de-l'image-choisie>
```

- Vérifier que l'application est en cours d'exécution. Pour ce faire, ouvrez un navigateur et tapez ```localhost:8200```

- Vérifier que le conteneur associé est actif :
```shell
ca250645@di-docker:~$ docker ps
```

- La sortie de ```docker ps``` doit être similaire à :
```shell
CONTAINER ID   IMAGE          COMMAND              CREATED          STATUS          PORTS                                   NAMES
b8f8f406b03c   httpd-juanlu   "httpd-foreground"   30 minutes ago   Up 30 minutes   0.0.0.0:8080->80/tcp, :::8080->80/tcp   quirky_tesla
```

- Finalement, arrêtez le conteneur avec la commande suivante (les dernières chiffres sont le code de hachage affiché par docker ps):
```shell
ca250645@di-docker:~$ docker stop b8f8f406b03c
```

- Encore, si on souhaite supprimer le conteneur, on peut taper :
```shell
ca250645@di-docker:~$ docker rm b8f8f406b03c
```
