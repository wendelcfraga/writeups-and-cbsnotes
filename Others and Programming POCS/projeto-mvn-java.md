## Compilar projeto maven

> mvn clean install

## Gerar projeto maven linha de comando

> mvn archetype:generate -DarchetypeArtifactId=maven-archetype-quickstart

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

[**INSTALAR NVM**](https://gist.github.com/d2s/372b5943bce17b964a79)


## Propriedades e dependências para compilar projeto solo (sem spring) maven

```xml
<properties>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    <maven.compiler.source>1.7</maven.compiler.source>
    <maven.compiler.target>1.7</maven.compiler.target>
 </properties>
  
 <build>
    <pluginManagement><!-- lock down plugins versions to avoid using Maven defaults (may be moved to parent pom) -->
      <plugins>
        <!-- clean lifecycle, see https://maven.apache.org/ref/current/maven-core/lifecycles.html#clean_Lifecycle -->
        <plugin>
          <artifactId>maven-clean-plugin</artifactId>
          <version>3.1.0</version>
        </plugin>
        <!-- default lifecycle, jar packaging: see https://maven.apache.org/ref/current/maven-core/default-bindings.html#Plugin_bindings_for_jar_packaging -->
        <plugin>
          <artifactId>maven-resources-plugin</artifactId>
          <version>3.0.2</version>
        </plugin>
        <plugin>
          <artifactId>maven-compiler-plugin</artifactId>
          <version>3.8.0</version>
        </plugin>
        <plugin>
          <artifactId>maven-surefire-plugin</artifactId>
          <version>2.22.1</version>
        </plugin>
        <plugin>
          <artifactId>maven-jar-plugin</artifactId>
          <version>3.0.2</version>
        </plugin>
        <plugin>
          <artifactId>maven-install-plugin</artifactId>
          <version>2.5.2</version>
        </plugin>
        <plugin>
          <artifactId>maven-deploy-plugin</artifactId>
          <version>2.8.2</version>
        </plugin>
        <!-- site lifecycle, see https://maven.apache.org/ref/current/maven-core/lifecycles.html#site_Lifecycle -->
        <plugin>
          <artifactId>maven-site-plugin</artifactId>
          <version>3.7.1</version>
        </plugin>
        <plugin>
          <artifactId>maven-project-info-reports-plugin</artifactId>
          <version>3.0.0</version>
        </plugin>
        <plugin>
          <groupId>org.apache.maven.plugins</groupId>
          <artifactId>maven-jar-plugin</artifactId>
          <version>3.0.2</version>
          <configuration>
            <archive>
              <manifest>
                <mainClass>com.wendel.App</mainClass>
              </manifest>
            </archive>
          </configuration>
        </plugin>
      </plugins>
    </pluginManagement>
  </build> 
```

