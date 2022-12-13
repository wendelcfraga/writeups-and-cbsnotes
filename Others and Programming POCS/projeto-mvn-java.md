## Compilar projeto maven

> mvn clean install

## Subir aplicação com Docker

> docker-compose up --build --force-recreate

## Site para pegar imagens Docker

[**HUB DOCKER**](hub.docker.com)

## Criar Docker File(escrever instruções ex)

```python
FROM openjdk
WORKDIR /app
COPY target/arquivo-app-1.0.0.jar /app/arquivo-app.jar
ENTRYPOINT ["java", "-jar", "arquivo-app.jar"]
```
## Gerar imagem

``` docker build -t <nomeapp>:<versão> ```
  
## Executar e redirecionar de uma porta pra outra

> docker run -p 8001:8080 arquivo-app

## Re-buildar app depois de alterações

> ./mvn clean package -DskipTests

## Fazer imagem docker direto no maven

> mvn spring-boot:build-image

## Listar dockers instalados

> docker -a

[**INSTALAR NVM **](https://gist.github.com/d2s/372b5943bce17b964a79)


