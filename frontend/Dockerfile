FROM nginx:alpine

COPY ../nginx/nginx.conf /etc/nginx/nginx.conf

COPY frontend/* /usr/share/nginx/html

RUN apk --no-cache add curl

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]

