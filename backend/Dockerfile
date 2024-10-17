FROM node:alpine

# Install json-server globally
RUN npm install -g json-server

# Create the /data directory before writing the file
RUN mkdir -p /data

RUN apk --no-cache add nano

# Conditionally create the JSON file only if it doesn't exist
RUN if [ ! -f /data/db.json ]; then \
      echo '{ \
        "products": [ \
          { \
            "id": 1, \
            "name": "Product 1", \
            "description": "Description for product 1", \
            "price": 9.99 \
          }, \
          { \
            "id": 2, \
            "name": "Product 2", \
            "description": "Description for product 2", \
            "price": 19.99 \
          } \
        ] \
      }' > /data/db.json; \
    fi

# Expose port 3000
EXPOSE 3000

# Start json-server, watching the db.json file and exposing on port 3000
CMD ["json-server", "--watch", "/data/db.json", "--host", "0.0.0.0", "--port", "3000"]