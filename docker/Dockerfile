ARG openjdk_version=16-buster
FROM openjdk:${openjdk_version}

#-------------------
# graphviz, curl
RUN apt-get update && apt-get install -y graphviz curl

#-------------------
# plantuml
ARG plantuml_version=1.2020.26
ARG plantuml_url=https://sourceforge.net/projects/plantuml/files/plantuml.${plantuml_version}.jar

RUN mkdir -p /plantuml \
  && cd /plantuml \
  && curl -L ${plantuml_url} -o plantuml.jar \
  && printf '#!/bin/sh\njava -jar /plantuml/plantuml.jar $*' > /usr/local/bin/plantuml \
  && chmod +x /usr/local/bin/plantuml

#-------------------
# font for jp
ARG font_url=https://ja.osdn.net/downloads/users/8/8637/genshingothic-20150607.zip/

RUN mkdir ~/.fonts \
  && cd /tmp \
  && curl -L ${font_url} -o font.zip \
  && unzip /tmp/font.zip -d ~/.fonts


