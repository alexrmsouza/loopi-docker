FROM node:latest

LABEL maintainer="Gilmar Bec <gilmarmscontato@gmail.com>"

# Installing basic ubuntu packages
RUN apt update
RUN apt install htop nano -y

# Installing Redis
RUN wget http://download.redis.io/redis-stable.tar.gz \
    && tar xvzf redis-stable.tar.gz \
    && cd redis-stable \
    && make

# Config credentials file 
ARG GOOGLE_APPLICATION_CREDENTIALS=/var/www/dev-gcloud.json
ENV GOOGLE_APPLICATION_CREDENTIALS=$GOOGLE_APPLICATION_CREDENTIALS

WORKDIR /var/www/default

## Hold Docker on without a server running
# ENTRYPOINT ["tail", "-f", "/dev/null"]

# Run Express app
CMD yarn; yarn dev
