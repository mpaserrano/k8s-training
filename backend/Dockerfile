FROM node:alpine

RUN npm install json-server

COPY . . 

EXPOSE 3000

CMD ["json-server", "--watch", "db.json", "--host 0.0.0.0.", "--port 3000"]

# Here you have to find a way to include db.json in the container
# The final command is 
# json-server --watch db.json --host 0.0.0.0 --port 3000