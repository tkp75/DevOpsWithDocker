FROM node
EXPOSE 5000
WORKDIR /home/node/
COPY . .
RUN chown -R node:node .
RUN npm install
CMD npm start
