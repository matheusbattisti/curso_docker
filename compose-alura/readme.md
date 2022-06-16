Inicialmente, crie uma pasta chamada ymls em sua área de trabalho. Dentro dessa pasta, você deverá criar um arquivo chamado **docker-compose.yml**, que será responsável por conter todas as definições de como os nossos **containers** serão executados.

Com seu editor de texto favorito, edite o arquivo **docker-compose.yml** e defina a estrutura base para começarmos:

```
version: "3.9"
services:COPIAR CÓDIGO
```

Agora, dentro de services, iremos definir primeiramente o comportamento de nosso container responsável pelo banco de dados:

```
version: "3.9"
services:
  mongodb:
    image: mongo:4.4.6
    container_name: meu-mongo
    networks:
      - compose-bridge
```

Para definirmos o container responsável pela nossa aplicação que consumirá do banco, seguiremos a mesma ideia, porém, adicionaremos as instruções responsáveis pelo mapeamento de portas:

```
version: "3.9"
services:
  mongodb:
    image: mongo:4.4.6
    container_name: meu-mongo
    networks:
      - compose-bridge

  alurabooks:
    image: aluradocker/alura-books:1.0
    container_name: alurabooks
    networks:
      - compose-bridge
    ports:
      - 3000:3000
```

Por fim, também será necessário definir a rede dos containers. No caso, estamos utilizando a rede compose-bridge. Alinhado ao conteúdo da linha de services, adicione o seguinte conteúdo:

```
version: "3.9"
services:
  mongodb:
    image: mongo:4.4.6
    container_name: meu-mongo
    networks:
      - compose-bridge

  alurabooks:
    image: aluradocker/alura-books:1.0
    container_name: alurabooks
    networks:
      - compose-bridge
    ports:
      - 3000:3000

networks:
  compose-bridge:
    driver: bridge

```
Através do terminal, acesse o diretório que contém o seu arquivo **docker-compose.yml** e execute o comando **docker-compose up -d**. No navegador, acesse a url **localhost:3001/seed** e em seguida **localhost:3001** e veja que tudo continua funcionando como anteriormente.
