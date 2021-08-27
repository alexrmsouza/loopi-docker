FROM node:latest

LABEL maintainer="Alex Souza <alexmscontato@gmail.com>"

# Installing Google Cloud SDK
RUN echo "deb [signed-by=/usr/share/keyrings/cloud.google.gpg] http://packages.cloud.google.com/apt cloud-sdk main" | tee -a /etc/apt/sources.list.d/google-cloud-sdk.list \
    && curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key --keyring /usr/share/keyrings/cloud.google.gpg add - \
    && apt update -y \
    && apt install google-cloud-sdk -y

# Installing basic ubuntu packages
RUN apt install htop nano -y

# Config credentials file 
ARG GOOGLE_APPLICATION_CREDENTIALS=/var/www/dev-gcloud.json
ENV GOOGLE_APPLICATION_CREDENTIALS=$GOOGLE_APPLICATION_CREDENTIALS

WORKDIR /var/www/loopi_seller_central_front

# Run Express app
CMD yarn start

EXPOSE 3000
EXPOSE 35729
