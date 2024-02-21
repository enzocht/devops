Docker TP - Enzo Charlot

Question 3 : 

J'installe httpd

Je close le port 8080 sur ma machine et ensuite je rentre la commande suivante : 
docker run -v /home/enzo/docker/html:/usr/local/apache2/htdocs/ -p 8080:80 -d hhtpd

Cela démarre le service dans le docker, si je lance un curl localhost:8080 on peut bien voir notre Hello World


