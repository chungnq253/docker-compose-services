FROM node:10.16.0

ENV TZ Asia/Ho_Chi_Minh

ENV INSTALL_PATH /var/www/gateway/

# Set working directory
WORKDIR $INSTALL_PATH

# Change current user to root
USER root

# Install dependencies
RUN apt-get update && apt-get install -y \
    build-essential \
    libpng-dev \
    libjpeg62-turbo-dev \
    libfreetype6-dev \
    locales \
    zip \
    jpegoptim optipng pngquant gifsicle \
    vim \
    unzip \
    bash \
    git

COPY package*.json yarn.lock $INSTALL_PATH

RUN yarn install

COPY . $INSTALL_PATH

EXPOSE 3000
CMD [ "yarn", "dev" ]
