# Persistir dados em um container, Utilizando bind mounts e volumes

## Utilizando Volume gerenciado pelo docker

- Primeiramente criamos um volume com

``` docker
docker volume create meu-volume

```

- executar container com o volume criado antes

``` docker
docker run -it -v meu-volume:/app --name whaler --rm debian /bin/bash

```

- Executar container já criando o volume

``` docker

docker run -it --mount source=outro-volume,target=/app --name whaler --rm debian /bin/bash

```

- OS VOLUMES FICAM EM _**/var/lib/docker/volumes/**_

---

## Criar volume temporario com _**--tmpfs**_

``` docker

docker run -it --tmpfs=/app --name whaler --rm debian /bin/bash

```


## Primeiramente crie um diretorio e um arquivo dentro

``` docker

mkdir docker-volume && touch $HOME/bind-mount.txt

```

## Rodar um novo container

``` docker

docker run -it -v $HOME/docker-volume:/app --rm debian /bin/bash

```

## Maneira mais recomendada para criar Volumes do que a anterior

``` docker
docker run -it -v /home/jesher/docker-volume:/app --name docker-mtLoko --rm debian /bin/bash

```
- obs: flag _**--rm**_ para remover imagem após stop do container