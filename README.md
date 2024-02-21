# Docker TP - Enzo Charlot

Question 3 : 

J'installe httpd

Je close le port 8080 sur ma machine et ensuite je rentre la commande suivante : 
docker run -v /home/enzo/docker/html:/usr/local/apache2/htdocs/ -p 8080:80 -d hhtpd

Cela démarre le service dans le docker, si je lance un curl localhost:8080 on peut bien voir notre Hello World

Après j'ai pu stopper et supprimer le docker avec : 
docker stop ID
docker rm ID

docker run -p 8080:80 -d httpd
docker cp /home/enzo/docker/html stupefied_carson:/usr/local/apache2/htdocs/

Cela à fonctionné, la question 3 est terminé.

----------------------------------------------------------------------------

Question 4 : 

Je crée mon dockerfile : 

FROM httpd:latest
EXPOSE 80
COPY ./html /usr/local/apache2/htdocs/
CMD ["httpd-foreground"]

Ensuite je crée mon image en utilisant la commande : docker build -t image 

Je lance l'image avec : docker run -d -p 8080:80 --name apache image

On peut constater que cela est plus simple que ce soit pour la configuration et l'éxécution.

----------------------------------------------------------------------------

Question 5 : 

Je récupère les paquet avec : docker pull

C'est OK.

----------------------------------------------------------------------------

Question 6 : 

docker run est utile pour lancer rapidement un conteneur unique à partir d'une image. Il est plus adapté pour les cas d'utilisation simples et ponctuels
docker-compose est idéal pour les applications composées de plusieurs conteneurs interconnectés. Il permet de définir les configurations une fois et de les réutiliser facilement, ce qui facilite la gestion des applications complexes

En résumé, si vous avez besoin de lancer une seule instance d'un conteneur, docker run est l'outil à utiliser. Si vous avez une application composée de plusieurs conteneurs, docker-compose est le choix approprié


