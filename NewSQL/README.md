### Serviços Databases NewSQL Dockerizados

Comandos disponíveis no Makefile das respectivas pastas dos databases facilitando o load no ambiente de desenvolvimento.

*OBS:* Para subir os containers do database CockroachDB é necessário criar rede com o comando abaixo:
```shell
# Cria rede docker para atender os cluster do CockroachDB
docker network create -d bridge network_cockroachdb

# Caso haja conflito de porta pode-se verificar com o comando abaixo:
lsof -i -sTCP:LISTEN | grep 26257

# Iniciar um cluster
docker exec -it node_1 ./cockroach init --insecure

# Interagir via console no nó específico
docker exec -it node_1 /bin/bash

# Após entrar no container uso o comando abaixo para entrar no shell interativo SQL do CockroachDB
./cockroach sql --insecure

# Ex de comando SQL
CREATE DATABASE <NomeDatabase>
```
