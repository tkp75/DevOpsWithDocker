FROM node
EXPOSE 8000
WORKDIR /home/node/
COPY . .
RUN mkdir logs
RUN mv -f logs.txt logs/
RUN ln -s /home/node/logs/logs.txt /home/node/logs.txt
RUN chown -R node:node .
RUN npm install
CMD npm start
