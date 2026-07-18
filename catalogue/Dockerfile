FROM node:20.20.2-alpine3.22 AS builder
WORKDIR /app
COPY package.json .
COPY *.js .
RUN npm install 

FROM node:20.20.2-alpine3.22
WORKDIR /app
EXPOSE 8080
RUN addgroup -S roboshop && adduser -S -G roboshop roboshop && \
    chown -R roboshop:roboshop /app
COPY --from=builder /app /app
USER roboshop
CMD ["node", "server.js"]


# FROM node:20
# # creates /app and set the directory to /app
# WORKDIR /app
# COPY package.json .
# COPY *.js .
# RUN npm install
# CMD ["node", "server.js"]