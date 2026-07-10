FROM node:20
# creates /app and set the directory to /app
WORKDIR /app
COPY package.json .
COPY *.js .
RUN npm install
CMD ["node", "server.js"]