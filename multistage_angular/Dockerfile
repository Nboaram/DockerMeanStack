FROM ubuntu:18.04 AS build
WORKDIR /opt/angular-server
USER root
RUN apt update
RUN apt-get install curl -y
RUN apt-get install git -y
RUN curl -sL https://deb.nodesource.com/setup_12.x | bash -
RUN apt-get install -y nodejs
RUN apt-get install -y build-essential
RUN git clone https://github.com/Nboaram/TeamAPoolProjectUI.git
WORKDIR /opt/angular-server/TeamAPoolProjectUI
RUN git checkout Developer
Run npm install typescript
RUN NG_CLI_ANALYTICS=ci npm -g install 
RUN NG_CLI_ANALYTICS=ci npm -g install @angular/cli
RUN ng build
#///////////////////
# NEW STAGE
#///////////////////
FROM nginx:alpine
WORKDIR /app
COPY --from=build /opt/angular-server/TeamAPoolProjectUI/dist/TeamAPoolProjectUI /app/angularproject
COPY nginx.conf /etc/nginx/nginx.conf
