# Essas funções fornecem um conjunto de comandos úteis para gerenciar o ambiente de desenvolvimento usando o Docker Compose.

# network_existe := $(shell docker network ls -f name=host-databases-newsql-network -q)

# make-network:
# 	@if [ "$(network_existe)" = "" ]; then \
# 		echo "Criando a rede name=host-databases-newsql-network..."; \
# 	docker network create name=host-databases-newsql-network; \
# 	else \
# 		echo "A rede name=host-databases-newsql-network já existe."; \
# 	fi

# docker-dev-up: make-network

# CockroachDB
# Inicia os contêineres definidos em modo detached.
docker-cockroachdb-up:
	docker-compose -f docker-compose-cockroachdb.yaml up -d
	
# Constrói e inicia os contêineres definidos em modo detached.	
docker-cockroachdb-build:
	docker-compose -f docker-compose-cockroachdb.yaml up --build -d

# Exibe os logs dos contêineres definidos com um limite de 100 linhas.
docker-cockroachdb-logs:
	docker-compose -f docker-compose-cockroachdb.yaml logs -f --tail=100

# Executa os targets `docker-cockroachdb-build` e `docker-cockroachdb-logs` sequencialmente.
docker-cockroachdb-build-logs: docker-cockroachdb-build docker-cockroachdb-logs

# Para a execução dos contêineres definidos.
docker-cockroachdb-stop:
	docker-compose -f docker-compose-cockroachdb.yaml stop

# Para e remove os contêineres, redes e volumes definidos.
docker-cockroachdb-down:
	docker-compose -f docker-compose-cockroachdb.yaml down
