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
