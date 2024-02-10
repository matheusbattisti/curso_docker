FROM node

WORKDIR /src

COPY package*.json ./

RUN npm install
RUN apt update && apt upgrade -y && apt install nano -y

COPY . .

EXPOSE 3000

CMD ["node", "app.js"]