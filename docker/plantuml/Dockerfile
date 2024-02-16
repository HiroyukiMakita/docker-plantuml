ARG PLANTUML_IMAGE

FROM ${PLANTUML_IMAGE}

USER root

RUN apt-get update && \
    apt-get install -y sudo python

USER jetty

CMD ["java" "-jar" "/usr/local/jetty/start.jar"]
ENTRYPOINT ["/entrypoint.sh"]