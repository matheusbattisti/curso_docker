## Baixar docker (documentação)

- Install Docker Engine on Ubuntu

```
[link](https://docs.docker.com/engine/install/ubuntu/){:target="_blank"}

<a href="https://docs.docker.com/engine/install/ubuntu/"> Download </a>

```

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

## Atribuir nome ao container

```
docker run -it 80:80 --name servidor-apache httpd

```

## Executar servidor nginx 

- Executando com parametro -d para exutar em background

```
docker run -it -d -p 8080:80 nginx

```

