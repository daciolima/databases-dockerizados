# Essas funções fornecem um conjunto de comandos úteis para gerenciar o ambiente de desenvolvimento usando o Docker Compose.

# network_existe := $(shell docker network ls -f name=host-databases-sql-network -q)

# make-network:
# 	@if [ "$(network_existe)" = "" ]; then \
# 		echo "Criando a rede name=host-databases-sql-network..."; \
# 	docker network create name=host-databases-sql-network; \
# 	else \
# 		echo "A rede name=host-databases-sql-network já existe."; \
# 	fi

# docker-dev-up: make-network

# Postgres
# Inicia os contêineres definidos em modo detached.
docker-postgres-up:
	docker-compose -f docker-compose-postgres.yaml up -d
	
# Constrói e inicia os contêineres definidos em modo detached.	
docker-postgres-build:
	docker-compose -f docker-compose-postgres.yaml up --build -d

# Exibe os logs dos contêineres definidos com um limite de 100 linhas.
docker-postgres-logs:
	docker-compose -f docker-compose-postgres.yaml logs -f --tail=100

# Executa os targets `docker-postgres-build` e `docker-postgres-logs` sequencialmente.
docker-postgres-build-logs: docker-postgres-build docker-postgres-logs

# Para a execução dos contêineres definidos.
docker-postgres-stop:
	docker-compose -f docker-compose-postgres.yaml stop

# Para e remove os contêineres, redes e volumes definidos.
docker-postgres-down:
	docker-compose -f docker-compose-postgres.yaml down