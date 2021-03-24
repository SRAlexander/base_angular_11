FROM node:10

# stage 1

FROM node:alpine AS my-app-build
WORKDIR /app
COPY . .
RUN npm install && npm run build --prod

# stage 2

FROM nginx:alpine
COPY --from=my-app-build /app/dist/fds-ui /usr/share/nginx/html
EXPOSE 80