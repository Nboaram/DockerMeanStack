FROM ubuntu
WORKDIR /opt/backend
USER root
RUN apt update
RUN apt-get install curl -y
RUN apt-get install git -y
RUN curl -sL https://deb.nodesource.com/setup_12.x | bash -
RUN apt-get install -y nodejs
RUN apt-get install -y build-essential
RUN git clone https://github.com/Nboaram/TeamAPoolProjectBackend.git
WORKDIR /opt/backend/TeamAPoolProjectBackend
RUN git checkout Terraform
RUN npm install 
RUN npm build
EXPOSE 8080
ENTRYPOINT ["/usr/bin/node","Index.js"]