## Listar networks

```
docker network ls

```

## Usar a rede modo none

```

docker run -d --network none ubuntu sleep 1d

```

- **Ver descrições de rede do container**

```
docker ps
docker inspect <CONTAINER ID>

```

> ### **O modo __none__ significa que o container vai ser completamente isolado, ele não terá nenhum tpo de interface de rede vinculada à ele**