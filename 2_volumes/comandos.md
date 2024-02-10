## Comandos executados

``` docker

docker build -t pgpmessages .

docker run -d -p 80:80 --name phpmessages_container -v /data --rm phpmessages

docker run -d -p 80:80 --name phpmessages_container -v phpvolume:/var/www/html/messages --rm phpmessages
docker run -d -p 81:80 --name phpmessages_container2 -v phpvolume:/var/www/html/messages --rm phpmessages

docker inspect <container id> 'para ver as informações'

docker run -d -p 80:80 --name phpmessages_container2 -v $HOME/Cursos/curso_docker/2_volumes/messages:/var/www/html/messages --rm phpmessages

docker run -d -p 80:80 --name phpmessages_container -v phpvolume:/var/www/html/messages --rm phpmessages
localizado lá em /var/lib/docker/volumes/phpvolume/_data


```