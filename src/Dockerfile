FROM node:16.15.0
#FROM node:18.7.0 
# (descobri a versao da latest com "docker run -it --rm node node --version")

WORKDIR /app  # diretorio atual

COPY ./package.json ./
COPY ./package-lock.json ./
RUN npm install

COPY . .

EXPOSE 8080
CMD ["node", "server.js"]
