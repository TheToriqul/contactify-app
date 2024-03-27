FROM node:alpine as build
WORKDIR /app
COPY . .
RUN npm install && npm run build


FROM nginx:alpine
WORKDIR /usr/share/nginx/html
# COPY dist/ .
COPY --from=build /app/dist/ .
EXPOSE 3000
ENTRYPOINT [ "nginx", "-g", "daemon off;"] 