FROM docker.io/jenkins/jenkins:2.263.1-lts 

ENV JENKINS_HOME /var/jenkins_home

USER root

RUN apt-get update && \
    apt-get -y install maven

RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash \
    export NVM_DIR="$HOME/.nvm" \
    [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm \
    [ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion

RUN nvm install node
RUN cp $(which node) /bin

USER jenkins

ARG JAVA_OPTS
ENV JAVA_OPTS "-Djenkins.install.runSetupWizard=false ${JAVA_OPTS:-}"

COPY plugins.txt /usr/share/jenkins/ref/plugins.txt.override
RUN xargs /usr/local/bin/install-plugins.sh < /usr/share/jenkins/ref/plugins.txt.override
