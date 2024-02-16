#########################################################
# imports
#########################################################

include .env
PLANTUML_PORT := ${PLANTUML_PORT}

#########################################################
# variables
#########################################################

COMPOSE := docker-compose
BUILD := $(COMPOSE) build --no-cache
UP := $(COMPOSE) up -d
DOWN := $(COMPOSE) down
SHELL = bash
EXEC = $(COMPOSE) exec $(CONTAINER) $(SHELL) $(ARG)
CONTAINER =
ARG =

# docker services (container name)
PLANTUML := plantuml

#########################################################
# if include source not exists commands
#########################################################

.env:
	@cp -n .env.example .env

#########################################################
# make commands
#########################################################

init:
	@make build up

build:
	@$(BUILD)

up:
	@$(UP) && echo "running PlantUML server on: http://localhost:$(PLANTUML_PORT)"

exec-uml:
	$(eval CONTAINER := $(PLANTUML))
	$(eval SHELL = sh)
	@$(EXEC)

down:
	@$(DOWN)

remove:
	@$(DOWN) --rmi all --volumes --remove-orphans