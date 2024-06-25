# Instalation 

## Table des matières
<details>
  <summary>⬇️⬇️⬇️</summary>
  <ul>
    <li><a href="#suits---main-repository">Suits - Dépôt principal</a></li>
		<li><a href="#schéma-de-lapplication">Schéma de l'application</a></li>
		<li><a href="#variables-denvrionnement-générales
">Variables d'envrionnement générales
</a></li>
		<li>
			<a href="#clone-the-repository">Dupliquer le dépôt</a>
			<ul>
				<li><a href="#ssh">SSH</a></li>
				<li><a href="#http">HTTP</a></li>
			</ul>
		</li>
		<li>
      <a href="#rachel---database">Rachel - Suits Interface</a>
      <ul>
        <li><a href="#clone-rachel">Dupliquer le dépôt Rachel</a></li>
				<ul>
        	<li><a href="#ssh-rachel">SSH</a></li>
					<li><a href="#http-rachel">HTTP</a></li>
				</ul>
				<li><a href="#env-rachel">Variables d'environnement</a></li>
				<li><a href="#instalation-rachel">Instalation</a></li>
				<li><a href="#development-rachel">Développement</a></li>
				<li><a href="#build-rachel">Test</a></li>
				<li><a href="#test-rachel">Construction</a></li>
				<li><a href="#docker-rachel">Docker</a></li>
			</ul>
    </li>
		<li>
      <a href="#mike---database">Mike - Suits API</a>
      <ul>
        <li><a href="#clone-mike">Dupliquer le dépôt Mike</a></li>
				<ul>
        	<li><a href="#ssh-mike">SSH</a></li>
					<li><a href="#http-mike">HTTP</a></li>
				</ul>
				<li><a href="#env-mike">Variables d'environnement</a></li>
				<li><a href="#instalation-mike">Instalation</a></li>
				<li><a href="#development-mike">Développement</a></li>
				<li><a href="#build-mike">Test</a></li>
				<li><a href="#test-mike">Construction</a></li>
				<li><a href="#docker-mike">Docker</a></li>
			</ul>
    </li>
		<li>
      <a href="#harvey---database">Harvey - Suits Service Externe</a>
      <ul>
        <li><a href="#clone-harvey">Dupliquer le dépôt Harvey</a></li>
				<ul>
        	<li><a href="#ssh-harvey">SSH</a></li>
					<li><a href="#http-harvey">HTTP</a></li>
				</ul>
				<li><a href="#env-harvey">Variables d'environnement</a></li>
				<li><a href="#docker-harvey">Docker</a></li>
			</ul>
    </li>
		<li>
      <a href="#donna---database">Donna - Suits Base de données</a>
      <ul>
        <li><a href="#clone-donna">Dupliquer le dépôt</a></li>
				<ul>
        	<li><a href="#ssh-donna">SSH</a></li>
					<li><a href="#http-donna">HTTP</a></li>
				</ul>
				<li><a href="#env-donna">Variables d'environnement</a></li>
				<li><a href="#docker-donna">Docker</a></li>
			</ul>
    </li>
  </ul> 
</details>

# Suits - Main repository

## Clone the repository

### SSH

```bash
git clone git@github.com:j-renevier/suits.git
```
### HTTP

```bash
git clone https://github.com/j-renevier/suits.git
```

# Variables d'envrionnement générales

```bash 
# Value: development | test | build | production
ENV = development
DOMAINE_NAME = ChangeMe
EXTENSION = .ChangeMe
HOST = ChangeMe
```

# Rachel - Suits Interface

<h2 id="clone-rachel">Dupliquer le dépôt</h2>

<h2 id="ssh-rachel">SSH</h2>

```bash
git clone 
```

<h2 id="http-rachel">HTTP</h2>

```bash
git clone 
```

<h2 id="env-rachel">Variables d'environnement</h2>

```bash 
# .env
# .env
NODE_ENV = development
DOMAINE_NAME = ChangeMe
EXTENSION = .ChangeMe
HOST = localhost

INTERFACE_CONTAINER_NAME = interface
INTERFACE_HOST = localhost
INTERFACE_PORT = 82
INTERFACE_PORT_SSL = 445

API_CONTAINER_NAME = api
API_HOST = localhost
API_PORT = 81
API_PORT_SSL = 444
```

<h2 id="installation-rachel">Installation</h2>

```bash
npm install
```

<h2 id="development-rachel">Développement</h2>

```bash
# development
npm run start

# watch mode
npm run start:dev

# debug mode
npm run start:debug

# production mode
npm run start:prod
```

<h2 id="test-rachel">Test</h2>

```bash
# unit tests
npm run test

# unit tests, watch mode
npm run test:watch

# unit tests, debug mode
npm run test:debug

# e2e tests
npm run test:e2e

# test coverage
npm run test:cov
```

<h2 id="build-rachel">Construction</h2>

```bash
# build
npm run build
```

<h2 id="lint-rachel">Lint</h2>

```bash
# lint
npm run lint
```

<h2 id="docker-rachel">Docker</h2>

Démarrer le conteneur

``` bash 
# Rachel - Suits Interface

docker compose up --build
```

Exécuter des commandes dans le conteneur

``` bash 
# Rachel - Suits Interface

docker exec -it interface sh
```

# Mike - Suits API

<h2 id="clone-mike">Dupliquer le dépôt</h2>

<h2 id="ssh-mike">SSH</h2>

```bash
git clone 
```

<h2 id="http-mike">HTTP</h2>

```bash
git clone 
```

<h2 id="env-mike">Variables d'environnement</h2>

```bash 
# .env
NODE_ENV = development
DOMAINE_NAME = ChangeMe
EXTENSION = .ChangeMe
HOST = localhost

API_CONTAINER_NAME = api
API_HOST = localhost
API_PORT = 81
API_PORT_SSL = 444

# ADD DB ENV VAR
```

<h2 id="installation-mike">Installation</h2>

```bash
npm install
```

<h2 id="development-mike">Développement</h2>

```bash
# development
npm run start

# watch mode
npm run start:dev

# debug mode
npm run start:debug

# production mode
npm run start:prod
```

<h2 id="test-mike">Test</h2>

```bash
# unit tests
npm run test

# unit tests, watch mode
npm run test:watch

# unit tests, debug mode
npm run test:debug

# e2e tests
npm run test:e2e

# test coverage
npm run test:cov
```

<h2 id="build-mike">Construction</h2>

```bash
# build
npm run build
```

<h2 id="lint-mike">Lint</h2>

```bash
# lint
npm run lint
```

<h2 id="docker-mike">Docker</h2>

Démarrer le conteneur

``` bash 
# Mike - Suits API

docker compose up --build
```

Exécuter des commandes dans le conteneur

``` bash 
# Mike - Suits API

docker exec -it api sh
```


# Harvey - Suits Service Externe

<h2 id="clone-harvey">Dupliquer le dépôt</h2>

<h3 id="ssh-harvey">SSH</h3>

```bash
git clone 
```

<h3 id="http-harvey">HTTP</h3>

```bash
git clone 
```

<h2 id="env-harvey">Variables d'environnement</h2>

```bash 
# .env
ENV = development
DOMAINE_NAME = ChangeMe
EXTENSION = .ChangeMe
HOST = localhost
```

<h2 id="docker-harvey">Docker</h2>

Démarer le conteneur

``` bash 
# Harvey - Suits Service Externe

docker compose up --build
```

# Donna - Suits Base de données

<h2 id="clone-donna">Dupliquer le dépôt</h2>

<h3 id="ssh-donna">SSH</h3>

```bash
git clone 
```

<h3 id="http-donna">HTTP</h3>

```bash
git clone 
```

<h2 id="env-donna">Variables d'environnement</h2>

```bash 
# .env
ENV = development
DOMAINE_NAME = ChangeMe
EXTENSION = .ChangeMe
HOST = localhost


# CHANGE ENV VAR 
DB_CONTAINER_NAME = mariadb
MYSQL_ROOT_PASSWORD = ChangeMe
MYSQL_USER = j.renevier
MYSQL_PASSWORD = ChangeMe
MYSQL_PORT = 3307

PHPMYADMIN_PORT = 83
```

<h2 id="docker-donna">Docker</h2>

Start the container

``` bash 
# Donna - Suits Base de données

docker compose up --build
```



# Désinstalation 

reset:
	@docker-compose down -v --rmi all
	@docker-compose rm -f
	@echo "Reset complete."