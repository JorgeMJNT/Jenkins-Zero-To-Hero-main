# Usa uma versão leve do Java 17
FROM eclipse-temurin:17-jre-slim

# Define um argumento para o nome do JAR
ARG artifact=target/spring-boot-web.jar

# Define o diretório de trabalho
WORKDIR /opt/app

# Copia o JAR para dentro do contêiner
COPY ${artifact} app.jar

# Garante que o JAR tem permissões de execução
RUN chmod +x app.jar

# Define o comando de entrada
ENTRYPOINT ["java", "-jar", "app.jar"]