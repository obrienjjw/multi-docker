# this is an example of a phased process
# this will run during the build phase
FROM node:alpine as builder
WORKDIR '/app'
COPY package.json ./
RUN npm install
COPY . . 
RUN npm run build

# the second FROM statement is understood to be a second phase
FROM nginx
# this will expose port 80 on AWS Elastic Beanstalk so that it will be available
EXPOSE 3000
# copy from 0 which is the first FROM instance
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/build /usr/share/nginx/html