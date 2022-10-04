FROM node:13.8.0

# create work dir
WORKDIR /usr/src/app

# install dependencies
COPY ./backend/package*.json ./
RUN npm install pm2@5.2.0 -g && npm install

# copy source
COPY ./backend .
COPY ./backend/.env.sample ./.env

EXPOSE 3030
CMD [ "pm2-runtime", "start", "--name", "backend", "npm", "--", "start" ]