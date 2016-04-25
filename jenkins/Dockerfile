FROM jenkins:latest
COPY plugins.txt /usr/share/jenkins/ref/
RUN /usr/local/bin/plugins.sh /usr/share/jenkins/ref/plugins.txt

USER root
# Install some basics
RUN apt-get update && \
    apt-get install -y build-essential git python3-pip python3-dev libpq-dev apache2 apache2-dev

# Install virtual env
RUN pip3 install virtualenv
# Clean up apt
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

USER jenkins
