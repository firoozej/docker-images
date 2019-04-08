FROM touchvie/tomcat8-jdk8


ENV PG_JDBC_URL https://jdbc.postgresql.org/download/postgresql-42.2.5.jar

ADD "$PG_JDBC_URL" $CATALINA_HOME/lib/
COPY assets/libreplan.xml $CATALINA_HOME/conf/Catalina/localhost/
COPY assets/catalina.policy $CATALINA_HOME/conf/
COPY assets/setenv.sh $CATALINA_HOME/bin/
COPY assets/libreplan.war $CATALINA_HOME/webapps/

RUN mkdir /home/ext
WORKDIR /home
COPY assets/icu4j-63_1.jar ./ext
COPY assets/icu4j-localespi-63_1.jar ./ext
COPY assets/agent-1.0-jar-with-dependencies.jar ./


RUN apt-get update && apt-get install -y \
    cutycapt \
    xvfb

