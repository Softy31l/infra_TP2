# infra_TP2
TP 2
Docker
Mise en pratique - Docker Application Express JS
1. Récupérer le zip TP-2-Docker.zip sur Moodle.
Initialiser un nouveau repository git qui vous permettra de sauvegarder les fichiers
créés pendant le TP.

infra_TP2

Vous enverrez un zip du repository à la fin du TP avec vos
réponses aux questions / exécutions et résultats sur la console dans un fichier
Markdown
Utilisez git progressivement ! (Ne pas faire qu’un seul commit à la fin)
3. Compléter le Dockerfile afin de builder correctement l’application contenu dans src/
FROM node:12-alpine3.9

COPY . .

# installe les éléments de production
RUN npm install --production

# appel appli
CMD ["node", "src/index.js"]

a. Une option de npm vous permet de n’installer que ce qui est nécessaire.
Quelle est cette option ?
Il faut installer le module npm sur la machine et par la suite utiliser "npm --production" 

Quelle bonne pratique Docker permet t-elle de
respecter ?
Cela permet de ne faire appel qu'aux élément nécessaire au bon focntionnement de l'appli au sein du container

4. A l’aide de la commande docker build, créer l’image ma_super_app
ubase@ynov:~/docker/infra_TP2/TP-2-Docker2/tp-docker-2$ docker build -f Dockerfile -t ma_super_app .
[+] Building 4.2s (1/2)                                                   docker:default
 => [internal] load build definition from Dockerfile                                0.1s
 => => transferring dockerfile: 186B                                                0.0s
 => [internal] load metadata for docker.io/library/node:12-alpine3.9                4.1s

6. Compléter le fichier docker-compose.yml afin d’éxécuter ma_super_app avec sa
base de données.
/!\ Utiliser correctement les variables d’environnement afin de configurer la
base de données et l’application /!\
