FROM node:16-alpine AS builder

WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build  

FROM caddy:2 AS runner
COPY --from=builder /app/dist /app/client
