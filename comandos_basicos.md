## Baixar docker (documentação)

- Install Docker Engine on Ubuntu

[docker-install](https://docs.docker.com/engine/install/ubuntu/)


## Configura docker para funcionar sem sudo

```
sudo groupadd docker
sudo usermod -aG docker $USER
newgrp docker
sudo systemctl enable docker

```

## Informações e Versões

```
docker --version
docker version
docker info

```

## Listar imagens no nosso host

```
docker images

```

## Procurar imagem (semelhante ao __apt search__)

- busca imagem no docker hub

```
docker search node

```

- baixar imagem do repositório

```
docker pull node

```

## Executar uma imagem, obs (caso não tem essa imagem no host, ele da um pull direto do repositório)

```
docker run -it ubuntu

docker run docker/whalesay cowsay "Hello_World"

docker run hello_world

```

- Parametro -d para executar em segundo plano 

```
docker run -it -d node

```

## Verificar containers em execução

```
docker ps

```

- Lista todos containers usados

```
docker ps -a

```

## Docker status

```
docker stats (id ou apelido do container)

```

- Caso você precise de mais detalhes sobre a sua imagem ou o seu contêiner,

```
docker inspect (id da imagem ou container)

```

## Docker stop

```
docker stop (id ou nome container)

```

## Executar container novamente após exit

```
docker ps

docker start (id do container)

```

- **-i** Modo interativo. Mantém o STDIN aberto mesmo sem console anexado

```
docker start -i (id do container)

```

## Atribuir nome ao container

```
docker run -it 80:80 --name servidor-apache httpd

```

## Executar servidor nginx 

- Executando com a flag **-d** para executar em background

```
docker run -d -p 80:80 --name nginx-docker nginx

```

- Executando com a flag **--rm** para remover o container após ele ser parado

```
docker run -d -p 80:80 --name nginx-docker --rm nginx

```

## Acessando docker logs com parametro -f de follow

```
docker logs -f (id do container)

```

## Remover containers

```
docker container rm <NAMES>

```

## Remover images

```
docker rmi <IMAGE ID>
docker image rm <IMAGE ID>

```
- Forçar remoção de imagem em uso

```
docker image rm --force <IMAGE ID>

```

## Remover containers nao usados(CUIDADO)

```
docker system prune -a

```

## Copiando arquivos de um container para o outro

```
docker cp <CONTAINER ID>:/app/dump.sql /home/user

```

## Verificar informações de processamento

```
docker top <CONTAINER ID>

```

## Inspecionar um container
- usar o nome ou id

```
docker inspect <CONTAINER ID>

```

## Verificar processamento de memoria e cpu dos containers

```
docker stats

```

## Enviar imagens para docker hub

```
docker login
docker push
docker logout

```