# ---------- Stage 1: Build ----------
FROM maven:3.9-eclipse-temurin-17 AS build

WORKDIR /app

# copy pom first (better caching)
COPY pom.xml ./

RUN mvn -B dependency:go-offline

# copy source later
COPY src ./src

RUN mvn -B clean package -DskipTests


# ---------- Stage 2: Runtime ----------
FROM eclipse-temurin:17-jre-alpine

WORKDIR /app

COPY --from=build /app/target/*.jar app.jar

EXPOSE 8080

ENTRYPOINT ["java","-jar","app.jar"]
