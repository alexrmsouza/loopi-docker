FROM node:latest

LABEL maintainer="Alex Souza <alexmscontato@gmail.com>"

# Installing basic ubuntu packages
# RUN apt update
# RUN apt install htop nano -y

# Config credentials file 
ARG GOOGLE_APPLICATION_CREDENTIALS=/var/www/dev-gcloud.json
ENV GOOGLE_APPLICATION_CREDENTIALS=$GOOGLE_APPLICATION_CREDENTIALS

WORKDIR /var/www/loopi_api_discount

# Run Express app
CMD yarn run dev

EXPOSE 8080
