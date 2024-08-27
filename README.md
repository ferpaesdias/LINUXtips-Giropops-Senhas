# LINUXtips-Giropops-Senhas
<br> 

## Dockerfile

No diretório Dockerfile tem um arquivo *dockerfile* que cria a imagem com o app **Giropops-Senhas**.

---

<br> 

### Criação de uma rede em comum entre os containers 

A rede foi criada para o acesso entre os containers via **Hostname**.
```shell
docker network create --driver bridge desafio_02
```
<br>

### Execução do container Redis

Executa o container Redis com o **Nome** e **Hostname** igual a *redis-desafio02*. 
```shell
docker container run -d --net desafio_02 --name redis-desafio02 --hostname redis-desafio02 redis:7.4-alpine3.20
```

<br>

### Execução do container do APP Giropops-Senhas

Executa o container do APP Giropops-Senhas e o acesso ao APP é pelo navegador na porta 5000.
```shell
docker container run -d --net desafio_02 --name giropops-senhas -p 5000:5000 ferpdias/linuxtips-giropops-senhas:1.0
```

<br>

--- 

**Obs**.: Este é um desafio do curso **Descomplicando o Docker** da [LinuxTips](https://www.linuxtips.io/course/descomplicando-docker).
