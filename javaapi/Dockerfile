FROM openjdk:8 AS  JAVA_BUILD
WORKDIR /usr/src/app/
RUN apt update && apt install maven -y
RUN mavan install -DskipTests

FROM openjdk:8
WORKDIR /user/src/app/
COPY --from=BUILD_IMAGE /usr/src/app/target/book-work-0.0.1-SNAPSHOT.jar ./book-work-0.0.1.jar

EXPOSE 9000

ENTRYPOINT ["java", "-jar", "book-work-0.0.1.jar"]