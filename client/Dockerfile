FROM node:alpine as builder 
WORKDIR '/Users/srija/Desktop/redis'
COPY ./package.json ./
RUN npm install
COPY . .
RUN npm run build

FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /Users/srija/Desktop/redis/build /usr/share/nginx/html