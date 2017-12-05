## 'Dockerisation' des différents services

Pour dockeriser nos différents services Spring Boot, on passe par les étapes suivantes :

## Ajout du Dockerfile

On commence par l'ajout d'un Dockerfile dans le répertoire principal du projet qui contient les caractéristiques de l'image à créer.

![1ère capture](/Capture3.PNG?raw=true "Ajout du Dockerfile")

## Ajout du plugin offert par Spotify

On ajoute un plugin Maven offert par Spotify au fichier pom.xml, en spécifiant le répertoire, le nom de l'image Docker à créer, et le nom du jar. Ce plugin permet de faire un build de l'image Docker.

![2ème capture](/Capture2.PNG?raw=true "Ajout du plugin")

## Ajout du plugin group com.spotify

Ensuite, on crée un fichier settings.xml sous le répertoire .m2. On ajoute à ce fichier le plugin group "com.spotify"

![3ème capture](/Capture.PNG?raw=true "Ajout du plugin group")

## Lancer la commande pour construire l'image

On utilise le terminal d'IntelliJ puor exécuter la commande "mvnw package dockerfile:build" qui permet de construire l'image Docker.

![4ème capture](/Capture4.PNG?raw=true "Build terminé")

![5ème capture](/Capture5.PNG?raw=true "Vérification que l'image est créée")

## Exécuter l'image

On exécute l'image à partir de l'invite de commande avec la commande "docker run -p 9999:9999 -t tp4/proxy-service" (le port et le nom de l'image varient selon le service à lancer).

![6ème capture](/Capture6.PNG?raw=true "Lancer l'image")

![7ème capture](/Capture7.PNG?raw=true "Service lancé")