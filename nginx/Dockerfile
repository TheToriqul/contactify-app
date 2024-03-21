FROM nginx:stable-alpine
COPY ./conf/nginx.conf /nginx.conf
CMD ["/bin/sh" , "-c" , "envsubst < /nginx.conf.template > /etc/nginx/nginx.conf && exec nginx -g 'daemon off;'"]