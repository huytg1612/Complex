FROM node:16-alpine
WORKDIR "/app"
COPY ./package.json ./
#RUN npm install cross-env
RUN npm install 
COPY . .
CMD [ "npm", "run", "start" ]