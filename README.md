Docker TP - Enzo Charlot

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

Question 4 : 

Je crée mon dockerfile : 

# Utilisation de l'image officielle d'Apache
FROM httpd:latest

# Exposer le port 80
EXPOSE 80

# Copier les fichiers de configuration personnalisés dans le conteneur
COPY ./html /usr/local/apache2/htdocs/

# Commande pour démarrer Apache
CMD ["httpd-foreground"]

Ensuite je crée mon image en utilisant la commande : docker build -t image .

Je lance l'image avec : docker run -d -p 8080:80 --name apache image

On peut constater que cela est plus simple que ce soit pour la configuration et l'éxécution.

