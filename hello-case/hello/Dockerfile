FROM nginx:stable-bullseye
RUN mkdir -p /tmp/nginx && chmod -R 777 /tmp/nginx

USER root

COPY nginx.conf /etc/nginx/nginx.conf
COPY index.html .

RUN apt-get update && apt-get install -y  \
    bash=5.1-2+deb11u1 \
    curl=7.74.0-1.3+deb11u11 \
    libcurl4=7.74.0-1.3+deb11u11 \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /app

RUN chown -R nginx:nginx /app /var/cache/nginx

EXPOSE 80
EXPOSE 443

CMD ["nginx", "-g", "daemon off;", "-p", "$PWD"]