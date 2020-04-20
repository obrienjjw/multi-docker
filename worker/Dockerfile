FROM node:alpine
WORKDIR "/app"
COPY ./package.json ./
RUN npm install
COPY . . 
# the start command comes from the package.json
CMD ["npm", "run", "start"]