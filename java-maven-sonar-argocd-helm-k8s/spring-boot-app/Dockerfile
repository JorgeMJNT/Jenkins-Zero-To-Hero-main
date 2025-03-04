# Usa uma versão leve do Java 17
FROM eclipse-temurin:17-jre-slim

# Define variáveis de ambiente para facilitar a manutenção
ENV APP_HOME=/opt/app
ENV JAR_NAME=spring-boot-web.jar

# Define um usuário não-root para melhorar a segurança
RUN addgroup --system appgroup && adduser --system --group appuser

# Define o diretório de trabalho
WORKDIR $APP_HOME

# Copia o JAR para dentro do contêiner
COPY target/$JAR_NAME app.jar

# Garante que o JAR tem permissões de execução
RUN chmod +x app.jar && chown -R appuser:appgroup $APP_HOME

# Muda para o usuário não-root
USER appuser

# Expor a porta padrão do Spring Boot (8080)
EXPOSE 8080

# Define o comando de entrada
ENTRYPOINT ["java", "-jar", "app.jar"]
