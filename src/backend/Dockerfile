FROM php:8.1-fpm-alpine

# Install extensions with build method (all required packages must be install manually)
# RUN docker-php-ext-install pdo_mysql bcmath

# Install extensions with docker-php-extension-installer  (all required packages are install automatically)
# repo: https://github.com/mlocati/docker-php-extension-installer
ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/
RUN chmod +x /usr/local/bin/install-php-extensions && \
    install-php-extensions bcmath opcache readline curl xml mbstring zip ldap intl imap gd

# Install Composer
COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer

# Create user based on provided user ID
ARG HOST_UID
RUN adduser --disabled-password --gecos "" --uid $HOST_UID demo

# Switch to that user
USER demo



# second method

# FROM debian:bullseye

# # Install extensions
# RUN apt update \
#     && apt install -y lsb-release ca-certificates curl \
#     && curl -sSLo /usr/share/keyrings/deb.sury.org-php.gpg https://packages.sury.org/php/apt.gpg \
#     && sh -c 'echo "deb [signed-by=/usr/share/keyrings/deb.sury.org-php.gpg] https://packages.sury.org/php/ $(lsb_release -sc) main" > /etc/apt/sources.list.d/php.list' \
#     && apt update \
#     && apt install -y php8.1-fpm \
#     php8.1-bcmath \
#     php8.1-cli \
#     php8.1-common \
#     php8.1-fpm \
#     php8.1-opcache \
#     php8.1-readline \
#     php8.1-curl \
#     php8.1-xml \
#     php8.1-mbstring \
#     php8.1-zip \
#     php8.1-ldap \
#     php8.1-intl \
#     php8.1-imap \
#     php8.1-gd 

# RUN apt clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
# RUN apt autoremove --yes && apt autoclean

# # Install Composer
# COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer

# # Create user based on provided user ID
# ARG HOST_UID
# # RUN useradd --create-home --shell /bin/bash --uid $HOST_UID demo
# RUN useradd -ms /bin/bash --uid $HOST_UID demo

# # Switch to that user
# USER demo