#building a custom webserver project
FROM nginx:alpine3.20
COPY --chown=nginx:nginx index.html /usr/share/nginx/html/index.html

HEALTHCHECK --interval=30s --timeout=5s \
  CMD wget -qO- http://localhost || exit 1
