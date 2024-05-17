FROM jenkins/ssh-agent:5.12.0-jdk17
ENV DEBIAN_FRONTEND=noninteractive
#COPY plugins.txt /usr/share/jenkins/ref/plugins.txt
EXPOSE 2222
USER root
RUN apt-get update && apt-get install -y curl python3 python3-pip unzip ansible git
RUN groupadd -g 997 docker
RUN usermod -aG docker jenkins
RUN curl -fsSL https://get.docker.com
RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" && unzip awscliv2.zip &&  ./aws/install
RUN curl -L "https://github.com/docker/compose/releases/download/v2.12.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
#USER jenkins
#RUN jenkins-plugin-cli -f /usr/share/jenkins/ref/plugins.txt