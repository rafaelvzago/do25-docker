# Readme

[Link](https://learn.hashicorp.com/tutorials/vagrant/getting-started-index)

```sh
vagrant init hashicorp/bionic64
```

```sh
vagrant up
```

```sh
vagrant destroy
```

```sh
vagrant ssh
```

```sh
uname -a
touch oi
```

```sh
vagrant halt
```

- vagrant box list
- vagrant box remove hashicorp/bionic64
- vagrant box add hashicorp/bionic64
- vagrant reload --provision

[Tutorial de instalação do docker no bionic](https://docs.docker.com/engine/install/ubuntu/)

https://medium.com/@johnathanfercher/mysql-docker-7ff6d50d6cf1

docker build -t alura-database .

docker pull mysql/mysql-server:latest

docker pull mysql:5.7

docker images

docker run hello-world

docker run --name=alura-database -d mysql:5.7

docker logs --tail 100 alura-database

docker run -e MYSQL_ALLOW_EMPTY_PASSWORD=1 -e MYSQL_DATABASE=alura_forum -e MYSQL_USER=alura -e MYSQL_PASSWORD=alura --name alura-database mysql:5.7

docker ps

docker kill <container_id>

docker rm <container_id>

- Faltou a porta, e pra não ter q ficar removendo --rm

config.vm.network :forwarded_port, guest: 3306, host: 3306

vagrant reload --provision

docker run --rm -p 3306:3306 -e MYSQL_ALLOW_EMPTY_PASSWORD=1 -e MYSQL_DATABASE=alura_forum -e MYSQL_USER=alura -e MYSQL_PASSWORD=alura --name alura-database mysql:5.7

criar docker file básico

docker build -t alura-database .

docker run --rm -p 3306:3306 -e MYSQL_ALLOW_EMPTY_PASSWORD=1 -e MYSQL_DATABASE=alura_forum -e MYSQL_USER=alura -e MYSQL_PASSWORD=alura alura-database

- Comando muito grande, vamos simplificar!

- Instalar o docker compose:

```bash
config.vm.provision "shell", inline: "sudo curl --silent -L \"https://github.com/docker/compose/releases/download/1.27.4/docker-compose-$(uname -s)-$(uname -m)\" -o /usr/local/bin/docker-compose"
config.vm.provision "shell", inline: "sudo chmod +x /usr/local/bin/docker-compose"
```

