# Используем официальный образ nginx
FROM nginx:latest

# Устанавливаем OpenSSL для генерации самоподписанного сертификата
RUN apt-get update && apt-get install -y openssl

# Создаем директорию для хранения сертификатов
RUN mkdir /etc/nginx/ssl

# Копируем конфигурационный файл nginx в контейнер
COPY nginx.conf /etc/nginx/nginx.conf

# Копируем сертификаты в контейнер
COPY server.crt /etc/nginx/ssl/server.crt
COPY server.key /etc/nginx/ssl/server.key

# Копируем статическую HTML страницу в контейнер
COPY index.html /usr/share/nginx/html/index.html

EXPOSE 80 443

