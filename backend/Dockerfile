# Dockerfile for Render.com web service
FROM node:20-alpine

WORKDIR /app

# install project dependencies (cache-friendly)
#COPY package*.json ./
#RUN npm ci --no-audit --no-fund

# copy source
#COPY . .

# run requested commands
#RUN npx medusa build
RUN cd .medusa/server && npm install

ENV NODE_ENV=production
ENV PORT=9000

EXPOSE 9000
RUN cd .medusa/server && npm run predeploy
RUN cd.medusa/server
CMD ["npm", "run", "start"]