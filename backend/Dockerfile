FROM node:latest

WORKDIR /app/medusa

COPY package.json .

# Install dependencies (Global dependencies and local ones)
RUN apt-get update \
    && apt-get install -y python3 \
    && npm install -g npm@latest \
    && npm install -g @medusajs/medusa-cli@latest \
    && npm install --loglevel=error

COPY . .

ENTRYPOINT ["./develop.sh", "develop"]
