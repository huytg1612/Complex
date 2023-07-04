#Build phase
FROM node:16-alpine as builder
WORKDIR '/app'
COPY ./package.json ./
RUN npm install
COPY . .
RUN npm run build

#Run phase
FROM nginx
EXPOSE 3000
#Replace the client's default.conf over the nginx's default.conf
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/build /usr/share/nginx/html
