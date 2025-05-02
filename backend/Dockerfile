# Étape 1 : Compilation avec JDK
FROM eclipse-temurin:21-jdk-alpine AS build
WORKDIR /usr/src/app
COPY Main.java .
RUN javac --release 21 Main.java

# Étape 2 : Exécution avec JRE
FROM eclipse-temurin:21-jre-alpine
WORKDIR /app
COPY --from=build /usr/src/app/Main.class .
CMD ["java", "Main"]