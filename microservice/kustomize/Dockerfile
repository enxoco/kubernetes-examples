FROM nginx:alpine as base
ARG ENVIRONMENT
COPY index.html /usr/share/nginx/html
RUN sed -i "s/{{ENV}}/${ENVIRONMENT}/g" /usr/share/nginx/html/index.html

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]