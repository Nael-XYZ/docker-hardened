FROM node:20-slim AS builder
WORKDIR /app
COPY package*.json .
RUN npm ci --production
COPY . .

FROM gcr.io/distroless/nodejs20-debian12
COPY --from=builder /app /app
WORKDIR /app
USER nonroot
ENTRYPOINT ["node", "server.js"]
