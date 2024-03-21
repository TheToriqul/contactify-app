# # Use the official Nginx image as the base image
# FROM nginx:latest

# # Copy Nginx configuration file
# COPY nginx.conf nginx\conf\nginx.conf

# # Copy frontend and backend files
# COPY frontend/ ./frontend
# COPY backend/ ./backend

# # Expose port 80
# EXPOSE 80

# # Start Nginx when the container starts
# CMD ["nginx", "-g", "daemon off;"]

FROM nginx:stable-alpine
COPY ./conf/nginx.conf /nginx.conf
CMD ["/bin/sh" , "-c" , "envsubst < /nginx.conf.template > /etc/nginx/nginx.conf && exec nginx -g 'daemon off;'"]