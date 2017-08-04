FROM maven:3.5-jdk-8

EXPOSE 8080 8081 8082 8443 8444 8445 8983

ENV JAVA_OPTS=""

RUN apt-get install -y git lsof && \
    mkdir -p /opt/broadleaf && \
    cd /opt/broadleaf && \
    git clone https://github.com/BroadleafCommerce/CommunityStarter.git && \
    cd CommunityStarter && \
    mvn install && \
    rm -rf "$HOME/.m2"

WORKDIR /opt/broadleaf/CommunityStarter
ENTRYPOINT [ "sh", "-c", "java $JAVA_OPTS -Djava.security.egd=file:/dev/./urandom -jar target/ROOT.jar" ]