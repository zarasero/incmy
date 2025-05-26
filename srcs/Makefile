# Пути
COMPOSE_FILE = ./requirements/docker-compose.yml



# Цвета (для ошибок)
RED   = \e[1;91m
RESET = \033[0m

# --- Цели ---


all: run

run:
	mkdir -p ${HOME}/data/mariadb
	mkdir -p ${HOME}/data/wordpress
	docker-compose -f $(COMPOSE_FILE) up --build -d

# Запуск docker-compose + создание директорий данных
up:
	mkdir -p ${HOME}/data/mariadb
	mkdir -p ${HOME}/data/wordpress
	docker-compose -f $(COMPOSE_FILE) up --build -d

# Остановка и удаление контейнеров + томов + директорий
clean:
	docker-compose -f $(COMPOSE_FILE) down
	sudo rm -rf ${HOME}/data/mariadb
	sudo rm -rf ${HOME}/data/wordpress

# Перезапуск: пересборка + запуск
re: clean all

.PHONY: run up clean re
