# Curso de Node: AluizioDev - Udemy

### Docker

- Iniciar, parar e reiniciar o docker
  - `sudo systemctl start docker.service`
  - `sudo systemctl stop docker.service`
  - `sudo systemctl restart docker.service`

<br>

- Criar um novo container postgres no docker
  - `docker run --name postgres -e POSTGRES_PASSWORD=docker -p 5432:5432 -d postgres`
- --name: Nome escolhido para o container
- -e: Variável de ambiente
- -p: Porta (Porta do computador:Porta no docker)
- -d: Não entrar no modo interativo quando o container estiver rodando
- postgres: Nome da imagem

<br>

- Criar um container redis no docker
  - `docker run --name redis -p 6379:6379 -d -t redis:alpine`

<br>

- Criar um container do redis-client no docker
  - `docker run --name redis-client -v redisinsight:/db -p 8001:8001 -d -t redislabs/redisinsight:latest`
- Endereço para acessar: localhost:8001
- Lá dentro se conecta com o banco redis: Para isso é necessário o ip da máquina.

### Postgres

- Utilizamos DBeaver para criar e gerenciar este banco de dados
- Para que ele funcione com uuid_generate_v4() é necessário adicionar a extensão uuid-ossp
  - Pelo DBeaver dá pra fazer isso

### Build

- Gerar build pelo babel
  - `https://github.com/aluiziodeveloper/api-vendas-deploy/blob/main/babel.md`

<br>

- Comando para gerar build
  - `build": "babel src --extensions \".js,.ts\" --out-dir dist --copy-files`

<br>

- Testar a aplicação após o build
  - `yarn start`
- Será necessário trocar src por dist e _.ts por _.js provisóriamente para executar este comando
- Troca deve ser feita em ormconfig.json
