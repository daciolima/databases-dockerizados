# Essas funções fornecem um conjunto de comandos úteis para gerenciar o ambiente de desenvolvimento usando o Docker Compose.

# network_existe := $(shell docker network ls -f name=host-databases-nosql-network -q)

# make-network:
# 	@if [ "$(network_existe)" = "" ]; then \
# 		echo "Criando a rede name=host-databases-nosql-network..."; \
# 	docker network create name=host-databases-nosql-network; \
# 	else \
# 		echo "A rede name=host-databases-nosql-network já existe."; \
# 	fi

# docker-dev-up: make-network

# REDIS
# Inicia os contêineres definidos em modo detached.
docker-redis-up:
	docker-compose -f docker-compose-redis.yaml up -d
	
# Constrói e inicia os contêineres definidos em modo detached.	
docker-redis-build:
	docker-compose -f docker-compose-redis.yaml up --build -d

# Exibe os logs dos contêineres definidos com um limite de 100 linhas.
docker-redis-logs:
	docker-compose -f docker-compose-redis.yaml logs -f --tail=100

# Executa os targets `docker-redis-build` e `docker-redis-logs` sequencialmente.
docker-redis-build-logs: docker-redis-build docker-redis-logs

# Para a execução dos contêineres definidos.
docker-redis-stop:
	docker-compose -f docker-compose-redis.yaml stop

# Para e remove os contêineres, redes e volumes definidos.
docker-redis-down:
	docker-compose -f docker-compose-redis.yaml down