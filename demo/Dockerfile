FROM maven:3.5-jdk-8 as builder
WORKDIR /usr/src


#COPY . .
COPY ./ /usr/src



RUN mvn clean  install -DskipTests
RUN ls /usr/src/target
FROM openjdk:8-jre-alpine
#RUN ln -sf /bin/bash /bin/sh



#RUN ls -a /usr/src/
COPY --from=builder /usr/src/target/currency-exchange-service-0.0.1-SNAPSHOT.jar currency-exchange-service-0.0.1-SNAPSHOT.jar.jar
CMD ["/usr/bin/java", "-jar", "/demo.jar"]