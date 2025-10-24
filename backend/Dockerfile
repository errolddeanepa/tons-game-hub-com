# Dockerfile for Render.com web service
FROM node:18-alpine

WORKDIR /app

# install project dependencies (cache-friendly)
COPY package*.json ./
RUN npm ci --no-audit --no-fund

# copy source
COPY . .

# run requested commands
RUN npx medusa build
RUN cd .medusa/server && npm install

ENV NODE_ENV=production
ENV PORT=9000

EXPOSE 9000

CMD ["npm", "run", "start"]