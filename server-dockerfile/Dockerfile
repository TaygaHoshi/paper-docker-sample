FROM openjdk:22-slim-bullseye
RUN groupadd -g 2000 serveruser \
&& useradd -m -u 2001 -g serveruser serveruser
WORKDIR /home/serveruser/server
COPY paper-1.19.4-550.jar .
RUN chown -R serveruser:serveruser /home/serveruser/server
USER serveruser
RUN chmod -R 755 /home/serveruser/server
RUN java -jar paper-1.19.4-550.jar
RUN sed -i "s/false/true/g" eula.txt
EXPOSE 25565
ENTRYPOINT ["java", "-jar", "paper-1.19.4-550.jar", "--nogui"]
