FROM nginxinc/nginx-unprivileged:alpine3.22-perl

USER nginx

COPY index.html /usr/share/nginx/html/index.html
COPY app.js /usr/share/nginx/html/app.js
COPY styles.css /usr/share/nginx/html/styles.css

EXPOSE 80
HEALTHCHECK --timeout=5s --retries=3 \
    CMD curl --fail http://localhost:8080|| exit 1
