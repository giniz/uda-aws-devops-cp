FROM node:13.8.0

# create work dir
WORKDIR /usr/src/app

# install dependencies
COPY package*.json ./
RUN npm install
RUN npm install pm2 -g

# copy source
COPY . .
COPY .env.sample ./.env

EXPOSE 3030
CMD [ "pm2-runtime", "start", "--name", "backend", "npm", "--", "start" ]